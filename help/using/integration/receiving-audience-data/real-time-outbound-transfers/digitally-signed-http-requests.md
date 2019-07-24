---
description: Für Audience Manager müssen die HTTP-Server-to-Server-Anforderungen digital zur Gültigkeit signiert werden. In diesem Dokument wird beschrieben, wie Sie HTTP-Anforderungen mit privaten Schlüsseln signieren können.
seo-description: Für Audience Manager müssen die HTTP-Server-to-Server-Anforderungen digital zur Gültigkeit signiert werden. In diesem Dokument wird beschrieben, wie Sie HTTP-Anforderungen mit privaten Schlüsseln signieren können.
seo-title: Digital signierte HTTP-Anforderungen
solution: Audience Manager
title: Digital signierte HTTP-Anforderungen
uuid: 1183 a 70 f -0 c 96-42 cf-a 4 f 5-37 a 83 ffa 1286
translation-type: tm+mt
source-git-commit: 9bf1f3771b6a4b9bb9a52149e812b37d1c8e27f8

---


# Digitally Signed `HTTP` Requests {#digitally-signed-http-requests}

Audience Manager requires the `HTTP` server-to-server requests to be digitally signed for validity. This document describes how you can sign `HTTP` requests with private keys.

## Überblick {#overview}

<!-- digitally_signed_http_requests.xml -->

Using a private key provided by you and shared with [!DNL Audience Manager], we can digitally sign the `HTTP` requests that are sent between [IRIS](../../../reference/system-components/components-data-action.md#iris) and your HTTP server. Dies gewährleistet Folgendes:

* **Authentizität**: Nur der Sender, der über den privaten Schlüssel ([!UICONTROL IRIS]) verfügt, kann gültige `HTTP(S)` Nachrichten an den Partner senden.
* **Meldungsintegrität**: Bei diesem Ansatz sind Sie selbst dann `HTTP`von einem Mann im mittleren Angriff geschützt, wenn die Nachrichten verzerrt werden.

[!UICONTROL IRIS] verfügt über integrierte Unterstützung, um die Schlüssel mit null Ausfallzeiten zu drehen, wie im Abschnitt [zum Drehen des privaten Schlüssels](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) unten dargestellt.

## Information you need to provide {#info-to-provide}

For an `HTTP` real-time server-to-server destination, contact your [!DNL Audience Manager] consultant and specify:

* Der Schlüssel zum Signieren der Anforderung.
* The name of the `HTTP` header that will hold the generated signature (X-Signature in the example header below).
* Optional: der Hashtyp für die Unterschrift (md 5, Sha 1, Sha 256).

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## How it works {#how-it-works}

1. [!UICONTROL IRIS] erstellt die `HTTP` Nachricht, die an den Partner gesendet wird.
1. [!UICONTROL IRIS] erstellt eine Signatur basierend auf `HTTP` der Meldung und dem vom Partner gesendeten privaten Schlüssel.
1. [!UICONTROL IRIS] sendet die `HTTP(S)` Anfrage an den Partner. Diese Meldung enthält die Unterschrift und die tatsächliche Nachricht, wie im obigen Beispiel gezeigt.
1. The partner server receives the `HTTP(S)` request. It reads the message body and the signature received from [!UICONTROL IRIS].
1. Basierend auf dem empfangenen Nachrichtentext und dem privaten Schlüssel wird der Partnerserver die Unterschrift neu berechnen. See the [How to calculate the signature](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) section just below on how to achieve this.
1. Compare the signature created on the partner server (receiver) with the one received from [!UICONTROL IRIS] (sender).
1. If the signatures match, then the **authenticity** and **message integrity** have been validated. Nur der Sender, der über den privaten Schlüssel verfügt, kann eine gültige Signatur (Authentizität) senden. Darüber hinaus kann ein Man in der Mitte die Nachricht nicht ändern und eine neue gültige Signatur generieren, da sie nicht über den privaten Schlüssel (Meldungsintegrität) verfügen.

![](assets/iris-digitally-sign-http-request.png)

## How to calculate the signature {#calculate-signature}

[!DNL HMAC] (Hash-basierter Nachrichtenauthentifizierungscode) ist die Methode, die [!UICONTROL IRIS] für die Signaturunterzeichnung verwendet wird. Implementierungen und Bibliotheken sind grundsätzlich in jeder Programmiersprache verfügbar. [!DNL HMAC] hat keine bekannten Erweiterungsangriffe. See an example in [!DNL Java] below:

```
// Message to be signed.
// For GET type HTTP destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

The RFC for the [!DNL HMAC] hash implementation is [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). A test site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (note that you have to [convert](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) the hex encoding to base64).

## Rotating the private key {#rotate-private-key}

Aus Sicherheitsgründen wird empfohlen, den privaten Schlüssel regelmäßig zu drehen. Es liegt an Ihnen, den privaten Schlüssel und die Drehungsdauer festzulegen. In order to achieve the key rotation with zero downtime, [!UICONTROL IRIS] supports adding multiple signature headers. Eine Kopfzeile enthält die mit dem alten Schlüssel generierte Signatur, eine weitere Kopfzeile die mit dem neuen privaten Schlüssel generierte Unterschrift. Unter den Schritten finden Sie weitere Informationen:

1. Partner communicates the new private key to [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] beginnt, zwei Unterschriftskopfzeilen zu senden (eine mit dem alten Schlüssel, die andere mit dem neuen Schlüssel).
1. Sobald Sie beide Überschriften erhalten haben, können Sie den alten Schlüssel verwerfen und sich nur die neue Unterschrift ansehen.
1. The old key is removed from [!DNL Audience Manager] and [!UICONTROL IRIS] only sends the new signature header. Die Schlüssel wurden gedreht.

## Data used for signing {#data-signing}

For `GET` type destinations, the message used for signing will be the *REQUEST_PATH + QUERY STRING* (e.g. */from-aam-s2s?sids=1,2,3*). IRIS does not take into account the hostname or `HTTP` headers - these can be modified / misconfigured along the path or reported incorrectly.

For `POST` type destinations, the message used for signing is the *REQUEST BODY*. Wiederum werden Überschriften oder andere Anforderungsparameter ignoriert.

---
description: Für den Audience Manager müssen die HTTP(S)-Server-zu-Server-Anfragen digital signiert werden, damit sie gültig sind. In diesem Dokument wird beschrieben, wie Sie HTTP-Anfragen mit privaten Schlüsseln signieren können.
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: Digital signierte HTTP(S)-Anfragen
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---

# Digitale `HTTP(S)` {#digitally-signed-http-requests}

Für den Audience Manager müssen die `HTTP(S)`-Server-zu-Server-Anfragen digital signiert werden, damit sie gültig sind. In diesem Dokument wird beschrieben, wie Sie `HTTP(S)` mit privaten Schlüsseln signieren können.

## Überblick {#overview}

<!-- digitally_signed_http_requests.xml -->

Mit einem privaten Schlüssel, der von Ihnen bereitgestellt und für [!DNL Audience Manager] freigegeben wurde, können wir die `HTTP(S)` Anfragen, die zwischen [IRIS](../../../reference/system-components/components-data-action.md#iris) und Ihrem HTTP(S)-Server gesendet werden, digital signieren. Dadurch wird Folgendes sichergestellt:

* **Authentizität**: Nur der Absender mit dem privaten Schlüssel ([!UICONTROL IRIS]) kann gültige `HTTP(S)` an den Partner senden.
* **Nachrichtenintegrität**: Mit diesem Ansatz sind Sie selbst auf `HTTP` vor einem Mann im mittleren Angriff geschützt, bei dem die Nachrichten verzerrt werden.

[!UICONTROL IRIS] verfügt über integrierte Unterstützung zum Drehen der Schlüssel ohne Ausfallzeiten, wie im Abschnitt [Drehen des privaten Schlüssels](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) unten gezeigt.

## Zu übermittelnde Informationen {#info-to-provide}

Wenden Sie sich für ein `HTTP(S)` Echtzeit-Server-zu-Server-Ziel an Ihren [!DNL Audience Manager] und geben Sie Folgendes an:

* Der Schlüssel, mit dem die Anfrage signiert wurde.
* Der Name des `HTTP(S)`, der die generierte Signatur enthält (X-Signatur im Beispiel-Header unten).
* Optional: Der für die Signatur verwendete Hash-Typ (md5, sha1, sha256).

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

## Funktionsweise {#how-it-works}

1. [!UICONTROL IRIS] erstellt die `HTTP(S)` Nachricht, die an den Partner gesendet werden soll.
1. [!UICONTROL IRIS] erstellt eine Signatur basierend auf der `HTTP(S)` Nachricht und dem vom Partner übermittelten privaten Schlüssel.
1. [!UICONTROL IRIS] sendet die `HTTP(S)` an den Partner. Diese Nachricht enthält die Signatur und die eigentliche Nachricht, wie im Beispiel oben gezeigt.
1. Der Partnerserver erhält die `HTTP(S)`. Er liest den Nachrichtentext und die von [!UICONTROL IRIS] erhaltene Signatur.
1. Basierend auf dem empfangenen Nachrichtentext und dem privaten Schlüssel berechnet der Partner-Server die Signatur neu. Wie Sie [ erreichen, erfahren Sie im Abschnitt ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature)Berechnen der Signatur“ weiter unten.
1. Vergleichen Sie die auf dem Partnerserver (Empfänger) erstellte Signatur mit der von [!UICONTROL IRIS] (Absender) empfangenen Signatur.
1. Wenn die Signaturen übereinstimmen, **die** Authentizität“ und **Nachrichtenintegrität** validiert. Nur der Absender, der über den privaten Schlüssel verfügt, kann eine gültige Signatur (Authentizität) senden. Außerdem kann ein Mann in der Mitte die Nachricht nicht ändern und keine neue gültige Signatur erzeugen, da er nicht über den privaten Schlüssel (Nachrichtenintegrität) verfügt.

![](assets/iris-digitally-sign-http-request.png)

## Berechnen der Signatur {#calculate-signature}

[!DNL HMAC] (Hash-basierter Nachrichtenauthentifizierungs-Code) ist die Methode, die von [!UICONTROL IRIS] zum Signieren von Nachrichten verwendet wird. Implementierungen und Bibliotheken sind grundsätzlich in jeder Programmiersprache verfügbar. [!DNL HMAC] hat keine bekannten Erweiterungsangriffe. Siehe ein Beispiel in [!DNL Java] unten:

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
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

Die RFC für die [!DNL HMAC] Hash-Implementierung ist [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Eine Test-Site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (beachten Sie, dass Sie die [&#128279;](https://tomeko.net/online_tools/hex_to_base64.php?lang=en)-Codierung in base64 konvertieren).

## Privaten Schlüssel drehen {#rotate-private-key}

Um den privaten Schlüssel zu rotieren, müssen Partner den neuen privaten Schlüssel ihrem [!DNL Adobe Audience Manager] mitteilen. Der alte Schlüssel wird aus [!DNL Audience Manager] entfernt und [!UICONTROL IRIS] nur die neue Signaturkopfzeile. Die Tasten wurden gedreht.

## Zum Signieren verwendete Daten {#data-signing}

Für Ziele vom Typ `GET` wird zum Signieren die Nachricht *REQUEST_PATH + QUERY STRING* verwendet (z. B. */from-aam-s2s?sids=1,2,3*). IRIS berücksichtigt nicht den Host-Namen oder `HTTP(S)`-Header - diese können entlang des Pfads geändert/falsch konfiguriert oder falsch gemeldet werden.

Bei Zielen vom Typ &quot;`POST`&quot; ist die zum Signieren verwendete Nachricht der *ANFRAGETEXT*. Auch hier werden Kopfzeilen oder andere Anfrageparameter ignoriert.

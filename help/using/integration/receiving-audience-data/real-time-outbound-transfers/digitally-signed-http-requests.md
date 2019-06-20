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


# Digital signierte `HTTP` Anforderungen {#digitally-signed-http-requests}

Für Audience Manager sind die `HTTP` Server-zu-Server-Anforderungen für die Gültigkeit digital signiert. In diesem Dokument wird beschrieben, wie `HTTP` Sie Anforderungen mit privaten Schlüsseln signieren können.

## Überblick {#overview}

<!-- digitally_signed_http_requests.xml -->

Mithilfe eines von Ihnen und freigegebenen privaten Schlüssels bereitgestellten [!DNL Audience Manager]privaten Schlüssels können wir `HTTP` die zwischen [IRIS](../../../reference/system-components/components-data-action.md#iris) und Ihrem HTTP-Server gesendeten Anforderungen digital signieren. Dies gewährleistet Folgendes:

* **Authentizität**: Nur der Sender, der über den privaten Schlüssel ([!UICONTROL IRIS]) verfügt, kann gültige `HTTP(S)` Nachrichten an den Partner senden.
* **Meldungsintegrität**: Bei diesem Ansatz sind Sie selbst dann `HTTP`von einem Mann im mittleren Angriff geschützt, wenn die Nachrichten verzerrt werden.

[!UICONTROL IRIS] verfügt über integrierte Unterstützung, um die Schlüssel mit null Ausfallzeiten zu drehen, wie im Abschnitt [zum Drehen des privaten Schlüssels](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) unten dargestellt.

## Informationen, die Sie bereitstellen müssen {#info-to-provide}

Für ein `HTTP` Echtzeit-Server-to-Server-Ziel wenden Sie sich an Ihren [!DNL Audience Manager] Berater und geben Sie Folgendes an:

* Der Schlüssel zum Signieren der Anforderung.
* Der Name der `HTTP` Kopfzeile, die die generierte Signatur enthält (X-Signatur im Beispiel unten).
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

## Funktionsweise {#how-it-works}

1. [!UICONTROL IRIS] erstellt die `HTTP` Nachricht, die an den Partner gesendet wird.
1. [!UICONTROL IRIS] erstellt eine Signatur basierend auf `HTTP` der Meldung und dem vom Partner gesendeten privaten Schlüssel.
1. [!UICONTROL IRIS] sendet die `HTTP(S)` Anfrage an den Partner. Diese Meldung enthält die Unterschrift und die tatsächliche Nachricht, wie im obigen Beispiel gezeigt.
1. Der Partnerserver erhält die `HTTP(S)` Anforderung. Er liest den Nachrichtentext und die von [!UICONTROL IRIS]Ihnen empfangene Unterschrift.
1. Basierend auf dem empfangenen Nachrichtentext und dem privaten Schlüssel wird der Partnerserver die Unterschrift neu berechnen. Siehe [So berechnen Sie den](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) Unterschriftsabschnitt direkt unten.
1. Vergleichen Sie die auf dem Partner-Server (Empfänger) erstellte Signatur mit dem empfangenen [!UICONTROL IRIS] (Absender).
1. Stimmen die Signaturen überein, wurden die **Authentizität** und **die Meldungsintegrität** überprüft. Nur der Sender, der über den privaten Schlüssel verfügt, kann eine gültige Signatur (Authentizität) senden. Darüber hinaus kann ein Man in der Mitte die Nachricht nicht ändern und eine neue gültige Signatur generieren, da sie nicht über den privaten Schlüssel (Meldungsintegrität) verfügen.

![](assets/iris-digitally-sign-http-request.png)

## Berechnung der Signatur {#calculate-signature}

[!DNL HMAC] (Hash-basierter Nachrichtenauthentifizierungscode) ist die Methode, die [!UICONTROL IRIS] für die Signaturunterzeichnung verwendet wird. Implementierungen und Bibliotheken sind grundsätzlich in jeder Programmiersprache verfügbar. [!DNL HMAC] hat keine bekannten Erweiterungsangriffe. Siehe Beispiel [!DNL Java] unten:

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

Der RFC für die [!DNL HMAC] Hash-Implementierung lautet [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Eine Testsite: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (beachten Sie, dass Sie die hexadezimale Kodierung in base 64 [konvertieren](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) müssen).

## Drehen des privaten Schlüssels {#rotate-private-key}

Aus Sicherheitsgründen wird empfohlen, den privaten Schlüssel regelmäßig zu drehen. Es liegt an Ihnen, den privaten Schlüssel und die Drehungsdauer festzulegen. Um die Schlüsseldrehung mit null Ausfallzeiten zu erzielen, [!UICONTROL IRIS] unterstützt das Hinzufügen mehrerer Unterschriftskopfzeilen. Eine Kopfzeile enthält die mit dem alten Schlüssel generierte Signatur, eine weitere Kopfzeile die mit dem neuen privaten Schlüssel generierte Unterschrift. Unter den Schritten finden Sie weitere Informationen:

1. Partner communicates the new private key to [!DNL Adobe Audience Manager].
1. [!UICONTROL IRIS] beginnt, zwei Unterschriftskopfzeilen zu senden (eine mit dem alten Schlüssel, die andere mit dem neuen Schlüssel).
1. Sobald Sie beide Überschriften erhalten haben, können Sie den alten Schlüssel verwerfen und sich nur die neue Unterschrift ansehen.
1. Der alte Schlüssel wird aus [!DNL Audience Manager] und [!UICONTROL IRIS] sendet nur die neue Signaturkopfzeile. Die Schlüssel wurden gedreht.

## Zum Unterschreiben verwendete Daten {#data-signing}

Bei `GET` Typ-Zielen ist die für die Unterzeichnung verwendete Meldung REQUEST *_ PATH + QUERY STRING* (z. B. */from-aam-s2s? sids = 1,2,3*). IRIS berücksichtigt nicht den Hostnamen oder `HTTP` die Header - diese können entlang des Pfads geändert/falsch konfiguriert werden oder falsch gemeldet werden.

Bei `POST` Typ-Zielen ist die zum Signieren verwendete Meldung der *ANFORDERUNGSKÖRPER*. Wiederum werden Überschriften oder andere Anforderungsparameter ignoriert.

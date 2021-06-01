---
description: Audience Manager erfordert, dass die HTTP(S)-Server-zu-Server-Anforderungen für ihre Gültigkeit digital signiert werden. In diesem Dokument wird beschrieben, wie Sie HTTP-Anfragen mit privaten Schlüsseln signieren können.
seo-description: Audience Manager erfordert, dass die HTTP(S)-Server-zu-Server-Anforderungen für ihre Gültigkeit digital signiert werden. In diesem Dokument wird beschrieben, wie Sie HTTP(S)-Anfragen mit privaten Schlüsseln signieren können.
seo-title: Digital signierte HTTP(s)-Anforderungen
solution: Audience Manager
title: Digital signierte HTTP(s)-Anforderungen
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Ausgehende Datenübertragungen
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# Digital signierte `HTTP(S)` Anforderungen {#digitally-signed-http-requests}

Audience Manager erfordert, dass die `HTTP(S)`-Server-zu-Server-Anforderungen für ihre Gültigkeit digital signiert werden. In diesem Dokument wird beschrieben, wie Sie `HTTP(S)`-Anfragen mit privaten Schlüsseln signieren können.

## Überblick {#overview}

<!-- digitally_signed_http_requests.xml -->

Mithilfe eines von Ihnen bereitgestellten und für [!DNL Audience Manager] freigegebenen privaten Schlüssels können wir die `HTTP(S)`-Anforderungen digital signieren, die zwischen [IRIS](../../../reference/system-components/components-data-action.md#iris) und Ihrem HTTP(S)-Server gesendet werden. Dadurch wird Folgendes sichergestellt:

* **Authentizität**: Nur der Absender mit privatem Schlüssel ([!UICONTROL IRIS]) kann gültige  `HTTP(S)` Nachrichten an den Partner senden.
* **Nachrichtenintegrität**: mit diesem Ansatz, sogar auf  `HTTP`sind Sie vor einem Mann im mittleren Angriff geschützt, wo die Nachrichten verzerrt werden.

[!UICONTROL IRIS] verfügt über integrierte Unterstützung zum Drehen der Schlüssel ohne Ausfallzeiten, wie im Abschnitt  [Drehen des privaten ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) Schlüssels unten dargestellt.

## Informationen, die Sie bereitstellen müssen {#info-to-provide}

Wenden Sie sich an Ihren [!DNL Audience Manager] -Berater und geben Sie Folgendes an, wenn Sie ein `HTTP(S)` Echtzeit-Server-zu-Server-Ziel haben:

* Der zum Signieren der Anfrage verwendete Schlüssel.
* Der Name der `HTTP(S)`-Kopfzeile, die die generierte Signatur enthält (X-Signatur in der Beispielkopfzeile unten).
* Optional: der für die Signatur verwendete Hash-Typ (md5, sha1, sha256).

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

1. [!UICONTROL IRIS] erstellt die  `HTTP(S)` Nachricht, die an den Partner gesendet werden soll.
1. [!UICONTROL IRIS] erstellt eine Signatur, die auf der  `HTTP(S)` Nachricht und dem vom Partner kommunizierten privaten Schlüssel basiert.
1. [!UICONTROL IRIS] sendet die  `HTTP(S)` Anfrage an den Partner. Diese Nachricht enthält die Signatur und die eigentliche Nachricht, wie im Beispiel oben gezeigt.
1. Der Partner-Server erhält die `HTTP(S)` -Anfrage. Er liest den Nachrichtentext und die Signatur, die von [!UICONTROL IRIS] empfangen wurden.
1. Basierend auf dem empfangenen Nachrichten-Textkörper und dem privaten Schlüssel berechnet der Partnerserver die Signatur neu. Weitere Informationen dazu finden Sie im Abschnitt [Berechnung der Signatur](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) weiter unten.
1. Vergleichen Sie die auf dem Partner-Server (Empfänger) erstellte Signatur mit der von [!UICONTROL IRIS] (Absender) empfangenen Signatur.
1. Wenn die Signaturen übereinstimmen, wurden die **Authentizität** und die **Meldungsintegrität** validiert. Nur der Absender, der über den privaten Schlüssel verfügt, kann eine gültige Signatur (Authentizität) senden. Außerdem kann ein Mann in der Mitte die Nachricht nicht ändern und eine neue gültige Signatur generieren, da er nicht über den privaten Schlüssel (Integrität der Nachricht) verfügt.

![](assets/iris-digitally-sign-http-request.png)

## Berechnung der Signatur {#calculate-signature}

[!DNL HMAC] (Hash-basierter Authentifizierungscode für Nachrichten) ist die Methode, die  [!UICONTROL IRIS] zum Signieren von Nachrichten verwendet wird. Implementierungen und Bibliotheken sind grundsätzlich in jeder Programmiersprache verfügbar. [!DNL HMAC] hat keine bekannten Erweiterungsangriffe. Siehe ein Beispiel in [!DNL Java] unten:

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

Die RFC für die Hash-Implementierung von [!DNL HMAC] lautet [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Eine Test-Site: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (Beachten Sie, dass Sie [die Hex-Kodierung in base64 konvertieren müssen.)](https://tomeko.net/online_tools/hex_to_base64.php?lang=en)

## Drehen des privaten Schlüssels {#rotate-private-key}

Um den privaten Schlüssel zu drehen, müssen Partner den neuen privaten Schlüssel ihrem [!DNL Adobe Audience Manager]-Berater mitteilen. Der alte Schlüssel wird aus [!DNL Audience Manager] entfernt und [!UICONTROL IRIS] sendet nur den neuen Signaturheader. Die Schlüssel wurden gedreht.

## Daten zum Signieren {#data-signing}

Bei Zielen vom Typ `GET` lautet die zum Signieren verwendete Nachricht *REQUEST_PATH + QUERY STRING* (z. B. */from-aam-s2s?sids=1,2,3*). IRIS berücksichtigt weder den Hostnamen noch die `HTTP(S)`-Kopfzeilen - diese können über den Pfad geändert/falsch konfiguriert oder falsch gemeldet werden.

Bei Zielen vom Typ `POST` ist die zum Signieren verwendete Nachricht der *ANFORDERUNGSKÖRPER*. Auch hier werden Kopfzeilen oder andere Anforderungsparameter ignoriert.

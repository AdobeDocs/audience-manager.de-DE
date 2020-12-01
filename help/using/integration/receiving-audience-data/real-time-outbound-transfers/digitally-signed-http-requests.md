---
description: Audience Manager erfordert, dass die HTTP(S)-Server-zu-Server-Anforderungen für ihre Gültigkeit digital signiert werden. In diesem Dokument wird beschrieben, wie Sie HTTP-Anforderungen mit privaten Schlüsseln signieren können.
seo-description: Audience Manager erfordert, dass die HTTP(S)-Server-zu-Server-Anforderungen für ihre Gültigkeit digital signiert werden. In diesem Dokument wird beschrieben, wie Sie HTTP(S)-Anforderungen mit privaten Schlüsseln signieren können.
seo-title: Digital signierte HTTP(S)-Anforderungen
solution: Audience Manager
title: Digital signierte HTTP(S)-Anforderungen
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: 4877aa5391193ee2187609fdc9cb3740c91feb96
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---


# Digital signierte `HTTP(S)`-Anforderungen {#digitally-signed-http-requests}

Audience Manager erfordert, dass die `HTTP(S)`-Server-zu-Server-Anforderungen für ihre Gültigkeit digital signiert werden. In diesem Dokument wird beschrieben, wie Sie `HTTP(S)`-Anforderungen mit privaten Schlüsseln signieren können.

## Überblick {#overview}

<!-- digitally_signed_http_requests.xml -->

Mithilfe eines von Ihnen bereitgestellten und für [!DNL Audience Manager] freigegebenen privaten Schlüssels können wir die `HTTP(S)`-Anforderungen digital signieren, die zwischen [IRIS](../../../reference/system-components/components-data-action.md#iris) und Ihrem HTTP(S)-Server gesendet werden. Dadurch wird sichergestellt:

* **Authentizität**: nur der Absender mit dem privaten Schlüssel ([!UICONTROL IRIS]) kann gültige  `HTTP(S)` Nachrichten an den Partner senden.
* **Nachrichtenintegrität**: mit diesem Ansatz, sogar auf  `HTTP`werden Sie vor einem Mann im mittleren Angriff geschützt, wo die Nachrichten verzerrt werden.

[!UICONTROL IRIS] verfügt über integrierte Unterstützung zum Drehen der Schlüssel mit null Ausfallzeiten, wie im Abschnitt  [Drehen des privaten ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) Suchbegriffs unten gezeigt.

## Informationen, die Sie bereitstellen müssen{#info-to-provide}

Wenden Sie sich für ein `HTTP(S)`-Echtzeit-Server-zu-Server-Ziel an Ihren [!DNL Audience Manager]-Berater und geben Sie Folgendes an:

* Der zum Signieren der Anforderung verwendete Schlüssel.
* Der Name der `HTTP(S)`-Kopfzeile, die die generierte Signatur enthält (X-Signatur in der Beispielüberschrift unten).
* Optional: der Hash-Typ, der für die Signatur verwendet wird (md5, sha1, sha256).

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
1. [!UICONTROL IRIS] erstellt eine Signatur, die auf der  `HTTP(S)` Nachricht und dem vom Partner mitgeteilten privaten Schlüssel basiert.
1. [!UICONTROL IRIS] sendet die  `HTTP(S)` Anfrage an den Partner. Diese Meldung enthält die Unterschrift und die eigentliche Meldung, wie im Beispiel oben dargestellt.
1. Der Partnerserver erhält die `HTTP(S)`-Anforderung. Es liest den Nachrichtentext und die Signatur, die von [!UICONTROL IRIS] empfangen wurde.
1. Basierend auf dem Nachrichtentext und dem privaten Schlüssel berechnet der Partnerserver die Signatur neu. Weitere Informationen zum Erreichen dieses Ziels finden Sie im Abschnitt [Berechnung der Signatur](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature).
1. Vergleichen Sie die auf dem Partnerserver (Empfänger) erstellte Signatur mit der Signatur, die von [!UICONTROL IRIS] (Absender) empfangen wurde.
1. Wenn die Unterschriften übereinstimmen, wurden die **Authentizität** und **Meldungsintegrität** validiert. Nur der Absender, der über den privaten Schlüssel verfügt, kann eine gültige Signatur (Authentizität) senden. Darüber hinaus kann ein Mann in der Mitte die Nachricht nicht ändern und eine neue gültige Signatur generieren, da er nicht über den privaten Schlüssel (Nachrichtintegrität) verfügt.

![](assets/iris-digitally-sign-http-request.png)

## Berechnung der Signatur {#calculate-signature}

[!DNL HMAC] (Hash-basierter Authentifizierungscode) ist die Methode, die  [!UICONTROL IRIS] zum Signieren von Nachrichten verwendet wird. Implementierungen und Bibliotheken stehen grundsätzlich in jeder Programmiersprache zur Verfügung. [!DNL HMAC] hat keine bekannten Erweiterungsangriffe. Siehe ein Beispiel in [!DNL Java] unten:

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

Die RFC für die Hash-Implementierung von [!DNL HMAC] lautet [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Eine Testsite: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (Beachten Sie, dass [die Hex-Kodierung in base64 konvertieren muss).](https://tomeko.net/online_tools/hex_to_base64.php?lang=en)

## Drehen des privaten Schlüssels {#rotate-private-key}

Um den privaten Schlüssel zu drehen, müssen Partner den neuen privaten Schlüssel an ihren [!DNL Adobe Audience Manager]-Berater weiterleiten. Der alte Schlüssel wird von [!DNL Audience Manager] entfernt und [!UICONTROL IRIS] sendet nur den neuen Signaturheader. Die Schlüssel wurden gedreht.

## Für die Signierung verwendete Daten {#data-signing}

Bei Zielen vom Typ `GET` wird die Signaturmeldung *REQUEST_PATH + ABFRAGE STRING* (z. B. */from-aam-s2s?sids=1,2,3*). IRIS berücksichtigt nicht den Hostnamen oder die `HTTP(S)`-Kopfzeilen - diese können geändert/falsch konfiguriert werden oder falsch gemeldet werden.

Bei Zielen vom Typ `POST` ist die zum Signieren verwendete Meldung der *ANFORDERUNGSKÖRPER*. Auch hier werden Kopfzeilen oder andere Anforderungsparameter ignoriert.

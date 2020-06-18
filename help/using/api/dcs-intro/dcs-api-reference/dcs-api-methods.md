---
description: Senden Sie Daten mit GET- oder POST-Methoden an die DCS-API.
seo-description: Senden Sie Daten mit GET- oder POST-Methoden an die DCS-API.
seo-title: DCS API-Methoden
solution: Audience Manager
title: DCS API-Methoden
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 0%

---


# DCS API-Methoden {#dcs-api-methods}

Senden Sie Daten an die [!DNL DCS][!DNL API] mit `GET` oder `POST` Methoden.

Sie können Daten entweder mit einer der [!DNL DCS] oder mit einer der `GET` `POST` Methoden an die Gruppe senden. Sehen Sie sich die unten stehenden Beispielaufrufe mit [curl](https://curl.haxx.se/)an. In allen drei Beispielaufrufen fügen wir die Signale `c_likes = famous popstar` und `c_loves = famous actress` das Profil des Geräts hinzu `12345678901234567890123456789012345678`.


## Daten über GET senden {#send-data-via-get}

Beachten Sie, dass die maximal zulässige Größe für `GET` Anrufe 8 KB beträgt.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Daten über POST senden {#send-data-via-post}

Beachten Sie die Anforderungen zum Senden von Daten mit der `POST` Methode:

* Die maximal zulässige Größe beträgt 32K.
* Legen Sie den Inhaltstyp auf `application/x-www-form-urlencoded`.

### Beispielaufruf

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```

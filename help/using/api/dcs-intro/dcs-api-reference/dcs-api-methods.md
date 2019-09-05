---
description: Senden Sie Daten mit GET- oder POST-Methoden an die DCS-API.
seo-description: Senden Sie Daten mit GET- oder POST-Methoden an die DCS-API.
seo-title: DCS-API-Methoden
solution: Audience Manager
title: DCS-API-Methoden
uuid: 6 e 407458-11 d 4-4342-a 84 a -512 afa 5 fc 183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# DCS-API-Methoden {#dcs-api-methods}

Senden Sie Daten [!UICONTROL DCS][!DNL API] mit `GET` oder `POST` Methoden.

Sie können Daten [!UICONTROL DCS] entweder mit einer der `GET` beiden `POST` Methoden senden. Sehen Sie sich die unten stehenden Beispielaufrufe mit [curl](https://curl.haxx.se/)an. In allen drei Beispielaufrufen fügen wir die Signale `c_likes = famous popstar` und `c_loves = famous actress` das Geräteprofil `12345678901234567890123456789012345678`hinzu.


## Daten über GET senden {#send-data-via-get}

Beachten Sie, dass die maximal zulässige Größe für `GET` Aufrufe 8 K beträgt.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Daten über POST senden {#send-data-via-post}

Beachten Sie die Anforderungen zum Senden von Daten mithilfe der `POST` Methode:

* Die maximal zulässige Größe beträgt 32 K.
* Legen Sie den Inhaltstyp `application/x-www-form-urlencoded`auf.

### Beispielaufruf

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```

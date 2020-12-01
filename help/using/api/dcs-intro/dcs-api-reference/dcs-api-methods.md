---
description: Senden Sie Daten mit GET- oder POST-Methoden an die DCS-API.
seo-description: Senden Sie Daten mit GET- oder POST-Methoden an die DCS-API.
seo-title: DCS-API-Methoden
solution: Audience Manager
title: DCS-API-Methoden
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 6%

---


# [!DNL DCS] [!DNL API] Methoden {#dcs-api-methods}

Senden Sie Daten mit den Methoden [!DNL DCS] [!DNL API] oder `GET` an die `POST`.

Sie können Daten mit einer der Methoden `GET` oder `POST` an [!DNL DCS] senden. Sehen Sie sich die unten stehenden Beispielaufrufe mit [curl](https://curl.haxx.se/) an. In allen drei Beispielaufrufen fügen wir die Signale `c_likes = famous popstar` und `c_loves = famous actress` zum Profil `12345678901234567890123456789012345678` hinzu.

## Daten senden über [!DNL GET] {#send-data-via-get}

Beachten Sie, dass die maximal zulässige Größe für `GET`-Aufrufe 8 K beträgt.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Daten senden über [!DNL POST] {#send-data-via-post}

Beachten Sie die Anforderungen zum Senden von Daten mit der `POST`-Methode:

* Die maximal zulässige Größe beträgt 32K.
* Legen Sie den Inhaltstyp auf `application/x-www-form-urlencoded` fest.

### Beispielaufruf

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```

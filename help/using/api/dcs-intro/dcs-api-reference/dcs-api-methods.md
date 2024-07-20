---
description: Senden Sie Daten mithilfe von GET- oder POST-Methoden an die DCS-API.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS-API-Methoden
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# [!DNL DCS] [!DNL API] Methoden {#dcs-api-methods}

Senden Sie Daten mit den Methoden `GET` oder `POST` an die [!DNL DCS] [!DNL API].

Sie können Daten mit einer der Methoden `GET` oder `POST` an die [!DNL DCS] senden. Sehen Sie sich die folgenden Beispielaufrufe mit [curl](https://curl.haxx.se/) an. In allen drei Beispielaufrufen fügen wir die Signale `c_likes = famous popstar` und `c_loves = famous actress` zum Geräteprofil `12345678901234567890123456789012345678` hinzu.

## Daten senden über [!DNL GET] {#send-data-via-get}

Beachten Sie, dass die maximal zulässige Größe für `GET` -Aufrufe 8 K beträgt.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Daten senden über [!DNL POST] {#send-data-via-post}

Beachten Sie die Anforderungen zum Senden von Daten mit der `POST` -Methode:

* Die maximal zulässige Größe beträgt 32 K.
* Setzen Sie den Inhaltstyp auf `application/x-www-form-urlencoded`.

### Beispielaufruf

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```

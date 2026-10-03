---
description: Senden Sie Daten mithilfe von GET- oder POST-Methoden an die DCS-API.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS-API-Methoden
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
TQID: 'https://experienceleague.adobe.com/dERIW4EM4-oMg8p33N2dtDy5BBw3jF1BCQJstW2cZTY'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
    internal-label: APIs and SDKs
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
    internal-label: Data Collection Server
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 0%
---
# [!DNL DCS] [!DNL API] {#dcs-api-methods}

Senden Sie Daten mithilfe von `GET`- oder `POST`-Methoden an die [!DNL DCS] [!DNL API].

Sie können Daten mit einer der Methoden `GET` oder `POST` an die [!DNL DCS] senden. Sehen Sie sich die folgenden Beispielaufrufe an, indem Sie [curl](https://curl.haxx.se/) verwenden. In allen drei Beispielaufrufen fügen wir die Signale `c_likes = famous popstar` und `c_loves = famous actress` zur `12345678901234567890123456789012345678` des Geräteprofils hinzu.

## Senden von Daten über [!DNL GET] {#send-data-via-get}

Beachten Sie, dass die maximal zulässige Größe für `GET`-Aufrufe 8K beträgt.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Senden von Daten über [!DNL POST] {#send-data-via-post}

Beachten Sie die Anforderungen für das Senden von Daten mit der `POST`-Methode:

* Die maximal zulässige Größe beträgt 32 K.
* Legen Sie den Inhaltstyp auf `application/x-www-form-urlencoded` fest.

### Beispielaufruf

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```

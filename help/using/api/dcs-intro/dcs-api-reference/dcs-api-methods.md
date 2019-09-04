---
description: Senden Sie Daten mit GET- oder POST-Methoden an die DCS-API.
seo-description: Senden Sie Daten mit GET- oder POST-Methoden an die DCS-API.
seo-title: DCS-API-Methoden
solution: Audience Manager
title: DCS-API-Methoden
uuid: 6 e 407458-11 d 4-4342-a 84 a -512 afa 5 fc 183
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# DCS-API-Methoden {#dcs-api-methods}

Senden Sie Daten [!UICONTROL DCS][!DNL API] mit `GET` oder `POST` Methoden.

Sie können Daten [!UICONTROL DCS] entweder mit einer der `GET` beiden `POST` Methoden senden. Sehen Sie sich die unten stehenden Beispielaufrufe mit [curl](https://curl.haxx.se/)an. In allen drei Beispielaufrufen fügen wir die Signale `c_likes = famous popstar` und `c_loves = famous actress` das Geräteprofil `12345678901234567890123456789012345678`hinzu.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Ersetzen Sie einen echten Wert für den Platzhalter, wenn Sie Daten an diese [!UICONTROL DCS] Methode senden.

## Daten über GET senden {#send-data-via-get}

Beachten Sie, dass die maximal zulässige Größe für `GET` Aufrufe 8 K beträgt.

<pre><code>curl -i "<i>yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&amp;d_rtbd=jsonc_likes=famous%20popstar&amp;c_loves=famous%20actress</i><i></i><i></i><i></i>"</code></pre>

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

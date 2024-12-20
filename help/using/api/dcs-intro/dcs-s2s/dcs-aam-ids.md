---
description: In diesem Abschnitt wird beschrieben, wie Sie eine DCS-Antwort parsen, um die Besucher- und Regions-IDs abzurufen, die für Echtzeit-Aufrufe an den DCS erforderlich sind.
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%

---

# Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort {#get-user-ids-and-regions-from-a-dcs-response}

In diesem Abschnitt wird beschrieben, wie Sie eine [!DNL DCS]-Antwort parsen, um die Besucher- und Regions-IDs abzurufen, die für Echtzeit-Aufrufe an die -[!DNL DCS] erforderlich sind.

## Benutzer- und Regions-IDs {#user-region-ids}

Eine [!DNL DCS] Antwort enthält Daten zu den Besuchern Ihrer Site. Sie benötigen die Besucher- und Regions-ID, bevor Sie Server-zu-Server-Aufrufe an die [!DNL DCS] durchführen können.

* Die Benutzer-ID ist erforderlich, um Daten zu identifizieren und mit einem bestimmten Besucher zu verknüpfen.
* Die Regions-ID ist erforderlich, da sie an einen regionalen Servernamen gebunden ist, den Sie zum Senden von Daten an die [!DNL DCS] benötigen. Die [!DNL DCS] speichert Informationen in Rechenzentren, die geografisch den Besuchern der Website am nächsten liegen. Siehe [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Diese Parameter werden nachfolgend beschrieben. Code in *Kursiv* stellt einen Variablenplatzhalter dar.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Datentyp </th> 
   <th colname="col3" class="entry"> Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielantwort {#sample-response}

Diese einfache Antwort zeigt die `UUID`- und `ID`. Beachten Sie: Dies sind nur Beispieldaten. Ihre Protokolldateien können länger und komplexer sein.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Nächste Schritte {#next-steps}

Sobald Sie über die Benutzer-ID und den regionalen Server-Namen verfügen, können Sie mit dem Senden und Empfangen [!DNL DCS] Daten beginnen. Siehe [Erstellen von DCS-API-Aufrufen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).

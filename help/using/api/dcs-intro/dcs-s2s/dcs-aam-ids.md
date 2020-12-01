---
description: In diesem Abschnitt wird beschrieben, wie Sie eine DCS-Antwort analysieren, um die Besucher- und Regions-IDs abzurufen, die für Echtzeitaufrufe des DCS erforderlich sind.
seo-description: In diesem Abschnitt wird beschrieben, wie Sie eine DCS-Antwort analysieren, um die Besucher- und Regions-IDs abzurufen, die für Echtzeitaufrufe des DCS erforderlich sind.
seo-title: Abrufen von Benutzer-IDs und Regionen über eine DCS-Antwort
solution: Audience Manager
title: Abrufen von Benutzer-IDs und Regionen über eine DCS-Antwort
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 17%

---


# Abrufen von Benutzer-IDs und Regionen über eine DCS-Antwort {#get-user-ids-and-regions-from-a-dcs-response}

In diesem Abschnitt wird beschrieben, wie Sie eine [!DNL DCS]-Antwort analysieren, um die Besucher- und Regions-IDs abzurufen, die für Echtzeitaufrufe von [!DNL DCS] erforderlich sind.

## Benutzer- und Regions-IDs {#user-region-ids}

Eine [!DNL DCS]-Antwort enthält Daten zu Ihren Site-Besuchern. Sie benötigen die Besucher- und Regions-ID, bevor Sie Server-zu-Server-Aufrufe an das [!DNL DCS] durchführen können.

* Die Benutzer-ID ist erforderlich, um Daten zu identifizieren und mit einem bestimmten Besucher zu verbinden.
* Die Regions-ID ist erforderlich, da sie an einen regionalen Servernamen gebunden ist, den Sie an das [!DNL DCS] senden müssen. Das [!DNL DCS] speichert Informationen in Rechenzentren, die geografisch am nächsten zu Site-Besuchern liegen. Siehe [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Diese Parameter werden nachfolgend beschrieben. Code in *kursiv* stellt einen variablen Platzhalter dar.

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
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielantwort {#sample-response}

Diese einfache Antwort zeigt die Variablen `UUID` und Region `ID`. Beachten Sie, dass dies nur Musterdaten sind. Ihre Protokolldateien können länger und komplexer sein.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Nächste Schritte {#next-steps}

Sobald Sie die Benutzer-ID und den regionalen Servernamen haben, können Sie Beginn zum Senden und Empfangen von [!DNL DCS]-Daten verwenden. Siehe [Durchführen von DCS-API-Aufrufen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).

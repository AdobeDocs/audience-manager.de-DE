---
description: In diesem Abschnitt wird beschrieben, wie Sie eine DCS-Antwort analysieren, um die Besucher- und Regions-IDs abzurufen, die erforderlich sind, um Echtzeit-Aufrufe dem DCS zu ermöglichen.
seo-description: In diesem Abschnitt wird beschrieben, wie Sie eine DCS-Antwort analysieren, um die Besucher- und Regions-IDs abzurufen, die erforderlich sind, um Echtzeit-Aufrufe dem DCS zu ermöglichen.
seo-title: Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort
solution: Audience Manager
title: Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort
uuid: 08036045-3 b 26-4 d 40-8 e 94-7 d 088883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort {#get-user-ids-and-regions-from-a-dcs-response}

In diesem Abschnitt wird beschrieben, wie [!UICONTROL DCS] Sie eine Antwort analysieren, um die Besucher- und Regions-IDs abzurufen, die erforderlich sind, um Echtzeit-Aufrufe an [!UICONTROL DCS].

## Benutzer- und Regions-IDs {#user-region-ids}

Eine [!UICONTROL DCS] Antwort enthält Daten über Ihre Site-Besucher. Sie benötigen die Besucher- und Regions-ID, bevor Sie Server-zu-Server-Aufrufe an den [!UICONTROL DCS]Server durchführen können.

* Die Benutzer-ID ist erforderlich, um Daten mit einem bestimmten Besucher zu identifizieren und zu verknüpfen.
* Die Regions-ID ist erforderlich, da sie an einen regionalen Servernamen gebunden ist, an [!UICONTROL DCS]den Sie Daten senden müssen. Die Speicherung [!UICONTROL DCS] von Informationen in Datenzentren, die den Besuchern der Site geografisch am nächsten sind. Siehe [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Diese Parameter werden unten beschrieben. Der *kursiv gedruckte Code* stellt einen Variablenplatzhalter dar.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Datentyp </th> 
   <th colname="col3" class="entry"> Beispiel  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>" uuid ": <i>Benutzer-ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p> <code> " uuid ": " 123456789 "</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>" dcs_ region ":<i>Regions-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> " dcs_ region ": 9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielantwort {#sample-response}

Diese einfache Antwort zeigt die `UUID` und die Region `ID`. Beachten Sie, dass dies nur Musterdaten ist. Ihre Protokolldateien können länger und komplexer sein.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Nächste Schritte {#next-steps}

Sobald Sie über die Benutzer-ID und den regionalen Servernamen verfügen, können Sie mit dem Senden und Empfangen [!UICONTROL DCS] von Daten beginnen. Siehe [Erstellen von DCS-API-Aufrufen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).

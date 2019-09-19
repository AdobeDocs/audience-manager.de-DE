---
description: In diesem Abschnitt wird beschrieben, wie Sie eine DCS-Antwort analysieren, um die Besucher- und Regions-IDs abzurufen, die zum Aufrufen des DCS in Echtzeit erforderlich sind.
seo-description: In diesem Abschnitt wird beschrieben, wie Sie eine DCS-Antwort analysieren, um die Besucher- und Regions-IDs abzurufen, die zum Aufrufen des DCS in Echtzeit erforderlich sind.
seo-title: Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort
solution: Audience Manager
title: Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort
uuid: 08036045-3b26-4d40-8e94-7d0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

In diesem Abschnitt wird beschrieben, wie Sie eine [!UICONTROL DCS] Antwort analysieren, um die Besucher- und Regions-IDs abzurufen, die für Echtzeitaufrufe an den Benutzer erforderlich sind [!UICONTROL DCS].

## Benutzer- und Regions-IDs {#user-region-ids}

Eine [!UICONTROL DCS] Antwort enthält Daten zu Ihren Site-Besuchern. Sie benötigen die Besucher- und Regions-ID, bevor Sie Server-zu-Server-Aufrufe an die [!UICONTROL DCS]Gruppe durchführen können.

* Die Benutzer-ID ist erforderlich, um Daten zu einem bestimmten Besucher zu identifizieren und ihm zuzuordnen.
* Die Regions-ID ist erforderlich, da sie mit einem regionalen Servernamen verknüpft ist, den Sie an die [!UICONTROL DCS]Gruppe senden müssen. Die [!UICONTROL DCS] Daten werden in Rechenzentren gespeichert, die den Site-Besuchern am nächsten sind. Siehe [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Diese Parameter werden nachfolgend beschrieben. Code *kursiv* stellt einen variablen Platzhalter dar.

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
   <td colname="col1"> <p><code>"uuid": <i>Benutzer-ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>Regions-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielantwort {#sample-response}

Diese einfache Antwort zeigt die `UUID` Region `ID`. Beachten Sie, dass dies nur Musterdaten sind. Ihre Protokolldateien können länger und komplexer sein.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Nächste Schritte {#next-steps}

Sobald Sie die Benutzer-ID und den regionalen Servernamen haben, können Sie mit dem Senden und Empfangen von [!UICONTROL DCS] Daten beginnen. Siehe [Durchführen von DCS-API-Aufrufen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).

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


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

This section describes how to parse a [!UICONTROL DCS] response to retrieve the visitor and region IDs required to make real-time calls to the [!UICONTROL DCS].

## User and Region IDs {#user-region-ids}

A [!UICONTROL DCS] response contains data about your site visitors. You need the visitor and region ID before you can make server-to-server calls to the [!UICONTROL DCS].

* Die Benutzer-ID ist erforderlich, um Daten mit einem bestimmten Besucher zu identifizieren und zu verknüpfen.
* The region ID is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. Siehe [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Diese Parameter werden unten beschrieben. Code in *italics* represents a variable placeholder.

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

This simple response shows the `UUID` and region `ID`. Beachten Sie, dass dies nur Musterdaten ist. Ihre Protokolldateien können länger und komplexer sein.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Nächste Schritte {#next-steps}

Once you have the user ID and regional server name, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).

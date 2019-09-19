---
description: Der regionale Hostname des DCS-Servers ist erforderlich, um den DCS aufzurufen. Der Grund dafür ist, dass der DCS Informationen in Rechenzentren speichert, die geografisch nahe an den Site-Besuchern liegen. Ihre Abfragen funktionieren, wenn Sie sie an das falsche DCS senden, aber diese Aufrufe sind ineffizient und können die Antwort verzögern. Um eine DCS-Anforderung zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Hostnamen zu und erstellen Sie Ihre Abfrage mit dem richtigen Hostnamen.
seo-description: Der regionale Hostname des DCS-Servers ist erforderlich, um den DCS aufzurufen. Der Grund dafür ist, dass der DCS Informationen in Rechenzentren speichert, die geografisch nahe an den Site-Besuchern liegen. Ihre Abfragen funktionieren, wenn Sie sie an das falsche DCS senden, aber diese Aufrufe sind ineffizient und können die Antwort verzögern. Um eine DCS-Anforderung zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Hostnamen zu und erstellen Sie Ihre Abfrage mit dem richtigen Hostnamen.
seo-title: DCS-Regions-IDs, Speicherorte und Hostnamen
solution: Audience Manager
title: DCS-Regions-IDs, Speicherorte und Hostnamen
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

Der Hostname des regionalen [!UICONTROL DCS] Servers ist erforderlich, um Aufrufe an den Server durchzuführen [!UICONTROL DCS]. Dies liegt daran, dass die [!UICONTROL DCS] Daten in Rechenzentren gespeichert werden, die geografisch nahe an den Site-Besuchern liegen. Ihre Abfragen funktionieren dann, wenn Sie sie an den falschen senden [!UICONTROL DCS], aber diese Aufrufe sind ineffizient und können die Antwort verzögern. Um eine [!UICONTROL DCS] Anforderung zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Hostnamen zu und erstellen Sie Ihre Abfrage mit dem richtigen Hostnamen.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS-Regions-ID (dcs_region) </th> 
   <th colname="col2" class="entry"> Region (und Standort) </th> 
   <th colname="col3" class="entry"> Hostname </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>Südostasien (Singapur) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>Südamerika (São Paulo, Brasilien) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublin, Irland) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>US East (Virginia, USA) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>Südpazifik/Ozeanien (Sydney, Australien) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>US West (Oregon, USA) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>Asien (Tokio, Japan) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>Indien </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Sie können auch [!DNL API] Methoden verwenden, um eine Liste der verfügbaren [!UICONTROL DCS] Regionen abzurufen. Siehe API-Methoden für [DCS-Regionen](../../../api/rest-api-main/aam-api-dcs-regions.md).
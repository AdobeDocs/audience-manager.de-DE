---
description: Der regionale Hostname des DCS-Servers ist erforderlich, um dem DCS Aufrufe zu tätigen. Dies liegt daran, dass das DCS Informationen in Datenzentren speichert, die geografisch zu den Besuchern der Site nah sind. Ihre Abfragen funktionieren, wenn Sie sie an das falsche DCS senden, diese Aufrufe jedoch ineffizient sind und die Antwort verzögern können. Um eine DCS-Anforderung vorzunehmen, passen Sie die Regions-ID an den entsprechenden regionalen Hostnamen an und bilden Sie Ihre Abfrage mit dem richtigen Hostnamen.
seo-description: Der regionale Hostname des DCS-Servers ist erforderlich, um dem DCS Aufrufe zu tätigen. Dies liegt daran, dass das DCS Informationen in Datenzentren speichert, die geografisch zu den Besuchern der Site nah sind. Ihre Abfragen funktionieren, wenn Sie sie an das falsche DCS senden, diese Aufrufe jedoch ineffizient sind und die Antwort verzögern können. Um eine DCS-Anforderung vorzunehmen, passen Sie die Regions-ID an den entsprechenden regionalen Hostnamen an und bilden Sie Ihre Abfrage mit dem richtigen Hostnamen.
seo-title: DCS Regions-IDs, Speicherorte und Hostnamen
solution: Audience Manager
title: DCS Regions-IDs, Speicherorte und Hostnamen
uuid: ad 150 ffe -4583-472 b-ac 8 b-fb 900 a 7966 e 4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Regions-IDs, Speicherorte und Hostnamen {#dcs-region-ids-locations-and-host-names}

Der Hostname des regionalen [!UICONTROL DCS] Servers ist erforderlich, um an [!UICONTROL DCS]die. Dies liegt daran, dass die Informationen [!UICONTROL DCS] in Datenzentren, die geografisch zu den Besuchern der Site nah sind, gespeichert werden. Ihre Abfragen funktionieren, wenn Sie sie an den falschen [!UICONTROL DCS]Ort senden, diese Aufrufe sind jedoch ineffizient und können die Antwort verzögern. Um [!UICONTROL DCS] eine Anforderung zu erstellen, passen Sie die Regions-ID an den entsprechenden regionalen Hostnamen an und bilden Sie Ihre Abfrage mit dem richtigen Hostnamen.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS Regions-ID (dcs_ region) </th> 
   <th colname="col2" class="entry"> Region (und Standort) </th> 
   <th colname="col3" class="entry"> Hostname </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>Südostasien (Singapur) </p> </td> 
   <td colname="col3"> <p> <code> apse. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>Südamerika (São Paulo, Brasilien) </p> </td> 
   <td colname="col3"> <p> <code> sae. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublin, Irland) </p> </td> 
   <td colname="col3"> <p> <code> irl 1. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>US East (Virginia, USA) </p> </td> 
   <td colname="col3"> <p> <code> use. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>South Pacific/Oceania (Sydney, Australien) </p> </td> 
   <td colname="col3"> <p> <code> exit 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>US West (Oregon, USA) </p> </td> 
   <td colname="col3"> <p> <code> usw 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>Asien (Tokio, Japan) </p> </td> 
   <td colname="col3"> <p> <code> tyo 3. demdex. net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>Indien </p> </td> 
   <td colname="col3"> <p> <code> ind 1. demdex. net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Sie können [!DNL API] auch Methoden verwenden, um eine Liste der verfügbaren [!UICONTROL DCS] Regionen zu erhalten. Siehe [DCS-Region-API-Methoden](../../../api/rest-api-main/aam-api-dcs-regions.md).
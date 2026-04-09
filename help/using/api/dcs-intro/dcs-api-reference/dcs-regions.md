---
description: Für Aufrufe an den DCS ist der regionale Hostname des DCS-Servers erforderlich. Dies liegt daran, dass der DCS Informationen in Rechenzentren speichert, die geografisch nah an den Besuchern der Website liegen. Ihre Abfragen funktionieren, wenn Sie sie an die falschen DCS senden, aber diese Aufrufe sind ineffizient und können die Antwort verzögern. Um eine DCS-Anfrage zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Host-Namen zu und erstellen Sie eine Abfrage mit dem richtigen Host-Namen.
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: DCS-Regions-IDs, Standorte und Hostnamen
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
TQID: https://experienceleague.adobe.com/1oK9TLEwbGO-6r9Hempmz8Al6AIYVFkdpKB-ya2UBWw
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 234
ht-degree: 0%

---

# DCS-Regions-IDs, Standorte und Hostnamen {#dcs-region-ids-locations-and-host-names}

Der Hostname des regionalen [!DNL DCS]-Servers ist erforderlich, um Aufrufe an die [!DNL DCS] durchzuführen. Dies liegt daran, dass der [!DNL DCS] Informationen in Rechenzentren speichert, die geografisch nahe an den Besuchern der Website liegen. Ihre Abfragen funktionieren, wenn Sie sie an die falsche [!DNL DCS] senden, aber diese Aufrufe sind ineffizient und können die Antwort verzögern. Um eine [!DNL DCS] Anfrage zu stellen, gleichen Sie die Regions-ID mit dem entsprechenden regionalen Host-Namen ab und geben Sie in Ihrer Abfrage den richtigen Host-Namen ein.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS-Regions-ID (dcs_region) </th> 
   <th colname="col2" class="entry"> Region (und Standort) </th> 
   <th colname="col3" class="entry"> Host-Name </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>Südostasien (Singapur) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>Südamerika (São Paulo, Brasilien) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublin, Irland) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>US East (Virginia, USA) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>Südpazifik / Ozeanien (Sydney, Australien) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>US West (Oregon, USA) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>Asien (Tokio, Japan) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>Indien </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Sie können auch [!DNL API] Methoden verwenden, um eine Liste der verfügbaren [!DNL DCS]-Regionen abzurufen. Siehe [DCS Region API-Methoden](../../../api/rest-api-main/aam-api-dcs-regions.md).

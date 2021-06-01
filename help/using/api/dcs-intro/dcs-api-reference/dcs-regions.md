---
description: Der regionale DCS-Server-Hostname ist erforderlich, um Aufrufe an den DES durchzuführen. Der Grund dafür ist, dass der DES Informationen in Rechenzentren speichert, die geografisch nah an den Site-Besuchern liegen. Ihre Abfragen funktionieren, wenn Sie sie an das falsche DCS senden, diese Aufrufe sind jedoch ineffizient und können die Antwort verzögern. Um eine DCS-Anfrage zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Hostnamen zu und formulieren Sie Ihre Abfrage mit dem richtigen Hostnamen.
seo-description: Der regionale DCS-Server-Hostname ist erforderlich, um Aufrufe an den DES durchzuführen. Der Grund dafür ist, dass der DES Informationen in Rechenzentren speichert, die geografisch nah an den Site-Besuchern liegen. Ihre Abfragen funktionieren, wenn Sie sie an das falsche DCS senden, diese Aufrufe sind jedoch ineffizient und können die Antwort verzögern. Um eine DCS-Anfrage zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Hostnamen zu und formulieren Sie Ihre Abfrage mit dem richtigen Hostnamen.
seo-title: DCS-Regions-IDs, Standorte und Hostnamen
solution: Audience Manager
title: DCS-Regions-IDs, Standorte und Hostnamen
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 9%

---

# DCS-Regions-IDs, Standorte und Hostnamen {#dcs-region-ids-locations-and-host-names}

Der regionale Hostname [!DNL DCS] des Servers ist erforderlich, um Aufrufe an [!DNL DCS] durchzuführen. Dies liegt daran, dass [!DNL DCS] Informationen in Rechenzentren speichert, die geografisch nahe den Besuchern der Website liegen. Ihre Abfragen funktionieren, wenn Sie sie an die falsche [!DNL DCS] senden, diese Aufrufe sind jedoch ineffizient und können die Antwort verzögern. Um eine [!DNL DCS] -Anfrage zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Hostnamen zu und formulieren Sie Ihre Abfrage mit dem richtigen Hostnamen.

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
   <td colname="col2"> <p>USA, Osten (Virginia, USA) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>Südpazifik/Ozeanien (Sydney, Australien) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>USA, Westen (Oregon, USA) </p> </td> 
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

Sie können auch [!DNL API]-Methoden verwenden, um eine Liste der verfügbaren [!DNL DCS]-Regionen zu erhalten. Siehe [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).

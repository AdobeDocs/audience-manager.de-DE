---
description: Hier in Audience Manager sind wir Techniker, Entwickler und Code ninjas genau wie Sie. Ebenso wie Sie möchten wir mit zuverlässigen, genauen API-Dokumenten arbeiten. Daher schreiben wir den API-Inhalt in Swagger und verschieben ihn an eine neue Position. Diese Änderungen helfen Ihnen, Ihr Erlebnis mit dem Audience Manager-API-Code zu verbessern.
seo-description: Hier in Audience Manager sind wir Techniker, Entwickler und Code ninjas genau wie Sie. Ebenso wie Sie möchten wir mit zuverlässigen, genauen API-Dokumenten arbeiten. Daher schreiben wir den API-Inhalt in Swagger und verschieben ihn an eine neue Position. Diese Änderungen helfen Ihnen, Ihr Erlebnis mit dem Audience Manager-API-Code zu verbessern.
seo-title: Migration von Audience Manager-API-Code
solution: Audience Manager
title: Migration von Audience Manager-API-Code
uuid: 93 cc 28 c 4-4 b 91-4 c 79-93 d 5-ece 9 bb 4 cc 9 d 5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# Migration von Audience Manager-API-Code {#audience-manager-api-code-migration}

Hier in Audience Manager sind wir Techniker, Entwickler und Code ninjas genau wie Sie. Ebenso wie Sie möchten wir mit zuverlässigen, genauen [!DNL API] Dokumentation arbeiten. Daher schreiben wir unseren [!DNL API] Inhalt neu und [!DNL Swagger] verschieben ihn an eine neue Position. Diese Änderungen helfen Ihnen, Ihr Erlebnis mit dem Audience Manager [!DNL API] -Code zu verbessern.

## Movin&#39;On Up {#code-migration-details}

<!-- api-swagger-migration.xml -->

Die [Adobe Audience Manager API-Docs-](https://bank.demdex.com/portal/swagger/index.html) Site ist das neue Zuhause unseres überprüften [!DNL API] Inhalts. Wir versuchen, einige Gruppen von [!DNL API] Methoden mit jeder Version neu zu schreiben und zu verschieben. Dies bedeutet, dass Sie sowohl den neuen Ort als auch die [REST-API](../api/rest-api-main/rest-api-main.md) -Dokumentation überprüfen müssen, um alle verfügbaren Methoden zu finden. Letztendlich befinden sich alle öffentlichen [!DNL API]s auf der [!DNL Audience Manager][!DNL API] Docs-Site. Die folgende Tabelle listet die überarbeitet und migrierten [!DNL API]s auf.

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API-Typ </th> 
   <th colname="col2" class="entry"> API-Methoden </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Algorithmische Modelle</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Algorithmische Modelle</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Data Feeds</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Datenfeed-Anforderung</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Datenfeed-Finance</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Datenfeed-Pläne</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Datenfeed-Abonnements</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Datenquelle</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Data Sources</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Abgeleitete Signale</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Abgeleitete Signale</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Ordner</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Segmentordner</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Eigenschaftenordner</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Berichterstellung</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Berichterstellung</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmente</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segmente</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Segmenttestgruppen</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> Segment-Test-Gruppenentwurf-API</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaften</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Eigenschaften</a> </p> </td> 
  </tr>
 </tbody>
</table>
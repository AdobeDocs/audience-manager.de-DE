---
description: Hier im Audience Manager sind wir Ingenieure, Entwickler und Code-Ninjas wie Sie. Und wie Sie möchten wir mit zuverlässiger, genauer API-Dokumentation arbeiten. Daher schreiben wir unseren API-Inhalt in Swagger neu und verschieben ihn an einen neuen Speicherort. Diese Änderungen sollen Ihnen helfen, Ihr Erlebnis mit dem Audience Manager-API-Code zu verbessern.
seo-description: Hier im Audience Manager sind wir Ingenieure, Entwickler und Code-Ninjas wie Sie. Und wie Sie möchten wir mit zuverlässiger, genauer API-Dokumentation arbeiten. Daher schreiben wir unseren API-Inhalt in Swagger neu und verschieben ihn an einen neuen Speicherort. Diese Änderungen sollen Ihnen helfen, Ihr Erlebnis mit dem Audience Manager-API-Code zu verbessern.
seo-title: Audience Manager-API-Codemigration
solution: Audience Manager
title: Audience Manager-API-Codemigration
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# Audience Manager API Code Migration {#audience-manager-api-code-migration}

Hier im Audience Manager sind wir Ingenieure, Entwickler und Code-Ninjas wie Sie. Und wie Sie wollen wir mit zuverlässiger, genauer [!DNL API] Dokumentation arbeiten. Infolgedessen schreiben wir unseren [!DNL API] Inhalt neu [!DNL Swagger] und verschieben ihn an einen neuen Ort. Diese Änderungen sollen Ihnen helfen, Ihre Erfahrung mit dem Audience Manager- [!DNL API] Code zu verbessern.

## Movin' On Up {#code-migration-details}

<!-- api-swagger-migration.xml -->

Die [Adobe Audience Manager API Docs](https://bank.demdex.com/portal/swagger/index.html) -Site ist die neue Heimat für unsere überarbeiteten [!DNL API] Inhalte. Wir werden versuchen, mit jeder Version ein paar [!DNL API] Methoden neu zu schreiben und zu verschieben. Dies bedeutet, dass Sie sowohl den neuen Speicherort als auch die [REST API](../api/rest-api-main/rest-api-main.md) -Dokumentation einsehen müssen, um alle verfügbaren Methoden zu finden. Irgendwann werden alle öffentlichen [!DNL API]s auf der [!DNL Audience Manager] docs-Website [!DNL API] sein. In der folgenden Tabelle sind die überarbeiteten und migrierten [!DNL API]s aufgeführt.

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
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Datenfeed-Finanzen</a> </li> 
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
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Eigenschaftsordner</a> </li> 
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
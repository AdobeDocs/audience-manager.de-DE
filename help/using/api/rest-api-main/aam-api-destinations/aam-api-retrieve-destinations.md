---
description: Eine GET-Methode, die das Ziel für die angegebene destinationId zurückgibt.
seo-description: A GET method that returns the destination for the specified destinationId.
seo-title: Return A Destination by Destination ID
solution: Audience Manager
title: Zurückgeben eines Ziels nach Ziel-ID
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
exl-id: c0850e71-7830-4635-b773-e9a28ab5bd68
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 2%

---

# Zurückgeben eines Ziels nach Ziel-ID {#return-a-destination-by-destination-id}

Eine `GET` Methode, die das Ziel für die angegebene `destinationId` zurückgibt.

<!-- r_get_all_destinations_order_id.xml -->

## Anfrage

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>Um das Feld `mappings` auszufüllen, übergeben Sie `includeMappings=true` in die URL.

## Antwort

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Alle Ziele zurückgeben {#return-all-destinations}

Eine `GET` Methode, die alle Ziele für den angegebenen Partner zurückgibt.

<!-- r_get_all_destinations.xml -->

### Anfrage

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Optional)* Übergeben Sie `containsSegment=<sid>` , um ein Array aller Ziele zurückzugeben, die dem angegebenen Segment zugeordnet sind. Ihre Abfrage könnte beispielsweise in etwa wie folgt aussehen: `GET .../destinations/?containsSegment=4321`.
>
>* Gibt nicht das vollständige Zielobjekt zurück. Rufen Sie die Zieldaten nach Reihenfolge ab, wenn Sie ein vollständig ausgefülltes Objekt benötigen.

### Optionale Abfrageparameter

Sie können diese optionalen Parameter mit API-Methoden verwenden, die *alle*-Eigenschaften für ein -Objekt zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an den [!DNL API] übergeben. Siehe [Optionale Parameter](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th>
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> Gibt Ergebnisse nach Seitenzahl zurück. Nummerierung beginnt bei 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> Legt die Anzahl der von der Anfrage zurückgegebenen Antwortergebnisse fest (10 ist der Standardwert). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">Sortiert Ergebnisse nach der angegebenen <span class="keyword"> JSON</span>-Eigenschaft und gibt sie zurück. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Sortiert die Ergebnisse in absteigender Reihenfolge und gibt sie zurück. Aufsteigend ist Standard. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle finden, die das Wort „Test“ in einem der Wertefelder für dieses Element enthalten. Ihre Beispielanfrage könnte wie folgt aussehen: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Sie können nach jedem Wert suchen, der von einer „get all“-Methode zurückgegeben wird. </p> </td>
  </tr>
 </tbody>
</table>

### Antwort

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Gibt eine Zielzuordnung mit der Zuordnungs-ID zurück. {#return-dest-mapping-id}

Eine `GET` Methode, die eine einzelne Zielzuordnung basierend auf der `mappingId` zurückgibt.

<!-- r_get_destination_trait_data_order.xml -->

### Anfrage

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### Antwort

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Rückgabe von Zielzuordnungen {#return-dest-mappings}

Eine `GET` Methode, die die Zuordnungen für ein Ziel zurückgibt.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>Die zurückgegebene Zuordnung ist spezifisch für den Zieltyp und die Zielkonfiguration.

### Anfrage

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>Unterstützt Paging-Parameter.

### Antwort

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Alle verfügbaren Zielplattformen zurückgeben {#return-dest-platforms}

Eine `GET` Methode, die alle verfügbaren Geräteplattformen für Ziele zurückgibt.

<!-- r_get_dest_platforms.xml -->

### Anfrage

`GET /destinations/configurations/available-platforms/`

### Antwort

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## S2S- und Massen-S2S-Zielvorgangsverlauf zurückgeben {#return-job-history}

Eine `GET` Methode, die Informationen zum Verlauf ausgehender [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) und zum Verlauf [!UICONTROL S2S] Massenzielaufträge zurückgibt.

<!-- r_get_job_history.xml -->

### Anfrage

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Erforderliche Abfrageparameter: `startDate` = *&lt;`epochtime`>* und `endDate` = *&lt;`epochtime`>*.

### Antwort

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```

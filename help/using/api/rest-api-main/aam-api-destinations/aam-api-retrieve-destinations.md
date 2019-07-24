---
description: Eine GET-Methode, die das Ziel für die angegebene destinationid zurückgibt.
seo-description: Eine GET-Methode, die das Ziel für die angegebene destinationid zurückgibt.
seo-title: Zurückgeben eines Ziels nach Ziel-ID
solution: Audience Manager
title: Zurückgeben eines Ziels nach Ziel-ID
uuid: abce 7426-55 a 5-4045-93 a 7-0487652 a 7189
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Return A Destination by Destination ID {#return-a-destination-by-destination-id}

A `GET` method that returns the destination for the specified `destinationId`.

<!-- r_get_all_destinations_order_id.xml -->

## Anfrage

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>To populate the `mappings` field pass in `includeMappings=true` in the URL.

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

## Return All Destinations {#return-all-destinations}

A `GET` method that returns all destinations for the specified partner.

<!-- r_get_all_destinations.xml -->

### Anfrage

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Optional)* Geben Sie an, `containsSegment=<sid>` um ein Array aller Ziele zurückzugeben, die dem angegebenen Segment zugeordnet sind. For example, your query could look similar to this: `GET .../destinations/?containsSegment=4321`.
   >
   >
* Gibt das vollständige Zielobjekt nicht zurück. Rufen Sie das Ziel nach Datenreihenfolge ab, wenn Sie ein vollständig ausgefülltes Objekt benötigen.


### Optionale Abfrageparameter

You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col1"><code> Pagesize</code> </td>
   <td colname="col2"> Legt die Anzahl der von der Anforderung zurückgegebenen Antwortergebnisse fest (Standard: 10). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Sortby</code> </td>
   <td colname="col2">Sorts and returns results according to the specified <span class="keyword"> JSON</span> property. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> absteigend</code> </td>
   <td colname="col2"> Sortiert die Ergebnisse in absteigender Reihenfolge und gibt sie zurück. Aufsteigend ist die Standardeinstellung. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> suchen</code> </td>
   <td colname="col2">Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle mit dem Wort "Test" in allen Wertfeldern für dieses Element suchen. Ihre Beispielanforderung könnte wie folgt aussehen: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Sie können nach jedem Wert suchen, der von einer "get all" -Methode zurückgegeben wird. </p> </td>
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

## Return a Destination Mapping With the Mapping ID {#return-dest-mapping-id}

A `GET` method that returns an individual destination mapping based on the `mappingId`.

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

## Return Destination Mappings {#return-dest-mappings}

A `GET` method that returns the mappings for a destination.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>Die zurückgegebene Zuordnung ist spezifisch für den Zieltyp und die Konfiguration.

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

## Return All Available Destination Platforms {#return-dest-platforms}

`GET` Eine Methode, die alle verfügbaren Geräteplattformen für Ziele zurückgibt.

<!-- r_get_dest_platforms.xml -->

### Anfrage

`GET /destinations/configurations/available-platforms/`

### Antwort

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Return S2S and Bulk S2S Destination Job History {#return-job-history}

A `GET` method that returns outbound [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) and bulk [!UICONTROL S2S] destination job history information.

<!-- r_get_job_history.xml -->

### Anfrage

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Required query parameters: `startDate` = *&lt;`epochtime`&gt;* and `endDate` = *&lt;`epochtime`&gt;*.

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

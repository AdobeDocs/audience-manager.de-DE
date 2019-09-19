---
description: Eine GET-Methode, die das Ziel für die angegebene destinationId zurückgibt.
seo-description: Eine GET-Methode, die das Ziel für die angegebene destinationId zurückgibt.
seo-title: Ziel nach Ziel-ID zurückgeben
solution: Audience Manager
title: Ziel nach Ziel-ID zurückgeben
uuid: abce7426-55a5-4045-93a7-0487652a7189
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Ziel nach Ziel-ID zurückgeben {#return-a-destination-by-destination-id}

Eine `GET` Methode, die das Ziel für die angegebene `destinationId`Methode zurückgibt.

<!-- r_get_all_destinations_order_id.xml -->

## Anfrage

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>Um das `mappings` Feld auszufüllen, geben Sie `includeMappings=true` die URL ein.

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
>* *(Optional)* Geben Sie ein Array aller Ziele `containsSegment=<sid>` zurück, die dem angegebenen Segment zugeordnet sind. Ihre Abfrage könnte z. B. wie folgt aussehen: `GET .../destinations/?containsSegment=4321`.
   >
   >
* Gibt nicht das vollständige Zielobjekt zurück. Rufen Sie das Ziel nach Datenreihenfolge ab, wenn Sie ein vollständig ausgefülltes Objekt benötigen.


### Optionale Abfrageparameter

Sie können diese optionalen Parameter mit API-Methoden verwenden, die *alle* Eigenschaften eines Objekts zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an die [!DNL API]übergeben. Siehe [Optionale Parameter](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Gibt Ergebnisse nach Seitenzahl zurück. Die Nummerierung beginnt bei 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> Legt die Anzahl der Antwortergebnisse fest, die von der Anforderung zurückgegeben werden (10 ist standardmäßig). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">Sortiert Ergebnisse und gibt sie entsprechend der angegebenen <span class="keyword"> JSON</span> -Eigenschaft zurück. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> absteigend</code> </td>
   <td colname="col2"> Sortiert die Ergebnisse und gibt sie in absteigender Reihenfolge zurück. "Aufsteigend"ist die Standardeinstellung. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Nehmen wir beispielsweise an, Sie möchten Ergebnisse für alle Modelle suchen, die das Wort "Test"in einem der Wertefelder für dieses Element enthalten. Ihre Musteranforderung könnte wie folgt aussehen: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Sie können nach jedem Wert suchen, der von der Methode "get all"zurückgegeben wird. </p> </td>
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

## Eine Zielzuordnung mit der Zuordnungs-ID zurückgeben {#return-dest-mapping-id}

Eine `GET` Methode, die eine individuelle Zielzuordnung basierend auf der `mappingId`Methode zurückgibt.

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

## Zuordnungen rückkehrender Ziele {#return-dest-mappings}

Eine `GET` Methode, die die Zuordnungen für ein Ziel zurückgibt.

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

## S2S- und Bulk-S2S-Zielauftragsverlauf zurückgeben {#return-job-history}

Eine `GET` Methode, die Informationen zum Ausgangsauftragsverlauf [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) und zum Massenzielauftragsverlauf [!UICONTROL S2S] zurückgibt.

<!-- r_get_job_history.xml -->

### Anfrage

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Erforderliche Abfrageparameter: `startDate` = *&lt;`epochtime`&gt;* und `endDate` = *&lt;`epochtime`&gt;*.

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

---
description: Ordnen Sie Segmente Ziele mit diesen restful-API-Methoden zu.
seo-description: Ordnen Sie Segmente Ziele mit diesen restful-API-Methoden zu.
seo-title: Segmente einem Ziel zuordnen
solution: Audience Manager
title: Segmente einem Ziel zuordnen
uuid: 35358 ace -3082-4 e 86-a 6 eb-d 77281 af 6 d 7 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Map Segments to a Destination {#map-segments-to-a-destination}

Map segments to destinations with these [!DNL RESTful API] methods.

<!-- c_api_map_seg_dest.xml -->

## Unterstützte Zieltypen: Nur URL und Cookie

The available `POST` methods let you map segments to [!UICONTROL URL] and [!UICONTROL cookie destinations] only. Currently, you cannot map segments to [!UICONTROL server-to-server destinations] with these [!DNL REST API] methods. Verwenden Sie stattdessen die Benutzeroberfläche. However, the related destination `GET` methods let you retrieve information about [!UICONTROL server-to-server destinations] created in the user interface.

>[!MORE_ LIKE_ THIS]
>
>* [Ziele](../../../features/destinations/destinations.md#destination-api-methods)
>* [Zielreihenbildung](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Wichtige Wertpaare](../../../reference/key-value-pairs-explained.md)


## Map a Segment to a Non-Serialized URL Destination {#map-segment-non-serial}

A `POST` method that lets you map a segment to a non-serial [!UICONTROL URL] destination.

<!-- r_map_noserial_url.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### Antwort

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## Map a Segment to a Serialized URL Destination {#map-segment-serial}

A `POST` method that lets you map a segment to a serialized [!UICONTROL URL] destination.

<!-- r_map_serialized_url.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Beispielanforderung

In the request, the `traitAlias` corresponds to the key in a key-value pair. Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Antwort

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Map a Segment to a Cookie Destination: Single-Key, Non-Serialized {#map-segment-cookie-noserial}

A `POST` method that lets you map a segment to single-key, non-serialized [!UICONTROL cookie] destination.

<!-- r_map_cookie_noserial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

In the request, the `valueAlias` corresponds to the value in a key-value pair. Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### Antwort

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Map a Segment to a Cookie Destination: Multi-Key, Non-Serialized {#map-segment-cookie-multi-noserial}

A `POST` method that lets you map a segment to multi-key, non-serialized [!UICONTROL cookie] destination.

<!-- r_map_cookie_multikey_noserial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

In the request, the `traitAlias` and `valueAlias` set the key and the value respectively in a key-value pair. Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Antwort

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Map a Segment to a Cookie Destination: Multi-Key, Serialized {#map-segment-cookie-multi-serial}

`POST` Eine Methode, mit der Sie ein Segment einem Mehrschlüssel serialisieren [!UICONTROL cookie destination]können.

<!-- r_map_cookie_multikey_serialized.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

In the request, the `traitAlias` and `valueAlias` set the key and the value in a key-value pair. Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Antwort

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Map a Segment to a Server-to-Server Destination {#map-segment-s2s}

A `POST` method that lets you map a segment to an existing [!UICONTROL server-to-server] destination. Note, however, that you cannot create [!UICONTROL server-to-server] destinations with these currently available [!DNL API] methods.

<!-- r_map_segment_s2s.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

In the request, the `traitAlias` corresponds to the key in a key-value pair. Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Antwort

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## Bulk Create Destination Mappings {#bulk-create}

A `POST` method that lets you pass in an array of [!UICONTROL cookie] or [!UICONTROL URL] destination mappings.

<!-- r_bulk_create.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### Beispielanforderung

Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Antwort

Eine erfolgreiche Antwort gibt das Array der erstellten Zuordnungen zurück.

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Add Multiple Segments to a Destination {#add-segments-dest}

A `POST` method that lets you map multiple segments to a destination.

<!-- r_add_segments_to_destination.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### Beispielanforderung

Erstellen Sie mehrere Zielgruppenzuordnungen in einem Array. Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Antwort

Gibt ein Array mit erstellten Zuordnungen zurück.

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Update a Destination by Destination ID {#update-dest-data-order}

`PUT` Eine Methode, mit der Sie ein vorhandenes Ziel aktualisieren `destinationId`können.

<!-- r_update_destination_data_order_id.xml -->

### Anfrage

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### Beispielanforderung

Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Antwort

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## Update a Mapping to a Destination by Mapping ID {#update-mapping-dest-id}

`PUT` Eine Methode, mit der Sie eine Zuordnung auf einem Ziel durch den angegebenen aktualisieren `mappingId`können.

<!-- r_update_destination_trait_data_order_id.xml -->

### Anfrage

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### Beispielanforderung

Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### Antwort

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```

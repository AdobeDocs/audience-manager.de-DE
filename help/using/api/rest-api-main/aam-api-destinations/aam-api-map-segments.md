---
description: Ordnen Sie Ziele mit diesen RESTful-API-Methoden Segmente zu.
seo-description: Ordnen Sie Ziele mit diesen RESTful-API-Methoden Segmente zu.
seo-title: Zuordnen von Segmenten zu einem Ziel
solution: Audience Manager
title: Zuordnen von Segmenten zu einem Ziel
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 11%

---


# Zuordnen von Segmenten zu einem Ziel {#map-segments-to-a-destination}

Ordnen Sie Segmente mit diesen [!DNL RESTful API]-Methoden Zielen zu.

<!-- c_api_map_seg_dest.xml -->

## Unterstützte Zieltypen: Nur URL und Cookie

Mit den verfügbaren `POST`-Methoden können Sie Segmente nur [!UICONTROL URL] und [!UICONTROL cookie destinations] zuordnen. Derzeit können Segmente mit diesen [!DNL REST API]-Methoden nicht [!UICONTROL server-to-server destinations] zugeordnet werden. Verwenden Sie stattdessen die Benutzeroberfläche. Mit den entsprechenden Methoden `GET` können Sie jedoch Informationen zu [!UICONTROL server-to-server destinations] abrufen, die in der Benutzeroberfläche erstellt wurden.

## Zuordnen eines Segments zu einem nicht serialisierten URL-Ziel {#map-segment-non-serial}

Eine `POST`-Methode, mit der Sie ein Segment einem nicht seriellen [!UICONTROL URL]-Ziel zuordnen können.

<!-- r_map_noserial_url.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

## Zuordnen eines Segments zu einem serialisierten URL-Ziel {#map-segment-serial}

Eine `POST`-Methode, mit der Sie ein Segment einem serialisierten [!UICONTROL URL]-Ziel zuordnen können.

<!-- r_map_serialized_url.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Beispielanforderung

In der Anforderung entspricht das `traitAlias` dem Schlüssel in einem Schlüssel-Wert-Paar. Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

## Ordnen Sie einem Cookie-Ziel ein Segment zu: Einzelschlüssel, nicht serialisiert {#map-segment-cookie-noserial}

Eine `POST`-Methode, mit der Sie ein Segment einem nicht serialisierten Einzelschlüssel [!UICONTROL cookie]-Ziel zuordnen können.

<!-- r_map_cookie_noserial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

In der Anforderung entspricht `valueAlias` dem Wert in einem Schlüssel-Wert-Paar. Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

## Ordnen Sie einem Cookie-Ziel ein Segment zu: Multi-Key, nicht serialisiert {#map-segment-cookie-multi-noserial}

Eine `POST`-Methode, mit der Sie ein Segment einem nicht serialisierten Multi-Key-Ziel [!UICONTROL cookie] zuordnen können.

<!-- r_map_cookie_multikey_noserial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

Legen Sie in der Anforderung den Schlüssel bzw. den Wert in einem Schlüssel-Wert-Paar fest. `traitAlias``valueAlias` Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

## Ordnen Sie einem Cookie-Ziel ein Segment zu: Multi-Key, serialisiert {#map-segment-cookie-multi-serial}

Eine `POST`-Methode, mit der Sie ein Segment einem mehrfachen, serialisierten [!UICONTROL cookie destination] zuordnen können.

<!-- r_map_cookie_multikey_serialized.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

Legen Sie in der Anforderung den Schlüssel und den Wert in einem Schlüssel-Wert-Paar fest. `traitAlias``valueAlias` Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

## Zuordnen eines Segments zu einem Server-zu-Server-Ziel {#map-segment-s2s}

Eine `POST`-Methode, mit der Sie ein Segment einem vorhandenen [!UICONTROL server-to-server]-Ziel zuordnen können. Beachten Sie jedoch, dass Sie mit den derzeit verfügbaren [!DNL API]-Methoden keine [!UICONTROL server-to-server]-Ziele erstellen können.

<!-- r_map_segment_s2s.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Beispielanforderung

In der Anforderung entspricht das `traitAlias` dem Schlüssel in einem Schlüssel-Wert-Paar. Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

## Massen-Erstellen von Zielzuordnungen {#bulk-create}

Eine `POST`-Methode, mit der Sie ein Array von [!UICONTROL cookie]- oder [!UICONTROL URL]-Zielzuordnungen übergeben können.

<!-- r_bulk_create.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### Beispielanforderung

Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

## hinzufügen mehrerer Segmente an ein Ziel {#add-segments-dest}

Eine `POST`-Methode, mit der Sie einem Ziel mehrere Segmente zuordnen können.

<!-- r_add_segments_to_destination.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### Beispielanforderung

Erstellen Sie mehrere Zielzuordnungen in einem Array. Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

Gibt ein Array erstellter Zuordnungen zurück.

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

## Ziel nach Ziel-ID {#update-dest-data-order} aktualisieren

Eine `PUT`-Methode, mit der Sie ein vorhandenes Ziel um `destinationId` aktualisieren können.

<!-- r_update_destination_data_order_id.xml -->

### Anfrage

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### Beispielanforderung

Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

## Zuordnung zu einem Ziel aktualisieren durch Zuordnung der ID {#update-mapping-dest-id}

Eine `PUT`-Methode, mit der Sie eine Zuordnung zu einem Ziel mit dem angegebenen `mappingId` aktualisieren können.

<!-- r_update_destination_trait_data_order_id.xml -->

### Anfrage

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### Beispielanforderung

Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

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

>[!MORELIKETHIS]
>
>* [Ziele ](../../../features/destinations/destinations.md)
>* [Ziel-Serialisierung](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Schlüssel-Wert-Paare – Erklärung](../../../reference/key-value-pairs-explained.md)


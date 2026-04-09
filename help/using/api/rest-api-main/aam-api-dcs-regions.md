---
description: Methoden, mit denen Sie Audience Manager DCS-Regionen programmgesteuert auflisten können.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: DCS Region API-Methoden
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
TQID: https://experienceleague.adobe.com/ipsOlq24Y00SHvGKgUFJHnRQ11DZIuDNY76D5LCAgso
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 110
ht-degree: 3%

---

# DCS Region API-Methoden {#dcs-region-api-methods}

Methoden, mit denen Sie Audience Manager [!DNL DCS]-Regionen programmgesteuert auflisten können.

<!-- c_rest_api_regions.xml -->

Eine Liste der Regionen und der zugehörigen Ganzzahlen finden Sie unter [DCS-Regions-IDs, Standorte und Hostnamen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Auflisten einer bestimmten DCS-Region {#list-specific-dcs-region}

Eine `GET` Methode zum Auflisten einer bestimmten [!DNL DCS].

<!-- r_rest_api_regions_list_specific.xml -->

### Anfrage

`GET /v1/dcs-regions/`*`<id>`*

### Beispielantwort

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

Gibt bei Erfolg `200 OK` zurück.

Eine Liste der Regionen und der zugehörigen Ganzzahlen finden Sie unter [DCS-Regions-IDs, Standorte und Hostnamen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## DCS-Regionen auflisten {#list-dcs-regions}

Eine `GET` Methode zum Auflisten [!DNL DCS] Regionen.

<!-- r_rest_api_regions_list.xml -->

### Anfrage

`GET /v1/dcs-regions/`

### Beispielantwort

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

Gibt bei Erfolg `200 OK` zurück.

Eine Liste der Regionen und der zugehörigen Ganzzahlen finden Sie unter [DCS-Regions-IDs, Standorte und Hostnamen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

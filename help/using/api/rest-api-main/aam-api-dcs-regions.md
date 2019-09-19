---
description: Methoden, mit denen Sie Audience Manager-DCS-Regionen programmatisch auflisten können.
seo-description: Methoden, mit denen Sie Audience Manager-DCS-Regionen programmatisch auflisten können.
seo-title: API-Methoden für DCS-Regionen
solution: Audience Manager
title: API-Methoden für DCS-Regionen
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API-Methoden für DCS-Regionen {#dcs-region-api-methods}

Methoden, mit denen Sie Audience Manager- [!UICONTROL DCS] Regionen programmatisch auflisten können.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Eine bestimmte DCS-Region auflisten {#list-specific-dcs-region}

Eine `GET` Methode zur Auflistung einer bestimmten [!UICONTROL DCS] Region.

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

Gibt `200 OK` bei erfolgreicher Ausführung zurück.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## DCS-Regionen auflisten {#list-dcs-regions}

Eine `GET` Methode zur Auflistung von [!UICONTROL DCS] Regionen.

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

Gibt `200 OK` bei erfolgreicher Ausführung zurück.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

---
description: Methoden, mit denen Sie Audience Manager-DCS-Regionen programmgesteuert auflisten können.
seo-description: Methoden, mit denen Sie Audience Manager-DCS-Regionen programmgesteuert auflisten können.
seo-title: API-Methoden für die DCS-Region
solution: Audience Manager
title: API-Methoden für die DCS-Region
uuid: 00 b 70927-b 3 b 7-46 bb -8 be 1-37 c 6100 ecf 80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API-Methoden für die DCS-Region {#dcs-region-api-methods}

Methoden, mit denen Sie Audience Manager [!UICONTROL DCS] -Regionen programmgesteuert auflisten können.

<!-- c_rest_api_regions.xml -->

Eine Liste der Regionen und der entsprechenden Ganzzahlen finden Sie unter [DCS Regions-IDs, Speicherorte und Hostnamen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Eine bestimmte DCS-Region auflisten {#list-specific-dcs-region}

`GET` Eine Methode zur Liste einer bestimmten [!UICONTROL DCS] Region.

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

Gibt zurück, `200 OK` wenn erfolgreich.

Eine Liste der Regionen und der entsprechenden Ganzzahlen finden Sie unter [DCS Regions-IDs, Speicherorte und Hostnamen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Liste der DCS-Regionen {#list-dcs-regions}

`GET` Eine Methode für [!UICONTROL DCS] die Regionen.

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

Gibt zurück, `200 OK` wenn erfolgreich.

Eine Liste der Regionen und der entsprechenden Ganzzahlen finden Sie unter [DCS Regions-IDs, Speicherorte und Hostnamen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

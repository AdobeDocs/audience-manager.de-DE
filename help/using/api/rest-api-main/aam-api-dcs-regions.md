---
description: Methoden, mit denen Sie Audience Manager-DCS-Regionen programmatisch Liste erhalten.
seo-description: Methoden, mit denen Sie Audience Manager-DCS-Regionen programmatisch Liste erhalten.
seo-title: API-Methoden für DCS-Regionen
solution: Audience Manager
title: API-Methoden für DCS-Regionen
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 14%

---


# API-Methoden für DCS-Regionen {#dcs-region-api-methods}

Methoden, mit denen Sie Audience Manager [!DNL DCS] programmgesteuert Liste durchführen können.

<!-- c_rest_api_regions.xml -->

Eine Liste der Regionen und der zugehörigen Ganzzahlen finden Sie unter [DCS-Regions-IDs, Standorte und Hostnamen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Liste einer bestimmten DCS-Region {#list-specific-dcs-region}

Eine `GET`-Methode zur Liste eines bestimmten [!DNL DCS]-Bereichs.

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

Gibt `200 OK` zurück, wenn erfolgreich.

Eine Liste der Regionen und der zugehörigen Ganzzahlen finden Sie unter [DCS-Regions-IDs, Standorte und Hostnamen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Liste DCS Regionen {#list-dcs-regions}

Eine `GET`-Methode zur Liste von [!DNL DCS]-Regionen.

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

Gibt `200 OK` zurück, wenn erfolgreich.

Eine Liste der Regionen und der zugehörigen Ganzzahlen finden Sie unter [DCS-Regions-IDs, Standorte und Hostnamen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

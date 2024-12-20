---
description: REST-API-Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: API-Methoden zur Berechtigungsverwaltung
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%

---

# API-Methoden zur Berechtigungsverwaltung {#permissions-management-api-methods}

REST [!DNL API] Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.

<!-- c_rest_api_perm_man.xml -->

## Verfügbare Objekttypen auflisten {#list-object-types}

Eine `GET` Methode zum Auflisten der verfügbaren Objekttypen, für die rollenbasierte Zugriffssteuerelemente festgelegt werden können.

<!-- r_rest_api_perm_list.xml -->

### Anfrage

`GET /api/v1/permissionable-object-types/`

### Antwort

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Auflisten der verfügbaren Berechtigungen für einen Objekttyp {#list-permissions-object-type}

Eine `GET` Methode zum Auflisten der verfügbaren Berechtigungen für einen Objekttyp.

<!-- r_rest_api_perm_list_perms.xml -->

### Anfrage

`GET /api/v1/permissionable-object-types/SEGMENT/`

### Antwort

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>Die Objekttypen TAGS und DERIVED SIGNALS verfügen über keine regulären Verwendungsberechtigungen. Die Steuerelemente für diese Objekttypen werden nur durch die Platzhalterberechtigungen „Alles oder nichts“ geändert.

---
description: REST-API-Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.
seo-description: REST-API-Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.
seo-title: API-Methoden zur Berechtigungsverwaltung
solution: Audience Manager
title: API-Methoden zur Berechtigungsverwaltung
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# API-Methoden zur Berechtigungsverwaltung {#permissions-management-api-methods}

Die übrigen [!DNL API] Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.

<!-- c_rest_api_perm_man.xml -->

## Verfügbare Objekttypen auflisten {#list-object-types}

Eine `GET` Methode zur Auflistung der verfügbaren Objekttypen, für die rollenbasierte Zugriffssteuerelemente festgelegt werden können.

<!-- r_rest_api_perm_list.xml -->

### Anfrage

`GET /api/v1/permissionable-object-types/`

### Antwort

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Verfügbare Berechtigungen für einen Objekttyp auflisten {#list-permissions-object-type}

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
>Die Objekttypen TAGS und DERIVED SIGNALS haben keine regulären Berechtigungen zur Verwendung. Die Steuerelemente für diese Objekttypen werden nur durch die Berechtigungen "Alle"oder "Keine Platzhalter"geändert.
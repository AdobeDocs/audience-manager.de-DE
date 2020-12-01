---
description: REST-API-Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.
seo-description: REST-API-Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.
seo-title: API-Methoden für die Berechtigungsverwaltung
solution: Audience Manager
title: API-Methoden für die Berechtigungsverwaltung
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 14%

---


# API-Methoden für die Berechtigungsverwaltung {#permissions-management-api-methods}

REST [!DNL API]-Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.

<!-- c_rest_api_perm_man.xml -->

## Liste Verfügbare Objekttypen {#list-object-types}

Eine `GET`-Methode zur Liste verfügbarer Objekttypen, für die rollenbasierte Zugriffskontrollen festgelegt werden können.

<!-- r_rest_api_perm_list.xml -->

### Anfrage

`GET /api/v1/permissionable-object-types/`

### Antwort

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Verfügbare Berechtigungen für eine Liste für einen Objekttyp {#list-permissions-object-type}

Eine `GET`-Methode zur Liste der verfügbaren Berechtigungen für einen Objekttyp.

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
>Die Objekttypen TAGS und DERIVED SIGNALS haben keine regulären Berechtigungen zur Verwendung. Die Steuerelemente für diese Objekttypen werden nur durch die Berechtigungen &quot;Alle&quot;oder &quot;Keine Platzhalter&quot;geändert.
---
description: REST-API-Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.
seo-description: REST-API-Methoden zum Verwalten von Berechtigungen für Objekte und Gruppen.
seo-title: Zugriffssteuerungsungs-API-Methoden
solution: Audience Manager
title: Zugriffssteuerungsungs-API-Methoden
uuid: 111 d 0 f 92-d 92 c -4 d 4 b-b 0 d 6-10 dd 3 fa 466 ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Permissions Management API Methods {#permissions-management-api-methods}

Rest [!DNL API] methods to manage permissions for objects and groups.

<!-- c_rest_api_perm_man.xml -->

## List Available Object Types {#list-object-types}

`GET` Eine Methode zur Liste verfügbarer Objekttypen, auf denen rollenbasierte Zugriffssteuerungselemente festgelegt werden können.

<!-- r_rest_api_perm_list.xml -->

### Anfrage

`GET /api/v1/permissionable-object-types/`

### Antwort

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## List Available Permissions for an Object Type {#list-permissions-object-type}

`GET` Eine Methode zur Liste der verfügbaren Berechtigungen für einen Objekttyp.

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
>Die Objekttypen TAGS und abgeleitete SIGNALE haben keine regulären Berechtigungen. Steuerelemente für diese Objekttypen werden nur durch Alle oder Nichts Wildcard-Berechtigungen geändert.
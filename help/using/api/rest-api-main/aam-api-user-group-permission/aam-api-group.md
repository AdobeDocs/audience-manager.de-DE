---
description: REST-API-Methoden zur Verwaltung von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.
seo-description: REST-API-Methoden zur Verwaltung von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.
seo-title: Gruppenverwaltungs-API-Methoden
solution: Audience Manager
title: Gruppenverwaltungs-API-Methoden
uuid: fe 042 eb 5-ea 12-42 fe-be 98-d 721 f 987 a 914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Group Management API Methods {#group-management-api-methods}

Rest [!DNL API] methods to manage groups, including creating, updating, listing, deleting groups.

<!-- c_rest_api_user_man_group.xml -->

## Eine Gruppe erstellen {#create-group}

`POST` Eine Methode zum Erstellen einer neuen Benutzergruppe.

<!-- r_rest_api_group_create.xml -->

### Anfrage

`POST /api/v1/groups/`

### Beispielanforderungskörper

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Antwort

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Update a Group {#update-group}

`PUT` Eine Methode zum Aktualisieren einer Benutzergruppe.

<!--
r_rest_api_group_update.xml
-->

### Anfrage

`PUT /api/v1/groups/`*`<groupId>`*

### Beispielanforderungskörper

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Antwort

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## List Groups {#list-groups}

`GET` Eine Methode zum Auflisten von Benutzergruppen.

<!--
r_rest_api_group_list.xml
-->

### Anfrage

`GET /api/v1/groups/`

### Antwort

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## Eine Gruppe löschen {#delete-groups}

`DELETE` Eine Methode zum Löschen einer Benutzergruppe und zum Entfernen aller Mitglieder aus dieser Gruppe.

<!-- r_rest_api_group_delete.xml -->

### Anfrage

`DELETE /api/v1/groups/`*`<groupId>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Groups in Bulk {#delete-groups-bulk}

A `DELETE` method to delete multiple groups in bulk and remove all members from that group.

<!-- r_rest_api_group_delete_bulk.xml -->

### Anfrage

`DELETE /api/v1/groups/bulk-delete`

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## List All Permissions for a Group {#list-permissions-group}

`GET` Eine Methode zur Liste der Berechtigungsobjekte einer Gruppe.

<!-- r_rest_api_perm_list_group.xml -->

### Anfrage

`GET /api/v1/groups/{groupId}/permissions`

### Antwort

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

Returns `400 Bad Request` if the group is inaccessible.

## Set Permissions for a Group {#set-permissions-group}

`PUT` Eine Methode zum Aktualisieren von Gruppenberechtigungen. Diese Methode überschreibt die alten Berechtigungen mit den neuen Berechtigungen.

<!-- r_rest_api_perm_set.xml -->

### Anfrage

`PUT /api/v1/groups/{groupId}/permissions/`

### Antwort

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

Die Beispielantwort stellt die aktualisierte Liste der Berechtigungsobjekte dar.

Returns `200 OK` if successful. Returns `400` if any given permission is invalid. Can also return `403` if the object is not accessible by the logged-in user.
---
description: REST-API-Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: API-Methoden für die Gruppenverwaltung
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---

# API-Methoden für die Gruppenverwaltung {#group-management-api-methods}

[!DNL API] Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.

<!-- c_rest_api_user_man_group.xml -->

## Eine Gruppe erstellen {#create-group}

Eine `POST` Methode zum Erstellen einer neuen Benutzergruppe.

<!-- r_rest_api_group_create.xml -->

### Anfrage

`POST /api/v1/groups/`

### Beispiel-Anfrageinhalt

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

## Aktualisieren einer Gruppe {#update-group}

Eine `PUT` Methode zum Aktualisieren einer Benutzergruppe.

<!--
r_rest_api_group_update.xml
-->

### Anfrage

`PUT /api/v1/groups/`*`<groupId>`*

### Beispiel-Anfrageinhalt

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

## Gruppen auflisten {#list-groups}

Eine `GET` Methode zum Auflisten von Benutzergruppen.

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

Eine `DELETE` Methode zum Löschen einer Benutzergruppe und zum Entfernen aller Mitglieder aus dieser Gruppe.

<!-- r_rest_api_group_delete.xml -->

### Anfrage

`DELETE /api/v1/groups/`*`<groupId>`*

Gibt bei Erfolg `204 No Content` zurück. Im Konfliktfall gibt `409 Conflict` zurück.

## Gruppen stapelweise löschen {#delete-groups-bulk}

Eine `DELETE` Methode zum Massenlöschen mehrerer Gruppen und zum Entfernen aller Mitglieder aus dieser Gruppe.

<!-- r_rest_api_group_delete_bulk.xml -->

### Anfrage

`DELETE /api/v1/groups/bulk-delete`

Gibt bei Erfolg `204 No Content` zurück. Im Konfliktfall gibt `409 Conflict` zurück.

## Auflisten aller Berechtigungen für eine Gruppe {#list-permissions-group}

Eine `GET` Methode zum Auflisten der Berechtigungsobjekte für eine Gruppe.

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

Gibt `400 Bad Request` zurück, wenn die Gruppe nicht zugänglich ist.

## Festlegen von Berechtigungen für eine Gruppe {#set-permissions-group}

Eine `PUT` Methode zum Aktualisieren von Gruppenberechtigungen. Diese Methode überschreibt die alten Berechtigungen mit den neuen Berechtigungen.

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

Gibt bei Erfolg `200 OK` zurück. Gibt `400` zurück, wenn eine gegebene Berechtigung ungültig ist. Kann auch `403` zurückgeben, wenn der angemeldete Benutzer nicht auf das Objekt zugreifen kann.

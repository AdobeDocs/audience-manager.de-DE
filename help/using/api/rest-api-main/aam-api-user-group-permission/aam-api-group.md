---
description: REST-API-Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.
seo-description: REST-API-Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.
seo-title: API-Methoden für Gruppenverwaltung
solution: Audience Manager
title: API-Methoden für Gruppenverwaltung
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# API-Methoden für Gruppenverwaltung {#group-management-api-methods}

Die übrigen [!DNL API] Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.

<!-- c_rest_api_user_man_group.xml -->

## Eine Gruppe erstellen {#create-group}

Eine `POST` Methode zum Erstellen einer neuen Benutzergruppe.

<!-- r_rest_api_group_create.xml -->

### Anfrage

`POST /api/v1/groups/`

### Stichprobenanforderungskörper

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

## Eine Gruppe aktualisieren {#update-group}

Eine `PUT` Methode zum Aktualisieren einer Benutzergruppe.

<!--
r_rest_api_group_update.xml
-->

### Anfrage

`PUT /api/v1/groups/`*`<groupId>`*

### Stichprobenanforderungskörper

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

## Listengruppen {#list-groups}

Eine `GET` Methode zur Auflistung von Benutzergruppen.

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

Gibt `204 No Content` bei erfolgreicher Ausführung zurück. Im Falle eines Konflikts gibt es `409 Conflict`.

## Gruppen stapelweise löschen {#delete-groups-bulk}

Eine `DELETE` Methode, mit der mehrere Gruppen stapelweise gelöscht und alle Mitglieder aus dieser Gruppe entfernt werden können.

<!-- r_rest_api_group_delete_bulk.xml -->

### Anfrage

`DELETE /api/v1/groups/bulk-delete`

Gibt `204 No Content` bei erfolgreicher Ausführung zurück. Im Falle eines Konflikts gibt es `409 Conflict`.

## Alle Berechtigungen für eine Gruppe auflisten {#list-permissions-group}

Eine `GET` Methode zum Auflisten der Berechtigungsobjekte in einer Gruppe.

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

Gibt zurück, `400 Bad Request` wenn auf die Gruppe nicht zugegriffen werden kann.

## Set Permissions for a Group {#set-permissions-group}

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

Gibt `200 OK` bei erfolgreicher Ausführung zurück. Gibt zurück, `400` wenn eine angegebene Berechtigung ungültig ist. Kann auch zurückgegeben werden, `403` wenn der angemeldete Benutzer nicht auf das Objekt zugreifen kann.
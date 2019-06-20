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


# Gruppenverwaltungs-API-Methoden {#group-management-api-methods}

Rest [!DNL API] -Methoden zur Verwaltung von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.

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

## Eine Gruppe aktualisieren {#update-group}

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

## Listengruppen {#list-groups}

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

Gibt zurück, `204 No Content` wenn erfolgreich. Bei Konflikten zurückgegeben `409 Conflict`.

## Gruppen stapelweise löschen {#delete-groups-bulk}

Eine `DELETE` Methode, um mehrere Gruppen stapelweise zu löschen und alle Mitglieder aus dieser Gruppe zu entfernen.

<!-- r_rest_api_group_delete_bulk.xml -->

### Anfrage

`DELETE /api/v1/groups/bulk-delete`

Gibt zurück, `204 No Content` wenn erfolgreich. Bei Konflikten zurückgegeben `409 Conflict`.

## Alle Berechtigungen für eine Gruppe auflisten {#list-permissions-group}

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

Gibt zurück, `400 Bad Request` wenn die Gruppe nicht verfügbar ist.

## Berechtigungen für eine Gruppe festlegen {#set-permissions-group}

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

Gibt zurück, `200 OK` wenn erfolgreich. Gibt zurück, `400` wenn eine angegebene Berechtigung ungültig ist. Kann auch zurückgegeben `403` werden, wenn das Objekt vom angemeldeten Benutzer nicht zugänglich ist.
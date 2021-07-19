---
description: REST-API-Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.
seo-description: REST-API-Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.
seo-title: API-Methoden für die Gruppenverwaltung
solution: Audience Manager
title: API-Methoden für die Gruppenverwaltung
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 13%

---

# API-Methoden für die Gruppenverwaltung {#group-management-api-methods}

REST [!DNL API]-Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.

<!-- c_rest_api_user_man_group.xml -->

## Eine Gruppe erstellen {#create-group}

Eine `POST`-Methode zum Erstellen einer neuen Benutzergruppe.

<!-- r_rest_api_group_create.xml -->

### Anfrage

`POST /api/v1/groups/`

### Beispielanfragetext

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

## Gruppe aktualisieren {#update-group}

Eine `PUT`-Methode zum Aktualisieren einer Benutzergruppe.

<!--
r_rest_api_group_update.xml
-->

### Anfrage

`PUT /api/v1/groups/`*`<groupId>`*

### Beispielanfragetext

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

## Listen-Gruppen {#list-groups}

Eine `GET`-Methode zur Auflistung von Benutzergruppen.

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

Eine `DELETE`-Methode zum Löschen einer Benutzergruppe und zum Entfernen aller Mitglieder aus dieser Gruppe.

<!-- r_rest_api_group_delete.xml -->

### Anfrage

`DELETE /api/v1/groups/`*`<groupId>`*

Gibt `204 No Content` zurück, falls erfolgreich. Im Falle eines Konflikts wird `409 Conflict` zurückgegeben.

## Massenlöschung von Gruppen {#delete-groups-bulk}

Eine `DELETE`-Methode zum Löschen mehrerer Gruppen in großen Mengen und zum Entfernen aller Mitglieder aus dieser Gruppe.

<!-- r_rest_api_group_delete_bulk.xml -->

### Anfrage

`DELETE /api/v1/groups/bulk-delete`

Gibt `204 No Content` zurück, falls erfolgreich. Im Falle eines Konflikts wird `409 Conflict` zurückgegeben.

## Alle Berechtigungen für eine Gruppe auflisten {#list-permissions-group}

Eine `GET`-Methode zum Auflisten der Berechtigungsobjekte einer Gruppe.

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

Gibt `400 Bad Request` zurück, wenn auf die Gruppe nicht zugegriffen werden kann.

## Festlegen von Berechtigungen für eine Gruppe {#set-permissions-group}

Eine `PUT`-Methode zum Aktualisieren von Gruppenberechtigungen. Diese Methode überschreibt die alten Berechtigungen mit den neuen Berechtigungen.

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

Gibt `200 OK` zurück, falls erfolgreich. Gibt `400` zurück, wenn eine gegebene Berechtigung ungültig ist. Kann auch `403` zurückgeben, wenn der angemeldete Benutzer nicht auf das Objekt zugreifen kann.

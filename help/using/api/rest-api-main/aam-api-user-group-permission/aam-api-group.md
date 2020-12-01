---
description: REST-API-Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.
seo-description: REST-API-Methoden zum Verwalten von Gruppen, einschließlich Erstellen, Aktualisieren, Auflisten und Löschen von Gruppen.
seo-title: API-Methoden für die Gruppenverwaltung
solution: Audience Manager
title: API-Methoden für die Gruppenverwaltung
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '222'
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

## Eine Gruppe {#update-group} aktualisieren

Eine `PUT`-Methode zum Aktualisieren einer Benutzergruppe.

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

## Listen-Gruppen {#list-groups}

Eine `GET`-Methode zur Liste von Benutzergruppen.

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

Eine `DELETE`-Methode, um eine Benutzergruppe zu löschen und alle Mitglieder aus dieser Gruppe zu entfernen.

<!-- r_rest_api_group_delete.xml -->

### Anfrage

`DELETE /api/v1/groups/`*`<groupId>`*

Gibt `204 No Content` zurück, wenn erfolgreich. Im Falle eines Konflikts gibt `409 Conflict` zurück.

## Gruppen stapelweise löschen {#delete-groups-bulk}

Eine `DELETE`-Methode, um mehrere Gruppen stapelweise zu löschen und alle Mitglieder aus dieser Gruppe zu entfernen.

<!-- r_rest_api_group_delete_bulk.xml -->

### Anfrage

`DELETE /api/v1/groups/bulk-delete`

Gibt `204 No Content` zurück, wenn erfolgreich. Im Falle eines Konflikts gibt `409 Conflict` zurück.

## Liste aller Berechtigungen für eine Gruppe {#list-permissions-group}

Eine `GET`-Methode zur Liste der Berechtigungsobjekte in einer Gruppe.

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

## Berechtigungen für eine Gruppe {#set-permissions-group} festlegen

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

Die Beispielantwort stellt die aktualisierte Liste von Berechtigungsobjekten dar.

Gibt `200 OK` zurück, wenn erfolgreich. Gibt `400` zurück, wenn eine angegebene Berechtigung ungültig ist. Kann auch `403` zurückgeben, wenn der angemeldete Benutzer nicht auf das Objekt zugreifen kann.
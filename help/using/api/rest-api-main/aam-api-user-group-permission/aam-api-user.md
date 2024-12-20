---
description: REST-API-Methoden zum Verwalten von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: User Management-API-Methoden
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 1%

---

# User Management-API-Methoden {#user-management-api-methods}

REST [!DNL API] Methoden zum Verwalten von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.

<!-- c_rest_api_user_man_user.xml -->

## Benutzer erstellen {#create-user}

Eine `POST` Methode zum Erstellen eines neuen Benutzers.

<!-- r_rest_api_user_create.xml -->

### Anfrage

`POST /api/v1/users/`

### Beispiel-Anfrageinhalt

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### Antwort

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

Wenn `isAdmin` auf „true“ gesetzt ist, wird der Benutzer als Partner-Admin erstellt. Diese Eigenschaft informiert Sie auch darüber, ob ein Benutzer ein Partneradministrator ist.

Gibt `409 Conflict` zurück, wenn der Benutzername bereits verwendet wird.

## Aktualisieren von Benutzern {#update-user}

Eine `PUT` Methode zum Aktualisieren eines Benutzers.

<!-- r_rest_api_user_update.xml -->

### Anfrage

`PUT /api/v1/users/`*`<userId>`*

### Beispiel-Anfrageinhalt

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### Antwort

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

Gibt `409 Conflict` zurück, wenn der Benutzername bereits verwendet wird.

## Angemeldeter Benutzer aktualisieren {#update-logged-in-user}

Eine `PUT` Methode zum Aktualisieren des aktuell angemeldeten Benutzers.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode nur von Benutzern ohne Administratorrechte aufrufbar.

### Anfrage

`PUT /self/update`

### Beispiel-Anfrageinhalt

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### Antwort

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

Gibt `409 Conflict` zurück, wenn der Benutzername bereits verwendet wird.

## Aktualisieren des angemeldeten Benutzerkennworts {#update-logged-in-user-pw}

Eine `PUT` Methode zum Aktualisieren des aktuell angemeldeten Benutzers.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode nur von Benutzern ohne Administratorrechte aufrufbar.

### Anfrage

`POST /users/self/update-password`

### Beispiel-Anfrageinhalt

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Gibt bei Erfolg `200 OK` zurück. Gibt `400 Bad Request` zurück, wenn mit einem der Kennwörter etwas nicht stimmt.

## Angemeldetes Benutzerkennwort zurücksetzen {#reset-logged-in-user-pw}

Eine `PUT` Methode zum Zurücksetzen des aktuell angemeldeten Benutzers. [!UICONTROL Audience Management] sendet dem Benutzer ein systemgeneriertes Kennwort.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode nur von Benutzern ohne Administratorrechte aufrufbar.

### Anfrage

`POST /self/reset-password`

Gibt bei Erfolg `200 OK` zurück.

## Ausgabe des Benutzerobjekts für eine Benutzer-ID {#return-user-object-for-id}

Eine `Get` Methode, um das Benutzerobjekt für eine Benutzer-ID zurückzugeben.

<!-- r_rest_api_user_get_user_obj.xml -->

### Anfrage

`GET /api/v1/users/`*`<userId>`*

### Antwort

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Rückgabe des Benutzerobjekts für angemeldeten Benutzer {#return-user-object-for-logged-in-user}

Eine `Get` Methode, um das Benutzerobjekt für den aktuell angemeldeten Benutzer zurückzugeben.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode nur von Benutzern ohne Administratorrechte aufrufbar.

### Anfrage

`GET /api/v1/users/self`

### Antwort

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Benutzer auflisten {#list-users}

Eine `GET` Methode zum Auflisten von Benutzern.

<!-- r_rest_api_user_list.xml -->

### Anfrage

`GET /api/v1/users/`

Sie können in den Abfrageparametern mehrere Gruppen-IDs angeben:

`GET /api/v1/users/?groupId=343&groupdId=12`

Diese Abfrage gibt eine Liste aller Benutzer in den angegebenen Gruppen zurück.

### Antwort

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## Löschen von Benutzern {#delete-users}

Eine `DELETE` Methode zum Löschen eines Benutzers.

<!-- r_rest_api_user_delete.xml -->

### Anfrage

`DELETE /api/v1/users/`*`<user_id>`*

Gibt bei Erfolg `204 No Content` zurück. Im Konfliktfall gibt `409 Conflict` zurück.

## Benutzer stapelweise löschen {#delete-users-bulk}

Eine `POST` Methode zum Massenlöschen mehrerer Benutzer.

<!-- r_rest_api_user_delete_bulk.xml -->

### Anfrage

`POST /api/v1/users/bulk-delete`

### Beispiel-Anfrageinhalt

```
{[<user_id_1>, <user_id_2>, ...]}
```

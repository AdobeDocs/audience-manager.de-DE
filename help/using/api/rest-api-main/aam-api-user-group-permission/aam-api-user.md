---
description: REST-API-Methoden zur Verwaltung von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.
seo-description: REST-API-Methoden zur Verwaltung von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.
seo-title: API-Methoden für Benutzerverwaltung
solution: Audience Manager
title: API-Methoden für Benutzerverwaltung
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API-Methoden für Benutzerverwaltung {#user-management-api-methods}

Verwenden Sie keine [!DNL API] Methoden zum Verwalten von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.

<!-- c_rest_api_user_man_user.xml -->

## Create a User {#create-user}

Eine `POST` Methode zum Erstellen eines neuen Benutzers.

<!-- r_rest_api_user_create.xml -->

### Anfrage

`POST /api/v1/users/`

### Stichprobenanforderungskörper

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

Wenn "true" `isAdmin` festgelegt ist, wird der Benutzer als Partner-Administrator erstellt. Diese Eigenschaft informiert Sie auch darüber, ob ein Benutzer ein Partner-Administrator ist.

Gibt zurück, `409 Conflict` wenn der Benutzername bereits verwendet wurde.

## Benutzer aktualisieren {#update-user}

Eine `PUT` Methode zum Aktualisieren eines Benutzers.

<!-- r_rest_api_user_update.xml -->

### Anfrage

`PUT /api/v1/users/`*`<userId>`*

### Stichprobenanforderungskörper

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

Gibt zurück, `409 Conflict` wenn der Benutzername bereits verwendet wurde.

## Anmeldenamen Benutzer aktualisieren {#update-logged-in-user}

Eine `PUT` Methode zum Aktualisieren des derzeit angemeldeten Benutzers.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Benutzern ohne Administratorrechte aufgerufen werden können.

### Anfrage

`PUT /self/update`

### Stichprobenanforderungskörper

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

Gibt zurück, `409 Conflict` wenn der Benutzername bereits verwendet wurde.

## Kennwort des angemeldeten Benutzers aktualisieren {#update-logged-in-user-pw}

Eine `PUT` Methode zum Aktualisieren des derzeit angemeldeten Benutzers.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Benutzern ohne Administratorrechte aufgerufen werden können.

### Anfrage

`POST /users/self/update-password`

### Stichprobenanforderungskörper

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Gibt `200 OK` bei erfolgreicher Ausführung zurück. Gibt zurück, `400 Bad Request` wenn mit einem der beiden Kennwörter etwas nicht stimmt.

## Passwort des angemeldeten Benutzers zurücksetzen {#reset-logged-in-user-pw}

Eine `PUT` Methode zum Zurücksetzen des derzeit angemeldeten Benutzers. [!UICONTROL Audience Management] sendet dem Benutzer ein vom System generiertes Kennwort.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Benutzern ohne Administratorrechte aufgerufen werden können.

### Anfrage

`POST /self/reset-password`

Gibt `200 OK` bei erfolgreicher Ausführung zurück.

## Rückgabe eines Benutzerobjekts für eine Benutzer-ID {#return-user-object-for-id}

Eine `Get` Methode zur Rückgabe des Benutzerobjekts für eine Benutzer-ID.

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

## Rückgabebenutzerobjekt für angemeldeten Benutzer {#return-user-object-for-logged-in-user}

Eine `Get` Methode zur Rückgabe des Benutzerobjekts für den derzeit angemeldeten Benutzer.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Benutzern ohne Administratorrechte aufgerufen werden können.

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

Sie können mehrere Gruppen-IDs in den Abfrageparametern angeben:

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

## Delete a User {#delete-users}

Eine `DELETE` Methode zum Löschen eines Benutzers.

<!-- r_rest_api_user_delete.xml -->

### Anfrage

`DELETE /api/v1/users/`*`<user_id>`*

Gibt `204 No Content` bei erfolgreicher Ausführung zurück. Im Falle eines Konflikts gibt es `409 Conflict`.

## Benutzer stapelweise löschen {#delete-users-bulk}

Eine `POST` Methode zum Massenlöschen mehrerer Benutzer.

<!-- r_rest_api_user_delete_bulk.xml -->

### Anfrage

`POST /api/v1/users/bulk-delete`

### Stichprobenanforderungskörper

```
{[<user_id_1>, <user_id_2>, ...]}
```

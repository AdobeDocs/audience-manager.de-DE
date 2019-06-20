---
description: REST-API-Methoden zur Verwaltung von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.
seo-description: REST-API-Methoden zur Verwaltung von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.
seo-title: User Management-API-Methoden
solution: Audience Manager
title: User Management-API-Methoden
uuid: 6 e 1 f 2 c 35-bb 9 d -4166-b 7 d 4-d 9 c 5518 a 61 ad
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# User Management-API-Methoden {#user-management-api-methods}

Rest [!DNL API] -Methoden zur Verwaltung von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.

<!-- c_rest_api_user_man_user.xml -->

## Einen Benutzer erstellen {#create-user}

`POST` Eine Methode zum Erstellen eines neuen Benutzers.

<!-- r_rest_api_user_create.xml -->

### Anfrage

`POST /api/v1/users/`

### Beispielanforderungskörper

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

Wenn `isAdmin` &quot;true&quot; festgelegt ist, wird der Benutzer als Partner-Administrator erstellt. Mit dieser Eigenschaft können Sie auch erkennen, ob ein Benutzer ein Partner-Administrator ist.

Gibt zurück, `409 Conflict` wenn der Benutzername bereits erfolgt ist.

## Einen Benutzer aktualisieren {#update-user}

`PUT` Eine Methode zum Aktualisieren eines Benutzers.

<!-- r_rest_api_user_update.xml -->

### Anfrage

`PUT /api/v1/users/`*`<userId>`*

### Beispielanforderungskörper

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

Gibt zurück, `409 Conflict` wenn der Benutzername bereits erfolgt ist.

## Angemeldete Benutzer aktualisieren {#update-logged-in-user}

`PUT` Eine Methode zum Aktualisieren des derzeit angemeldeten Benutzers.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, kann diese Methode von Nichtadministratoren aufgerufen werden.

### Anfrage

`PUT /self/update`

### Beispielanforderungskörper

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

Gibt zurück, `409 Conflict` wenn der Benutzername bereits erfolgt ist.

## Angemeldete Benutzerkennwort aktualisieren {#update-logged-in-user-pw}

`PUT` Eine Methode zum Aktualisieren des derzeit angemeldeten Benutzers.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, kann diese Methode von Nichtadministratoren aufgerufen werden.

### Anfrage

`POST /users/self/update-password`

### Beispielanforderungskörper

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Gibt zurück, `200 OK` wenn erfolgreich. Gibt zurück `400 Bad Request` , wenn bei einem Kennwort etwas falsch ist.

## Angemeldete Benutzerkennwort zurücksetzen {#reset-logged-in-user-pw}

`PUT` Eine Methode zum Zurücksetzen des derzeit angemeldeten Benutzers. [!UICONTROL Audience Management] dem Benutzer ein vom System generiertes Kennwort senden.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, kann diese Methode von Nichtadministratoren aufgerufen werden.

### Anfrage

`POST /self/reset-password`

Gibt zurück, `200 OK` wenn erfolgreich.

## Zurückkehrendes Benutzerobjekt für eine Benutzer-ID {#return-user-object-for-id}

`Get` Eine Methode zum Zurückgeben des Benutzerobjekts für eine Benutzer-ID.

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

## Zurückkehrendes Benutzerobjekt für angemeldete Benutzer {#return-user-object-for-logged-in-user}

`Get` Eine Methode zum Zurückgeben des Benutzerobjekts für den derzeit angemeldeten Benutzer.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API] Methoden nur von Partneradministratoren aufgerufen werden können, kann diese Methode von Nichtadministratoren aufgerufen werden.

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

## Listenbenutzer {#list-users}

Eine `GET` Methode für Benutzer.

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

## Benutzer löschen {#delete-users}

`DELETE` Eine Methode zum Löschen eines Benutzers.

<!-- r_rest_api_user_delete.xml -->

### Anfrage

`DELETE /api/v1/users/`*`<user_id>`*

Gibt zurück, `204 No Content` wenn erfolgreich. Bei Konflikten zurückgegeben `409 Conflict`.

## Benutzer stapelweise löschen {#delete-users-bulk}

`POST` Eine Methode zum Stapellöschen mehrerer Benutzer.

<!-- r_rest_api_user_delete_bulk.xml -->

### Anfrage

`POST /api/v1/users/bulk-delete`

### Beispielanforderungskörper

```
{[<user_id_1>, <user_id_2>, ...]}
```

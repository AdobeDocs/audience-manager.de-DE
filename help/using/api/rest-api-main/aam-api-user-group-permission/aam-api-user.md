---
description: REST-API-Methoden zum Verwalten von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.
seo-description: REST-API-Methoden zum Verwalten von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.
seo-title: API-Methoden für die Benutzerverwaltung
solution: Audience Manager
title: API-Methoden für die Benutzerverwaltung
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 7%

---

# API-Methoden für die Benutzerverwaltung {#user-management-api-methods}

REST [!DNL API]-Methoden zum Verwalten von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.

<!-- c_rest_api_user_man_user.xml -->

## Erstellen eines Benutzers {#create-user}

Eine `POST`-Methode zum Erstellen eines neuen Benutzers.

<!-- r_rest_api_user_create.xml -->

### Anfrage

`POST /api/v1/users/`

### Beispielanfragetext

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

Wenn `isAdmin` auf &quot;true&quot;gesetzt ist, wird der Benutzer als Partner-Administrator erstellt. Diese Eigenschaft informiert Sie auch darüber, ob ein Benutzer Partneradministrator ist.

Gibt `409 Conflict` zurück, wenn der Benutzername bereits verwendet wurde.

## Aktualisieren eines Benutzers {#update-user}

Eine `PUT`-Methode zum Aktualisieren eines Benutzers.

<!-- r_rest_api_user_update.xml -->

### Anfrage

`PUT /api/v1/users/`*`<userId>`*

### Beispielanfragetext

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

Gibt `409 Conflict` zurück, wenn der Benutzername bereits verwendet wurde.

## Aktualisierter angemeldeter Benutzer {#update-logged-in-user}

Eine `PUT` -Methode zum Aktualisieren des aktuell angemeldeten Benutzers.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API]-Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Benutzern ohne Administratorrechte abrufbar.

### Anfrage

`PUT /self/update`

### Beispielanfragetext

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

Gibt `409 Conflict` zurück, wenn der Benutzername bereits verwendet wurde.

## Aktualisieren des angemeldeten Benutzerkennworts {#update-logged-in-user-pw}

Eine `PUT` -Methode zum Aktualisieren des aktuell angemeldeten Benutzers.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API]-Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Benutzern ohne Administratorrechte abrufbar.

### Anfrage

`POST /users/self/update-password`

### Beispielanfragetext

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Gibt `200 OK` zurück, falls erfolgreich. Gibt `400 Bad Request` zurück, wenn bei beiden Passwörtern etwas nicht stimmt.

## Zurücksetzen des angemeldeten Benutzerkennworts {#reset-logged-in-user-pw}

Eine `PUT` -Methode zum Zurücksetzen des derzeit angemeldeten Benutzers. [!UICONTROL Audience Management] sendet dem Benutzer ein systemgeneriertes Kennwort.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API]-Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Benutzern ohne Administratorrechte abrufbar.

### Anfrage

`POST /self/reset-password`

Gibt `200 OK` zurück, falls erfolgreich.

## Zurückgeben eines Benutzerobjekts für eine Benutzer-ID {#return-user-object-for-id}

Eine `Get` -Methode, mit der das Benutzerobjekt für eine Benutzer-ID zurückgegeben wird.

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

## Zurückgeben des Benutzerobjekts für angemeldeten Benutzer {#return-user-object-for-logged-in-user}

Eine `Get` -Methode, um das Benutzerobjekt für den derzeit angemeldeten Benutzer zurückzugeben.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API]-Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Benutzern ohne Administratorrechte abrufbar.

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

Eine `GET`-Methode zur Auflistung von Benutzern.

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

## Löschen eines Benutzers {#delete-users}

Eine `DELETE`-Methode zum Löschen eines Benutzers.

<!-- r_rest_api_user_delete.xml -->

### Anfrage

`DELETE /api/v1/users/`*`<user_id>`*

Gibt `204 No Content` zurück, falls erfolgreich. Im Falle eines Konflikts wird `409 Conflict` zurückgegeben.

## Benutzer stapelweise löschen {#delete-users-bulk}

Eine `POST`-Methode zum Löschen mehrerer Benutzer in großen Mengen.

<!-- r_rest_api_user_delete_bulk.xml -->

### Anfrage

`POST /api/v1/users/bulk-delete`

### Beispielanfragetext

```
{[<user_id_1>, <user_id_2>, ...]}
```

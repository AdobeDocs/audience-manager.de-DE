---
description: REST-API-Methoden zur Verwaltung von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.
seo-description: REST-API-Methoden zur Verwaltung von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.
seo-title: API-Methoden für die Benutzerverwaltung
solution: Audience Manager
title: API-Methoden für die Benutzerverwaltung
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 7%

---


# API-Methoden für die Benutzerverwaltung {#user-management-api-methods}

REST [!DNL API]-Methoden zur Verwaltung von Benutzern, einschließlich Erstellen, Aktualisieren, Auflisten, Löschen und Zurückgeben von Benutzerobjekten.

<!-- c_rest_api_user_man_user.xml -->

## Einen Benutzer {#create-user} erstellen

Eine `POST`-Methode zum Erstellen eines neuen Benutzers.

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

Wenn `isAdmin` auf &quot;true&quot;gesetzt ist, wird der Benutzer als Partner-Administrator erstellt. Diese Eigenschaft informiert Sie auch darüber, ob ein Benutzer ein Partner-Administrator ist.

Gibt `409 Conflict` zurück, wenn der Benutzername bereits verwendet wurde.

## Aktualisieren eines Benutzers {#update-user}

Eine `PUT`-Methode zum Aktualisieren eines Benutzers.

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

Gibt `409 Conflict` zurück, wenn der Benutzername bereits verwendet wurde.

## Anmeldenamen Benutzer aktualisieren {#update-logged-in-user}

Eine `PUT`-Methode zum Aktualisieren des derzeit angemeldeten Benutzers.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API]-Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Nicht-Admin-Benutzern aufgerufen werden können.

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

Gibt `409 Conflict` zurück, wenn der Benutzername bereits verwendet wurde.

## Kennwort für angemeldete Benutzer aktualisieren {#update-logged-in-user-pw}

Eine `PUT`-Methode zum Aktualisieren des derzeit angemeldeten Benutzers.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API]-Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Nicht-Admin-Benutzern aufgerufen werden können.

### Anfrage

`POST /users/self/update-password`

### Stichprobenanforderungskörper

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Gibt `200 OK` zurück, wenn erfolgreich. Gibt `400 Bad Request` zurück, wenn bei einem der beiden Kennwörter etwas nicht stimmt.

## Zurücksetzen des angemeldeten Benutzerkennworts {#reset-logged-in-user-pw}

Eine `PUT`-Methode zum Zurücksetzen des derzeit angemeldeten Benutzers. [!UICONTROL Audience Management] sendet dem Benutzer ein vom System generiertes Kennwort.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API]-Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Nicht-Admin-Benutzern aufgerufen werden können.

### Anfrage

`POST /self/reset-password`

Gibt `200 OK` zurück, wenn erfolgreich.

## Rückgabe eines Benutzerobjekts für eine Benutzer-ID {#return-user-object-for-id}

Eine `Get`-Methode, um das Benutzerobjekt für eine Benutzer-ID zurückzugeben.

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

Eine `Get`-Methode, um das Benutzerobjekt für den derzeit angemeldeten Benutzer zurückzugeben.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Während die meisten [!DNL API]-Methoden nur von Partneradministratoren aufgerufen werden können, ist diese Methode von Nicht-Admin-Benutzern aufgerufen werden können.

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

## Liste-Benutzer {#list-users}

Eine `GET`-Methode zur Liste von Benutzern.

<!-- r_rest_api_user_list.xml -->

### Anfrage

`GET /api/v1/users/`

Sie können mehrere Gruppen-IDs in den Parametern für die Abfrage angeben:

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

Gibt `204 No Content` zurück, wenn erfolgreich. Im Falle eines Konflikts gibt `409 Conflict` zurück.

## Benutzer stapelweise löschen {#delete-users-bulk}

Eine `POST`-Methode, um mehrere Benutzer stapelweise zu löschen.

<!-- r_rest_api_user_delete_bulk.xml -->

### Anfrage

`POST /api/v1/users/bulk-delete`

### Stichprobenanforderungskörper

```
{[<user_id_1>, <user_id_2>, ...]}
```

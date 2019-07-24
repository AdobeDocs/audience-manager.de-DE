---
description: Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderungs-urls und anderen Referenzen.
seo-description: Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderungs-urls und anderen Referenzen.
seo-title: Erste Schritte mit REST-apis
solution: Audience Manager
title: Erste Schritte mit REST-apis
uuid: af 0 e 527 e -6 eec -449 c -9709-f 90 e 57 cd 188 d
translation-type: tm+mt
source-git-commit: 27800ce003a62733eece0d5de3b94737ed61133a

---


# Getting Started with REST APIs {#getting-started-with-rest-apis}

Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderungs-urls und anderen Referenzen.

<!-- c_rest_api_overview.xml -->

## API Requirements and Recommendations {#api-requirements-recommendations}

Things you must and should do when working with the Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

Note the following when working with [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **Anforderungsparameter:** Alle Anforderungsparameter sind erforderlich, falls nicht anders angegeben.
* **[!DNL JSON]Inhaltstyp:** Geben Sie an `content-type: application/json`*und* `accept: application/json` in Ihrem Code.

* **Anforderungen und Antworten:** Senden Sie Anforderungen als ein ordnungsgemäß formatiertes [!DNL JSON] Objekt. [!DNL Audience Manager] mit [!DNL JSON] formatierten Daten beantwortet. Serverantworten können angeforderte Daten, einen Status-Code oder beides enthalten.

* **Zugriff:** Ihr [!DNL Audience Manager] Berater stellt Ihnen eine Client-ID und einen Schlüssel zur Verfügung, mit dem Sie Anforderungen erstellen [!DNL API] können.

* **Dokumentation und Codebeispiele:** *Kursiv gedruckter Text* stellt eine Variable dar, die Sie beim Erstellen oder Empfangen [!DNL API] von Daten bereitstellen oder weitergeben. Replace *italicised* text with your own code, parameters, or other required information.

## Recommendations: Create a Generic API User {#requirements}

We recommend you create a separate, technical user account for working with the Audience Manager [!DNL API]s. This is a generic account that is not tied to or associated with a specific user in your organization. This type of [!DNL API] user account helps you accomplish 2 things:

* Identify what service is calling the [!DNL API] (e.g., calls from your apps that use our [!DNL API]s or from other tools that make [!DNL API] requests).
* Provide uninterrupted access to the [!DNL API]s. An account tied to a specific person may be deleted when they leave your company. This will prevent you from working with the available [!DNL API] code. Ein generisches Konto, das nicht an einen bestimmten Mitarbeiter gebunden ist, hilft Ihnen dabei, dieses Problem zu vermeiden.

As an example or use case for this type of account, let's say you want to change a lot of segments at once with the [Bulk Management Tools](../../reference/bulk-management-tools/bulk-management-intro.md). Well, to do this, your user account needs [!DNL API] access. Rather than add permissions to a specific user, create a non-specific, [!DNL API] user account that has the appropriate credentials, key, and secret to make [!DNL API] calls. This is also useful if you develop your own applications that use the Audience Manager [!DNL API]s.

Work with your Audience Manager consultant to set up a generic, [!DNL API]-only user account.

## OAuth Authentication {#oauth}

The Audience Manager [!UICONTROL REST API] follows [!DNL OAuth 2.0] standards for token authentication and renewal. The sections below describe how to authenticate and start working with the [!DNL API]s.

## Password Authentication Workflow {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Password authentication secure access our [!DNL REST API]. The steps below outline the workflow for password authentication from a [!DNL JSON] client in your browser.

>[!TIP]
>
>Verschlüsseln Sie den Zugriff und aktualisieren Sie Token, wenn Sie sie in einer Datenbank speichern.

### Schritt 1: API-Zugriff anfordern

Wenden Sie sich an Ihren Partner Solutions Manager. They will provide you with an [!DNL API] client ID and secret. The ID and secret authenticate you to the [!DNL API].

Note: If you'd like to receive a refresh token, specify that when you request [!DNL API] access.

### Schritt 2: Token anfordern

Pass in a token request with your preferred [!DNL JSON] client. Wenn Sie die Anforderung erstellen:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und den geheimen Schlüssel in eine base -64-kodierte Zeichenfolge. Trennen Sie die ID und den geheimen Schlüssel durch einen Doppelpunkt während des Konvertierungsprozesses. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the [!DNL HTTP] headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded` . For example, your header could look like this: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Richten Sie den Anforderungstext wie folgt ein:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Schritt 3: Empfangen des Tokens

The [!DNL JSON] response contains your access token. Die Antwort sollte wie folgt aussehen:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

The `expires_in` key represents the number of seconds until the access token expires. Es empfiehlt sich, eine kurze Ablaufzeit zu verwenden, um die Exposition einzuschränken, wenn das Token jemals offen gelegt wird.

## Refresh Token {#refresh-token}

Refresh tokens renew [!DNL API] access after the original token expires. If requested, the response [!DNL JSON] in the password workflow includes a refresh token. Wenn Sie kein Aktualisierungstoken erhalten, erstellen Sie über den Kennwortauthentifizierungsprozess eine neue.

Sie können ein Aktualisierungstoken auch verwenden, um ein neues Token zu generieren, bevor das vorhandene Zugriffstoken abläuft.

If your access token has expired, you receive a `401 Status Code` and the following header in the response:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

The following steps outline the workflow for using a refresh token to create a new access token from a [!DNL JSON] client in your browser.

### Schritt 1: Neues Token anfordern

Pass in a refresh token request with your preferred [!DNL JSON] client. Wenn Sie die Anforderung erstellen:

* Use a `POST` method to call `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und den geheimen Schlüssel in eine base -64-kodierte Zeichenfolge. Trennen Sie die ID und den geheimen Schlüssel durch einen Doppelpunkt während des Konvertierungsprozesses. For example, the credentials `testId : testSecret` convert to `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Pass in the HTTP headers `Authorization:Basic <base-64 clientID:clientSecret>` and `Content-Type: application/x-www-form-urlencoded`. For example, your header could look like this: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* In the request body, specify the `grant_type:refresh_token` and pass in the refresh token you received in your previous access request. The request should look like this: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Schritt 2: Empfangen des neuen Token

The [!DNL JSON] response contains your new access token. Die Antwort sollte wie folgt aussehen:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

## Authorization Code and Implicit Authentication {#authentication-code-implicit}

The Audience Manager [!UICONTROL REST API] supports authorization code and implicit authentication. To use these access methods, your users need to log in to `https://api.demdex.com/oauth/authorize` to get access and refresh tokens.

>[!MORE_ LIKE_ THIS]
>
>* [Oauth 2.0](https://oauth.net/2/)
>* [Oauth 2 vereinfacht](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Make Authenticated API Requests {#authenticated-api-requests}

Requirements for calling [!DNL API] methods after you receive an authentication token.

<!-- c_oauth_call_methods.xml -->

To make calls against the available [!DNL API] methods:

* In the `HTTP` header, set `Authorization: Bearer <token>`.
* Call the required [!DNL API] method.

>[!MORE_ LIKE_ THIS]
>
>* [Oauth-Authentifizierung](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optional API Query Parameters {#optional-api-query-parameters}

Legen Sie die optionalen Parameter fest, die für Methoden verfügbar sind, die alle Eigenschaften für ein Objekt zurückgeben.

<!-- c_rest_api_optional.xml -->

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API].

| Parameter | Beschreibung |
|--- |--- |
| Seite | Gibt Ergebnisse nach Seitenzahl zurück. Nummerierung beginnt bei 0. |
| Pagesize | Legt die Anzahl der von der Anforderung zurückgegebenen Antwortergebnisse fest (Standard: 10). |
| Sortby | Sorts and returns results according to the specified [!DNL JSON] property. |
| absteigend | Sortiert die Ergebnisse in absteigender Reihenfolge und gibt sie zurück. Aufsteigend ist die Standardeinstellung. |
| Suche | Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle mit dem Wort "Test" in allen Wertfeldern für dieses Element suchen. Your sample request could look like this:   `GET https://api.demdex.com/v1/models/?search=Test`.  Sie können nach jedem Wert suchen, der von einer "get all" -Methode zurückgegeben wird. |
| Folderid | Gibt alle IDs für Eigenschaften innerhalb des angegebenen Ordners zurück. Nicht für alle Methoden verfügbar. |
| Berechtigungen | Gibt eine Liste von Segmenten basierend auf der angegebenen Berechtigung zurück. READ ist Default. Zu den Berechtigungen gehören:<ul><li>`READ` : Geben Sie Informationen zu einem Segment zurück und zeigen Sie Informationen an.</li><li>`WRITE` : Dient `PUT` zum Aktualisieren eines Segments.</li><li>`CREATE` : Zum `POST` Erstellen eines Segments.</li><li>`DELETE` : Segmente löschen. Benötigt Zugriff auf die zugrunde liegenden Eigenschaften, falls vorhanden. Sie benötigen zum Beispiel Rechte zum Löschen der Eigenschaften, die zu einem Segment gehören, wenn Sie sie entfernen möchten.</li></ul><br>Geben Sie mehrere Berechtigungen für separate Schlüssel-Wert-Paare an. For example, to return a list of segments with  `READ`  and  `WRITE`  permissions only, pass in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| Includepermissions | (Boolescher Wert) Auf "true" setzen, um die Berechtigungen für das Segment zurückzugeben. Standard ist „false“. |

### Hinweis zu Seitenoptionen

When page information *is not* specified, the request returns plain [!DNL JSON] results in an array. If page information *is* specified, then the returned list is wrapped in a [!DNL JSON] object that contains information about the total result and current page. Ihre Beispielanforderung mithilfe der Seitenoptionen könnte wie folgt aussehen:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API-URLs {#api-urls}

[!DNL URLs] für Anforderungen, Staging- und Produktionsumgebungen und Versionen.

<!-- r_rest_urls.xml -->

## Request URLs {#request-urls}

The following table lists the request URLs used to pass in [!DNL API] requests, by method.

| [!DNL API] Methoden | Anfrage [!DNL URL] |
|--- |--- |
| Algorithmische Modellierung | `https://api.demdex.com/v1/models/` |
| Datenquelle | `https://api.demdex.com/v1/datasources/` |
| Abgeleitete Signale | `https://api.demdex.com/v1/signals/derived/` |
| Ziele | `https://api.demdex.com/v1/destinations/` |
| Domänen | `https://api.demdex.com/v1/partner-sites/` |
| Ordner | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segments:  `https://api.demdex.com/v1/folders/segments /` |
| Schema | `https://api.demdex.com/v1/schemas/` |
| Segmente | `https://api.demdex.com/v1/segments/` |
| Eigenschaften | `https://api.demdex.com/v1/traits/` |
| Trait-Typen | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomy | `https://api.demdex.com/v1/taxonomies/0/` |

## Environments {#environments}

The [!DNL Audience Manager] [!DNL API]s provide access to different working environments. Diese Umgebungen helfen Ihnen, Code für separate Datenbanken zu testen, ohne dass sich dies auf die Live-Produktionsdaten auswirkt. The following table lists the available [!DNL API] environments and corresponding resource hostnames.

| Umgebung | Hostname |
|---|---|
| **Produktion** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Die Beta-Umgebung von Audience Manager ist eine eigenständige, eigenständige Version der Produktionsumgebung. Alle Daten, die Sie testen möchten, müssen in dieser Umgebung eingegeben und erfasst werden.

## Versionen {#versions}

New versions of these [!DNL API]s are released on a regular schedule. A new release increments the [!DNL API] version number. The version number is referenced in the request URL as `v<version number>` as shown in the following example:

`https://<host>/v1/...`

## Response Codes Defined {#response-codes-defined}

`HTTP` Statuscodes und Antworttext, der vom Audience Manager zurückgegeben [!UICONTROL REST API]wird.

<!-- r_api_http_response_codes.xml -->

| Antwortcode-ID | Antworttext | Definition |
|---|---|---|
| 200 |  OK- | Die Anforderung wurde erfolgreich verarbeitet. Gibt bei Bedarf erwartete Inhalte oder Daten zurück. |
| 201 | Erstellt | Die Ressource wurde erstellt. Returns for `PUT` and `POST` requests. |
| 204 | Kein Inhalt | Die Ressource wurde gelöscht. Der Antwortkörper ist leer. |
| 400 | Unzulässige Anfrage | Der Server hat die Anforderung nicht verstanden. Normalerweise aufgrund einer falsch formatierten Syntax. Überprüfen Sie Ihre Anforderung und versuchen Sie es erneut. |
| 403 | Forbidden | Sie haben keinen Zugriff auf die Ressource. |
| 404 | nicht gefunden | Die Ressource konnte für den angegebenen Pfad nicht gefunden werden. |
| 409 | Konflikt | Die Anfrage konnte aufgrund eines Konflikts mit dem Status der Ressource nicht abgeschlossen werden. |
| 500 | Serverfehler | Der Server hat einen unerwarteten Fehler festgestellt, der die Erfüllung der Anforderung verhinderte. |
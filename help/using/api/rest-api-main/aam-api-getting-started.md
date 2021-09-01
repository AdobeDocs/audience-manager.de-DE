---
description: Informationen zu allgemeinen Anforderungen, Authentifizierungen, optionalen Parametern für die Abfrage, Anforderungs-URLs und anderen Verweisen.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Erste Schritte mit REST-APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 95182160b37bb15df4867bbacd06d8d75c971fa3
workflow-type: tm+mt
source-wordcount: '1942'
ht-degree: 3%

---

# Erste Schritte mit [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderung [!DNL URLs] und anderen Verweisen.

<!-- c_rest_api_overview.xml -->

## API-Anforderungen und -Empfehlungen {#api-requirements-recommendations}

Was Sie tun müssen und sollten, wenn Sie mit [!DNL Audience Manager] [!DNL API]s arbeiten.

<!-- aam-api-requirements.xml -->

Beachten Sie Folgendes beim Arbeiten mit dem Code [Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#/):

* **Anforderungsparameter:** Alle Anforderungsparameter sind erforderlich, sofern nicht anders angegeben.
* **Anforderungsheader**: bei Verwendung von  [Adobe I/](https://www.adobe.io/) Token müssen Sie die  `x-api-key` Kopfzeile angeben. Sie können Ihren [!DNL API]-Schlüssel abrufen, indem Sie die Anweisungen auf der Seite [Dienstkontointegration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) befolgen.
* **[!DNL JSON]Inhaltstyp:** Geben Sie  `content-type: application/json`  **  `accept: application/json` und Ihren Code an.
* **Anforderungen und Antworten:** Anforderungen als ordnungsgemäß formatiertes  [!DNL JSON] Objekt senden. [!DNL Audience Manager] antwortet mit  [!DNL JSON] formatierten Daten. Serverantworten können angeforderte Daten, einen Statuscode oder beides enthalten.
* **Zugriff:** Ihr  [!DNL Audience Manager] Berater stellt Ihnen eine Client-ID und einen Schlüssel zur Verfügung, mit denen Sie  [!DNL API] Anfragen stellen können.
* **Dokumentation und Codebeispiele:** Text in  ** Kursivschrift stellt eine Variable dar, die Sie beim Erstellen oder Empfangen von  [!DNL API] Daten bereitstellen oder übergeben. Ersetzen Sie den Text *kursiv* durch Ihren eigenen Code, Ihre eigenen Parameter oder andere erforderliche Informationen.

## Authentifizierung {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] unterstützt zwei Authentifizierungsmethoden.

* [JWT (Service Account)-](#jwt) Authentifizierung mithilfe der  [Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] ist das Entwickler-Ökosystem und die Community der Adobe. Sie enthält die [Adobe I/O-Entwicklertools und -APIs](https://www.adobe.io/apis/experienceplatform.html) und [APIs für alle Adobe-Produkte](https://www.adobe.io/apis.html). Dies ist die empfohlene Methode zum Einrichten und Verwenden von [!DNL Adobe] [!DNL APIs].
* [OAuth-Authentifizierung (nicht mehr unterstützt)](#oauth). Diese Methode wird zwar nicht mehr unterstützt, Kunden mit vorhandenen [!DNL OAuth] -Integrationen können diese Methode jedoch weiterhin verwenden.

>[!IMPORTANT]
>
>Abhängig von Ihrer Authentifizierungsmethode müssen Sie Ihre Anfrage [!DNL URLs] entsprechend anpassen. Weitere Informationen zu den Hostnamen, die Sie verwenden sollten, finden Sie im Abschnitt [Umgebungen](#environments) .

## [!DNL JWT] ([!DNL Service Account]) Authentifizierung mit Adobe I/O {#jwt}

### Übersicht über Adoben I/O {#adobeio}

[!DNL Adobe I/O] ist das Entwickler-Ökosystem und die Community der Adobe. Sie enthält die [Adobe I/O-Entwicklertools und -APIs](https://www.adobe.io/apis/experienceplatform.html) und [APIs für alle Adobe-Produkte](https://www.adobe.io/apis.html).

Dies ist die empfohlene Methode zum Einrichten und Verwenden von [!DNL Adobe] [!DNL APIs].

### Voraussetzungen {#prerequisites}

Bevor Sie die [!DNL JWT]-Authentifizierung konfigurieren können, stellen Sie sicher, dass Sie Zugriff auf die [Adobe Developer Console](https://console.adobe.io/) in [Adobe I/O](https://www.adobe.io/) haben. Wenden Sie sich für Zugriffsanfragen an Ihren Organisationsadministrator.

### Authentifizierung {#auth}

Gehen Sie wie folgt vor, um die [!DNL JWT (Service Account)]-Authentifizierung mit [!DNL Adobe I/O] zu konfigurieren:

1. Melden Sie sich bei [Adobe Developer Console](https://console.adobe.io/) an.
1. Führen Sie die Schritte unter [Dienstkontenverbindung](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) aus.
   * Während [Schritt 2: Fügen Sie Ihrem Projekt mithilfe der Service Account-Authentifizierung](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) eine API hinzu und wählen Sie die Option [!DNL Audience Manager] [!DNL API] .
1. Probieren Sie die Verbindung aus, indem Sie Ihren ersten [!DNL API]-Aufruf anhand der Anweisungen von [Schritt 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) ausführen.

>[!NOTE]
>
>Um das [!DNL Audience Manager] [!DNL REST APIs] in automatisierter Weise zu konfigurieren und zu verwenden, können Sie das [!DNL JWT] programmatisch generieren. Detaillierte Anweisungen finden Sie unter [JWT (Service Account) Authentication](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) .

### RBAC-Berechtigungen für technische Konten

Wenn Ihr Audience Manager-Konto [Rollenbasierte Zugriffssteuerung](../../features/administration/administration-overview.md) verwendet, müssen Sie ein technisches Audience Manager-Benutzerkonto erstellen und es zur Audience Manager-RBAC-Gruppe hinzufügen, die die API-Aufrufe durchführt.

Gehen Sie wie folgt vor, um ein technisches Benutzerkonto zu erstellen und es einer RBAC-Gruppe hinzuzufügen:

1. Rufen Sie `GET` auf `https://aam.adobe.io/v1/users/self`. Durch den Aufruf wird ein technisches Benutzerkonto erstellt, das Sie auf der Seite [!UICONTROL Admin Console] auf der Seite [!UICONTROL Users] sehen können.

   ![technisches Konto](assets/technical-account.png)

1. Melden Sie sich bei Ihrem Benutzerkonto an und [fügen Sie das technische Benutzerkonto](../../features/administration/administration-overview.md#create-group) zur Benutzergruppe hinzu, die die API-Aufrufe durchführt.

## [!DNL OAuth] Authentifizierung (veraltet) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] Die Token-Authentifizierung und -Erneuerung über  [!DNL OAuth 2.0] ist jetzt veraltet.
>
> Verwenden Sie stattdessen [JWT (Service Account) Authentication](#jwt-service-account-authentication-jwt) .

Der [!DNL Audience Manager] [!UICONTROL REST API] folgt [!DNL OAuth 2.0]-Standards für die Token-Authentifizierung und -Erneuerung. In den folgenden Abschnitten wird beschrieben, wie Sie sich authentifizieren und mit den [!DNL API]s arbeiten.

### Erstellen eines generischen [!DNL API]-Benutzers {#requirements}

Es wird empfohlen, ein separates technisches Benutzerkonto für die Arbeit mit [!DNL Audience Manager] [!DNL API]s zu erstellen. Dies ist ein generisches Konto, das nicht an einen bestimmten Benutzer in Ihrem Unternehmen gebunden ist oder mit diesem verknüpft ist. Mit diesem Benutzerkonto von [!DNL API] können Sie zwei Dinge erreichen:

* Ermitteln Sie, welcher Dienst die [!DNL API] aufruft (z. B. Aufrufe aus Ihren Apps, die unsere [!DNL API]s verwenden, oder aus anderen Tools, die [!DNL API]-Anfragen stellen).
* Gewähren Sie unterbrechungsfreien Zugriff auf die [!DNL API]s. Ein Konto, das an eine bestimmte Person gebunden ist, kann gelöscht werden, wenn sie Ihr Unternehmen verlässt. Dadurch wird verhindert, dass Sie mit dem verfügbaren [!DNL API]-Code arbeiten. Ein generisches Konto, das nicht an einen bestimmten Mitarbeiter gebunden ist, hilft Ihnen, dieses Problem zu vermeiden.

Nehmen wir als Beispiel oder Anwendungsfall für diesen Kontotyp an, Sie möchten viele Segmente gleichzeitig mit den [Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-management-intro.md) ändern. Dazu benötigt Ihr Benutzerkonto [!DNL API] Zugriff. Anstatt einem bestimmten Benutzer Berechtigungen hinzuzufügen, erstellen Sie ein unspezifisches [!DNL API]-Benutzerkonto mit den entsprechenden Anmeldeinformationen, Schlüsseln und Geheimnissen, um [!DNL API]-Aufrufe durchzuführen. Dies ist auch nützlich, wenn Sie eigene Anwendungen entwickeln, die [!DNL Audience Manager] [!DNL API]s verwenden.

Arbeiten Sie mit Ihrem [!DNL Audience Manager] -Berater zusammen, um ein allgemeines, ausschließlich [!DNL API]-Benutzerkonto einzurichten.

### Workflow zur Kennwortauthentifizierung {#password-authentication-workflow}

Passwortauthentifizierung sicher Zugriff auf [!DNL REST API]. Die folgenden Schritte beschreiben den Workflow für die Kennwortauthentifizierung von einem [!DNL JSON]-Client in Ihrem Browser.

>[!TIP]
>
>Verschlüsseln Sie den Zugriff und aktualisieren Sie Token, wenn Sie sie in einer Datenbank speichern.

#### Schritt 1: Zugriff anfordern [!DNL API]

Wenden Sie sich an Ihren Partner Solutions Manager. Sie erhalten eine [!DNL API] Client-ID und ein Geheimnis. Die Kennung und das Geheimnis authentifizieren Sie bei [!DNL API].

Hinweis: Wenn Sie ein Aktualisierungstoken erhalten möchten, geben Sie dies an, wenn Sie den [!DNL API]-Zugriff anfordern.

#### Schritt 2: Token anfordern

Übergeben Sie eine Token-Anfrage mit Ihrem bevorzugten [!DNL JSON]-Client. Wenn Sie die Anforderung erstellen:

* Verwenden Sie eine `POST`-Methode, um `https://api.demdex.com/oauth/token` aufzurufen.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise werden die Anmeldedaten `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=` konvertiert.
* Übergeben Sie die [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded` . Die Kopfzeile könnte beispielsweise wie folgt aussehen: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Richten Sie den Anfragetext wie folgt ein:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Schritt 3: Token empfangen

Die Antwort [!DNL JSON] enthält Ihr Zugriffstoken. Die Antwort sollte wie folgt aussehen:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

Der Schlüssel `expires_in` stellt die Anzahl der Sekunden dar, bis das Zugriffstoken abläuft. Es hat sich bewährt, kurze Ablaufzeiten zu verwenden, um die Exposition zu begrenzen, wenn das Token jemals offen gelegt wird.

### Token aktualisieren {#refresh-token}

Token aktualisieren verlängern den [!DNL API]-Zugriff, nachdem das ursprüngliche Token abgelaufen ist. Bei Bedarf enthält die Antwort [!DNL JSON] im Kennwort-Workflow ein Aktualisierungstoken. Wenn Sie kein Aktualisierungstoken erhalten, erstellen Sie mithilfe des Kennwortauthentifizierungsprozesses ein neues.

Sie können auch ein Aktualisierungstoken verwenden, um ein neues Token zu generieren, bevor das vorhandene Zugriffstoken abläuft.

Wenn Ihr Zugriffstoken abgelaufen ist, erhalten Sie einen `401 Status Code` und die folgende Kopfzeile in der Antwort:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Die folgenden Schritte beschreiben den Workflow für die Verwendung eines Aktualisierungstokens zum Erstellen eines neuen Zugriffstokens aus einem [!DNL JSON]-Client in Ihrem Browser.

#### Schritt 1: Anfordern des neuen Tokens

Übergeben Sie eine Aktualisierungs-Token-Anfrage mit Ihrem bevorzugten [!DNL JSON]-Client. Wenn Sie die Anforderung erstellen:

* Verwenden Sie eine `POST`-Methode, um `https://api.demdex.com/oauth/token` aufzurufen.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise werden die Anmeldedaten `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=` konvertiert.
* Übergeben Sie die HTTP-Header `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded`. Die Kopfzeile könnte beispielsweise wie folgt aussehen: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Geben Sie im Anfragetext `grant_type:refresh_token` an und übergeben Sie das Aktualisierungstoken, das Sie in Ihrer vorherigen Zugriffsanfrage erhalten haben. Die Anfrage sollte wie folgt aussehen: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Schritt 2: Empfangen des neuen Tokens

Die Antwort [!DNL JSON] enthält Ihr neues Zugriffstoken. Die Antwort sollte wie folgt aussehen:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### Autorisierungscode und implizite Authentifizierung {#authentication-code-implicit}

[!DNL Audience Manager] [!UICONTROL REST API] unterstützt Autorisierungscode und implizite Authentifizierung. Um diese Zugriffsmethoden verwenden zu können, müssen sich Ihre Benutzer bei `https://api.demdex.com/oauth/authorize` anmelden, um Zugriff auf Token zu erhalten und sie zu aktualisieren.

## Authentifizierte [!DNL API]-Anforderungen stellen {#authenticated-api-requests}

Voraussetzungen für den Aufruf von [!DNL API]-Methoden, nachdem Sie ein Authentifizierungstoken erhalten haben.

So stellen Sie Aufrufe für die verfügbaren [!DNL API]-Methoden bereit:

* Legen Sie in der Kopfzeile `HTTP` `Authorization: Bearer <token>` fest.
* Bei Verwendung von [JWT (Service Account) Authentication](#jwt) müssen Sie die `x-api-key`-Kopfzeile angeben, die mit der `client_id` übereinstimmt. Sie können Ihr `client_id` von der Seite [Adobe I/O integration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) abrufen.
* Rufen Sie die erforderliche [!DNL API]-Methode auf.

## Optionale [!DNL API] Abfrageparameter {#optional-api-query-parameters}

Legen Sie die optionalen Parameter fest, die für Methoden verfügbar sind, die alle Eigenschaften für ein Objekt zurückgeben.

Sie können diese optionalen Parameter mit [!DNL API]-Methoden verwenden, die *alle*-Eigenschaften für ein Objekt zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an [!DNL API] übergeben.

| Parameter | Beschreibung |
|--- |--- |
| `page` | Gibt Ergebnisse nach Seitenzahl zurück. Die Nummerierung beginnt bei 0. |
| `pageSize` | Legt die Anzahl der von der Anfrage zurückgegebenen Antwortergebnisse fest (standardmäßig 10). |
| `sortBy` | Sortiert Ergebnisse und gibt sie gemäß der angegebenen [!DNL JSON]-Eigenschaft zurück. |
| `descending` | Sortiert Ergebnisse und gibt sie in absteigender Reihenfolge zurück. `ascending` ist Standard. |
| `search` | Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle mit dem Wort &quot;Test&quot;in einem der Wertefelder für dieses Element finden. Ihre Beispielanfrage könnte wie folgt aussehen:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Sie können nach jedem Wert suchen, der von einer &quot;[!DNL get all]&quot;-Methode zurückgegeben wird. |
| `folderId` | Gibt alle IDs für [!UICONTROL traits] innerhalb des angegebenen Ordners zurück. Nicht für alle Methoden verfügbar. |
| `permissions` | Gibt eine Liste von Segmenten basierend auf der angegebenen Berechtigung zurück. `READ` ist Standard. Zu den Berechtigungen gehören:<ul><li>`READ` : Zurückgeben und Anzeigen von Informationen zu einem Segment.</li><li>`WRITE` : Verwenden Sie   `PUT`  zum Aktualisieren eines Segments.</li><li>`CREATE` : Verwenden Sie   `POST`  zum Erstellen eines Segments.</li><li>`DELETE` : Segmente löschen. Erfordert Zugriff auf zugrunde liegende Eigenschaften, falls vorhanden. Beispielsweise benötigen Sie Berechtigungen zum Löschen der Eigenschaften, die zu einem Segment gehören, wenn Sie es entfernen möchten.</li></ul><br>Geben Sie mehrere Berechtigungen mit separaten Schlüssel-Wert-Paaren an. Um beispielsweise eine Liste von Segmenten mit `READ`- und `WRITE`-Berechtigungen zurückzugeben, geben Sie `"permissions":"READ"`, `"permissions":"WRITE"` ein. |
| `includePermissions` | ([!DNL Boolean]) Auf `true` setzen, um Ihre Berechtigungen für das Segment zurückzugeben. Standardwert ist `false`. |

### Ein Hinweis zu Seitenoptionen

Wenn die Seiteninformationen *nicht* angegeben sind, gibt die Anforderung nur [!DNL JSON] zurück und führt zu einem Array. Wenn die Seiteninformationen ** angegeben sind, wird die zurückgegebene Liste in ein [!DNL JSON] -Objekt eingeschlossen, das Informationen zum Gesamtergebnis und zur aktuellen Seite enthält. Ihre Beispielanfrage mit Seitenoptionen könnte in etwa wie folgt aussehen:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] für Anforderungen, Staging- und Produktionsumgebungen und -versionen.

## Anfrage [!DNL URLs] {#request-urls}

Die folgende Tabelle listet die Anfrage [!DNL URLs] auf, die zum Übergeben von [!DNL API]-Anforderungen verwendet wird, nach Methode.

Abhängig von der verwendeten Authentifizierungsmethode müssen Sie Ihre Anfrage [!DNL URLs] entsprechend den Tabellen unten anpassen.

### Anfrage [!DNL URLs] für [!DNL JWT] Authentifizierung {#request-urls-jwt}

| [!DNL API] Methoden | Anfrage [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Eigenschaften:  `https://aam.adobe.io/v1/folders/traits /`<br>Segmente:  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### Anfrage [!DNL URLs] für [!DNL OAuth] Authentifizierung (veraltet) {#request-urls-oauth}

| [!DNL API] Methoden | Anfrage [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Eigenschaften:  `https://api.demdex.com/v1/folders/traits /`<br>Segmente:  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## Umgebungen {#environments}

Die [!DNL Audience Manager] [!DNL API]s bieten Zugriff auf verschiedene Arbeitsumgebungen. Diese Umgebungen helfen Ihnen beim Testen von Code mit separaten Datenbanken, ohne dass sich dies auf Live-Produktionsdaten auswirkt. In der folgenden Tabelle sind die verfügbaren [!DNL API]-Umgebungen und die entsprechenden Ressourcen-Hostnamen aufgeführt.

Abhängig von der verwendeten Authentifizierungsmethode müssen Sie Ihre Umgebung [!DNL URLs] entsprechend der unten stehenden Tabelle anpassen.

| Umgebung | Hostname für [!DNL JWT] Authentifizierung | Hostname für [!DNL OAuth] Authentifizierung |
|---|---|---|
| **Produktion** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Die Beta-Umgebung [!DNL Audience Manager] ist eine kleinere, eigenständige Version der Produktionsumgebung. Alle Daten, die Sie testen möchten, müssen in dieser Umgebung eingegeben und erfasst werden.

## Versionen {#versions}

Neue Versionen dieser [!DNL API]s werden regelmäßig veröffentlicht. Bei einer neuen Version wird die Versionsnummer [!DNL API] inkrementiert. Die Versionsnummer wird in der Anfrage [!DNL URL] als `v<version number>` referenziert, wie im folgenden Beispiel gezeigt:

`https://<host>/v1/...`

## Definierte Antwortcodes {#response-codes-defined}

`HTTP` Status-Codes und Antworttext, der vom  [!DNL Audience Manager] [!UICONTROL REST API]zurückgegeben wird.

| Antwort-Code-ID | Antworttext | Definition |
|---|---|---|
| `200` | `OK` | Die Anfrage wurde erfolgreich verarbeitet. Gibt bei Bedarf erwartete Inhalte oder Daten zurück. |
| `201` | `Created` | Die Ressource wurde erstellt. Gibt für `PUT`- und `POST`-Anforderungen zurück. |
| `204` | `No Content` | Die Ressource wurde gelöscht. Der Antworttext ist leer. |
| `400` | `Bad Request` | Der Server hat die Anfrage nicht verstanden. In der Regel aufgrund einer fehlerhaften Syntax. Überprüfen Sie Ihre Anfrage und versuchen Sie es erneut. |
| `403` | `Forbidden` | Sie haben keinen Zugriff auf die Ressource. |
| `404` | `Not Found` | Die Ressource konnte für den angegebenen Pfad nicht gefunden werden. |
| `409` | `Conflict` | Die Anfrage konnte aufgrund eines Konflikts mit dem Status der Ressource nicht abgeschlossen werden. |
| `500` | `Server Error` | Auf dem Server ist ein unerwarteter Fehler aufgetreten, der die Erfüllung der Anforderung verhinderte. |

>[!MORELIKETHIS]
>
>* [JWT-Authentifizierung (Dienstkonto)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth-Authentifizierung](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 vereinfacht](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


---
description: Informationen zu allgemeinen Anforderungen, Authentifizierungen, optionalen Parametern für die Abfrage, Anforderungs-URLs und anderen Verweisen.
seo-description: Informationen zu allgemeinen Anforderungen, Authentifizierungen, optionalen Parametern für die Abfrage, Anforderungs-URLs und anderen Verweisen.
seo-title: Erste Schritte mit REST-APIs
solution: Audience Manager
title: Erste Schritte mit REST-APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: ab8745a8ba24154793201893a39a039b5a098833
workflow-type: tm+mt
source-wordcount: '1860'
ht-degree: 4%

---


# Getting Started with [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Information about general requirements, authentication, optional query parameters, request [!DNL URLs], and other references.

<!-- c_rest_api_overview.xml -->

## API-Anforderungen und -Empfehlungen {#api-requirements-recommendations}

Was Sie tun müssen und sollten, wenn Sie mit den [!DNL Audience Manager] [!DNL API]s arbeiten.

<!-- aam-api-requirements.xml -->

Beachten Sie beim Arbeiten mit [Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#/) -Code Folgendes:

* **Anforderungsparameter:** alle Anforderungsparameter sind erforderlich, sofern nicht anders angegeben.
* **Anforderungsheader**: Wenn Sie [Adobe-E/A](https://www.adobe.io/) -Token verwenden, müssen Sie die `x-api-key` Kopfzeile angeben. Sie können Ihren [!DNL API] Schlüssel abrufen, indem Sie die Anweisungen auf der Seite [Dienstkontointegration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) befolgen.
* **[!DNL JSON]Inhaltstyp:** Geben Sie `content-type: application/json` und *geben Sie Ihren Code ein* `accept: application/json` .
* **Anforderungen und Antworten:** Senden von Anforderungen als korrekt formatiertes [!DNL JSON] Objekt [!DNL Audience Manager] antwortet mit [!DNL JSON] formatierten Daten. Serverantworten können angeforderte Daten, einen Statuscode oder beides enthalten.
* **Zugriff:** Ihr [!DNL Audience Manager] Berater stellt Ihnen eine Client-ID und einen Schlüssel zur Verfügung, mit denen Sie [!DNL API] Anforderungen stellen können.
* **Dokumentation und Codebeispiele:** Text in *Kursivschrift* stellt eine Variable dar, die Sie beim Herstellen oder Empfangen von [!DNL API] Daten angeben oder übermitteln. Ersetzen Sie *kursiv gedruckten* Text durch Ihren eigenen Code, Ihre eigenen Parameter oder andere erforderliche Informationen.

## Authentifizierung {#authentication}

Die [!DNL Audience Manager] Unterstützung [!DNL REST APIs] umfasst zwei Authentifizierungsmethoden.

* [JWT-Authentifizierung](#jwt) (Dienstkonto) mit [Adobe-E/A](https://www.adobe.io/). [!DNL Adobe I/O] ist das Entwicklerökosystem und die Community der Adobe. Es enthält die [Adobe-E/A-Entwicklerwerkzeuge sowie APIs](https://www.adobe.io/apis/experienceplatform.html) und [APIs für alle Adobe-Produkte](https://www.adobe.io/apis.html). Dies ist die empfohlene Art der Einrichtung und Verwendung [!DNL Adobe][!DNL APIs].
* [OAuth-Authentifizierung (nicht mehr unterstützt)](#oauth). Diese Methode wird nicht mehr unterstützt, Kunden mit vorhandenen [!DNL OAuth] Integrationen können diese Methode weiterhin verwenden.

>[!IMPORTANT]
>
>Je nach Authentifizierungsmethode müssen Sie Ihre Anforderung [!DNL URLs] entsprechend anpassen. Einzelheiten zu den zu verwendenden Hostnamen finden Sie im Abschnitt [Umgebung](#environments) .

## [!DNL JWT] ([!DNL Service Account]) Authentifizierung mit Adobe-E/A {#jwt}

### Adobe-E/A-Übersicht {#adobeio}

[!DNL Adobe I/O] ist das Entwicklerökosystem und die Community der Adobe. Es enthält die [Adobe-E/A-Entwicklerwerkzeuge sowie APIs](https://www.adobe.io/apis/experienceplatform.html) und [APIs für alle Adobe-Produkte](https://www.adobe.io/apis.html).

Dies ist die empfohlene Art der Einrichtung und Verwendung [!DNL Adobe][!DNL APIs].

### Voraussetzungen {#prerequisites}

Bevor Sie die [!DNL JWT] Authentifizierung konfigurieren können, stellen Sie sicher, dass Sie Zugriff auf die [Adobe Developer Console](https://console.adobe.io/) in der [Adobe I/O](https://www.adobe.io/)haben. Wenden Sie sich für Zugriffsanfragen an Ihren Unternehmensadministrator.

### Authentifizierung {#auth}

Gehen Sie wie folgt vor, um die [!DNL JWT (Service Account)] Authentifizierung mithilfe [!DNL Adobe I/O]der folgenden Schritte zu konfigurieren:

1. Melden Sie sich bei der [Adobe Developer Console](https://console.adobe.io/)an.
1. Führen Sie die Schritte unter [Dienstkontoverbindung](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)aus.
   * Während [Schritt 2: Wählen Sie Hinzufügen eine API für Ihr Projekt mithilfe der Dienstkontoauthentifizierung](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)die [!DNL Audience Manager][!DNL API] Option.
1. Versuchen Sie, die Verbindung herzustellen, indem Sie Ihren ersten [!DNL API] Aufruf gemäß den Anweisungen in [Schritt 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)tätigen.

>[!NOTE]
>
>Um die Konfiguration und die Arbeit mit der [!DNL Audience Manager][!DNL REST APIs] automatisiert zu gestalten, können Sie die [!DNL JWT] programmgesteuert generieren. Detaillierte Anweisungen finden Sie unter [JWT-Authentifizierung](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) (Dienstkontoauthentifizierung).

## [!DNL OAuth] Authentifizierung (nicht mehr unterstützt) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] Token-Authentifizierung und -Erneuerung über [!DNL OAuth 2.0] ist jetzt veraltet.
>
> Bitte verwenden Sie stattdessen die [JWT-Authentifizierung](#jwt-service-account-authentication-jwt) (Dienstkonto).

Die [!DNL Audience Manager] Variable [!UICONTROL REST API] entspricht den [!DNL OAuth 2.0] Standards für die Token-Authentifizierung und -Erneuerung. In den folgenden Abschnitten wird beschrieben, wie Sie sich authentifizieren und Beginn mit den [!DNL API]s arbeiten.

### Generischen [!DNL API] Benutzer erstellen {#requirements}

Es wird empfohlen, ein separates technisches Benutzerkonto für die Arbeit mit den [!DNL Audience Manager] s einzurichten. [!DNL API]Es wird empfohlen. Dies ist ein generisches Konto, das nicht an einen bestimmten Benutzer in Ihrem Unternehmen gebunden ist oder mit diesem verknüpft ist. Mit diesem [!DNL API] Benutzerkonto können Sie zwei Dinge erreichen:

* Identifizieren Sie, welcher Dienst den Dienst aufruft [!DNL API] (z. B. Aufrufe von Apps, die unsere [!DNL API]s verwenden, oder von anderen Tools, die Anforderungen [!DNL API] stellen).
* Gewähren Sie ununterbrochenen Zugriff auf die [!DNL API]s. Ein an eine bestimmte Person gebundenes Konto kann gelöscht werden, wenn sie Ihre Firma verlässt. Dadurch wird verhindert, dass Sie mit dem verfügbaren [!DNL API] Code arbeiten. Ein generisches Konto, das nicht an einen bestimmten Mitarbeiter gebunden ist, hilft Ihnen, dieses Problem zu vermeiden.

Beispiel oder Anwendungsfall für diesen Kontotyp: Sie möchten mit den [Massenverwaltungstools](../../reference/bulk-management-tools/bulk-management-intro.md)viele Segmente gleichzeitig ändern. Um dies zu tun, muss Ihr Benutzerkonto [!DNL API] Zugriff haben. Anstatt einem bestimmten Benutzer Berechtigungen hinzuzufügen, erstellen Sie ein unspezifisches [!DNL API] Benutzerkonto, das über die entsprechenden Anmeldeinformationen, den entsprechenden Schlüssel und das geheime Schlüssel zum [!DNL API] Aufrufen verfügt. Dies ist auch nützlich, wenn Sie eigene Anwendungen entwickeln, die die [!DNL Audience Manager] [!DNL API]s verwenden.

Arbeiten Sie mit Ihrem [!DNL Audience Manager] Berater zusammen, um ein generisches, [!DNL API]ausschließlich-benutzerkonto einzurichten.

### Arbeitsablauf für die Kennwortauthentifizierung {#password-authentication-workflow}

Passwortauthentifizierung sicher Zugriff auf unsere [!DNL REST API]. Die folgenden Schritte beschreiben den Arbeitsablauf für die Kennwortauthentifizierung von einem [!DNL JSON] Client in Ihrem Browser.

>[!TIP]
>
>Verschlüsseln Sie den Zugriff und aktualisieren Sie Token, wenn Sie sie in einer Datenbank speichern.

#### Schritt 1: Zugriff [!DNL API] anfordern

Wenden Sie sich an Ihren Partner Solutions Manager. Sie geben Ihnen eine [!DNL API] Client-ID und ein Geheimnis. Die ID und das Geheimnis authentifizieren Sie sich beim [!DNL API].

Hinweis: Wenn Sie ein Aktualisierungstoken erhalten möchten, geben Sie dies an, wenn Sie den [!DNL API] Zugriff anfordern.

#### Schritt 2: Token anfordern

Geben Sie eine Token-Anforderung an Ihren bevorzugten [!DNL JSON] Client weiter. Beim Erstellen der Anforderung:

* Verwenden Sie eine `POST` Methode zum Aufrufen `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise werden die Anmeldeinformationen `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=`konvertiert.
* Übergeben Sie die [!DNL HTTP] und [!DNL headers]`Authorization:Basic <base-64 clientID:clientSecret>` `Content-Type: application/x-www-form-urlencoded` . Ihre Kopfzeile könnte z. B. wie folgt aussehen: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Richten Sie den Anforderungstext wie folgt ein:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Schritt 3: Token empfangen

Die [!DNL JSON] Antwort enthält Ihr Zugriffstoken. Die Antwort sollte wie folgt aussehen:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

Der `expires_in` Schlüssel gibt die Anzahl der Sekunden an, bis das Zugriffstoken abläuft. Als Best Practice sollten Sie kurze Ablaufzeiten verwenden, um die Exposition zu begrenzen, wenn das Token jemals offen gelegt wird.

### Token aktualisieren {#refresh-token}

Token aktualisieren erneuern den [!DNL API] Zugriff, nachdem das ursprüngliche Token abgelaufen ist. Bei Anforderung enthält die Antwort [!DNL JSON] im Passwortarbeitsablauf ein Aktualisierungstoken. Wenn Sie kein Aktualisierungstoken erhalten, erstellen Sie mithilfe der Kennwortauthentifizierung ein neues.

Sie können auch ein Aktualisierungstoken verwenden, um ein neues Token zu generieren, bevor das vorhandene Zugriffstoken abläuft.

Wenn Ihr Zugriffstoken abgelaufen ist, erhalten Sie eine `401 Status Code` und die folgende Kopfzeile in der Antwort:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Die folgenden Schritte beschreiben den Arbeitsablauf für die Verwendung eines Aktualisierungstokens zum Erstellen eines neuen Zugriffstokens von einem [!DNL JSON] Client in Ihrem Browser.

#### Schritt 1: Neues Token anfordern

Geben Sie eine Aktualisierungstoken-Anforderung an Ihren bevorzugten [!DNL JSON] Client weiter. Beim Erstellen der Anforderung:

* Verwenden Sie eine `POST` Methode zum Aufrufen `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise werden die Anmeldeinformationen `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=`konvertiert.
* Übergeben Sie die HTTP-Header `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded`. Ihre Kopfzeile könnte z. B. wie folgt aussehen: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Geben Sie im Anforderungstext das Aktualisierungstoken an, das Sie in Ihrer vorherigen Zugriffsanforderung erhalten haben, `grant_type:refresh_token` und übergeben Sie es an. Die Anfrage sollte wie folgt aussehen: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Schritt 2: Neues Token erhalten

Die [!DNL JSON] Antwort enthält Ihr neues Zugriffstoken. Die Antwort sollte wie folgt aussehen:

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

Die [!DNL Audience Manager] Unterstützung [!UICONTROL REST API] von Autorisierungscode und impliziter Authentifizierung. Um diese Zugriffsmethoden verwenden zu können, müssen sich Ihre Benutzer anmelden, um Zugriff auf Token zu erhalten und sie zu aktualisieren. `https://api.demdex.com/oauth/authorize`

## Authentifizierte [!DNL API] Anforderungen erstellen {#authenticated-api-requests}

Voraussetzungen für den Aufruf von [!DNL API] Methoden nach Erhalt eines Authentifizierungstokens.

Aufrufe anhand der verfügbaren [!DNL API] Methoden durchzuführen:

* Legen Sie in der `HTTP` Kopfzeile `Authorization: Bearer <token>`fest.
* Bei Verwendung der [JWT-Authentifizierung](#jwt)(Dienstkontoauthentifizierung) müssen Sie die `x-api-key` Kopfzeile angeben, die mit der Ihrer identisch ist `client_id`. Sie können Ihre Daten `client_id` von der [Adobe-I/O-Integrationsseite](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) abrufen.
* Rufen Sie die erforderliche [!DNL API] Methode auf.

## Optionale [!DNL API] Abfrage-Parameter {#optional-api-query-parameters}

Legen Sie die optionalen Parameter fest, die für Methoden verfügbar sind, die alle Eigenschaften für ein Objekt zurückgeben.

Sie können diese optionalen Parameter mit [!DNL API] Methoden verwenden, die *alle* Eigenschaften für ein Objekt zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn diese Abfrage an die [!DNL API]übergeben wird.

| Parameter | Beschreibung |
|--- |--- |
| `page` | Gibt Ergebnisse nach Seitenzahl zurück. Nummerierung von Beginn bei 0. |
| `pageSize` | Legt die Anzahl der Antwortergebnisse fest, die von der Anforderung zurückgegeben werden (10 ist standardmäßig). |
| `sortBy` | Sortiert Ergebnisse und gibt sie entsprechend der angegebenen [!DNL JSON] Eigenschaft zurück. |
| `descending` | Sortiert die Ergebnisse und gibt sie in absteigender Reihenfolge zurück. `ascending` ist Standard. |
| `search` | Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Nehmen wir beispielsweise an, Sie möchten Ergebnisse für alle Modelle suchen, die das Wort &quot;Test&quot;in einem der Wertefelder für dieses Element enthalten. Ihre Musteranforderung könnte wie folgt aussehen:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Sie können nach jedem Wert suchen, der von einer &quot;[!DNL get all]&quot;-Methode zurückgegeben wird. |
| `folderId` | Gibt alle IDs für [!UICONTROL traits] den angegebenen Ordner zurück. Nicht für alle Methoden verfügbar. |
| `permissions` | Gibt eine Liste von Segmenten basierend auf der angegebenen Berechtigung zurück. `READ` ist Standard. Zu den Berechtigungen gehören:<ul><li>`READ` : Rückgabe- und Segmentinformationen zur Ansicht.</li><li>`WRITE` : Aktualisieren Sie `PUT` ein Segment.</li><li>`CREATE` : Verwenden Sie `POST` zum Erstellen eines Segments.</li><li>`DELETE` : Segmente löschen. Erfordert Zugriff auf zugrunde liegende Eigenschaften, falls vorhanden. Sie benötigen beispielsweise Rechte zum Löschen der Eigenschaften, die zu einem Segment gehören, wenn Sie es entfernen möchten.</li></ul><br>Geben Sie mehrere Berechtigungen mit separaten Schlüssel/Wert-Paaren an. Um beispielsweise eine Liste von Segmenten mit `READ` und nur `WRITE` Berechtigungen zurückzugeben, geben Sie `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Legen Sie fest, dass `true` Sie Ihre Berechtigungen für das Segment zurückgeben. Standardwert ist `false`. |

### Hinweis zu Seitenoptionen

Wenn keine *Seiteninformationen angegeben* werden, gibt die Anforderung Nur- [!DNL JSON] Ergebnisse in einem Array zurück. Wenn Seiteninformationen angegeben *werden* , wird die zurückgegebene Liste in ein [!DNL JSON] Objekt eingeschlossen, das Informationen zum Gesamtergebnis und zur aktuellen Seite enthält. Ihre Musteranforderung mit Seitenoptionen könnte wie folgt aussehen:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] für Anforderungen, Staging- und Produktions-Umgebung und Versionen.

## Anfrage [!DNL URLs] {#request-urls}

In der folgenden Tabelle wird die Anforderung [!DNL URLs] für die Übermittlung von [!DNL API] Anforderungen nach Methode Liste.

Je nach der von Ihnen verwendeten Authentifizierungsmethode müssen Sie Ihre Anforderung [!DNL URLs] entsprechend den unten stehenden Tabellen anpassen.

### Anfrage [!DNL URLs] zur [!DNL JWT] Authentifizierung {#request-urls-jwt}

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

### Anfrage [!DNL URLs] zur [!DNL OAuth] Authentifizierung (überholt) {#request-urls-oauth}

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

## Umgebung {#environments}

Die [!DNL Audience Manager] Arbeitsabläufe [!DNL API]bieten Zugang zu verschiedenen Umgebung. Diese Umgebung helfen Ihnen, Code mit separaten Datenbanken zu testen, ohne dass sich dies auf die Live-Produktionsdaten auswirkt. In der folgenden Tabelle werden die verfügbaren [!DNL API] Umgebung und die entsprechenden Ressourcen-Hostnamen Liste.

Je nach der von Ihnen verwendeten Authentifizierungsmethode müssen Sie Ihre Umgebung [!DNL URLs] entsprechend der unten stehenden Tabelle anpassen.

| Umgebung | Hostname für [!DNL JWT] Authentifizierung | Hostname für [!DNL OAuth] Authentifizierung |
|---|---|---|
| **Produktion** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Die [!DNL Audience Manager] Beta-Umgebung ist eine kleinere, eigenständige Version der Umgebung. Alle Daten, die Sie testen möchten, müssen in diese Umgebung eingegeben und gesammelt werden.

## Versionen {#versions}

Neue Versionen dieser [!DNL API]Dateien werden regelmäßig veröffentlicht. Bei einer neuen Version wird die [!DNL API] Versionsnummer inkrementiert. Die Versionsnummer wird in der Anforderung [!DNL URL] wie im folgenden Beispiel gezeigt `v<version number>` angegeben:

`https://<host>/v1/...`

## Antwortcodes definiert {#response-codes-defined}

`HTTP` Statuscodes und Antworttext, der vom [!DNL Audience Manager][!UICONTROL REST API].

| Antwortcode-ID | Antworttext | Definition |
|---|---|---|
| `200` | `OK` | Die Anforderung wurde erfolgreich verarbeitet. Gibt bei Bedarf erwartete Inhalte oder Daten zurück. |
| `201` | `Created` | Die Ressource wurde erstellt. Gibt für `PUT` und `POST` Anforderungen zurück. |
| `204` | `No Content` | Die Ressource wurde gelöscht. Der Antwortkörper ist leer. |
| `400` | `Bad Request` | Der Server hat die Anforderung nicht verstanden. In der Regel aufgrund einer fehlerhaften Syntax. Überprüfen Sie Ihre Anforderung und versuchen Sie es erneut. |
| `403` | `Forbidden` | Sie haben keinen Zugriff auf die Ressource. |
| `404` | `Not Found` | Die Ressource konnte für den angegebenen Pfad nicht gefunden werden. |
| `409` | `Conflict` | Die Anforderung konnte aufgrund eines Konflikts mit dem Zustand der Ressource nicht abgeschlossen werden. |
| `500` | `Server Error` | Auf dem Server ist ein unerwarteter Fehler aufgetreten, durch den die Anforderung nicht erfüllt werden konnte. |

>[!MORELIKETHIS]
>
>* [JWT-Authentifizierung (Dienstkonto)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth-Authentifizierung](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 Vereinfacht](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


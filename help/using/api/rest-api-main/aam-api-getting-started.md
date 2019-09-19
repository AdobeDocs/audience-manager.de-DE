---
description: Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderungs-URLs und anderen Verweisen.
seo-description: Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderungs-URLs und anderen Verweisen.
seo-title: Erste Schritte mit REST-APIs
solution: Audience Manager
title: Erste Schritte mit REST-APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: 27800ce003a62733eece0d5de3b94737ed61133a

---


# Erste Schritte mit REST-APIs {#getting-started-with-rest-apis}

Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderungs-URLs und anderen Verweisen.

<!-- c_rest_api_overview.xml -->

## API-Anforderungen und Empfehlungen {#api-requirements-recommendations}

Dinge, die Sie beim Arbeiten mit Audience Manager [!DNL API]tun müssen und sollten.

<!-- aam-api-requirements.xml -->

Beachten Sie beim Arbeiten mit [Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#/) -Code Folgendes:

* **** Abfrageparameter: Sofern nicht anders angegeben, sind alle Anforderungsparameter erforderlich.
* **[!DNL JSON]** Inhaltstyp: Geben Sie `content-type: application/json` und *geben Sie Ihren Code ein* `accept: application/json`.

* **** Anforderungen und Antworten: Senden von Anforderungen als korrekt formatiertes [!DNL JSON] Objekt [!DNL Audience Manager] antwortet mit [!DNL JSON] formatierten Daten. Serverantworten können angeforderte Daten, einen Statuscode oder beides enthalten.

* **** Zugriff: Ihr [!DNL Audience Manager] Berater stellt Ihnen eine Client-ID und einen Schlüssel zur Verfügung, mit denen Sie [!DNL API] Anforderungen stellen können.

* **** Dokumentation und Codebeispiele: Text in *Kursivschrift* stellt eine Variable dar, die Sie beim Herstellen oder Empfangen von [!DNL API] Daten angeben oder übermitteln. Ersetzen Sie *kursiv gedruckten* Text durch Ihren eigenen Code, Ihre eigenen Parameter oder andere erforderliche Informationen.

## Empfehlungen: Erstellen eines generischen API-Benutzers {#requirements}

Es wird empfohlen, ein separates technisches Benutzerkonto für die Arbeit mit Audience Manager [!DNL API]zu erstellen. Dies ist ein generisches Konto, das nicht an einen bestimmten Benutzer in Ihrem Unternehmen gebunden ist oder mit diesem verknüpft ist. Mit diesem [!DNL API] Benutzerkonto können Sie zwei Dinge erreichen:

* Identifizieren Sie, welcher Dienst die Anwendung aufruft [!DNL API] (z. B. Aufrufe von Apps, die unsere [!DNL API]s verwenden, oder von anderen Tools, die Anforderungen [!DNL API] stellen).
* Gewähren Sie ununterbrochenen Zugriff auf die [!DNL API]s. Ein Konto, das an eine bestimmte Person gebunden ist, kann gelöscht werden, wenn sie Ihr Unternehmen verlassen. Dadurch wird verhindert, dass Sie mit dem verfügbaren [!DNL API] Code arbeiten. Ein generisches Konto, das nicht an einen bestimmten Mitarbeiter gebunden ist, hilft Ihnen, dieses Problem zu vermeiden.

Beispiel oder Anwendungsfall für diesen Kontotyp: Sie möchten mit den [Massenverwaltungstools](../../reference/bulk-management-tools/bulk-management-intro.md)viele Segmente gleichzeitig ändern. Um dies zu tun, muss Ihr Benutzerkonto [!DNL API] Zugriff haben. Anstatt einem bestimmten Benutzer Berechtigungen hinzuzufügen, erstellen Sie ein unspezifisches [!DNL API] Benutzerkonto, das über die entsprechenden Anmeldeinformationen, den entsprechenden Schlüssel und das geheime Schlüssel zum [!DNL API] Aufrufen verfügt. Dies ist auch nützlich, wenn Sie eigene Anwendungen entwickeln, die Audience Manager [!DNL API]verwenden.

Wenden Sie sich an Ihren Audience Manager-Berater, um ein generisches, [!DNL API]ausschließlich auf Benutzer beschränktes Benutzerkonto einzurichten.

## OAuth Authentication {#oauth}

Der Audience Manager [!UICONTROL REST API] befolgt [!DNL OAuth 2.0] Standards für die Token-Authentifizierung und -Erneuerung. In den folgenden Abschnitten wird beschrieben, wie Sie sich authentifizieren und mit den [!DNL API]s arbeiten.

## Arbeitsablauf für die Kennwortauthentifizierung {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Passwortauthentifizierung sicher Zugriff auf unsere [!DNL REST API]. Die folgenden Schritte beschreiben den Arbeitsablauf für die Kennwortauthentifizierung von einem [!DNL JSON] Client in Ihrem Browser.

>[!TIP]
>
>Verschlüsseln Sie den Zugriff und aktualisieren Sie Token, wenn Sie sie in einer Datenbank speichern.

### Schritt 1: API-Zugriff anfordern

Wenden Sie sich an Ihren Partner Solutions Manager. Sie geben Ihnen eine [!DNL API] Client-ID und ein Geheimnis. Die ID und das Geheimnis authentifizieren Sie sich beim [!DNL API].

Hinweis: Wenn Sie ein Aktualisierungstoken erhalten möchten, geben Sie dies an, wenn Sie den [!DNL API] Zugriff anfordern.

### Schritt 2: Token anfordern

Geben Sie eine Token-Anforderung an Ihren bevorzugten [!DNL JSON] Client weiter. Beim Erstellen der Anforderung:

* Verwenden Sie eine `POST` Methode zum Aufrufen `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise werden die Anmeldeinformationen `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=`konvertiert.
* Geben Sie die [!DNL HTTP] Kopfzeilen `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded` . Ihre Kopfzeile könnte z. B. wie folgt aussehen: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Richten Sie den Anforderungstext wie folgt ein:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Schritt 3: Token empfangen

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

## Token aktualisieren {#refresh-token}

Token aktualisieren erneuern den [!DNL API] Zugriff, nachdem das ursprüngliche Token abgelaufen ist. Bei Anforderung enthält die Antwort [!DNL JSON] im Passwortarbeitsablauf ein Aktualisierungstoken. Wenn Sie kein Aktualisierungstoken erhalten, erstellen Sie mithilfe der Kennwortauthentifizierung ein neues.

Sie können auch ein Aktualisierungstoken verwenden, um ein neues Token zu generieren, bevor das vorhandene Zugriffstoken abläuft.

Wenn Ihr Zugriffstoken abgelaufen ist, erhalten Sie eine `401 Status Code` und die folgende Kopfzeile in der Antwort:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Die folgenden Schritte beschreiben den Arbeitsablauf für die Verwendung eines Aktualisierungstokens zum Erstellen eines neuen Zugriffstokens von einem [!DNL JSON] Client in Ihrem Browser.

### Schritt 1: Neues Token anfordern

Geben Sie eine Aktualisierungstoken-Anforderung an Ihren bevorzugten [!DNL JSON] Client weiter. Beim Erstellen der Anforderung:

* Verwenden Sie eine `POST` Methode zum Aufrufen `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise werden die Anmeldeinformationen `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=`konvertiert.
* Übergeben Sie die HTTP-Header `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded`. Ihre Kopfzeile könnte z. B. wie folgt aussehen: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* Geben Sie im Anforderungstext das Aktualisierungstoken an, das Sie in Ihrer vorherigen Zugriffsanforderung erhalten haben, `grant_type:refresh_token` und übergeben Sie es an. Die Anfrage sollte wie folgt aussehen: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Schritt 2: Neues Token erhalten

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

## Autorisierungscode und implizite Authentifizierung {#authentication-code-implicit}

Audience Manager [!UICONTROL REST API] unterstützt Autorisierungscode und implizite Authentifizierung. Um diese Zugriffsmethoden verwenden zu können, müssen sich Ihre Benutzer anmelden, um Zugriff auf Token zu erhalten und sie zu aktualisieren. `https://api.demdex.com/oauth/authorize`

>[!MORE_LIKE_THIS]
>
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 Vereinfacht](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Authentifizierte API-Anforderungen erstellen {#authenticated-api-requests}

Voraussetzungen für den Aufruf von [!DNL API] Methoden nach Erhalt eines Authentifizierungstokens.

<!-- c_oauth_call_methods.xml -->

Aufrufe anhand der verfügbaren [!DNL API] Methoden durchzuführen:

* Legen Sie im `HTTP` Header `Authorization: Bearer <token>`fest.
* Rufen Sie die erforderliche [!DNL API] Methode auf.

>[!MORE_LIKE_THIS]
>
>* [OAuth-Authentifizierung](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optionale API-Abfrageparameter {#optional-api-query-parameters}

Legen Sie die optionalen Parameter fest, die für Methoden verfügbar sind, die alle Eigenschaften für ein Objekt zurückgeben.

<!-- c_rest_api_optional.xml -->

Sie können diese optionalen Parameter mit [!DNL API] Methoden verwenden, die *alle* Eigenschaften eines Objekts zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an die [!DNL API]übergeben.

| Parameter | Beschreibung |
|--- |--- |
| Seite | Gibt Ergebnisse nach Seitenzahl zurück. Die Nummerierung beginnt bei 0. |
| pageSize | Legt die Anzahl der Antwortergebnisse fest, die von der Anforderung zurückgegeben werden (10 ist standardmäßig). |
|  sortBy | Sortiert Ergebnisse und gibt sie entsprechend der angegebenen [!DNL JSON] Eigenschaft zurück. |
| absteigend | Sortiert die Ergebnisse und gibt sie in absteigender Reihenfolge zurück. "Aufsteigend"ist die Standardeinstellung. |
| Suche | Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Nehmen wir beispielsweise an, Sie möchten Ergebnisse für alle Modelle suchen, die das Wort "Test"in einem der Wertefelder für dieses Element enthalten. Ihre Musteranforderung könnte wie folgt aussehen: `GET https://api.demdex.com/v1/models/?search=Test`.  Sie können nach jedem Wert suchen, der von der Methode "get all"zurückgegeben wird. |
|  folderId | Gibt alle IDs für Eigenschaften im angegebenen Ordner zurück. Nicht für alle Methoden verfügbar. |
| Berechtigungen | Gibt eine Liste der Segmente basierend auf der angegebenen Berechtigung zurück.  READ ist Standard. Zu den Berechtigungen gehören:<ul><li>`READ` : Geben Sie Informationen zu einem Segment zurück und zeigen Sie es an.</li><li>`WRITE` : Aktualisieren Sie `PUT` ein Segment.</li><li>`CREATE` : Verwenden Sie `POST` zum Erstellen eines Segments.</li><li>`DELETE` : Segmente löschen. Erfordert Zugriff auf zugrunde liegende Eigenschaften, falls vorhanden. Sie benötigen beispielsweise Rechte zum Löschen der Eigenschaften, die zu einem Segment gehören, wenn Sie es entfernen möchten.</li></ul><br>Geben Sie mehrere Berechtigungen mit separaten Schlüssel/Wert-Paaren an. Um beispielsweise eine Liste mit Segmenten zurückzugeben, die nur über `READ` und `WRITE` Berechtigungen verfügen, geben Sie `"permissions":"READ"`, `"permissions":"WRITE"` . |
| includePermissions | (Boolescher Wert) Auf "true"setzen, um die Berechtigungen für das Segment zurückzugeben. Standard ist „false“. |

### Hinweis zu Seitenoptionen

Wenn keine *Seiteninformationen angegeben* werden, gibt die Anforderung Nur- [!DNL JSON] Ergebnisse in einem Array zurück. Wenn Seiteninformationen angegeben *werden* , wird die zurückgegebene Liste in ein [!DNL JSON] Objekt eingeschlossen, das Informationen zum Gesamtergebnis und zur aktuellen Seite enthält. Ihre Musteranforderung mit Seitenoptionen könnte wie folgt aussehen:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API-URLs {#api-urls}

[!DNL URLs] für Anforderungen, Staging- und Produktionsumgebungen und Versionen.

<!-- r_rest_urls.xml -->

## URLs anfordern {#request-urls}

Die folgende Tabelle listet die Anforderungs-URLs auf, die zum Übergeben von [!DNL API] Anforderungen verwendet werden.

| [!DNL API] Methoden | Anfrage [!DNL URL] |
|--- |--- |
| Algorithmisches Modellieren | `https://api.demdex.com/v1/models/` |
| Datenquelle | `https://api.demdex.com/v1/datasources/` |
| Abgeleitete Signale | `https://api.demdex.com/v1/signals/derived/` |
| Ziele | `https://api.demdex.com/v1/destinations/` |
| Domänen | `https://api.demdex.com/v1/partner-sites/` |
| Ordner | Eigenschaften:  `https://api.demdex.com/v1/folders/traits /`<br>Segmente:  `https://api.demdex.com/v1/folders/segments /` |
| Schema | `https://api.demdex.com/v1/schemas/` |
| Segmente | `https://api.demdex.com/v1/segments/` |
| Eigenschaften | `https://api.demdex.com/v1/traits/` |
| Eigenschaftstypen | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomie | `https://api.demdex.com/v1/taxonomies/0/` |

## Umgebungen {#environments}

Die [!DNL Audience Manager] [!DNL API]s bieten Zugriff auf verschiedene Arbeitsumgebungen. Diese Umgebungen unterstützen Sie beim Testen von Code mit separaten Datenbanken, ohne dass sich dies auf Live-Produktionsdaten auswirkt. In der folgenden Tabelle sind die verfügbaren [!DNL API] Umgebungen und die entsprechenden Ressourcen-Hostnamen aufgeführt.

| Umgebung | Hostname |
|---|---|
| **Produktion** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Die Beta-Umgebung von Audience Manager ist eine kleinere, eigenständige Version der Produktionsumgebung. Alle Daten, die Sie testen möchten, müssen in dieser Umgebung eingegeben und gesammelt werden.

## Versionen {#versions}

Neue Versionen dieser [!DNL API]Dateien werden regelmäßig veröffentlicht. Bei einer neuen Version wird die [!DNL API] Versionsnummer erhöht. Die Versionsnummer wird in der Anforderungs-URL referenziert, wie im folgenden Beispiel gezeigt `v<version number>` :

`https://<host>/v1/...`

## Antwortcodes definiert {#response-codes-defined}

`HTTP` Statuscodes und Antworttext, der vom Audience Manager zurückgegeben wird [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| Antwortcode-ID | Antworttext | Definition |
|---|---|---|
| 200 |  OK- | Die Anforderung wurde erfolgreich verarbeitet. Gibt bei Bedarf erwartete Inhalte oder Daten zurück. |
| 201 | Erstellt | Die Ressource wurde erstellt. Gibt für `PUT` und `POST` Anforderungen zurück. |
| 204 | Kein Inhalt | Die Ressource wurde gelöscht. Der Antwortkörper ist leer. |
| 400 | Unzulässige Anfrage | Der Server hat die Anforderung nicht verstanden. In der Regel aufgrund einer fehlerhaften Syntax. Überprüfen Sie Ihre Anforderung und versuchen Sie es erneut. |
| 403 | Verboten | Sie haben keinen Zugriff auf die Ressource. |
| 404 | nicht gefunden | Die Ressource konnte für den angegebenen Pfad nicht gefunden werden. |
| 409 | Konflikt | Die Anforderung konnte aufgrund eines Konflikts mit dem Zustand der Ressource nicht abgeschlossen werden. |
| 500 | Serverfehler | Auf dem Server ist ein unerwarteter Fehler aufgetreten, durch den die Anforderung nicht erfüllt werden konnte. |
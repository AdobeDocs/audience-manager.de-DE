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


# Erste Schritte mit REST-apis {#getting-started-with-rest-apis}

Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderungs-urls und anderen Referenzen.

<!-- c_rest_api_overview.xml -->

## API-Anforderungen und Empfehlungen {#api-requirements-recommendations}

Alles, was Sie tun müssen und sollten, wenn Sie mit Audience Manager [!DNL API]arbeiten.

<!-- aam-api-requirements.xml -->

Beachten Sie Folgendes, wenn Sie mit [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) -Code arbeiten:

* **Anforderungsparameter:** Alle Anforderungsparameter sind erforderlich, falls nicht anders angegeben.
* **[!DNL JSON]Inhaltstyp:** Geben Sie an `content-type: application/json`*und* `accept: application/json` in Ihrem Code.

* **Anforderungen und Antworten:** Senden Sie Anforderungen als ein ordnungsgemäß formatiertes [!DNL JSON] Objekt. [!DNL Audience Manager] mit [!DNL JSON] formatierten Daten beantwortet. Serverantworten können angeforderte Daten, einen Status-Code oder beides enthalten.

* **Zugriff:** Ihr [!DNL Audience Manager] Berater stellt Ihnen eine Client-ID und einen Schlüssel zur Verfügung, mit dem Sie Anforderungen erstellen [!DNL API] können.

* **Dokumentation und Codebeispiele:** *Kursiv gedruckter Text* stellt eine Variable dar, die Sie beim Erstellen oder Empfangen [!DNL API] von Daten bereitstellen oder weitergeben. Ersetzen *Sie Text mit Kursivschrift* durch Ihren eigenen Code, Parameter oder andere erforderliche Informationen.

## Recommendations: Generische API-Benutzer erstellen {#requirements}

Wir empfehlen Ihnen, ein separates technisches Benutzerkonto für die Arbeit mit Audience Manager [!DNL API]zu erstellen. Dies ist ein generisches Konto, das nicht an einen bestimmten Benutzer in Ihrer Organisation gebunden oder mit ihm verknüpft ist. Diese Art [!DNL API] von Benutzerkonto hilft Ihnen dabei, 2 Dinge zu erreichen:

* Identifizieren Sie, welche Service-Aufrufe der [!DNL API] Dienst aufruft (z. B. Aufrufe aus Ihren Apps, die unsere [!DNL API]oder anderen Tools, die [!DNL API] Anforderungen tätigen).
* Stellen Sie unterbrechungsfreien Zugriff auf [!DNL API]die s. Ein mit einer bestimmten Person verbundenes Konto kann gelöscht werden, wenn sie Ihr Unternehmen verlassen. Dadurch wird verhindert, dass Sie mit dem verfügbaren [!DNL API] Code arbeiten. Ein generisches Konto, das nicht an einen bestimmten Mitarbeiter gebunden ist, hilft Ihnen dabei, dieses Problem zu vermeiden.

Als Beispiel oder Anwendungsfall für diesen Kontotyp möchten wir einige Segmente auf einmal mit den [Massenverwaltungstools ändern](../../reference/bulk-management-tools/bulk-management-intro.md). Hierfür muss Ihr Benutzerkonto [!DNL API] Zugriff haben. Anstatt einem bestimmten Benutzer Berechtigungen hinzuzufügen, erstellen Sie ein nicht spezifisches [!DNL API] Benutzerkonto, das über die entsprechenden Anmeldeinformationen, Schlüssel und geheimen Schlüssel verfügt, um [!DNL API] Aufrufe durchzuführen. Dies ist auch hilfreich, wenn Sie Ihre eigenen Anwendungen entwickeln, die den Audience Manager [!DNL API]verwenden.

Arbeiten Sie mit Ihrem Audience Manager-Berater zusammen, um ein generisches, [!DNL API]einziges Benutzerkonto einzurichten.

## Oauth-Authentifizierung {#oauth}

Der Audience Manager [!UICONTROL REST API] befolgt [!DNL OAuth 2.0] Standards für die Token-Authentifizierung und -verlängerung. Die folgenden Abschnitte beschreiben, wie Sie die s [!DNL API]authentifizieren und mit ihnen arbeiten können.

## Kennwortauthentifizierungsarbeitsablauf {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Sicherer Zugriff auf Passwortauthentifizierung unser [!DNL REST API]. Die unten stehenden Schritte beschreiben den Arbeitsablauf für die Kennwortauthentifizierung von einem [!DNL JSON] Kunden in Ihrem Browser.

>[!TIP]
>
>Verschlüsseln Sie den Zugriff und aktualisieren Sie Token, wenn Sie sie in einer Datenbank speichern.

### Schritt 1: API-Zugriff anfordern

Wenden Sie sich an Ihren Partner Solutions Manager. Sie erhalten eine [!DNL API] Client-ID und einen geheimen Schlüssel. Die ID und die geheime Authentifizierung [!DNL API].

Hinweis: Wenn Sie ein Aktualisierungstoken erhalten möchten, geben Sie dieses an, wenn Sie [!DNL API] den Zugriff anfordern.

### Schritt 2: Token anfordern

Geben Sie eine Token-Anfrage mit Ihrem bevorzugten [!DNL JSON] Client an. Wenn Sie die Anforderung erstellen:

* Verwenden Sie eine `POST` Methode zum Aufrufen `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und den geheimen Schlüssel in eine base -64-kodierte Zeichenfolge. Trennen Sie die ID und den geheimen Schlüssel durch einen Doppelpunkt während des Konvertierungsprozesses. Beispielsweise werden die Anmeldeinformationen `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=`&quot;.
* Übergeben Sie die [!DNL HTTP] Header `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded` . Beispielsweise könnte Ihre Kopfzeile wie folgt aussehen: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=`<br/>`Content-Type: application/x-www-form-urlencoded`
* Richten Sie den Anforderungstext wie folgt ein:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Schritt 3: Empfangen des Tokens

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

Der `expires_in` Schlüssel stellt die Anzahl der Sekunden dar, bis das Zugriffstoken abläuft. Es empfiehlt sich, eine kurze Ablaufzeit zu verwenden, um die Exposition einzuschränken, wenn das Token jemals offen gelegt wird.

## Token aktualisieren {#refresh-token}

Aktualisierungstoken verlängern [!DNL API] den Zugriff nach Ablauf des ursprünglichen Token. Bei Bedarf enthält die Antwort [!DNL JSON] im Kennwortarbeitsablauf ein Aktualisierungstoken. Wenn Sie kein Aktualisierungstoken erhalten, erstellen Sie über den Kennwortauthentifizierungsprozess eine neue.

Sie können ein Aktualisierungstoken auch verwenden, um ein neues Token zu generieren, bevor das vorhandene Zugriffstoken abläuft.

Wenn Ihr Zugriffstoken abgelaufen ist, erhalten Sie einen `401 Status Code` und die folgende Kopfzeile in der Antwort:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Die folgenden Schritte beschreiben den Arbeitsablauf für die Verwendung eines Aktualisierungstokens, um ein neues Zugriffstoken von einem [!DNL JSON] Client in Ihrem Browser zu erstellen.

### Schritt 1: Neues Token anfordern

Geben Sie eine Aktualisierungstoken-Anfrage an Ihren bevorzugten [!DNL JSON] Client weiter. Wenn Sie die Anforderung erstellen:

* Verwenden Sie eine `POST` Methode zum Aufrufen `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und den geheimen Schlüssel in eine base -64-kodierte Zeichenfolge. Trennen Sie die ID und den geheimen Schlüssel durch einen Doppelpunkt während des Konvertierungsprozesses. Beispielsweise werden die Anmeldeinformationen `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=`&quot;.
* Übermitteln Sie die HTTP-Header `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded`. Beispielsweise könnte Ihre Kopfzeile wie folgt aussehen: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* Geben Sie im Anforderungskörper das `grant_type:refresh_token` Aktualisierungstoken an, das Sie in Ihrer vorherigen Zugriffsanforderung erhalten haben. Die Anfrage sollte wie folgt aussehen: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Schritt 2: Empfangen des neuen Token

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

Der Audience Manager [!UICONTROL REST API] unterstützt Autorisierungscode und implizite Authentifizierung. Um diese Zugriffsmethoden zu verwenden, müssen sich Ihre Benutzer anmelden, um `https://api.demdex.com/oauth/authorize` Zugriff zu erhalten und Token zu aktualisieren.

>[!MORE_ LIKE_ THIS]
>
>* [Oauth 2.0](https://oauth.net/2/)
>* [Oauth 2 vereinfacht](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)


## Authentifizierte API-Anforderungen erstellen {#authenticated-api-requests}

Anforderungen für die Aufrufmethode [!DNL API] , nachdem ein Authentifizierungstoken erhalten wurde.

<!-- c_oauth_call_methods.xml -->

So rufen Sie die verfügbaren [!DNL API] Methoden auf:

* Legen Sie in der `HTTP` Kopfzeile `Authorization: Bearer <token>`fest.
* Rufen Sie die erforderliche [!DNL API] Methode auf.

>[!MORE_ LIKE_ THIS]
>
>* [Oauth-Authentifizierung](../../api/rest-api-main/aam-api-getting-started.md#oauth)


## Optionale API-Abfrageparameter {#optional-api-query-parameters}

Legen Sie die optionalen Parameter fest, die für Methoden verfügbar sind, die alle Eigenschaften für ein Objekt zurückgeben.

<!-- c_rest_api_optional.xml -->

Sie können diese optionalen Parameter mit [!DNL API] Methoden verwenden, die *alle* Eigenschaften für ein Objekt zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an [!DNL API]&quot;an&quot; übergeben.

| Parameter | Beschreibung |
|--- |--- |
| Seite | Gibt Ergebnisse nach Seitenzahl zurück. Nummerierung beginnt bei 0. |
| Pagesize | Legt die Anzahl der von der Anforderung zurückgegebenen Antwortergebnisse fest (Standard: 10). |
| Sortby | Sortiert die Ergebnisse nach der angegebenen [!DNL JSON] Eigenschaft und gibt sie zurück. |
| absteigend | Sortiert die Ergebnisse in absteigender Reihenfolge und gibt sie zurück. Aufsteigend ist die Standardeinstellung. |
| Suche | Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle mit dem Wort &quot;Test&quot; in allen Wertfeldern für dieses Element suchen. Ihre Beispielanforderung könnte wie folgt aussehen: `GET https://api.demdex.com/v1/models/?search=Test`. Sie können nach jedem Wert suchen, der von einer &quot;get all&quot; -Methode zurückgegeben wird. |
| Folderid | Gibt alle IDs für Eigenschaften innerhalb des angegebenen Ordners zurück. Nicht für alle Methoden verfügbar. |
| Berechtigungen | Gibt eine Liste von Segmenten basierend auf der angegebenen Berechtigung zurück. READ ist Default. Zu den Berechtigungen gehören:<ul><li>`READ` : Geben Sie Informationen zu einem Segment zurück und zeigen Sie Informationen an.</li><li>`WRITE` : Dient `PUT` zum Aktualisieren eines Segments.</li><li>`CREATE` : Zum `POST` Erstellen eines Segments.</li><li>`DELETE` : Segmente löschen. Benötigt Zugriff auf die zugrunde liegenden Eigenschaften, falls vorhanden. Sie benötigen zum Beispiel Rechte zum Löschen der Eigenschaften, die zu einem Segment gehören, wenn Sie sie entfernen möchten.</li></ul><br>Geben Sie mehrere Berechtigungen für separate Schlüssel-Wert-Paare an. Wenn Sie beispielsweise eine Liste mit Segmenten mit `READ` und `WRITE` Berechtigungen zurückgeben möchten, geben `"permissions":"READ"``"permissions":"WRITE"` Sie an. |
| Includepermissions | (Boolescher Wert) Auf &quot;true&quot; setzen, um die Berechtigungen für das Segment zurückzugeben. Standard ist „false“. |

### Hinweis zu Seitenoptionen

Wenn keine Seiteninformationen *angegeben* sind, gibt die Anforderung einfache [!DNL JSON] Ergebnisse in einem Array zurück. Wenn Seiteninformationen ** angegeben werden, wird die zurückgegebene Liste in ein [!DNL JSON] Objekt eingeschlossen, das Informationen über das Gesamtergebnis und die aktuelle Seite enthält. Ihre Beispielanforderung mithilfe der Seitenoptionen könnte wie folgt aussehen:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API-URLs {#api-urls}

[!DNL URLs] für Anforderungen, Staging- und Produktionsumgebungen und Versionen.

<!-- r_rest_urls.xml -->

## Urls anfordern {#request-urls}

In der folgenden Tabelle sind die urls aufgeführt, die für die Übergabe [!DNL API] von Anforderungen nach Methode verwendet werden.

| [!DNL API] Methoden | Anfrage [!DNL URL] |
|--- |--- |
| Algorithmische Modellierung | `https://api.demdex.com/v1/models/` |
| Datenquelle | `https://api.demdex.com/v1/datasources/` |
| Abgeleitete Signale | `https://api.demdex.com/v1/signals/derived/` |
| Ziele | `https://api.demdex.com/v1/destinations/` |
| Domänen | `https://api.demdex.com/v1/partner-sites/` |
| Ordner | Eigenschaften: `https://api.demdex.com/v1/folders/traits /`<br>Segmente: `https://api.demdex.com/v1/folders/segments /` |
| Schema | `https://api.demdex.com/v1/schemas/` |
| Segmente | `https://api.demdex.com/v1/segments/` |
| Eigenschaften | `https://api.demdex.com/v1/traits/` |
| Trait-Typen | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomy | `https://api.demdex.com/v1/taxonomies/0/` |

## Umgebungen {#environments}

Die [!DNL Audience Manager][!DNL API]s bieten Zugriff auf verschiedene Arbeitsumgebungen. Diese Umgebungen helfen Ihnen, Code für separate Datenbanken zu testen, ohne dass sich dies auf die Live-Produktionsdaten auswirkt. In der folgenden Tabelle sind die verfügbaren [!DNL API] Umgebungen und die entsprechenden Ressourcen-Hostnamen aufgeführt.

| Umgebung | Hostname |
|---|---|
| **Produktion** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Die Beta-Umgebung von Audience Manager ist eine eigenständige, eigenständige Version der Produktionsumgebung. Alle Daten, die Sie testen möchten, müssen in dieser Umgebung eingegeben und erfasst werden.

## Versionen {#versions}

Neue Versionen dieser [!DNL API]s werden regelmäßig veröffentlicht. Mit einer neuen Version wird die [!DNL API] Versionsnummer erhöht. Auf die Versionsnummer wird in der Anforderungs-URL verwiesen, wie `v<version number>` im folgenden Beispiel gezeigt:

`https://<host>/v1/...`

## Definierte Antwortcodes {#response-codes-defined}

`HTTP` Statuscodes und Antworttext, der vom Audience Manager zurückgegeben [!UICONTROL REST API]wird.

<!-- r_api_http_response_codes.xml -->

| Antwortcode-ID | Antworttext | Definition |
|---|---|---|
| 200 |  OK- | Die Anforderung wurde erfolgreich verarbeitet. Gibt bei Bedarf erwartete Inhalte oder Daten zurück. |
| 201 | Erstellt | Die Ressource wurde erstellt. Gibt an `PUT` und `POST` Anforderungen. |
| 204 | Kein Inhalt | Die Ressource wurde gelöscht. Der Antwortkörper ist leer. |
| 400 | Unzulässige Anfrage | Der Server hat die Anforderung nicht verstanden. Normalerweise aufgrund einer falsch formatierten Syntax. Überprüfen Sie Ihre Anforderung und versuchen Sie es erneut. |
| 403 | Forbidden | Sie haben keinen Zugriff auf die Ressource. |
| 404 | nicht gefunden | Die Ressource konnte für den angegebenen Pfad nicht gefunden werden. |
| 409 | Konflikt | Die Anfrage konnte aufgrund eines Konflikts mit dem Status der Ressource nicht abgeschlossen werden. |
| 500 | Serverfehler | Der Server hat einen unerwarteten Fehler festgestellt, der die Erfüllung der Anforderung verhinderte. |
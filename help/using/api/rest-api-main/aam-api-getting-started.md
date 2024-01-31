---
description: Informationen zu allgemeinen Anforderungen, Authentifizierungen, optionalen Parametern für die Abfrage, Anforderungs-URLs und anderen Verweisen.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Erste Schritte mit REST-APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 16421f8f15a8aa8c1a561b0b6682091bf78683ce
workflow-type: tm+mt
source-wordcount: '2551'
ht-degree: 1%

---

# Erste Schritte mit [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderung [!DNL URLs]und andere Verweise.

## API-Anforderungen und Recommendations {#api-requirements-recommendations}

Beachten Sie Folgendes beim Arbeiten mit [Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#/) code:

* **Anforderungsparameter:** alle Anfrageparameter sind erforderlich, sofern nicht anders angegeben.
* **Anfragekopfzeilen**: bei Verwendung von [Adobe Developer](https://www.adobe.io/) Token, müssen Sie die `x-api-key` -Kopfzeile. Sie können Ihre [!DNL API] durch Befolgen der Anweisungen im [Integration von Dienstkonten](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) Seite.
* **[!DNL JSON]Inhaltstyp:** Angeben `content-type: application/json`  *und*  `accept: application/json` in Ihrem Code.
* **Anforderungen und Antworten:** Anforderungen als ordnungsgemäß formatiert senden [!DNL JSON] -Objekt. [!DNL Audience Manager] antwortet mit [!DNL JSON] formatierten Daten. Serverantworten können angeforderte Daten, einen Statuscode oder beides enthalten.
* **Zugriff:** Ihre [!DNL Audience Manager] -Berater stellt Ihnen eine Client-ID und einen Schlüssel zur Verfügung, mit der Sie [!DNL API] -Anfragen.
* **Dokumentation und Codebeispiele:** Text in *kursiv* stellt eine Variable dar, die Sie bereitstellen oder übergeben, wenn Sie [!DNL API] Daten. Ersetzen *kursiv* Text mit Ihrem eigenen Code, Ihren eigenen Parametern oder anderen erforderlichen Informationen.

## Authentifizierung {#authentication}

Die [!DNL Audience Manager] [!DNL REST APIs] unterstützt drei Authentifizierungsmethoden.

* [!BADGE Empfohlen]{type=positive}[OAuth-Server-zu-Server-Authentifizierung](#oauth-adobe-developer) using [Adobe-Entwicklerkonsole](https://www.adobe.io/). [!DNL Adobe Developer] ist das Ökosystem und die Community für Entwickler. Er umfasst [APIs für alle Adobe-Produkte](https://developer.adobe.com/apis/). Dies ist die empfohlene Einrichtung und Verwendung von [!DNL Adobe] [!DNL APIs]. Mehr dazu [OAuth-Server-zu-Server-Authentifizierung](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) in der Adobe-Entwicklerdokumentation.
* [!BADGE Veraltet]{type=negative}[JWT-Authentifizierung (Dienstkonto)](#jwt) using [Adobe-Entwicklerkonsole](https://www.adobe.io/). [!DNL Adobe Developer] ist das Ökosystem und die Community für Entwickler. Er umfasst [APIs für alle Adobe-Produkte](https://developer.adobe.com/apis/).
* [!BADGE Veraltet]{type=negative}[Alte OAuth-Authentifizierung](#oauth-deprecated). Diese Methode wird zwar nicht mehr unterstützt, Kunden mit vorhandenen [!DNL OAuth] Integrationen können diese Methode weiterhin verwenden.

>[!IMPORTANT]
>
>Abhängig von Ihrer Authentifizierungsmethode müssen Sie Ihre Anfrage anpassen [!DNL URLs] entsprechend. Siehe [Umgebungen](#environments) für Details zu den Hostnamen, die Sie verwenden sollten.

## OAuth-Server-zu-Server-Authentifizierung mit Adobe Developer {#oauth-adobe-developer}

In diesem Abschnitt wird beschrieben, wie Sie die erforderlichen Anmeldeinformationen erfassen, um Audience Manager-API-Aufrufe zu authentifizieren, wie im unten stehenden Flussdiagramm beschrieben. Sie können die meisten erforderlichen Anmeldeinformationen bei der ersten einmaligen Einrichtung erfassen. Das Zugriffstoken muss jedoch alle 24 Stunden aktualisiert werden.

![Flussdiagramm für die Authentifizierung von Audience Managern.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Übersicht über Adobe Developer {#developer-overview}

[!DNL Adobe Developer] ist das Ökosystem und die Community für Entwickler. Er umfasst [APIs für alle Adobe-Produkte](https://developer.adobe.com/apis).

Dies ist die empfohlene Einrichtung und Verwendung von [!DNL Adobe] [!DNL APIs].

### Voraussetzungen {#prerequisites-server-to-server}

Vor der Konfiguration [!DNL OAuth Server-to-Server] Authentifizierung, stellen Sie sicher, dass Sie Zugriff auf die [Adobe Developer-Konsole](https://developer.adobe.com/console/home) in [Adobe Developer](https://developer.adobe.com/). Wenden Sie sich für Zugriffsanfragen an Ihren Organisationsadministrator.

### Authentifizierung {#oauth}

Gehen Sie wie folgt vor, um [!DNL OAuth Server-to-Server] Authentifizierung mithilfe von [!DNL Adobe Developer]:

1. Melden Sie sich bei [Adobe Developer-Konsole](https://developer.adobe.com/console/home).
1. Führen Sie die Schritte im Abschnitt [OAuth-Implementierungshandbuch für Server-zu-Server-Anmeldedaten](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Während [Schritt 2: Hinzufügen einer API zu Ihrem Projekt mithilfe der Authentifizierung für Dienstkonten](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), wählen Sie die [!DNL Audience Manager] [!DNL API] -Option.
1. Probieren Sie die Verbindung aus, indem Sie Ihre erste [!DNL API] -Aufruf basierend auf den Anweisungen von [Schritt 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>So konfigurieren und arbeiten Sie mit dem [!DNL Audience Manager] [!DNL REST APIs] in automatisierter Weise können Sie Client-Geheimnisse programmgesteuert rotieren. Siehe [Entwicklerdokumentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) für detaillierte Anweisungen.

### Hinzufügen einer Audience Manager-API zu einem Projekt {#add-aam-api-to-project}

Navigieren Sie zu [Adobe Developer-Konsole](https://www.adobe.com/go/devs_console_ui) und melden Sie sich mit Ihrer Adobe ID an. Führen Sie anschließend die im Tutorial beschriebenen Schritte aus. [Erstellen eines leeren Projekts](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) in der Dokumentation zur Adobe Developer Console .

Nachdem Sie ein neues Projekt erstellt haben, wählen Sie **[!UICONTROL Add API]** auf **[!UICONTROL Project Overview]** angezeigt.

>[!TIP]
>
>Wenn Sie für mehrere Organisationen bereitgestellt sind, verwenden Sie die Organisationsauswahl in der oberen rechten Ecke der Benutzeroberfläche, um sicherzustellen, dass Sie sich in der gewünschten Organisation befinden.

![Bildschirm &quot;Entwicklerkonsole&quot;mit hervorgehobener Option &quot;API hinzufügen&quot;.](/help/using/api/rest-api-main/assets/add-api.png)

Die **[!UICONTROL Add an API]** angezeigt. Wählen Sie das Produktsymbol für Adobe Experience Cloud aus und wählen Sie dann **[!UICONTROL Audience Manager API]** vor der Auswahl **[!UICONTROL Next]**.

![Wählen Sie Audience Manager-API aus.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Wählen Sie die **[!UICONTROL View docs]** -Option, um in einem separaten Browserfenster zum Abschluss zu navigieren [Referenzdokumentation zur Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#).

### Wählen Sie den Authentifizierungstyp OAuth Server-zu-Server aus. {#select-oauth-server-to-server}

Wählen Sie anschließend den Authentifizierungstyp aus, um Zugriffstoken zu generieren und auf die Audience Manager-API zuzugreifen.

>[!IMPORTANT]
>
>Wählen Sie die **[!UICONTROL OAuth Server-to-Server]** -Methode, da dies künftig die einzige unterstützte Methode sein wird. Die **[!UICONTROL Service Account (JWT)]** -Methode veraltet ist. Während Integrationen, die die JWT-Authentifizierungsmethode verwenden, bis zum 1. Januar 2025 weiterhin funktionieren, empfiehlt Adobe dringend, vorhandene Integrationen vor diesem Datum auf die neue OAuth Server-zu-Server-Methode zu migrieren.

![Wählen Sie die OAuth-Authentifizierungsmethode aus.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Produktprofile für Ihre Integration auswählen {#select-product-profiles}

Im **[!UICONTROL Configure API]** die gewünschten Produktprofile aus. Das Dienstkonto Ihrer Integration erhält über die hier ausgewählten Produktprofile Zugriff auf granulare Funktionen.

![Wählen Sie Produktprofile für Ihre Integration aus.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Auswählen **[!UICONTROL Save configured API]** wenn Sie bereit sind.

### Sammeln von Anmeldeinformationen {#gather-credentials}

Nachdem die API zum Projekt hinzugefügt wurde, wird die **[!UICONTROL Audience Manager API]** -Seite für das Projekt werden die folgenden Anmeldeinformationen angezeigt, die für alle Aufrufe an Audience Manager-APIs erforderlich sind:

![Integrationsinformationen nach dem Hinzufügen einer API in der Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Zugriffstoken generieren {#generate-access-token}

Der nächste Schritt besteht darin, eine `{ACCESS_TOKEN}` Berechtigung zur Verwendung in Audience Manager-API-Aufrufen. Im Gegensatz zu den Werten für `{API_KEY}` und `{ORG_ID}`muss ein neues Token alle 24 Stunden generiert werden, damit Sie weiterhin Audience Manager-APIs verwenden können. Auswählen **[!UICONTROL Generate access token]**, wie unten dargestellt.

![Anzeigen der Generierung des Zugriffstokens](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## API-Aufruf testen {#test-api-call}

Nachdem Sie Ihr Authentifizierungs-Bearer-Token erhalten haben, führen Sie einen API-Aufruf durch, um zu testen, ob Sie jetzt auf Audience Manager-APIs zugreifen können.

1. Navigieren Sie zum [API-Referenzdokumentation](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Auswählen **[!UICONTROL Authorize]** und fügen Sie das Zugriffstoken ein, das Sie im [Zugriffstoken generieren](#generate-access-token) Schritt.

   ![API-Aufrufe zulassen](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Führen Sie einen GET-Aufruf an die `/datasources` API-Endpunkt zum Abrufen einer Liste aller global verfügbaren Datenquellen, wie in der [API-Referenzdokumentation](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Auswählen **[!UICONTROL Try it out]**, gefolgt von **[!UICONTROL Execute]**, wie unten dargestellt.

   ![Ausführen von API-Aufrufen](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB API-Anfrage]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB API-Antwort bei Verwendung des richtigen Trägertokens]


Bei Verwendung eines funktionierenden Zugriffs-Tokens gibt der API-Endpunkt eine Antwort &quot;200&quot;zusammen mit einem Antworttext zurück, der alle globalen Datenquellen enthält, auf die Ihr Unternehmen Zugriff hat.

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE Veraltet]{type=negative}[!DNL JWT] ([!DNL Service Account]) Authentifizierung mit Adobe Developer {#jwt}

+++ Informationen zu veralteten Elementen anzeigen [!DNL JWT] ([!DNL Service Account]) Methode zum Abrufen von Authentifizierungstoken.

### Übersicht über Adobe Developer {#adobeio}

[!DNL Adobe Developer] ist das Ökosystem und die Community für Entwickler. Er umfasst [APIs für alle Adobe-Produkte](https://www.adobe.io/apis.html).

Dies ist die empfohlene Einrichtung und Verwendung von [!DNL Adobe] [!DNL APIs].

### Voraussetzungen {#prerequisites}

Vor der Konfiguration [!DNL JWT] Authentifizierung, stellen Sie sicher, dass Sie Zugriff auf die [Adobe Developer-Konsole](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). Wenden Sie sich für Zugriffsanfragen an Ihren Organisationsadministrator.

### Authentifizierung {#auth}

Gehen Sie wie folgt vor, um [!DNL JWT (Service Account)] Authentifizierung mithilfe von [!DNL Adobe Developer]:

1. Melden Sie sich bei [Adobe Developer-Konsole](https://console.adobe.io/).
1. Führen Sie die Schritte unter [Service-Konto-Verbindung](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Während [Schritt 2: Hinzufügen einer API zu Ihrem Projekt mithilfe der Authentifizierung für Dienstkonten](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), wählen Sie die [!DNL Audience Manager] [!DNL API] -Option.
1. Probieren Sie die Verbindung aus, indem Sie Ihre erste [!DNL API] -Aufruf basierend auf den Anweisungen von [Schritt 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>So konfigurieren und arbeiten Sie mit dem [!DNL Audience Manager] [!DNL REST APIs] In automatisierter Weise können Sie die [!DNL JWT] programmiert. Siehe [JWT-Authentifizierung (Dienstkonto)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) für detaillierte Anweisungen.

### RBAC-Berechtigungen für technische Konten

Wenn Ihr Audience Manager-Konto [Rollenbasierte Zugriffssteuerung](../../features/administration/administration-overview.md)müssen Sie ein technisches Audience Manager-Benutzerkonto erstellen und es der Audience Manager-RBAC-Gruppe hinzufügen, die die API-Aufrufe durchführt.

Gehen Sie wie folgt vor, um ein technisches Benutzerkonto zu erstellen und es einer RBAC-Gruppe hinzuzufügen:

1. Erstellen Sie eine `GET` Aufruf von `https://aam.adobe.io/v1/users/self`. Durch den Aufruf wird ein technisches Benutzerkonto erstellt, das Sie im [!UICONTROL Admin Console]in der [!UICONTROL Users] Seite.

   ![technisches Konto](assets/technical-account.png)

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und [das technische Benutzerkonto hinzufügen](../../features/administration/administration-overview.md#create-group) an die Benutzergruppe, die die API-Aufrufe durchführt.

+++

## [!BADGE Veraltet]{type=negative}[!DNL OAuth] Authentifizierung (veraltet) {#oauth-deprecated}

+++ Informationen zur veralteten Version anzeigen [!DNL OAuth] Authentifizierungsmethode zum Abrufen von Authentifizierungstoken.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] Token-Authentifizierung und -Erneuerung über [!DNL OAuth 2.0] ist jetzt veraltet.
>
> Verwenden Sie [JWT-Authentifizierung (Dienstkonto)](#jwt-service-account-authentication-jwt) anstatt.

Die [!DNL Audience Manager] [!UICONTROL REST API] following [!DNL OAuth 2.0] Standards für die Token-Authentifizierung und -Erneuerung. In den folgenden Abschnitten wird beschrieben, wie Sie sich authentifizieren und mit der Arbeit mit dem [!DNL API]s.

### Generische Elemente erstellen [!DNL API] Benutzer {#requirements}

Es wird empfohlen, ein eigenes technisches Benutzerkonto für die Arbeit mit der [!DNL Audience Manager] [!DNL API]s. Dies ist ein allgemeines Konto, das nicht an einen bestimmten Benutzer in Ihrem Unternehmen gebunden ist oder mit diesem verknüpft ist. Diese Art von [!DNL API] Mit dem Benutzerkonto können Sie zwei Dinge erreichen:

* Identifizieren, welcher Dienst die [!DNL API] (z. B. Aufrufe aus Ihren Apps, die unsere [!DNL API]s oder von anderen Werkzeugen, die [!DNL API] -Anfragen).
* Ununterbrochenen Zugriff auf die [!DNL API]s. Ein Konto, das an eine bestimmte Person gebunden ist, kann gelöscht werden, wenn sie Ihr Unternehmen verlässt. Dadurch wird verhindert, dass Sie mit den verfügbaren [!DNL API] Code. Ein generisches Konto, das nicht an einen bestimmten Mitarbeiter gebunden ist, hilft Ihnen, dieses Problem zu vermeiden.

Nehmen wir als Beispiel oder Anwendungsfall für diesen Kontotyp an, Sie möchten viele Segmente gleichzeitig mit der [Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-management-intro.md). Dazu benötigt Ihr Benutzerkonto [!DNL API] Zugriff. Anstatt einem bestimmten Benutzer Berechtigungen hinzuzufügen, erstellen Sie eine unspezifische [!DNL API] Benutzerkonto mit den entsprechenden Anmeldeinformationen, Schlüsseln und Geheimnissen für [!DNL API] -Aufrufe. Dies ist auch nützlich, wenn Sie eigene Anwendungen entwickeln, die die [!DNL Audience Manager] [!DNL API]s.

Arbeiten mit [!DNL Audience Manager] Berater, um eine generische [!DNL API]- nur Benutzerkonto.

### Workflow zur Kennwortauthentifizierung {#password-authentication-workflow}

Sicherer Zugriff auf die Passwortauthentifizierung [!DNL REST API]. Die folgenden Schritte beschreiben den Workflow für die Kennwortauthentifizierung von einem [!DNL JSON] Client in Ihrem Browser.

>[!TIP]
>
>Verschlüsseln Sie den Zugriff und aktualisieren Sie Token, wenn Sie sie in einer Datenbank speichern.

#### Schritt 1: Anforderung [!DNL API] Zugriff

Wenden Sie sich an Ihren Partner Solutions Manager. Sie werden Ihnen eine [!DNL API] Client-ID und geheimer Schlüssel. Die Kennung und das Geheimnis authentifizieren Sie bei der [!DNL API].

Hinweis: Wenn Sie ein Aktualisierungstoken erhalten möchten, geben Sie dies bei Anforderung an [!DNL API] Zugriff.

#### Schritt 2: Anfordern des Tokens

Übergeben einer Token-Anfrage mit Ihrer bevorzugten [!DNL JSON] Client. Wenn Sie die Anforderung erstellen:

* Verwenden Sie eine `POST` -Methode zum Aufrufen `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise die Anmeldedaten `testId : testSecret` konvertieren in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Übergeben Sie die [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded` . Die Kopfzeile könnte beispielsweise wie folgt aussehen: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Richten Sie den Anfragetext wie folgt ein:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Schritt 3: Token erhalten

Die [!DNL JSON] -Antwort enthält Ihr Zugriffstoken. Die Antwort sollte wie folgt aussehen:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

Die `expires_in` key gibt die Anzahl der Sekunden an, bis das Zugriffstoken abläuft. Es hat sich bewährt, kurze Ablaufzeiten zu verwenden, um die Exposition zu begrenzen, wenn das Token jemals offen gelegt wird.

### Token aktualisieren {#refresh-token}

Token aktualisieren erneuern [!DNL API] -Zugriff nach Ablauf des ursprünglichen Tokens. Auf Anfrage wird die Antwort [!DNL JSON] enthält im Kennwort-Workflow ein Aktualisierungstoken. Wenn Sie kein Aktualisierungstoken erhalten, erstellen Sie mithilfe des Kennwortauthentifizierungsprozesses ein neues.

Sie können auch ein Aktualisierungstoken verwenden, um ein neues Token zu generieren, bevor das vorhandene Zugriffstoken abläuft.

Wenn Ihr Zugriffstoken abgelaufen ist, erhalten Sie eine `401 Status Code` und die folgende Kopfzeile in der Antwort:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Die folgenden Schritte beschreiben den Workflow für die Verwendung eines Aktualisierungstokens zum Erstellen eines neuen Zugriffstokens aus einem [!DNL JSON] Client in Ihrem Browser.

#### Schritt 1: Anfordern des neuen Tokens

Übergeben einer Aktualisierungs-Token-Anforderung mit Ihrer bevorzugten [!DNL JSON] Client. Wenn Sie die Anforderung erstellen:

* Verwenden Sie eine `POST` -Methode zum Aufrufen `https://api.demdex.com/oauth/token`.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise die Anmeldedaten `testId : testSecret` konvertieren in `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Übergeben von HTTP-Headern `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded`. Die Kopfzeile könnte beispielsweise wie folgt aussehen: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Geben Sie im Anfrageinhalt die `grant_type:refresh_token` und geben Sie das Aktualisierungs-Token weiter, das Sie in Ihrer vorherigen Zugriffsanfrage erhalten haben. Die Anfrage sollte wie folgt aussehen: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Schritt 2: Empfangen des neuen Tokens

Die [!DNL JSON] -Antwort enthält Ihr neues Zugriffstoken. Die Antwort sollte wie folgt aussehen:

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

Die [!DNL Audience Manager] [!UICONTROL REST API] unterstützt Autorisierungscode und implizite Authentifizierung. Um diese Zugriffsmethoden verwenden zu können, müssen sich Ihre Benutzer bei `https://api.demdex.com/oauth/authorize` , um auf Token zuzugreifen und sie zu aktualisieren.

+++

## Authentifizieren [!DNL API] Anforderungen {#authenticated-api-requests}

Anforderungen an den Aufruf von [!DNL API] Methoden, nachdem Sie ein Authentifizierungstoken erhalten haben.

So stellen Sie Aufrufe gegen die verfügbare bereit [!DNL API] -Methoden:

* Im `HTTP` Header, festgelegt `Authorization: Bearer <token>`.
* Bei Verwendung von [JWT-Authentifizierung (Dienstkonto)](#jwt), müssen Sie die `x-api-key` -Kopfzeile, die mit Ihrem `client_id`. Sie können Ihre `client_id` aus dem [Adobe Developer-Integration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) Seite.
* Rufen Sie die erforderliche [!DNL API] -Methode.

## Optional [!DNL API] Abfrageparameter {#optional-api-query-parameters}

Legen Sie die optionalen Parameter fest, die für Methoden verfügbar sind, die alle Eigenschaften für ein Objekt zurückgeben.

Sie können diese optionalen Parameter mit [!DNL API] zurückgegebene Methoden *all* -Eigenschaften für ein Objekt. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an die [!DNL API].

| Parameter | Beschreibung |
|--- |--- |
| `page` | Gibt Ergebnisse nach Seitenzahl zurück. Die Nummerierung beginnt bei 0. |
| `pageSize` | Legt die Anzahl der von der Anfrage zurückgegebenen Antwortergebnisse fest (standardmäßig 10). |
| `sortBy` | Sortiert Ergebnisse und gibt Ergebnisse gemäß den angegebenen zurück [!DNL JSON] -Eigenschaft. |
| `descending` | Sortiert Ergebnisse und gibt sie in absteigender Reihenfolge zurück. `ascending` ist Standard. |
| `search` | Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle mit dem Wort &quot;Test&quot;in einem der Wertefelder für dieses Element finden. Ihre Beispielanfrage könnte wie folgt aussehen:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Sie können nach jedem Wert suchen, der von einem[!DNL get all]&quot;. |
| `folderId` | Gibt alle IDs für [!UICONTROL traits] im angegebenen Ordner. Nicht für alle Methoden verfügbar. |
| `permissions` | Gibt eine Liste von Segmenten basierend auf der angegebenen Berechtigung zurück. `READ` ist Standard. Zu den Berechtigungen gehören:<ul><li>`READ` : Kehren Sie Informationen zu einem Segment zurück und zeigen Sie es an.</li><li>`WRITE` : Verwenden Sie  `PUT`  , um ein Segment zu aktualisieren.</li><li>`CREATE` : Verwenden Sie  `POST`  , um ein Segment zu erstellen.</li><li>`DELETE` : Löschen Sie ein Segment. Erfordert Zugriff auf zugrunde liegende Eigenschaften, falls vorhanden. Beispielsweise benötigen Sie Berechtigungen zum Löschen der Eigenschaften, die zu einem Segment gehören, wenn Sie es entfernen möchten.</li></ul><br>Geben Sie mehrere Berechtigungen mit separaten Schlüssel-Wert-Paaren an. So geben Sie beispielsweise eine Liste von Segmenten mit  `READ`  und  `WRITE`  nur Berechtigungen, weitergeben  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Legen Sie `true` , um Ihre Berechtigungen für das Segment zurückzugeben. Der Standardwert ist `false`. |

### Ein Hinweis zu Seitenoptionen

Wann Seiteninformationen *ist nicht* angegeben, gibt die Anfrage die Ebene zurück. [!DNL JSON] führt zu einem Array. Wenn Seiteninformationen *is* angegeben ist, wird die zurückgegebene Liste in ein [!DNL JSON] -Objekt, das Informationen zum Gesamtergebnis und zur aktuellen Seite enthält. Ihre Beispielanfrage mit Seitenoptionen könnte in etwa wie folgt aussehen:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] für Anforderungen, Staging- und Produktionsumgebungen und -versionen.

## Anfrage [!DNL URLs] {#request-urls}

Die folgende Tabelle listet die Anforderung auf [!DNL URLs] verwendet, um [!DNL API] -Anfragen nach Methode.

Abhängig von der verwendeten Authentifizierungsmethode müssen Sie Ihre Anfrage anpassen [!DNL URLs] entsprechend den unten stehenden Tabellen.

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

Die [!DNL Audience Manager] [!DNL API]bietet Zugriff auf verschiedene Arbeitsumgebungen. Diese Umgebungen helfen Ihnen beim Testen von Code mit separaten Datenbanken, ohne dass sich dies auf Live-Produktionsdaten auswirkt. In der folgenden Tabelle sind die verfügbaren [!DNL API] Umgebungen und die entsprechenden Ressourcen-Hostnamen.

Abhängig von der verwendeten Authentifizierungsmethode müssen Sie Ihre Umgebung anpassen [!DNL URLs] entsprechend der unten stehenden Tabelle.

| Umgebung | Hostname für [!DNL JWT] Authentifizierung | Hostname für [!DNL OAuth] Authentifizierung |
|---|---|---|
| **Produktion** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Die [!DNL Audience Manager] Die Beta-Umgebung ist eine kleinere, eigenständige Version der Produktionsumgebung. Alle Daten, die Sie testen möchten, müssen in dieser Umgebung eingegeben und erfasst werden.

## Versionen {#versions}

Neue Versionen dieser [!DNL API]s werden regelmäßig veröffentlicht. Bei einer neuen Version wird die [!DNL API] Versionsnummer. Die Versionsnummer wird in der Anfrage referenziert [!DNL URL] as `v<version number>` wie im folgenden Beispiel gezeigt:

`https://<host>/v1/...`

## Definierte Antwortcodes {#response-codes-defined}

`HTTP` Status-Codes und Antworttext, der von der [!DNL Audience Manager] [!UICONTROL REST API].

| Antwort-Code-ID | Antworttext | Definition |
|---|---|---|
| `200` | `OK` | Die Anfrage wurde erfolgreich verarbeitet. Gibt bei Bedarf erwartete Inhalte oder Daten zurück. |
| `201` | `Created` | Die Ressource wurde erstellt. Gibt für `PUT` und `POST` -Anfragen. |
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

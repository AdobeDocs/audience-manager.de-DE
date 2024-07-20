---
description: Informationen zu allgemeinen Anforderungen, Authentifizierungen, optionalen Parametern für die Abfrage, Anforderungs-URLs und anderen Verweisen.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Erste Schritte mit REST-APIs
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2558'
ht-degree: 1%

---

# Erste Schritte mit [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, Anforderung [!DNL URLs] und anderen Verweisen.

## API-Anforderungen und Recommendations {#api-requirements-recommendations}

Beachten Sie Folgendes beim Arbeiten mit dem Code der [Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#/):

* **Anforderungsparameter:** Alle Anforderungsparameter sind erforderlich, sofern nicht anders angegeben.
* **Anforderungsheader**: Bei Verwendung von [Adobe Developer](https://www.adobe.io/)-Token müssen Sie die Kopfzeile `x-api-key` angeben. Sie können Ihren [!DNL API] -Schlüssel abrufen, indem Sie die Anweisungen auf der Seite [Dienstkontointegration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) befolgen.
* **[!DNL JSON]Content-Typ:** Geben Sie `content-type: application/json` *und* `accept: application/json` in Ihren Code ein.
* **Anforderungen und Antworten:** Anforderungen als ordnungsgemäß formatiertes [!DNL JSON] -Objekt senden. [!DNL Audience Manager] antwortet mit [!DNL JSON] formatierten Daten. Serverantworten können angeforderte Daten, einen Statuscode oder beides enthalten.
* **Zugriff:** Ihr [!DNL Audience Manager] -Berater stellt Ihnen eine Client-ID und einen Schlüssel zur Verfügung, mit denen Sie [!DNL API] -Anfragen stellen können.
* **Dokumentation und Codebeispiele:** Text in *kursiv* stellt eine Variable dar, die Sie beim Erstellen oder Empfangen von [!DNL API] -Daten bereitstellen oder übergeben. Ersetzen Sie den Text *kursiv gedruckt* durch Ihren eigenen Code, Ihre eigenen Parameter oder andere erforderliche Informationen.

## Authentifizierung {#authentication}

Die [!DNL Audience Manager] [!DNL REST APIs] unterstützen drei Authentifizierungsmethoden.

* [!BADGE Empfohlen]{type=positive}[OAuth Server-zu-Server-Authentifizierung](#oauth-adobe-developer) mit der [Adobe-Entwicklerkonsole](https://www.adobe.io/). [!DNL Adobe Developer] ist das Ökosystem und die Community für Adobe. Es enthält [APIs für alle Adobe-Produkte](https://developer.adobe.com/apis/). Dies ist die empfohlene Methode zum Einrichten und Verwenden von [!DNL Adobe] [!DNL APIs]. Weitere Informationen zu [OAuth Server-zu-Server-Authentifizierung](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) finden Sie in der Adobe-Entwicklerdokumentation.
* [!BADGE veraltet]{type=negative}[JWT (Service Account)-Authentifizierung](#jwt) mit der [Adobe-Entwicklerkonsole](https://www.adobe.io/). [!DNL Adobe Developer] ist das Ökosystem und die Community für Adobe. Es enthält [APIs für alle Adobe-Produkte](https://developer.adobe.com/apis/).
* [!BADGE veraltet]{type=negative}[Legacy OAuth Authentication](#oauth-deprecated). Diese Methode wird zwar nicht mehr unterstützt, Kunden mit vorhandenen [!DNL OAuth] -Integrationen können diese Methode jedoch weiterhin verwenden.

>[!IMPORTANT]
>
>Abhängig von Ihrer Authentifizierungsmethode müssen Sie Ihre Anfrage [!DNL URLs] entsprechend anpassen. Weitere Informationen zu den Hostnamen, die Sie verwenden sollten, finden Sie im Abschnitt [Umgebungen](#environments) .

## OAuth-Server-zu-Server-Authentifizierung mit Adobe Developer {#oauth-adobe-developer}

In diesem Abschnitt wird beschrieben, wie Sie die erforderlichen Anmeldeinformationen erfassen, um Audience Manager-API-Aufrufe zu authentifizieren, wie im unten stehenden Flussdiagramm beschrieben. Sie können die meisten erforderlichen Anmeldeinformationen bei der ersten einmaligen Einrichtung erfassen. Das Zugriffstoken muss jedoch alle 24 Stunden aktualisiert werden.

![Diagramm für den Ablauf der Audience Manager-Authentifizierung.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Übersicht über Adobe Developer {#developer-overview}

[!DNL Adobe Developer] ist das Ökosystem und die Community für Adobe. Es enthält [APIs für alle Adobe-Produkte](https://developer.adobe.com/apis).

Dies ist die empfohlene Methode zum Einrichten und Verwenden von [!DNL Adobe] [!DNL APIs].

### Voraussetzungen {#prerequisites-server-to-server}

Bevor Sie die [!DNL OAuth Server-to-Server]-Authentifizierung konfigurieren können, stellen Sie sicher, dass Sie Zugriff auf die [Adobe Developer Console](https://developer.adobe.com/console/home) in [Adobe Developer](https://developer.adobe.com/) haben. Wenden Sie sich für Zugriffsanfragen an Ihren Organisationsadministrator.

### Authentifizierung {#oauth}

Gehen Sie wie folgt vor, um die [!DNL OAuth Server-to-Server]-Authentifizierung mit [!DNL Adobe Developer] zu konfigurieren:

1. Melden Sie sich bei [Adobe Developer Console](https://developer.adobe.com/console/home) an.
1. Führen Sie die Schritte im Implementierungshandbuch für &quot;OAuth Server-zu-Server-Anmeldedaten&quot;](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) aus.[
   * Wählen Sie während [Schritt 2: Hinzufügen einer API zu Ihrem Projekt mithilfe der Dienstkontoauthentifizierung](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) die Option [!DNL Audience Manager] [!DNL API] aus.
1. Probieren Sie die Verbindung aus, indem Sie Ihren ersten [!DNL API] -Aufruf anhand der Anweisungen aus [Schritt 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) durchführen.

>[!NOTE]
>
>Um die [!DNL Audience Manager] [!DNL REST APIs] automatisch zu konfigurieren und damit zu arbeiten, können Sie Client-Geheimnisse programmgesteuert drehen. Detaillierte Anweisungen finden Sie in der [Entwicklerdokumentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) .

### Hinzufügen einer Audience Manager-API zu einem Projekt {#add-aam-api-to-project}

Wechseln Sie zu [Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) und melden Sie sich mit Ihrer Adobe ID an. Führen Sie anschließend die im Tutorial zum Erstellen eines leeren Projekts [ in der Adobe Developer Console-Dokumentation beschriebenen Schritte aus.](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/)

Nachdem Sie ein neues Projekt erstellt haben, wählen Sie **[!UICONTROL Add API]** auf dem Bildschirm **[!UICONTROL Project Overview]** aus.

>[!TIP]
>
>Wenn Sie für mehrere Organisationen bereitgestellt sind, verwenden Sie die Organisationsauswahl in der oberen rechten Ecke der Benutzeroberfläche, um sicherzustellen, dass Sie sich in der gewünschten Organisation befinden.

![Developer Console-Bildschirm mit hervorgehobener Option &quot;API hinzufügen&quot;.](/help/using/api/rest-api-main/assets/add-api.png)

Der Bildschirm **[!UICONTROL Add an API]** wird angezeigt. Wählen Sie das Produktsymbol für Adobe Experience Cloud und dann **[!UICONTROL Audience Manager API]** aus, bevor Sie **[!UICONTROL Next]** auswählen.

![Wählen Sie die Audience Manager-API.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Wählen Sie die Option **[!UICONTROL View docs]** aus, um in einem separaten Browserfenster zur vollständigen [Audience Manager API-Referenzdokumentation](https://bank.demdex.com/portal/swagger/index.html#) zu navigieren.

### Wählen Sie den Authentifizierungstyp OAuth Server-zu-Server aus. {#select-oauth-server-to-server}

Wählen Sie anschließend den Authentifizierungstyp aus, um Zugriffstoken zu generieren und auf die Audience Manager-API zuzugreifen.

>[!IMPORTANT]
>
>Wählen Sie die Methode **[!UICONTROL OAuth Server-to-Server]** aus, da dies künftig die einzige unterstützte Methode sein wird. Die **[!UICONTROL Service Account (JWT)]** -Methode wird nicht mehr unterstützt. Während Integrationen, die die JWT-Authentifizierungsmethode verwenden, bis zum 1. Januar 2025 weiterhin funktionieren, empfiehlt Adobe dringend, vorhandene Integrationen vor diesem Datum auf die neue OAuth Server-zu-Server-Methode zu migrieren.

![Wählen Sie die OAuth-Authentifizierungsmethode aus.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Produktprofile für Ihre Integration auswählen {#select-product-profiles}

Wählen Sie im Bildschirm **[!UICONTROL Configure API]** die gewünschten Produktprofile aus. Das Dienstkonto Ihrer Integration erhält über die hier ausgewählten Produktprofile Zugriff auf granulare Funktionen.

![Wählen Sie Produktprofile für Ihre Integration aus.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Wählen Sie **[!UICONTROL Save configured API]** aus, wenn Sie bereit sind.

### Sammeln von Anmeldeinformationen {#gather-credentials}

Nachdem die API zum Projekt hinzugefügt wurde, zeigt die Seite &quot;**[!UICONTROL Audience Manager API]**&quot;für das Projekt die folgenden Anmeldeinformationen an, die für alle Aufrufe an Audience Manager-APIs erforderlich sind:

![Integrationsinformationen nach dem Hinzufügen einer API in Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Zugriffstoken generieren {#generate-access-token}

Der nächste Schritt besteht darin, eine `{ACCESS_TOKEN}` -Berechtigung für die Verwendung in Audience Manager-API-Aufrufen zu generieren. Im Gegensatz zu den Werten für `{API_KEY}` und `{ORG_ID}` muss alle 24 Stunden ein neues Token generiert werden, um weiterhin Audience Manager-APIs zu verwenden. Wählen Sie &quot;**[!UICONTROL Generate access token]**&quot;, wie unten dargestellt.

![Anzeigen der Erstellung des Zugriffs-Tokens](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## API-Aufruf testen {#test-api-call}

Nachdem Sie Ihr Authentifizierungs-Bearer-Token erhalten haben, führen Sie einen API-Aufruf durch, um zu testen, ob Sie jetzt auf Audience Manager-APIs zugreifen können.

1. Navigieren Sie zur [API-Referenzdokumentation](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Wählen Sie **[!UICONTROL Authorize]** aus und fügen Sie das Zugriffstoken ein, das Sie im Schritt [Zugriffstoken generieren](#generate-access-token) erhalten haben.

   ![API-Aufrufe autorisieren](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Führen Sie einen GET-Aufruf an den API-Endpunkt `/datasources` durch, um eine Liste aller global verfügbaren Datenquellen abzurufen, wie in der [API-Referenzdokumentation](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_) angegeben. Wählen Sie &quot;**[!UICONTROL Try it out]**&quot;, gefolgt von &quot;**[!UICONTROL Execute]**&quot;, wie unten dargestellt.

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


>[!TAB API-Antwort bei Verwendung des korrekten Bearer-Tokens]


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

## [!BADGE veraltet]{type=negative}[!DNL JWT] ([!DNL Service Account]) Authentifizierung mit Adobe Developer {#jwt}

+++ Informationen zur veralteten Methode [!DNL JWT] ([!DNL Service Account]) zum Abrufen von Authentifizierungstoken anzeigen.

### Übersicht über Adobe Developer {#adobeio}

[!DNL Adobe Developer] ist das Ökosystem und die Community für Adobe. Es enthält [APIs für alle Adobe-Produkte](https://www.adobe.io/apis.html).

Dies ist die empfohlene Methode zum Einrichten und Verwenden von [!DNL Adobe] [!DNL APIs].

### Voraussetzungen {#prerequisites}

Bevor Sie die [!DNL JWT]-Authentifizierung konfigurieren können, stellen Sie sicher, dass Sie Zugriff auf die [Adobe Developer Console](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/) haben. Wenden Sie sich für Zugriffsanfragen an Ihren Organisationsadministrator.

### Authentifizierung {#auth}

Gehen Sie wie folgt vor, um die [!DNL JWT (Service Account)]-Authentifizierung mit [!DNL Adobe Developer] zu konfigurieren:

1. Melden Sie sich bei [Adobe Developer Console](https://console.adobe.io/) an.
1. Führen Sie die Schritte unter [Verbindung mit Dienstkonten](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) aus.
   * Wählen Sie während [Schritt 2: Hinzufügen einer API zu Ihrem Projekt mithilfe der Dienstkontoauthentifizierung](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) die Option [!DNL Audience Manager] [!DNL API] aus.
1. Probieren Sie die Verbindung aus, indem Sie Ihren ersten [!DNL API] -Aufruf anhand der Anweisungen aus [Schritt 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) durchführen.

>[!NOTE]
>
>Um den [!DNL Audience Manager] [!DNL REST APIs] automatisiert zu konfigurieren und zu verwenden, können Sie den [!DNL JWT] programmatisch generieren. Detaillierte Anweisungen finden Sie unter [JWT (Service Account) Authentication](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) .

### RBAC-Berechtigungen für technische Konten

Wenn Ihr Audience Manager-Konto die [rollenbasierte Zugriffssteuerung](../../features/administration/administration-overview.md) verwendet, müssen Sie ein technisches Audience Manager-Benutzerkonto erstellen und es der Audience Manager-RBAC-Gruppe hinzufügen, die die API-Aufrufe durchführt.

Gehen Sie wie folgt vor, um ein technisches Benutzerkonto zu erstellen und es einer RBAC-Gruppe hinzuzufügen:

1. Rufen Sie `GET` auf `https://aam.adobe.io/v1/users/self`. Durch den Aufruf wird ein technisches Benutzerkonto erstellt, das Sie auf der Seite [!UICONTROL Users] unter [!UICONTROL Admin Console] sehen können.

   ![technisches Konto](assets/technical-account.png)

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und fügen Sie das technische Benutzerkonto ](../../features/administration/administration-overview.md#create-group) der Benutzergruppe hinzu, die die API-Aufrufe durchführt.[

+++

## [!BADGE veraltet]{type=negative}[!DNL OAuth] Authentifizierung (veraltet) {#oauth-deprecated}

+++ Zeigen Sie Informationen zur veralteten Authentifizierungsmethode [!DNL OAuth] an, mit der Authentifizierungstoken abgerufen werden.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] Token-Authentifizierung und -Erneuerung über [!DNL OAuth 2.0] ist jetzt veraltet.
>
> Verwenden Sie stattdessen die Authentifizierung mit [JWT (Dienstkonto)](#jwt-service-account-authentication-jwt).

Die [!DNL Audience Manager] [!UICONTROL REST API] befolgt [!DNL OAuth 2.0] Standards für die Token-Authentifizierung und -Erneuerung. In den folgenden Abschnitten wird beschrieben, wie Sie sich authentifizieren und mit den [!DNL API]s arbeiten.

### Generischen [!DNL API] Benutzer erstellen {#requirements}

Es wird empfohlen, ein separates technisches Benutzerkonto für die Arbeit mit den [!DNL Audience Manager] [!DNL API]s zu erstellen. Dies ist ein generisches Konto, das nicht an einen bestimmten Benutzer in Ihrem Unternehmen gebunden ist oder mit diesem verknüpft ist. Mit diesem Benutzerkonto vom Typ [!DNL API] können Sie zwei Dinge erreichen:

* Identifizieren Sie, welcher Dienst die [!DNL API] aufruft (z. B. Aufrufe aus Ihren Apps, die unsere [!DNL API] verwenden, oder aus anderen Tools, die [!DNL API] -Anfragen stellen).
* Gewähren Sie unterbrechungsfreien Zugriff auf die [!DNL API]s. Ein Konto, das an eine bestimmte Person gebunden ist, kann gelöscht werden, wenn sie Ihr Unternehmen verlässt. Dadurch wird verhindert, dass Sie mit dem verfügbaren [!DNL API] -Code arbeiten. Ein generisches Konto, das nicht an einen bestimmten Mitarbeiter gebunden ist, hilft Ihnen, dieses Problem zu vermeiden.

Nehmen wir als Beispiel oder Anwendungsfall für diesen Kontotyp an, Sie möchten viele Segmente gleichzeitig mit den [Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-management-intro.md) ändern. Dazu benötigt Ihr Benutzerkonto [!DNL API] Zugriff. Anstatt einem bestimmten Benutzer Berechtigungen hinzuzufügen, erstellen Sie ein unspezifisches Benutzerkonto mit dem Namen [!DNL API] , das über die entsprechenden Anmeldeinformationen, den Schlüssel und das Geheimnis verfügt, um [!DNL API] -Aufrufe durchzuführen. Dies ist auch nützlich, wenn Sie eigene Anwendungen entwickeln, die die [!DNL Audience Manager] [!DNL API]s verwenden.

Arbeiten Sie mit Ihrem [!DNL Audience Manager] -Berater zusammen, um ein generisches Benutzerkonto einzurichten, das nur für [!DNL API] gilt.

### Workflow zur Kennwortauthentifizierung {#password-authentication-workflow}

Passwortauthentifizierung sicher auf unsere [!DNL REST API] zugreifen. Die folgenden Schritte beschreiben den Workflow für die Kennwortauthentifizierung von einem [!DNL JSON] -Client in Ihrem Browser.

>[!TIP]
>
>Verschlüsseln Sie den Zugriff und aktualisieren Sie Token, wenn Sie sie in einer Datenbank speichern.

#### Schritt 1: Anfordern des Zugriffs auf [!DNL API]

Wenden Sie sich an Ihren Partner Solutions Manager. Sie erhalten eine [!DNL API] Client-ID und ein Geheimnis. Die Kennung und das Geheimnis authentifizieren Sie bei [!DNL API].

Hinweis: Wenn Sie ein Aktualisierungstoken erhalten möchten, geben Sie dies an, wenn Sie den Zugriff auf [!DNL API] anfordern.

#### Schritt 2: Anfordern des Tokens

Übergeben Sie eine Token-Anfrage an Ihren bevorzugten [!DNL JSON]-Client. Wenn Sie die Anforderung erstellen:

* Verwenden Sie eine `POST` -Methode, um `https://api.demdex.com/oauth/token` aufzurufen.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise werden die Anmeldedaten `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=` konvertiert.
* Übergeben Sie die [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded`. Die Kopfzeile könnte beispielsweise wie folgt aussehen: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Richten Sie den Anfragetext wie folgt ein:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Schritt 3: Token erhalten

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

Der Schlüssel `expires_in` gibt die Anzahl der Sekunden an, bis das Zugriffstoken abläuft. Es hat sich bewährt, kurze Ablaufzeiten zu verwenden, um die Exposition zu begrenzen, wenn das Token jemals offen gelegt wird.

### Token aktualisieren {#refresh-token}

Aktualisieren Sie Token, um den [!DNL API] -Zugriff zu verlängern, nachdem das ursprüngliche Token abläuft. Bei Bedarf enthält die Antwort [!DNL JSON] im Kennwort-Workflow ein Aktualisierungstoken. Wenn Sie kein Aktualisierungstoken erhalten, erstellen Sie mithilfe des Kennwortauthentifizierungsprozesses ein neues.

Sie können auch ein Aktualisierungstoken verwenden, um ein neues Token zu generieren, bevor das vorhandene Zugriffstoken abläuft.

Wenn Ihr Zugriffstoken abgelaufen ist, erhalten Sie einen `401 Status Code` -Wert und die folgende Kopfzeile in der Antwort:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Die folgenden Schritte beschreiben den Workflow für die Verwendung eines Aktualisierungstokens zum Erstellen eines neuen Zugriffstokens von einem [!DNL JSON] -Client in Ihrem Browser.

#### Schritt 1: Anfordern des neuen Tokens

Übergeben Sie eine Aktualisierungs-Token-Anfrage mit Ihrem bevorzugten [!DNL JSON]-Client. Wenn Sie die Anforderung erstellen:

* Verwenden Sie eine `POST` -Methode, um `https://api.demdex.com/oauth/token` aufzurufen.
* Konvertieren Sie Ihre Client-ID und Ihr Geheimnis in eine Base-64-kodierte Zeichenfolge. Trennen Sie die ID und das Geheimnis während des Konvertierungsprozesses durch einen Doppelpunkt. Beispielsweise werden die Anmeldedaten `testId : testSecret` in `dGVzdElkOnRlc3RTZWNyZXQ=` konvertiert.
* Übergeben Sie die HTTP-Header `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded`. Die Kopfzeile könnte beispielsweise wie folgt aussehen: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Geben Sie im Anfragetext den Wert &quot;`grant_type:refresh_token`&quot;an und übergeben Sie das Aktualisierungstoken, das Sie in Ihrer vorherigen Zugriffsanforderung erhalten haben. Die Anfrage sollte wie folgt aussehen: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

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

Die [!DNL Audience Manager] [!UICONTROL REST API] unterstützt Autorisierungscode und implizite Authentifizierung. Um diese Zugriffsmethoden verwenden zu können, müssen sich Ihre Benutzer bei `https://api.demdex.com/oauth/authorize` anmelden, um Zugriff auf Token zu erhalten und sie zu aktualisieren.

+++

## Authentifizierte [!DNL API] Anforderungen stellen {#authenticated-api-requests}

Voraussetzungen für den Aufruf von [!DNL API] -Methoden nach Erhalt eines Authentifizierungstokens.

So führen Sie Aufrufe für die verfügbaren [!DNL API] -Methoden durch:

* Legen Sie in der Kopfzeile `HTTP` den Wert `Authorization: Bearer <token>` fest.
* Bei Verwendung der [JWT (Service Account)-Authentifizierung](#jwt) müssen Sie die `x-api-key` -Kopfzeile angeben, die mit Ihrer `client_id` übereinstimmt. Sie können Ihre `client_id` von der Seite [Adobe Developer-Integration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) abrufen.
* Rufen Sie die erforderliche [!DNL API] -Methode auf.

## Optionale [!DNL API] Abfrageparameter {#optional-api-query-parameters}

Legen Sie die optionalen Parameter fest, die für Methoden verfügbar sind, die alle Eigenschaften für ein Objekt zurückgeben.

Sie können diese optionalen Parameter mit [!DNL API] -Methoden verwenden, die *alle* -Eigenschaften für ein Objekt zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an den [!DNL API] übergeben.

| Parameter | Beschreibung |
|--- |--- |
| `page` | Gibt Ergebnisse nach Seitenzahl zurück. Die Nummerierung beginnt bei 0. |
| `pageSize` | Legt die Anzahl der von der Anfrage zurückgegebenen Antwortergebnisse fest (standardmäßig 10). |
| `sortBy` | Sortiert Ergebnisse und gibt Ergebnisse gemäß der angegebenen [!DNL JSON] -Eigenschaft zurück. |
| `descending` | Sortiert Ergebnisse und gibt sie in absteigender Reihenfolge zurück. `ascending` ist der Standardwert. |
| `search` | Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle mit dem Wort &quot;Test&quot;in einem der Wertefelder für dieses Element finden. Ihre Beispielanfrage könnte wie folgt aussehen:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Sie können nach jedem Wert suchen, der von einer &quot;[!DNL get all]&quot;-Methode zurückgegeben wird. |
| `folderId` | Gibt alle IDs für [!UICONTROL traits] innerhalb des angegebenen Ordners zurück. Nicht für alle Methoden verfügbar. |
| `permissions` | Gibt eine Liste von Segmenten basierend auf der angegebenen Berechtigung zurück. `READ` ist der Standardwert. Zu den Berechtigungen gehören:<ul><li>`READ` : Gibt Informationen zu einem Segment zurück und zeigt sie an.</li><li>`WRITE` : Mit `PUT` können Sie ein Segment aktualisieren.</li><li>`CREATE` : Verwenden Sie `POST`, um ein Segment zu erstellen.</li><li>`DELETE` : Löschen Sie ein Segment. Erfordert Zugriff auf zugrunde liegende Eigenschaften, falls vorhanden. Beispielsweise benötigen Sie Berechtigungen zum Löschen der Eigenschaften, die zu einem Segment gehören, wenn Sie es entfernen möchten.</li></ul><br>Geben Sie mehrere Berechtigungen mit separaten Schlüssel-Wert-Paaren an. Um beispielsweise nur eine Liste von Segmenten mit `READ` - und `WRITE` -Berechtigungen zurückzugeben, geben Sie `"permissions":"READ"`, `"permissions":"WRITE"` ein. |
| `includePermissions` | ([!DNL Boolean]) Setzen Sie dies auf `true` , um Ihre Berechtigungen für das Segment zurückzugeben. Der Standardwert ist `false`. |

{style="table-layout:auto"}

### Ein Hinweis zu Seitenoptionen

Wenn die Seiteninformationen *nicht* angegeben sind, gibt die Anfrage nur [!DNL JSON] zurück, was zu einem Array führt. Wenn die Seiteninformationen *den Wert* aufweisen, wird die zurückgegebene Liste in ein [!DNL JSON] -Objekt eingeschlossen, das Informationen zum Gesamtergebnis und zur aktuellen Seite enthält. Ihre Beispielanfrage mit Seitenoptionen könnte in etwa wie folgt aussehen:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] für Anforderungen, Staging- und Produktionsumgebungen sowie Versionen.

## Anfrage [!DNL URLs] {#request-urls}

In der folgenden Tabelle ist die Anfrage [!DNL URLs] aufgeführt, die zum Übergeben von [!DNL API] -Anforderungen verwendet wird (nach Methode).

Abhängig von der verwendeten Authentifizierungsmethode müssen Sie Ihre Anfrage [!DNL URLs] entsprechend den Tabellen unten anpassen.

### Anfrage [!DNL URLs] für den [!BADGE empfohlenen ]{type=positive}[!BADGE veraltet]{type=negative}[!DNL JWT] Authentifizierung über Adobe Developer {#request-urls-jwt}

| [!DNL API] Methoden | Anfrage [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Eigenschaften: `https://aam.adobe.io/v1/folders/traits /`<br>Segmente: `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

{style="table-layout:auto"}

### Anfrage [!DNL URLs] für den [!BADGE veralteten ]{type=negative}[!DNL OAuth] Authentifizierung {#request-urls-oauth}

| [!DNL API] Methoden | Anfrage [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Eigenschaften: `https://api.demdex.com/v1/folders/traits /`<br>Segmente: `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

{style="table-layout:auto"}

## Umgebungen {#environments}

Die [!DNL Audience Manager] [!DNL API] bieten Zugriff auf verschiedene Arbeitsumgebungen. Diese Umgebungen helfen Ihnen beim Testen von Code mit separaten Datenbanken, ohne dass sich dies auf Live-Produktionsdaten auswirkt. In der folgenden Tabelle sind die verfügbaren [!DNL API] -Umgebungen und die entsprechenden Ressourcen-Hostnamen aufgeführt.

Abhängig von der verwendeten Authentifizierungsmethode müssen Sie Ihre Umgebung [!DNL URLs] entsprechend der unten stehenden Tabelle anpassen.

| Umgebung | Hostname für [!DNL JWT] Authentifizierung | Hostname für [!DNL OAuth] Authentifizierung |
|---|---|---|
| **Produktion** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Die Beta-Umgebung [!DNL Audience Manager] ist eine kleinere, eigenständige Version der Produktionsumgebung. Alle Daten, die Sie testen möchten, müssen in dieser Umgebung eingegeben und erfasst werden.

## Versionen {#versions}

Neue Versionen dieser [!DNL API]s werden regelmäßig veröffentlicht. Bei einer neuen Version wird die Versionsnummer [!DNL API] erhöht. Die Versionsnummer wird in der Anfrage [!DNL URL] als `v<version number>` referenziert, wie im folgenden Beispiel gezeigt:

`https://<host>/v1/...`

## Definierte Antwortcodes {#response-codes-defined}

`HTTP` Statuscodes und Antworttext, die von der [!DNL Audience Manager] [!UICONTROL REST API] zurückgegeben werden.

| Antwort-Code-ID | Antworttext | Definition |
|---|---|---|
| `200` | `OK` | Die Anfrage wurde erfolgreich verarbeitet. Gibt bei Bedarf erwartete Inhalte oder Daten zurück. |
| `201` | `Created` | Die Ressource wurde erstellt. Gibt für `PUT` - und `POST` -Anforderungen zurück. |
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
>* [OAuth 2 Vereinfacht](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

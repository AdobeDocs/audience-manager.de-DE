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
source-wordcount: '2563'
ht-degree: 1%

---

# Erste Schritte mit [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Informationen zu allgemeinen Anforderungen, Authentifizierung, optionalen Abfrageparametern, [!DNL URLs] und anderen Referenzen.

## API-Anforderungen und -Empfehlungen {#api-requirements-recommendations}

Beachten Sie Folgendes beim Arbeiten mit dem [Audience Manager-API](https://bank.demdex.com/portal/swagger/index.html#/)Code:

* **Anfrageparameter:** Anfrageparameter sind erforderlich, sofern nicht anders angegeben.
* **Anfragekopfzeilen**: Bei Verwendung von [Adobe Developer](https://www.adobe.io/)-Token müssen Sie die `x-api-key` Kopfzeile angeben. Sie können Ihren [!DNL API]-Schlüssel erhalten, indem Sie die Anweisungen auf der Seite [Service-Kontointegration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) befolgen.
* **[!DNL JSON]Content-Typ:** Geben Sie `content-type: application/json` *und* in Ihrem Code `accept: application/json`.
* **Anfragen und Antworten:** Senden von Anfragen als ordnungsgemäß formatiertes [!DNL JSON]. [!DNL Audience Manager] antwortet mit [!DNL JSON] formatierten Daten. Serverantworten können angeforderte Daten, einen Status-Code oder beides enthalten.
* **Zugriff** Ihr [!DNL Audience Manager] stellt Ihnen eine Client-ID und einen Schlüssel zur Verfügung, mit denen Sie [!DNL API] Anfragen stellen können.
* **Dokumentations- und Codebeispiele:** Text in *kursiv* stellt eine Variable dar, die Sie angeben oder übergeben, wenn Sie [!DNL API] Daten erstellen oder empfangen. Ersetzen *kursiv* Text durch eigenen Code, eigene Parameter oder andere erforderliche Informationen.

## Authentifizierung {#authentication}

Die [!DNL Audience Manager] [!DNL REST APIs] drei Authentifizierungsmethoden unterstützen.

* [!BADGE Empfohlen]{type=positive} [OAuth-Server-zu-Server-Authentifizierung](#oauth-adobe-developer) mithilfe der [Adobe-](https://www.adobe.io/). [!DNL Adobe Developer] ist Adobes Entwickler-Ökosystem und Community. Es enthält [APIs für alle Adobe-Produkte](https://developer.adobe.com/apis/). Dies ist die empfohlene Methode zum Einrichten und Verwenden [!DNL Adobe] [!DNL APIs]. Weitere Informationen zur [OAuth-Server-zu-Server-Authentifizierung](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) finden Sie in der Adobe-Entwicklerdokumentation.
* [!BADGE Veraltet]{type=negative} [JWT-Authentifizierung (Service-Konto](#jwt) mithilfe der [Adobe-](https://www.adobe.io/). [!DNL Adobe Developer] ist Adobes Entwickler-Ökosystem und Community. Es enthält [APIs für alle Adobe-Produkte](https://developer.adobe.com/apis/).
* [!BADGE Veraltet]{type=negative} [veraltete OAuth-Authentifizierung](#oauth-deprecated). Diese Methode ist zwar veraltet, aber Kunden mit vorhandenen [!DNL OAuth] können diese Methode weiterhin verwenden.

>[!IMPORTANT]
>
>Abhängig von Ihrer Authentifizierungsmethode müssen Sie Ihre [!DNL URLs] entsprechend anpassen. Siehe den [Umgebungen](#environments) für Details zu den Host-Namen, die Sie verwenden sollten.

## OAuth-Server-zu-Server-Authentifizierung mit Adobe Developer {#oauth-adobe-developer}

In diesem Abschnitt wird beschrieben, wie Sie die erforderlichen Anmeldeinformationen sammeln, um Audience Manager-API-Aufrufe zu authentifizieren, wie im folgenden Flussdiagramm beschrieben. Die meisten erforderlichen Anmeldeinformationen können bei der einmaligen Ersteinrichtung erfasst werden. Das Zugriffs-Token muss jedoch alle 24 Stunden aktualisiert werden.

![Flussdiagramm für die Audience Manager-Authentifizierung.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Übersicht über Adobe Developer {#developer-overview}

[!DNL Adobe Developer] ist Adobes Entwickler-Ökosystem und Community. Es enthält [APIs für alle Adobe-Produkte](https://developer.adobe.com/apis).

Dies ist die empfohlene Methode zum Einrichten und Verwenden [!DNL Adobe] [!DNL APIs].

### Voraussetzungen {#prerequisites-server-to-server}

Bevor Sie [!DNL OAuth Server-to-Server] Authentifizierung konfigurieren können, stellen Sie sicher, dass Sie Zugriff auf die [Adobe Developer Console](https://developer.adobe.com/console/home) in [Adobe Developer](https://developer.adobe.com/) haben. Wenden Sie sich an den Admin Ihrer Organisation, um Zugriffsanfragen zu erhalten.

### Authentifizierung {#oauth}

Gehen Sie wie folgt vor, um [!DNL OAuth Server-to-Server] Authentifizierung mithilfe von [!DNL Adobe Developer] zu konfigurieren:

1. Melden Sie sich bei der [Adobe Developer Console](https://developer.adobe.com/console/home) an.
1. Führen Sie die Schritte im [Handbuch zur Implementierung von OAuth-Server-zu-Server-Anmeldeinformationen](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) aus.
   * Wählen Sie [ Schritt 2: Hinzufügen einer API zu Ihrem Projekt mithilfe der Authentifizierung ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) Service-Kontos die Option [!DNL Audience Manager] [!DNL API] .
1. Probieren Sie die Verbindung aus, indem Sie Ihren ersten [!DNL API]-Aufruf auf der Grundlage der Anweisungen aus [Schritt 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) ausführen.

>[!NOTE]
>
>Um die [!DNL Audience Manager]-[!DNL REST APIs] automatisch zu konfigurieren und zu verwenden, können Sie Client-Geheimnisse programmgesteuert rotieren. Detaillierte Anweisungen finden [ in ](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically) Entwicklerdokumentation .

### Hinzufügen der Audience Manager-API zu einem Projekt {#add-aam-api-to-project}

Wechseln Sie zu [Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) und melden Sie sich mit Ihrer Adobe ID an. Führen Sie anschließend die Schritte aus, die im Tutorial zum [ eines leeren Projekts in ](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) Dokumentation zu Adobe Developer Console beschrieben werden.

Nachdem Sie ein neues Projekt erstellt haben, wählen Sie **[!UICONTROL Add API]** auf dem Bildschirm **[!UICONTROL Project Overview]** aus.

>[!TIP]
>
>Wenn Sie für mehrere Organisationen bereitgestellt wurden, verwenden Sie die Organisationsauswahl in der rechten oberen Ecke der Benutzeroberfläche von , um sicherzustellen, dass Sie sich in der gewünschten Organisation befinden.

![Developer Console-Bildschirm mit hervorgehobener Option „API hinzufügen“](/help/using/api/rest-api-main/assets/add-api.png)

Der Bildschirm **[!UICONTROL Add an API]** wird angezeigt. Klicken Sie auf das Produktsymbol für Adobe Experience Cloud und dann auf **[!UICONTROL Audience Manager API]** , bevor Sie **[!UICONTROL Next]** auswählen.

![Audience Manager-API auswählen.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Wählen Sie die Option **[!UICONTROL View docs]** aus, um in einem separaten Browserfenster zur vollständigen [Audience Manager API-Referenzdokumentation zu ](https://bank.demdex.com/portal/swagger/index.html#).

### Wählen Sie den Authentifizierungstyp OAuth Server-zu-Server aus {#select-oauth-server-to-server}

Wählen Sie als Nächstes den Authentifizierungstyp aus, um Zugriffstoken zu generieren und auf die Audience Manager-API zuzugreifen.

>[!IMPORTANT]
>
>Wählen Sie die **[!UICONTROL OAuth Server-to-Server]** Methode aus, da dies die einzige Methode ist, die in Zukunft unterstützt wird. Die **[!UICONTROL Service Account (JWT)]** Methode ist veraltet. Während Integrationen, die die JWT-Authentifizierungsmethode verwenden, bis zum 1. Januar 2025 weiterhin funktionieren, empfiehlt Adobe dringend, vorhandene Integrationen vor diesem Datum zu der neuen OAuth-Server-zu-Server-Methode zu migrieren.

![OAuth-Authentifizierungsmethode auswählen.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Auswählen der Produktprofile für Ihre Integration {#select-product-profiles}

Wählen Sie im **[!UICONTROL Configure API]** die gewünschten Produktprofile aus. Das Service-Konto Ihrer Integration erhält über die hier ausgewählten Produktprofile Zugriff auf granulare Funktionen.

![Produktprofile für Ihre Integration auswählen.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Wählen Sie **[!UICONTROL Save configured API]** aus, wenn Sie bereit sind.

### Sammeln von Anmeldeinformationen {#gather-credentials}

Nachdem die API zum Projekt hinzugefügt wurde, zeigt die **[!UICONTROL Audience Manager API]** für das Projekt die folgenden Anmeldeinformationen an, die für alle Aufrufe an Audience Manager-APIs erforderlich sind:

![Integrationsinformationen nach dem Hinzufügen einer API in Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Erstellen eines Zugriffs-Tokens {#generate-access-token}

Der nächste Schritt besteht darin, eine `{ACCESS_TOKEN}` für die Verwendung in Audience Manager-API-Aufrufen zu generieren. Im Gegensatz zu den Werten für `{API_KEY}` und `{ORG_ID}` muss alle 24 Stunden ein neues Token generiert werden, um Audience Manager-APIs weiterhin verwenden zu können. Wählen Sie **[!UICONTROL Generate access token]** aus, wie unten dargestellt.

![Erfahren Sie, wie Sie ein Zugriffs-Token generieren](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Testen eines API-Aufrufs {#test-api-call}

Nachdem Sie Ihr Authentifizierungs-Bearer-Token abgerufen haben, führen Sie einen API-Aufruf aus, um zu testen, ob Sie jetzt auf Audience Manager-APIs zugreifen können.

1. Navigieren Sie zur [API-Referenzdokumentation](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Wählen Sie **[!UICONTROL Authorize]** aus und fügen Sie das Zugriffstoken ein, das Sie im Schritt [Zugriffstoken generieren](#generate-access-token) erhalten haben.

   ![Autorisieren von API-Aufrufen](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Führen Sie einen GET-Aufruf an den `/datasources`-API-Endpunkt durch, um eine Liste aller global verfügbaren Datenquellen abzurufen, wie in der [API-Referenzdokumentation“ ](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Wählen Sie **[!UICONTROL Try it out]** und dann **[!UICONTROL Execute]** aus, wie unten dargestellt.

   ![API-Aufrufe durchführen](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB API-Anfrage]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB API-Antwort bei Verwendung des richtigen Bearer-Tokens]


Bei Verwendung eines funktionierenden Zugriffstokens gibt der API-Endpunkt eine Antwort von 200 zusammen mit einem Antworttext zurück, der alle globalen Datenquellen enthält, auf die Ihre Organisation Zugriff hat.

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

## [!BADGE Veraltet]{type=negative} [!DNL JWT] ([!DNL Service Account])-Authentifizierung mit Adobe Developer {#jwt}

+++ Zeigen Sie Informationen zur veralteten [!DNL JWT] ([!DNL Service Account]) zum Abrufen von Authentifizierungs-Token an.

### Übersicht über Adobe Developer {#adobeio}

[!DNL Adobe Developer] ist Adobes Entwickler-Ökosystem und Community. Es enthält [APIs für alle Adobe-Produkte](https://www.adobe.io/apis.html).

Dies ist die empfohlene Methode zum Einrichten und Verwenden [!DNL Adobe] [!DNL APIs].

### Voraussetzungen {#prerequisites}

Bevor Sie [!DNL JWT] Authentifizierung konfigurieren können, stellen Sie sicher, dass Sie Zugriff auf die [Adobe Developer Console](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/) haben. Wenden Sie sich an den Admin Ihrer Organisation, um Zugriffsanfragen zu erhalten.

### Authentifizierung {#auth}

Gehen Sie wie folgt vor, um [!DNL JWT (Service Account)] Authentifizierung mithilfe von [!DNL Adobe Developer] zu konfigurieren:

1. Melden Sie sich bei der [Adobe Developer Console](https://console.adobe.io/) an.
1. Führen Sie die Schritte unter [Service-Kontoverbindung](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) aus.
   * Wählen Sie [ Schritt 2: Hinzufügen einer API zu Ihrem Projekt mithilfe der Authentifizierung ](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) Service-Kontos die Option [!DNL Audience Manager] [!DNL API] .
1. Probieren Sie die Verbindung aus, indem Sie Ihren ersten [!DNL API]-Aufruf auf der Grundlage der Anweisungen aus [Schritt 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) ausführen.

>[!NOTE]
>
>Um die [!DNL Audience Manager]-[!DNL REST APIs] automatisch zu konfigurieren und zu verwenden, können Sie die [!DNL JWT] programmgesteuert generieren. Detaillierte Anweisungen finden [ unter „JWT](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)Authentifizierung (Service-Konto)“.

### RBAC-Berechtigungen für technisches Konto

Wenn Ihr Audience Manager-Konto [Rollenbasierte Zugriffssteuerung](../../features/administration/administration-overview.md) verwendet, müssen Sie ein technisches Audience Manager-Benutzerkonto erstellen und es zur Audience Manager-RBAC-Gruppe hinzufügen, die die API-Aufrufe durchführt.

Gehen Sie wie folgt vor, um ein technisches Benutzerkonto zu erstellen und es einer RBAC-Gruppe hinzuzufügen:

1. Rufen Sie `GET` `https://aam.adobe.io/v1/users/self` an. Mit dem Aufruf wird ein technisches Benutzerkonto erstellt, das Sie im [!UICONTROL Admin Console] auf der [!UICONTROL Users] Seite sehen können.

   ![Technisches Konto](assets/technical-account.png)

1. Melden Sie sich bei Ihrem Audience Manager-[ an und fügen Sie der Benutzergruppe](../../features/administration/administration-overview.md#create-group) die die API-Aufrufe durchführt, das technische Benutzerkonto hinzu.

+++

## [!BADGE Veraltet]{type=negative} [!DNL OAuth]-Authentifizierung (veraltet) {#oauth-deprecated}

+++ Zeigen Sie Informationen zur veralteten Authentifizierungsmethode für ältere [!DNL OAuth] zum Abrufen von Authentifizierungs-Token an.

>[!WARNING]
> [!DNL Audience Manager] Authentifizierung und Verlängerung von [!UICONTROL REST API]-Token über [!DNL OAuth 2.0] wird jetzt nicht mehr unterstützt.
>
> Verwenden Sie stattdessen [JWT-Authentifizierung (Service-Konto](#jwt-service-account-authentication-jwt).

Die [!DNL Audience Manager] [!UICONTROL REST API] entspricht [!DNL OAuth 2.0] Standards für die Token-Authentifizierung und -Erneuerung. In den folgenden Abschnitten wird beschrieben, wie Sie sich authentifizieren und mit den [!DNL API] arbeiten.

### Erstellen eines generischen [!DNL API] {#requirements}

Es wird empfohlen, ein separates technisches Benutzerkonto für die Arbeit mit den [!DNL Audience Manager] [!DNL API]s zu erstellen. Dies ist ein generisches Konto, das nicht mit einem bestimmten Benutzer in Ihrer Organisation verknüpft ist. Mit [!DNL API] Benutzerkonto können Sie zwei Dinge erreichen:

* Ermitteln Sie, welcher Service die [!DNL API] aufruft (z. B. Aufrufe von Ihren Apps, die unsere [!DNL API] verwenden, oder von anderen Tools, die [!DNL API] Anfragen stellen).
* Ununterbrochener Zugriff auf die [!DNL API]s. Ein Konto, das mit einer bestimmten Person verknüpft ist, kann gelöscht werden, wenn diese Person Ihr Unternehmen verlässt. Dadurch wird verhindert, dass Sie mit dem verfügbaren [!DNL API]-Code arbeiten. Ein generisches Konto, das nicht an einen bestimmten Mitarbeiter gebunden ist, hilft Ihnen, dieses Problem zu vermeiden.

Angenommen, Sie möchten mit den „Tools für die Massenverwaltung“ viele Segmente gleichzeitig ändern, [ Beispiel für diesen Kontotyp](../../reference/bulk-management-tools/bulk-management-intro.md). Dazu benötigt Ihr Benutzerkonto [!DNL API] Zugriff. Anstatt einem bestimmten Benutzer Berechtigungen hinzuzufügen, erstellen Sie ein unspezifisches, [!DNL API] Benutzerkonto, das über die entsprechenden Anmeldeinformationen, den Schlüssel und das Geheimnis verfügt, um [!DNL API] Aufrufe durchzuführen. Dies ist auch nützlich, wenn Sie Ihre eigenen Anwendungen entwickeln, die die [!DNL Audience Manager] der [!DNL API] verwenden.

Arbeiten Sie mit Ihrem [!DNL Audience Manager] Berater zusammen, um ein generisches, [!DNL API] Benutzerkonto einzurichten.

### Workflow zur Passwortauthentifizierung {#password-authentication-workflow}

Passwortauthentifizierung Sicherer Zugriff auf unsere [!DNL REST API]. Die folgenden Schritte beschreiben den Workflow für die Passwortauthentifizierung von einem [!DNL JSON]-Client in Ihrem Browser.

>[!TIP]
>
>Verschlüsseln Sie Zugriffs- und Aktualisierungstoken, wenn Sie sie in einer Datenbank speichern.

#### Schritt 1: [!DNL API] anfordern

Wenden Sie sich an Ihren Partner Solutions Manager. Sie erhalten eine [!DNL API] Client-ID und ein Geheimnis. Die ID und das Geheimnis authentifizieren Sie beim [!DNL API].

Hinweis: Wenn Sie ein Aktualisierungs-Token erhalten möchten, geben Sie dies an, wenn Sie [!DNL API] Zugriff anfordern.

#### Schritt 2: Token anfordern

Übergeben Sie eine Token-Anfrage mit Ihrem bevorzugten [!DNL JSON]. Beim Erstellen der Anfrage:

* Verwenden Sie eine `POST` Methode, um `https://api.demdex.com/oauth/token` aufzurufen.
* Konvertieren Sie Ihre Client-ID und Ihr Client-Geheimnis in eine mit Base-64 verschlüsselte Zeichenfolge. Trennen Sie ID und Geheimnis während des Konvertierungsprozesses mit einem Doppelpunkt. Beispielsweise `testId : testSecret` die Anmeldeinformationen in `dGVzdElkOnRlc3RTZWNyZXQ=` konvertiert.
* Übergeben Sie die [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded` . Ihre Kopfzeile könnte zum Beispiel wie folgt aussehen: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Richten Sie den Anfragetext wie folgt ein:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Schritt 3: Token empfangen

Die [!DNL JSON]-Antwort enthält Ihr Zugriffstoken. Die Antwort sollte wie folgt aussehen:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

Der `expires_in` stellt die Anzahl der Sekunden dar, bis das Zugriffstoken abläuft. Verwenden Sie als Best Practice kurze Ablaufzeiten, um die Verfügbarkeit zu begrenzen, wenn das Token jemals verfügbar ist.

### Token aktualisieren {#refresh-token}

Aktualisieren Sie Token, um [!DNL API] Zugriff nach Ablauf des ursprünglichen Tokens zu verlängern. Wenn angefordert, enthält die im Kennwort-Workflow [!DNL JSON] Antwort ein Aktualisierungs-Token. Wenn Sie kein Aktualisierungs-Token erhalten, erstellen Sie mithilfe der Kennwortauthentifizierung ein neues.

Sie können auch ein Aktualisierungs-Token verwenden, um ein neues Token zu generieren, bevor das vorhandene Zugriffs-Token abläuft.

Wenn Ihr Zugriffs-Token abgelaufen ist, erhalten Sie eine `401 Status Code` und die folgende Kopfzeile in der Antwort:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Die folgenden Schritte beschreiben den Workflow für die Verwendung eines Aktualisierungstokens zum Erstellen eines neuen Zugriffstokens von einem [!DNL JSON] Client in Ihrem Browser.

#### Schritt 1: Anfordern des neuen Tokens

Übergeben Sie eine Aktualisierungs-Token-Anfrage mit Ihrem bevorzugten [!DNL JSON]. Beim Erstellen der Anfrage:

* Verwenden Sie eine `POST` Methode, um `https://api.demdex.com/oauth/token` aufzurufen.
* Konvertieren Sie Ihre Client-ID und Ihr Client-Geheimnis in eine mit Base-64 verschlüsselte Zeichenfolge. Trennen Sie ID und Geheimnis während des Konvertierungsprozesses mit einem Doppelpunkt. Beispielsweise `testId : testSecret` die Anmeldeinformationen in `dGVzdElkOnRlc3RTZWNyZXQ=` konvertiert.
* Übergeben Sie die HTTP-Kopfzeilen `Authorization:Basic <base-64 clientID:clientSecret>` und `Content-Type: application/x-www-form-urlencoded`. Ihre Kopfzeile könnte zum Beispiel wie folgt aussehen: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Geben Sie im Anfragetext den `grant_type:refresh_token` an und übergeben Sie das Aktualisierungs-Token, das Sie in Ihrer vorherigen Zugriffsanfrage erhalten haben. Die Anfrage sollte wie folgt aussehen: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Schritt 2: Neues Token erhalten

Die [!DNL JSON]-Antwort enthält Ihr neues Zugriffstoken. Die Antwort sollte wie folgt aussehen:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### Autorisierungs-Code und implizite Authentifizierung {#authentication-code-implicit}

Die [!DNL Audience Manager]-[!UICONTROL REST API] unterstützt Autorisierungs-Code und implizite Authentifizierung. Um diese Zugriffsmethoden verwenden zu können, müssen sich Ihre Benutzer bei `https://api.demdex.com/oauth/authorize` anmelden, um Zugriffs- und Aktualisierungs-Token zu erhalten.

+++

## Authentifizierte [!DNL API] stellen {#authenticated-api-requests}

Anforderungen für den Aufruf von [!DNL API]-Methoden, nachdem Sie ein Authentifizierungs-Token erhalten haben.

So führen Sie Aufrufe für die verfügbaren [!DNL API] durch:

* Legen Sie in der `HTTP`-Kopfzeile `Authorization: Bearer <token>` fest.
* Bei Verwendung der [JWT (Service Account)-](#jwt) müssen Sie den `x-api-key`-Header angeben, der mit Ihrem `client_id` übereinstimmt. Ihre `client_id` erhalten Sie auf der Seite [Adobe Developer-Integration](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) .
* Rufen Sie die erforderliche [!DNL API] auf.

## Optionale [!DNL API] Abfrageparameter {#optional-api-query-parameters}

Legen Sie die optionalen Parameter fest, die für Methoden verfügbar sind, die alle Eigenschaften für ein -Objekt zurückgeben.

Sie können diese optionalen Parameter mit [!DNL API] Methoden verwenden, die *alle*-Eigenschaften für ein Objekt zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an den [!DNL API] übergeben.

| Parameter | Beschreibung |
|--- |--- |
| `page` | Gibt Ergebnisse nach Seitenzahl zurück. Nummerierung beginnt bei 0. |
| `pageSize` | Legt die Anzahl der von der Anfrage zurückgegebenen Antwortergebnisse fest (10 ist der Standardwert). |
| `sortBy` | Sortiert Ergebnisse entsprechend der angegebenen [!DNL JSON]-Eigenschaft und gibt sie zurück. |
| `descending` | Sortiert die Ergebnisse in absteigender Reihenfolge und gibt sie zurück. `ascending` ist Standard. |
| `search` | Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle finden, die das Wort „Test“ in einem der Wertefelder für dieses Element enthalten. Ihre Beispielanfrage könnte wie folgt aussehen:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Sie können nach jedem Wert suchen, der von einer &quot;[!DNL get all]&quot;-Methode zurückgegeben wird. |
| `folderId` | Gibt alle IDs für [!UICONTROL traits] innerhalb des angegebenen Ordners zurück. Nicht für alle Methoden verfügbar. |
| `permissions` | Gibt eine Liste mit Segmenten basierend auf der angegebenen Berechtigung zurück. `READ` ist Standard. Zu den Berechtigungen gehören:<ul><li>`READ` : Rückgabe und Anzeige von Informationen zu einem Segment.</li><li>`WRITE` : Verwenden Sie `PUT`, um ein Segment zu aktualisieren.</li><li>`CREATE` : Verwenden Sie `POST`, um ein Segment zu erstellen.</li><li>`DELETE` : Segment löschen. Erfordert Zugriff auf zugrunde liegende Eigenschaften, falls vorhanden. Sie benötigen beispielsweise Berechtigungen zum Löschen der Eigenschaften, die zu einem Segment gehören, wenn Sie es entfernen möchten.</li></ul><br>Geben Sie mehrere Berechtigungen mit separaten Schlüssel-Wert-Paaren an. Um beispielsweise eine Liste von Segmenten zurückzugeben, für die nur `READ`- und `WRITE`-Berechtigungen vorliegen, übergeben Sie `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Legen Sie auf `true` fest, um Ihre Berechtigungen für das Segment zurückzugeben. Der Standardwert ist `false`. |

{style="table-layout:auto"}

### Ein Hinweis zu Seitenoptionen

Wenn keine *angegeben ist* gibt die Anfrage einfache [!DNL JSON] in einem Array zurück. Wenn Seiteninformationen *angegeben* wird, wird die zurückgegebene Liste in ein [!DNL JSON] Objekt eingeschlossen, das Informationen zum Gesamtergebnis und zur aktuellen Seite enthält. Ihre Beispielanfrage mit Seitenoptionen könnte in etwa wie folgt aussehen:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] für Anfragen, Staging- und Produktionsumgebungen und Versionen.

## [!DNL URLs] anfordern {#request-urls}

In der folgenden Tabelle sind die [!DNL URLs] aufgeführt, die zum Übergeben von [!DNL API]-Anforderungen verwendet werden, aufgeschlüsselt nach Methode.

Je nach der von Ihnen verwendeten Authentifizierungsmethode müssen Sie Ihre [!DNL URLs] entsprechend den folgenden Tabellen anpassen.

### [!DNL URLs] für die OAuth[!BADGE Server-zu-Server-Authentifizierung ]{type=positive}empfohlen) und die [!BADGE -Authentifizierung ]{type=negative}veraltet[!DNL JWT] über Adobe Developer {#request-urls-jwt}

| [!DNL API] | [!DNL URL] anfordern |
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

### [!DNL URLs] für die [!BADGE veraltete]{type=negative} alte [!DNL OAuth] Authentifizierung anfordern {#request-urls-oauth}

| [!DNL API] | [!DNL URL] anfordern |
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

Die [!DNL Audience Manager] [!DNL API]s bieten Zugriff auf verschiedene Arbeitsumgebungen. Mit diesen Umgebungen können Sie Code mit separaten Datenbanken testen, ohne die Live- und Produktionsdaten zu beeinflussen. In der folgenden Tabelle sind die verfügbaren [!DNL API] Umgebungen und die entsprechenden Ressourcen-Host-Namen aufgeführt.

Je nach der von Ihnen verwendeten Authentifizierungsmethode müssen Sie Ihre [!DNL URLs] gemäß der folgenden Tabelle anpassen.

| Umgebung | Hostname für die [!DNL JWT] Authentifizierung | Hostname für die [!DNL OAuth] Authentifizierung |
|---|---|---|
| **Produktion** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Die [!DNL Audience Manager] Beta-Umgebung ist eine kleinere, eigenständige Version der Produktionsumgebung. Alle Daten, die getestet werden sollen, müssen in dieser Umgebung eingegeben und erfasst werden.

## Versionen {#versions}

Neue Versionen dieser [!DNL API]s werden nach einem regulären Zeitplan veröffentlicht. In einer neuen Version wird die [!DNL API] Versionsnummer erhöht. Die Versionsnummer wird im Anfrage-[!DNL URL] referenziert, wie im folgenden Beispiel `v<version number>`:

`https://<host>/v1/...`

## Antwort-Codes definiert {#response-codes-defined}

`HTTP` Status-Codes und Antworttext, die vom [!DNL Audience Manager]-[!UICONTROL REST API] zurückgegeben werden.

| Antwort-Code-ID | Antworttext | Definition |
|---|---|---|
| `200` | `OK` | Die Anfrage wurde erfolgreich verarbeitet. Gibt bei Bedarf den erwarteten Inhalt oder die erwarteten Daten zurück. |
| `201` | `Created` | Die Ressource wurde erstellt. Gibt für `PUT` und `POST` Anfragen zurück. |
| `204` | `No Content` | Die Ressource wurde gelöscht. Der Antworttext ist leer. |
| `400` | `Bad Request` | Der Server hat die Anfrage nicht verstanden. Normalerweise aufgrund einer fehlerhaften Syntax. Überprüfen Sie Ihre Anfrage und versuchen Sie es erneut. |
| `403` | `Forbidden` | Sie haben keinen Zugriff auf die Ressource. |
| `404` | `Not Found` | Die Ressource konnte für den angegebenen Pfad nicht gefunden werden. |
| `409` | `Conflict` | Die Anfrage konnte aufgrund eines Konflikts mit dem Status der Ressource nicht abgeschlossen werden. |
| `500` | `Server Error` | Der Server hat einen unerwarteten Fehler festgestellt, der ihn daran hinderte, die Anfrage zu erfüllen. |

>[!MORELIKETHIS]
>
>* [JWT-Authentifizierung (Service-Konto)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth-Authentifizierung](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 vereinfacht](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

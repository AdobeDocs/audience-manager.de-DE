---
description: Wenn Sie Segmente über eine Echtzeit-Server-zu-Server-Integration auf dem Partnerziel veröffentlichen, kann der Audience Manager beim Erstellen der Anforderungen mit oauth 2.0 authentifiziert werden. Dadurch können authentifizierte Anforderungen aus Audience Manager an Ihren Endpunkt gesendet werden.
seo-description: Wenn Sie Segmente über eine Echtzeit-Server-zu-Server-Integration auf dem Partnerziel veröffentlichen, kann der Audience Manager beim Erstellen der Anforderungen mit oauth 2.0 authentifiziert werden. Dadurch können authentifizierte Anforderungen aus Audience Manager an Ihren Endpunkt gesendet werden.
seo-title: Oauth 2.0-Integration für Echtzeit-Ausgehende Übertragungen
solution: Audience Manager
title: Oauth 2.0-Integration für Echtzeit-Ausgehende Übertragungen
uuid: a 39 e 370 c-b 3 bd -4 b 6-a 1 af -60 a 024 ee 7 ee 4
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] Integration für Echtzeit-Ausgehende Übertragungen{#oauth-integration-for-real-time-outbound-transfers}

When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using [!DNL OAuth 2.0] when making the requests. Dadurch können authentifizierte Anforderungen aus Audience Manager an Ihren Endpunkt gesendet werden.

## Authentication Flow {#auth-flow}

The [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) authentication implementation is based on the Client Credentials grant flow and follows these steps:

1. Sie müssen uns Folgendes bereitstellen:
   * The [!DNL OAuth 2.0] endpoint that generates the authentication token.
   * Die zum Generieren eines Tokens verwendeten Anmeldeinformationen.
1. An [!DNL Audience Manager] consultant sets up the [destination](../../../features/destinations/destinations.md) using the information you provided.
1. Once a segment is mapped to this destination, our real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), makes a `POST` request to the token endpoint to exchange the credentials for a bearer token.
1. For each segment publishing request to the partner endpoint, [!UICONTROL IRIS] uses the bearer token to authenticate.

![](assets/oauth2-iris.png)

## Voraussetzungen {#auth-requirements}

As an [!DNL Audience Manager] partner, the following endpoints are needed to receive authenticated requests:

### Von IRIS zum Abrufen eines Inhabertoken verwendeter Endpunkt 1

Dieser Endpunkt akzeptiert die in Schritt 1 angegebenen Anmeldeinformationen und generiert ein Inhabertoken, das bei nachfolgenden Anforderungen verwendet wird.

* The endpoint must accept `HTTP POST` requests.
* The endpoint must accept and look at the [!DNL Authorization] header. The value for this header will be: `Basic <credentials_provided_by_partner>`.
* The endpoint must look at the [!DNL Content-type] header and validate that its value is `application/x-www-form-urlencoded ; charset=UTF-8`.
* The body of the request will be `grant_type=client_credentials`.

### Beispielanfrage von Audience Manager an den Partner-Endpunkt, um ein Platzhaltertoken abzurufen

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### Beispielantwort vom Partner-Endpunkt

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Von IRIS zum Veröffentlichen von Segmenten mit dem bearer Token verwendete Endpunkt 2

[!DNL Audience Manager] sendet Daten in Echtzeit an diesen Endpunkt, wenn die Benutzer sich für Segmente qualifizieren. Darüber hinaus kann diese Methode Stapel von Offline- oder Onlinedaten so oft wie alle 24 Stunden senden.

Das durch Endpunkt 1 generierte Inhabertoken wird zur Ausgabe von Anforderungen an diesen Endpunkt verwendet. The [!DNL Audience Manager] real-time data transfer system, [IRIS](../../../reference/system-components/components-data-action.md#iris), constructs a normal HTTPS request and includes an Authorization header. The value for this header will be: Bearer `<bearer token from step 1>`.

### Beispielantwort vom Partner-Endpunkt

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>Diese Anforderung enthält eine Standardnutzlast (Inhalt anfordern).

## Important Considerations {#considerations}

### Tokens sind Kennwörter

The credentials presented by the partner and the tokens obtained by [!DNL Audience Manager] when authenticating using the [!DNL OAuth 2.0] flow, are sensitive information and must not be shared with third parties.

### [!DNL SSL] erforderlich

[!DNL SSL] muss verwendet werden, um einen sicheren Authentifizierungsprozess zu gewährleisten. All requests, including the ones used to obtain and use the tokens must use `HTTPS` endpoints.
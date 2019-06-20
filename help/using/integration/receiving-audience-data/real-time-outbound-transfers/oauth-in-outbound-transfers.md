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

Wenn Sie Segmente über eine Echtzeit-Server-zu-Server-Integration auf dem Partnerziel veröffentlichen, kann Audience Manager für die Authentifizierung mithilfe der [!DNL OAuth 2.0] Anforderungen eingerichtet werden. Dadurch können authentifizierte Anforderungen aus Audience Manager an Ihren Endpunkt gesendet werden.

## Authentifizierungsfluss {#auth-flow}

Die [!DNL Adobe Audience Manager][oauth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) -Authentifizierungsimplementierung basiert auf den Clientberechtigungen und folgt diesen Schritten:

1. Sie müssen uns Folgendes bereitstellen:
   * Der [!DNL OAuth 2.0] Endpunkt, der das Authentifizierungstoken generiert.
   * Die zum Generieren eines Tokens verwendeten Anmeldeinformationen.
1. Ein [!DNL Audience Manager] Berater richtet das [Ziel](../../../features/destinations/destinations.md) anhand der von Ihnen angegebenen Informationen ein.
1. Sobald ein Segment diesem Ziel zugeordnet ist, sendet unser Echtzeit-Datenübertragungssystem [IRIS](../../../reference/system-components/components-data-action.md#iris)eine `POST` Anforderung an den Tokenendpunkt, um die Anmeldeinformationen für ein Inhabertoken auszutauschen.
1. Verwendet für jede Segmentveröffentlichungsanfrage an den Partner-Endpunkt [!UICONTROL IRIS] das Inhabertoken zur Authentifizierung.

![](assets/oauth2-iris.png)

## Voraussetzungen {#auth-requirements}

Als [!DNL Audience Manager] Partner sind die folgenden Endpunkte zum Erhalt authentifizierter Anforderungen erforderlich:

### Von IRIS zum Abrufen eines Inhabertoken verwendeter Endpunkt 1

Dieser Endpunkt akzeptiert die in Schritt 1 angegebenen Anmeldeinformationen und generiert ein Inhabertoken, das bei nachfolgenden Anforderungen verwendet wird.

* Der Endpunkt muss `HTTP POST` Anforderungen akzeptieren.
* Der Endpunkt muss die [!DNL Authorization] Kopfzeile akzeptieren und überprüfen. Der Wert für diese Kopfzeile lautet: `Basic <credentials_provided_by_partner>`.
* Der Endpunkt muss sich die [!DNL Content-type] Kopfzeile ansehen und überprüfen, ob der Wert ist `application/x-www-form-urlencoded ; charset=UTF-8`.
* Der Hauptteil der Anforderung `grant_type=client_credentials`.

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

Das durch Endpunkt 1 generierte Inhabertoken wird zur Ausgabe von Anforderungen an diesen Endpunkt verwendet. Das [!DNL Audience Manager] Echtzeit-Datenübertragungssystem [, IRIS](../../../reference/system-components/components-data-action.md#iris), erstellt eine normale HTTPS-Anforderung und enthält eine Autorisierungskopfzeile. Der Wert für diese Kopfzeile lautet: Bearer `<bearer token from step 1>`.

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

## Wichtige Überlegungen {#considerations}

### Tokens sind Kennwörter

Die vom Partner dargestellten Berechtigungen und die von [!DNL Audience Manager] der Authentifizierung mit dem [!DNL OAuth 2.0] Fluss erhaltenen Token sind sensible Informationen und dürfen nicht für Dritte freigegeben werden.

### [!DNL SSL] erforderlich

[!DNL SSL] muss verwendet werden, um einen sicheren Authentifizierungsprozess zu gewährleisten. Alle Anforderungen, einschließlich der zum Abrufen und Verwenden der Token verwendeten Anforderungen, müssen `HTTPS` Endpunkte verwenden.
---
description: Beim Veröffentlichen von Segmenten an das Partnerziel über eine Echtzeit-Server-zu-Server-Integration kann der -Audience Manager so eingerichtet werden, dass er sich bei Anfragen mit OAuth 2.0 authentifiziert. Dadurch wird die Möglichkeit geboten, authentifizierte Anfragen von Audience Manager an Ihren Endpunkt zu senden.
seo-description: When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using OAuth 2.0 when making the requests. This presents the ability to issue authenticated requests from Audience Manager to your endpoint.
seo-title: OAuth 2.0 Integration for Real-Time Outbound Transfers
solution: Audience Manager
title: OAuth 2.0-Integration für ausgehende Echtzeit-Übertragungen
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# [!DNL OAuth 2.0] für ausgehende Echtzeit-Übertragungen{#oauth-integration-for-real-time-outbound-transfers}

Beim Veröffentlichen von Segmenten im Partnerziel über eine Echtzeit-Server-zu-Server-Integration kann der -Audience Manager so eingerichtet werden, dass er sich bei Anfragen über [!DNL OAuth 2.0] authentifiziert. Dadurch wird die Möglichkeit geboten, authentifizierte Anfragen von Audience Manager an Ihren Endpunkt zu senden.

## Authentifizierungsfluss {#auth-flow}

Die [!DNL Adobe Audience Manager] Authentifizierungsimplementierung [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) basiert auf dem Fluss zur Gewährung von Client-Anmeldeinformationen und führt die folgenden Schritte aus:

1. Sie müssen uns Folgendes zur Verfügung stellen:
   * Der [!DNL OAuth 2.0]-Endpunkt, der das Authentifizierungstoken generiert.
   * Die zum Generieren eines Tokens verwendeten Anmeldedaten.
1. Ein [!DNL Audience Manager] Berater richtet das [Ziel](../../../features/destinations/destinations.md) anhand der von Ihnen bereitgestellten Informationen ein.
1. Sobald ein Segment diesem Ziel zugeordnet ist, sendet unser Echtzeit-Datenübertragungssystem [IRIS](../../../reference/system-components/components-data-action.md#iris) eine `POST` Anfrage an den Token-Endpunkt, um die Anmeldeinformationen gegen ein Bearer-Token einzutauschen.
1. Für jede Segmentveröffentlichungsanfrage an den Partnerendpunkt verwendet [!UICONTROL IRIS] das Bearer-Token zur Authentifizierung.

![](assets/oauth2-iris.png)

## Anforderungen {#auth-requirements}

Als [!DNL Audience Manager]-Partner werden die folgenden Endpunkte benötigt, um authentifizierte Anfragen zu empfangen:

### Endpunkt 1, der von IRIS zum Abrufen eines Bearer-Tokens verwendet wird

Dieser Endpunkt akzeptiert die in Schritt 1 angegebenen Anmeldeinformationen und generiert ein Bearer-Token, das bei nachfolgenden Anfragen verwendet wird.

* Der Endpunkt muss `HTTP POST` Anfragen akzeptieren.
* Der Endpunkt muss die [!DNL Authorization]-Kopfzeile akzeptieren und anzeigen. Der Wert für diese Kopfzeile lautet: `Basic <credentials_provided_by_partner>`.
* Der Endpunkt muss sich den [!DNL Content-type] Header ansehen und überprüfen, ob sein Wert `application/x-www-form-urlencoded ; charset=UTF-8` ist.
* Der Text der Anfrage wird `grant_type=client_credentials`.

### Beispielanfrage des Audience Managers an den Partnerendpunkt, um ein Bearer-Token zu erhalten

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

### Beispielantwort vom Partnerendpunkt

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Endpunkt 2, der von IRIS verwendet wird, um Segmente mithilfe des Bearer-Tokens zu veröffentlichen

[!DNL Audience Manager] sendet Daten nahezu in Echtzeit an diesen Endpunkt, da Benutzer für Segmente qualifiziert sind. Darüber hinaus kann diese Methode Batches mit Offline- oder Onboarding-Daten so häufig wie alle 24 Stunden senden.

Das von Endpunkt 1 generierte Bearer-Token wird verwendet, um Anfragen an diesen Endpunkt zu senden. Das [!DNL Audience Manager] Echtzeit-Datenübertragungssystem ([) ](../../../reference/system-components/components-data-action.md#iris) eine normale HTTPS-Anfrage und enthält eine Autorisierungs-Kopfzeile. Der Wert für diese Kopfzeile lautet: Bearer-`<bearer token from step 1>`.

### Beispielantwort vom Partnerendpunkt

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
>Diese Anfrage enthält eine Standard-Payload (Anfrageinhalt).

## Wichtige Überlegungen {#considerations}

### Token sind Passwörter

Die vom Partner präsentierten Anmeldeinformationen und die Token, die von [!DNL Audience Manager] bei der Authentifizierung über den [!DNL OAuth 2.0] erhalten wurden, sind vertrauliche Informationen und dürfen nicht an Dritte weitergegeben werden.

### [!DNL SSL] ist erforderlich

[!DNL SSL] muss verwendet werden, um einen sicheren Authentifizierungsprozess aufrechtzuerhalten. Alle Anfragen, einschließlich der Anfragen, die zum Abrufen und Verwenden der Token verwendet werden, müssen `HTTPS` Endpunkte verwenden.

---
description: Beim Veröffentlichen von Segmenten am Partnerziel über eine Echtzeit-Server-zu-Server-Integration kann Audience Manager so eingerichtet werden, dass die Authentifizierung beim Erstellen der Anforderungen mit OAuth 2.0 erfolgt. Dies bietet die Möglichkeit, authentifizierte Anfragen von Audience Manager bis zu Ihrem Endpunkt auszustellen.
seo-description: Beim Veröffentlichen von Segmenten am Partnerziel über eine Echtzeit-Server-zu-Server-Integration kann Audience Manager so eingerichtet werden, dass die Authentifizierung beim Erstellen der Anforderungen mit OAuth 2.0 erfolgt. Dies bietet die Möglichkeit, authentifizierte Anfragen von Audience Manager bis zu Ihrem Endpunkt auszustellen.
seo-title: OAuth 2.0-Integration für ausgehende Übertragungen in Echtzeit
solution: Audience Manager
title: OAuth 2.0-Integration für ausgehende Übertragungen in Echtzeit
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---


# [!DNL OAuth 2.0] Integration für ausgehende Echtzeit-Transfers{#oauth-integration-for-real-time-outbound-transfers}

Beim Veröffentlichen von Segmenten am Partnerziel über eine Echtzeit-Server-zu-Server-Integration kann Audience Manager so eingerichtet werden, dass die Authentifizierung bei Anforderungen mit [!DNL OAuth 2.0] erfolgt. Dies bietet die Möglichkeit, authentifizierte Anfragen von Audience Manager bis zu Ihrem Endpunkt auszustellen.

## Authentifizierungsfluss {#auth-flow}

Die [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4)-Authentifizierungsimplementierung basiert auf dem Grant-Fluss mit Clientanmeldeinformationen und führt folgende Schritte aus:

1. Sie müssen uns Folgendes zur Verfügung stellen:
   * Der [!DNL OAuth 2.0]-Endpunkt, der das Authentifizierungstoken generiert.
   * Die Anmeldeinformationen, mit denen ein Token generiert wird.
1. Ein [!DNL Audience Manager]-Berater richtet das [Ziel](../../../features/destinations/destinations.md) mithilfe der von Ihnen angegebenen Informationen ein.
1. Sobald ein Segment diesem Ziel zugeordnet ist, sendet unser Echtzeit-Datenübertragungssystem [IRIS](../../../reference/system-components/components-data-action.md#iris) eine `POST`-Anforderung an den Token-Endpunkt, um die Anmeldeinformationen für ein Inhabertoken auszutauschen.
1. Für jede Segmentveröffentlichungsanforderung am Partnerendpunkt verwendet [!UICONTROL IRIS] das Inhabertoken zur Authentifizierung.

![](assets/oauth2-iris.png)

## Anforderungen {#auth-requirements}

Als Partner für [!DNL Audience Manager] sind die folgenden Endpunkte erforderlich, um authentifizierte Anforderungen zu empfangen:

### Endpunkt 1, der von IRIS verwendet wird, um ein Inhabertoken zu erhalten

Dieser Endpunkt akzeptiert die in Schritt 1 angegebenen Anmeldeinformationen und generiert ein Inhabertoken, das bei nachfolgenden Anforderungen verwendet wird.

* Der Endpunkt muss `HTTP POST`-Anforderungen akzeptieren.
* Der Endpunkt muss die [!DNL Authorization]-Kopfzeile akzeptieren und anzeigen. Der Wert für diese Kopfzeile lautet: `Basic <credentials_provided_by_partner>`.
* Der Endpunkt muss sich die Überschrift [!DNL Content-type] ansehen und überprüfen, ob der Wert `application/x-www-form-urlencoded ; charset=UTF-8` lautet.
* Der Hauptteil der Anforderung ist `grant_type=client_credentials`.

### Beispielanfrage des Audience Managers zum Partnerendpunkt, um ein InhaberToken zu erhalten

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

### Endpunkt 2, der von IRIS verwendet wird, um Segmente mit dem Inhabertoken zu veröffentlichen

[!DNL Audience Manager] sendet Daten in Echtzeit an diesen Endpunkt, da sich Benutzer für Segmente qualifizieren. Darüber hinaus kann diese Methode Stapel von Offline- oder Onboarded-Daten bis zu 24 Stunden senden.

Das vom Endpunkt 1 generierte Inhabertoken wird verwendet, um Anforderungen an diesen Endpunkt auszugeben. Das [!DNL Audience Manager] Echtzeit-Datenübertragungssystem [IRIS](../../../reference/system-components/components-data-action.md#iris) erstellt eine normale HTTPS-Anforderung und enthält einen Autorisierungs-Header. Der Wert für diese Kopfzeile lautet: Träger `<bearer token from step 1>`.

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
>Diese Anforderung enthält eine Standard-Nutzlast (Anforderungsinhalt).

## Wichtige Überlegungen {#considerations}

### Tokens sind Kennwörter

Die vom Partner vorgelegten Anmeldeinformationen und die von [!DNL Audience Manager] bei der Authentifizierung mit dem [!DNL OAuth 2.0]-Fluss erhaltenen Token sind vertrauliche Informationen und dürfen nicht an Dritte weitergegeben werden.

### [!DNL SSL] erforderlich

[!DNL SSL] muss verwendet werden, um einen sicheren Authentifizierungsprozess aufrechtzuerhalten. Alle Anforderungen, einschließlich der zum Abrufen und Verwenden der Token verwendeten, müssen `HTTPS`-Endpunkte verwenden.
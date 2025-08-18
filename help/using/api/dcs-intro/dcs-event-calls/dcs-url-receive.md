---
description: Fahren Sie hier fort, um Informationen zum Anfordern einer DCS-Antwort in einem /event-Aufruf zu erhalten. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Empfangen von Daten vom DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 1%

---

# Empfangen von Daten vom DCS {#receive-data-from-the-dcs}

Fahren Sie hier fort, um Informationen zum Anfordern einer [!DNL DCS]-Antwort in einem `/event`-Aufruf zu erhalten. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.

Bevor Sie diesen Inhalt überprüfen, lesen [ „Daten an den DCS senden](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS-Antwortparameter: eine Überprüfung {#dcs-response-parameters}

Ihre [!DNL DCS] muss `d_rtbd=json` enthalten, wenn Sie eine Antwort von der [!DNL DCS] erhalten möchten. Die [!DNL DCS] gibt keine Daten zurück, wenn Sie diesen Parameter auslassen. Ein einfacher Aufruf an die [!DNL DCS], um Daten anzufordern, verwendet diese Syntax:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Beispielantwort {#sample-response}

Erinnern Sie sich daran[ dass das fiktive Unternehmen in der Dokumentation ](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)Daten an DCS senden[!DNL Acme, Inc.] diesen Aufruf ausgeführt hat:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Da dieser Aufruf den erforderlichen Antwortparameter enthält, wird der [!DNL DCS] an das unten dargestellte [!DNL JSON] zurückgesendet. Ihre kann ähnlich oder komplexer sein.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Antwortparameter {#response-parameters}

In der folgenden Tabelle sind die häufigsten Parameter aufgeführt und definiert, die Sie in einer Antwort des [!DNL DCS] sehen können. Dies gilt für Ereignisaufrufe oder andere [!DNL DCS] [!DNL API] Abfragen, die Daten zurückgeben.

| Parameter | Beschreibung |
|--- |--- |
| `c` | Eine als „URL-Ziel“ [ URL](../../../features/destinations/create-url-destination.md). |
| `cn` | Der Name oder die ID, die im Feld „Cookie-Name“ eines [Cookie-Ziels“ festgelegt ](../../../features/destinations/create-cookie-destination.md). |
| `cv` | Die Werte, die an das Ziel gesendet werden, das durch den Parameter „cn“: „destination name“ definiert wird. |
| `dcs_region` | Die [Server-zu-Server-DCS-Aufrufe](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Dieses Objekt enthält Informationen zu allen URL-Zielen, die in der Benutzeroberfläche konfiguriert sind. Die Liste dieses Objekts ist dynamisch und basiert auf den Aktionen des Benutzers. |
| `dmn` | Dies ist die Domain, die im Feld Cookie-Domain für ein Cookie-Ziel angegeben ist. Siehe [Optionale Einstellungen für Cookie-Ziele](../../../features/destinations/cookie-destination-options.md).  Bei Server-zu-Server-Integrationen empfehlen wir die Verwendung einer Domain wie `aam-api.com`. |
| `e` | Die sichere URL, die in einem URL-Ziel festgelegt wurde. |
| `stuff` | Dieses Objekt enthält Informationen für alle Cookie-Ziele. Die Liste dieses Objekts ist dynamisch und basiert auf den Aktionen des Benutzers. |
| `tid` | Transaktions-ID, eine eindeutige 12-stellige ID, die zu Debugging-Zwecken verwendet wird. Jeder /event-Aufruf an den DCS erhält eine TID, auf die Sie bei Support-Anfragen verweisen können, um eine bessere und schnellere Antwort zu erhalten. |
| `ttl` | Der Wert des Cookies für die Lebensdauer in Tagen. |
| `u` und `uuid` | Von Audience Manager zugewiesene eindeutige Benutzer-ID. Dies ist erforderlich, wenn Sie (Server-[-Server-DCS-Aufrufe) ](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Zieltyp, iFrame (`iframe`) oder Bild (`img`). |

>[!MORELIKETHIS]
>
>* [Vom DCS unterstützte Schlüssel-Wert-Präfixe und -Variablen](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

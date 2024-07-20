---
description: Weitere Informationen zum Anfordern einer DCS-Antwort in einem /event -Aufruf finden Sie hier . Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
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

Weitere Informationen zum Anfordern einer [!DNL DCS] -Antwort in einem `/event` -Aufruf finden Sie hier . Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.

Bevor Sie diesen Inhalt überprüfen, lesen Sie [Daten an den DCS senden](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS-Antwortparameter: Eine Überprüfung {#dcs-response-parameters}

Ihre [!DNL DCS] -Anfrage muss `d_rtbd=json` enthalten, wenn Sie eine Antwort von der [!DNL DCS] erhalten möchten. Die [!DNL DCS] gibt keine Daten zurück, wenn Sie diesen Parameter weglassen. Ein grundlegender Aufruf von [!DNL DCS] zur Datenanfrage verwendet diese Syntax:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Beispielantwort {#sample-response}

Beachten Sie, dass das fiktive Unternehmen [!DNL Acme, Inc.] aus der Dokumentation [Daten an den DCS senden](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) diesen Aufruf ausgeführt hat:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Da dieser Aufruf den erforderlichen Antwortparameter enthält, sendet der [!DNL DCS] das unten dargestellte [!DNL JSON] -Objekt zurück. Ihre können ähnlich oder komplexer sein.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Antwortparameter {#response-parameters}

In der folgenden Tabelle werden die gängigeren Parameter aufgelistet und definiert, die in einer Antwort von [!DNL DCS] angezeigt werden. Dies gilt für Ereignisaufrufe oder andere [!DNL DCS] [!DNL API] -Abfragen, die Daten zurückgeben.

| Parameter | Beschreibung |
|--- |--- |
| `c` | Eine URL, die als [URL-Ziel](../../../features/destinations/create-url-destination.md) festgelegt wurde. |
| `cn` | Der Name oder die ID, die im Feld &quot;Cookie-Name&quot;eines [Cookie-Ziels](../../../features/destinations/create-cookie-destination.md) festgelegt wurde. |
| `cv` | Die an das Ziel gesendeten Werte, die durch den Parameter &quot;cn&quot;:&quot;Zielname&quot;definiert werden. |
| `dcs_region` | Die DCS-Aufrufe [Server-zu-Server](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Dieses Objekt enthält Informationen zu allen URL-Zielen, die in der Benutzeroberfläche konfiguriert sind. Die Liste dieses Objekts ist dynamisch und basiert auf den Aktionen des Benutzers. |
| `dmn` | Dies ist die Domäne, die im Feld Cookie-Domäne für ein Cookie-Ziel angegeben ist. Siehe [Optionale Einstellungen für Cookie-Ziele](../../../features/destinations/cookie-destination-options.md).  Für Server-zu-Server-Integrationen empfehlen wir die Verwendung einer Domäne wie `aam-api.com`. |
| `e` | Die sichere URL, die in einem URL-Ziel festgelegt wurde. |
| `stuff` | Dieses Objekt enthält Informationen für alle Cookie-Ziele. Die Liste dieses Objekts ist dynamisch und basiert auf den Aktionen des Benutzers. |
| `tid` | Transaktions-ID, die eine eindeutige 12-stellige ID ist, die zu Debugging-Zwecken verwendet wird. Jeder /event-Aufruf an den DES erhält eine ID, die Sie in Supportanfragen für eine bessere und schnellere Antwort referenzieren können. |
| `ttl` | Der Wert der Cookie-Live-Zeit in Tagen. |
| `u` und `uuid` | Vom Audience Manager zugewiesene eindeutige Benutzer-ID. Dies ist erforderlich, wenn Sie [Server-zu-Server-DCS-Aufrufe durchführen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Zieltyp, iFrame (`iframe`) oder Bild (`img`). |

>[!MORELIKETHIS]
>
>* [Schlüsselwertpräfixe und -variablen, die vom DCS unterstützt werden](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

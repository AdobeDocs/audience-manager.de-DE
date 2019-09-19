---
description: Weitere Informationen zum Anfordern einer DCS-Antwort in einem /event-Aufruf finden Sie hier. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
seo-description: Weitere Informationen zum Anfordern einer DCS-Antwort in einem /event-Aufruf finden Sie hier. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
seo-title: Daten vom DCS empfangen
solution: Audience Manager
title: Daten vom DCS empfangen
uuid: fbb77197-8530-48a8-b708-d785f7214494
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# Daten vom DCS empfangen {#receive-data-from-the-dcs}

Weitere Informationen zum Anfordern einer [!UICONTROL DCS] Antwort in einem `/event` Aufruf finden Sie hier. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.

Bevor Sie diesen Inhalt überprüfen, lesen Sie [Daten an den DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)senden.

## DCS-Antwortparameter: Eine Überprüfung {#dcs-response-parameters}

Ihre [!UICONTROL DCS] Anforderung muss enthalten sein, `d_rtbd=json` wenn Sie eine Antwort von der erhalten möchten [!UICONTROL DCS]. Wenn Sie diesen Parameter weglassen, [!UICONTROL DCS] werden keine Daten zurückgegeben. Ein einfacher Aufruf an die [!UICONTROL DCS] zum Anfordern von Daten verwendet folgende Syntax:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Beispielantwort {#sample-response}

Denken Sie daran, dass das fiktive Unternehmen von der Dokumentation [Daten an den DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) senden folgenden Aufruf [!DNL Acme, Inc.] durchgeführt hat:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Da dieser Aufruf den erforderlichen Antwortparameter enthält, wird das [!UICONTROL DCS] unten dargestellte Objekt zurückgesendet [!DNL JSON] . Ihre mögen ähnlich oder komplexer sein.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Antwortparameter {#response-parameters}

Die unten stehende Tabelle listet die gebräuchlichsten Parameter auf, die Sie in einer Antwort aus dem [!UICONTROL DCS]Abschnitt sehen können. Dies gilt für Ereignisaufrufe oder andere [!UICONTROL DCS] [!DNL API] Abfragen, die Daten zurückgeben.

| Parameter | Beschreibung |
|--- |--- |
| `c` | Eine URL, die als [URL-Ziel](../../../features/destinations/create-url-destination.md)festgelegt wurde. |
| `cn` | Der Name oder die ID, die im Feld "Cookie-Name"eines [Cookie-Ziels](../../../features/destinations/create-cookie-destination.md)festgelegt wird. |
| `cv` | Die Werte, die an das Ziel gesendet werden, definiert durch den Parameter "cn":"Zielname". |
| `dcs_region` | Die [Server-zu-Server-DCS-Aufrufe](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Dieses Objekt enthält Informationen zu allen URL-Zielen, die in der Benutzeroberfläche konfiguriert sind. Die Liste dieses Objekts ist basierend auf den Aktionen des Benutzers dynamisch. |
| `dmn` | Dies ist die Domäne, die im Feld "Cookie-Domäne"für ein Cookie-Ziel angegeben wird. Siehe [Optionale Einstellungen für Cookie-Ziele](../../../features/destinations/cookie-destination-options.md).  Für Server-zu-Server-Integrationen empfehlen wir die Verwendung einer Domäne wie `aam-api.com`. |
| `e` | Die sichere URL, die in einem URL-Ziel festgelegt wurde. |
| `stuff` | Dieses Objekt enthält Informationen zu allen Cookie-Zielen. Die Liste dieses Objekts ist basierend auf den Aktionen des Benutzers dynamisch. |
| `tid` | Transaktions-ID, eine eindeutige 12-Zeichen-ID, die zum Debugging verwendet wird. Jeder /event-Aufruf an den DCS erhält eine Meldung, die Sie bei Supportanfragen für eine bessere und schnellere Antwort lesen können. |
| `ttl` | Der Wert für die Cookie-Zeit bis zur Live-Übertragung in Tagen. |
| `u` und `uuid` | Vom Audience Manager zugewiesene eindeutige Benutzer-ID. Dies ist erforderlich, wenn Sie DCS- [Aufrufe](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)von Server zu Server ausführen. |
| `y` | Zieltyp, iFrame (`iframe`) oder Bild (`img`). |

>[!MORE_LIKE_THIS]
>
>* [Präfixe und Variablen mit Schlüsselwerten, die vom DCS unterstützt werden](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)


---
description: Weitere Informationen zum Anfordern einer DCS-Antwort in einem /Ereignis-Aufruf finden Sie hier. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
seo-description: Weitere Informationen zum Anfordern einer DCS-Antwort in einem /Ereignis-Aufruf finden Sie hier. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
seo-title: Empfangen von Daten vom DCS
solution: Audience Manager
title: Empfangen von Daten vom DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 5%

---


# Empfangen von Daten vom DCS {#receive-data-from-the-dcs}

Weitere Informationen zum Anfordern einer [!DNL DCS] Antwort in einem `/event` Aufruf finden Sie hier. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.

Bevor Sie diesen Inhalt überprüfen, lesen Sie [Daten an den DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)senden.

## DCS-Antwortparameter: Eine Überprüfung {#dcs-response-parameters}

Ihre [!DNL DCS] Anforderung muss enthalten sein, `d_rtbd=json` wenn Sie eine Antwort von der erhalten möchten [!DNL DCS]. Wenn Sie diesen Parameter weglassen, [!DNL DCS] werden keine Daten zurückgegeben. Ein einfacher Aufruf an die [!DNL DCS] zum Anfordern von Daten verwendet folgende Syntax:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Beispielantwort {#sample-response}

Denken Sie daran, dass die fiktive Firma von der Dokumentation [Daten an den DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) senden diesen Aufruf [!DNL Acme, Inc.] ausgeführt hat:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Da dieser Aufruf den erforderlichen Antwortparameter enthält, wird das [!DNL DCS] unten dargestellte Objekt zurückgesendet [!DNL JSON] . Ihre mögen ähnlich oder komplexer sein.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Antwortparameter {#response-parameters}

In der Tabelle unten finden Sie Listen und die gebräuchlichsten Parameter, die Sie in einer Antwort aus dem [!DNL DCS]Abschnitt sehen können. Dies gilt für Ereignis-Aufrufe oder andere [!DNL DCS] [!DNL API] Abfragen, die Daten zurückgeben.

| Parameter | Beschreibung |
|--- |--- |
| `c` | Eine URL, die als [URL-Ziel](../../../features/destinations/create-url-destination.md)festgelegt wurde. |
| `cn` | Der Name oder die ID, die im Feld &quot;Cookie-Name&quot;eines [Cookie-Ziels](../../../features/destinations/create-cookie-destination.md)festgelegt wird. |
| `cv` | Die Werte, die an das Ziel gesendet werden, definiert durch den Parameter &quot;cn&quot;:&quot;Zielname&quot;. |
| `dcs_region` | Die [Server-zu-Server-DCS-Aufrufe](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Dieses Objekt enthält Informationen zu allen URL-Zielen, die in der Benutzeroberfläche konfiguriert sind. Die Liste dieses Objekts ist je nach Benutzeraktionen dynamisch. |
| `dmn` | Dies ist die Domäne, die im Feld &quot;Cookie-Domäne&quot;für ein Cookie-Ziel angegeben wird. See [Optional Settings for Cookie Destinations](../../../features/destinations/cookie-destination-options.md).  Für Server-zu-Server-Integrationen empfehlen wir die Verwendung einer Domäne wie `aam-api.com`. |
| `e` | Die sichere URL, die in einem URL-Ziel festgelegt wurde. |
| `stuff` | Dieses Objekt enthält Informationen zu allen Cookie-Zielen. Die Liste dieses Objekts ist je nach Benutzeraktionen dynamisch. |
| `tid` | Transaktions-ID, eine eindeutige 12-Zeichen-ID, die zum Debugging verwendet wird. Jeder /Ereignis-Aufruf an den DCS erhält eine Meldung, die Sie bei Supportanfragen für eine bessere und schnellere Antwort lesen können. |
| `ttl` | Der Wert für die Cookie-Zeit bis zur Live-Übertragung in Tagen. |
| `u` und `uuid` | Eindeutige Benutzer-ID, die von Audience Manager zugewiesen wird. Dies ist erforderlich, wenn Sie DCS- [Aufrufe](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)von Server zu Server ausführen. |
| `y` | Zieltyp, iFrame (`iframe`) oder Bild (`img`). |

>[!MORELIKETHIS]
>
>* [Präfixe und Variablen mit Schlüsselwerten, die vom DCS unterstützt werden](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)


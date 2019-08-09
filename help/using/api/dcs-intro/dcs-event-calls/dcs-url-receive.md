---
description: Weitere Informationen zum Anfordern einer DCS-Antwort in einem /event. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
seo-description: Weitere Informationen zum Anfordern einer DCS-Antwort in einem /event. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
seo-title: Daten aus dem DCS empfangen
solution: Audience Manager
title: Daten aus dem DCS empfangen
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Daten aus dem DCS empfangen {#receive-data-from-the-dcs}

Hier erfahren Sie, wie Sie eine [!UICONTROL DCS] Antwort in einem `/event` Aufruf anfordern. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.

Lesen Sie dazu die Option Daten an das DCS [senden](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS-Antwortparameter: Eine Überprüfung {#dcs-response-parameters}

Ihre [!UICONTROL DCS] Anforderung muss enthalten `d_rtbd=json` sein, wenn Sie eine Antwort von der [!UICONTROL DCS] Wenn [!UICONTROL DCS] Sie diesen Parameter weglassen, werden keine Daten zurückgegeben. Ein grundlegender Aufruf an [!UICONTROL DCS] die Anforderungsdaten verwendet diese Syntax:

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>= <i>val 1</i>, &amp;<i>key 2</i>= <i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code>
</pre>

## Beispielantwort {#sample-response}

Beachten Sie, dass der fiktive Unternehmen diesen Aufruf aus den [Daten Senden an die DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) -Dokumentation [!DNL Acme, Inc.] sendet:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Da dieser Aufruf den erforderlichen Antwortparameter enthält, wird das [!UICONTROL DCS] im Folgenden aufgeführte [!DNL JSON] Objekt zurückgesendet. Sie sind möglicherweise ähnlich oder komplexer.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Antwortparameter {#response-parameters}

In der folgenden Tabelle werden die allgemeineren Parameter aufgelistet und definiert, die in einer Antwort von der Antwort angezeigt [!UICONTROL DCS]werden. Dies gilt für Ereignisaufrufe oder andere [!UICONTROL DCS][!DNL API] Abfragen, die Daten zurückgeben.

| Parameter | Beschreibung |
|--- |--- |
| `c` | Eine URL, die als [URL-Ziel festgelegt](../../../features/destinations/create-url-destination.md)wurde. |
| `cn` | Der Name oder die ID, die im Cookie-Namensfeld eines [Cookie-Ziels festgelegt](../../../features/destinations/create-cookie-destination.md)ist. |
| `cv` | Die Werte, die an das durch den "cn" definierte Ziel gesendet werden: Parameter "destinatonname" . |
| `dcs_region` | Die [Server-to-Server-DCS-Aufrufe](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Dieses Objekt enthält Informationen für alle URL-Ziele, die in der Benutzeroberfläche konfiguriert sind. Die Liste dieses Objekts basiert auf den Aktionen des Benutzers. |
| `dmn` | Diese Domäne wird im Feld Cookie-Domäne für ein Cookie-Ziel angegeben. Siehe [Optionale Einstellungen für Cookie-Ziele](../../../features/destinations/cookie-destination-options.md). Für Serverintegrationen mit Server empfehlen wir die Verwendung einer Domäne wie `aam-api.com`z. B. |
| `e` | Die sichere URL, die in einem URL-Ziel festgelegt wurde. |
| `stuff` | Dieses Objekt enthält Informationen für alle Cookie-Ziele. Die Liste dieses Objekts basiert auf den Aktionen des Benutzers. |
| `tid` | Transaktions-ID, die eine eindeutige 12 Zeichen-ID für Debugging-Zwecke ist. Jeder /event Aufruf an den DCS erhält eine Tid, die Sie in Support-Erfragen für eine bessere und schnellere Antwort referenzieren können. |
| `ttl` | Der Wert für die Dauer des Cookies in Tagen. |
| `u` und `uuid` | Eindeutige Benutzer-ID von Audience Manager zugewiesen. Dies ist erforderlich, wenn [Sie Server-zu-Server-DCS-Aufrufe vornehmen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Zieltyp, iframe (`iframe`) oder Bild (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Wichtige Wertpräfixe und vom DCS unterstützte Variablen](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)


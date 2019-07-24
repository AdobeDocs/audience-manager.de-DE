---
description: Weitere Informationen zum Anfordern einer DCS-Antwort in einem /event. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
seo-description: Weitere Informationen zum Anfordern einer DCS-Antwort in einem /event. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.
seo-title: Daten aus dem DCS empfangen
solution: Audience Manager
title: Daten aus dem DCS empfangen
uuid: fbb 77197-8530-48 a 8-b 708-d 785 f 7214494
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Receive Data From the DCS {#receive-data-from-the-dcs}

Continue here for information about how to request a [!UICONTROL DCS] response in a `/event` call. Dieser Abschnitt enthält ein Antwortbeispiel und Definitionen für allgemeine Datenelemente in einer Antwort.

Before reviewing this content, see [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS Response Parameters: A Review {#dcs-response-parameters}

Your [!UICONTROL DCS] request must include `d_rtbd=json` if you want to receive a response from the [!UICONTROL DCS]. The [!UICONTROL DCS] will not return data if you omit this parameter. A basic call to the [!UICONTROL DCS] to request data uses this syntax:

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>= <i>val 1</i>, &amp;<i>key 2</i>= <i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code>
</pre>

## Beispielantwort {#sample-response}

Recall that from the [Send Data to the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentation, the fictional company [!DNL Acme, Inc.] made this call:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

As this call includes the required response parameter, the [!UICONTROL DCS] sent back the [!DNL JSON] object shown below. Sie sind möglicherweise ähnlich oder komplexer.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Antwortparameter {#response-parameters}

The table below lists and defines the more common parameters you may see in a response from the [!UICONTROL DCS]. This applies to event calls or other [!UICONTROL DCS] [!DNL API] queries that return data.

| Parameter | Beschreibung |
|--- |--- |
| `c` | A URL that has been set as a [URL destination](../../../features/destinations/manage-destinations.md#configure-url-destination). |
| `cn` | The name or ID set in the cookie name field of a [cookie destination](../../../features/destinations/manage-destinations.md#create-cookie-destination). |
| `cv` | Die Werte, die an das durch den "cn" definierte Ziel gesendet werden: Parameter "destinatonname" . |
| `dcs_region` | The [server-to-server DCS calls](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Dieses Objekt enthält Informationen für alle URL-Ziele, die in der Benutzeroberfläche konfiguriert sind. Die Liste dieses Objekts basiert auf den Aktionen des Benutzers. |
| `dmn` | Diese Domäne wird im Feld Cookie-Domäne für ein Cookie-Ziel angegeben. See [Optional Settings for Cookie Destinations](../../../features/destinations/manage-destinations.md#optional-settings-cookies).  For  Server to Server integrations we recommend using a domain like `aam-api.com`. |
| `e` | Die sichere URL, die in einem URL-Ziel festgelegt wurde. |
| `stuff` | Dieses Objekt enthält Informationen für alle Cookie-Ziele. Die Liste dieses Objekts basiert auf den Aktionen des Benutzers. |
| `tid` | Transaktions-ID, die eine eindeutige 12 Zeichen-ID für Debugging-Zwecke ist. Jeder /event Aufruf an den DCS erhält eine Tid, die Sie in Support-Erfragen für eine bessere und schnellere Antwort referenzieren können. |
| `ttl` | Der Wert für die Dauer des Cookies in Tagen. |
| `u` und `uuid` | Eindeutige Benutzer-ID von Audience Manager zugewiesen. This is required if you're making [server-to-server DCS calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Destination type,  iFrame (`iframe`) or image (`img`). |

>[!MORE_ LIKE_ THIS]
>
>* [Wichtige Wertpräfixe und vom DCS unterstützte Variablen](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)


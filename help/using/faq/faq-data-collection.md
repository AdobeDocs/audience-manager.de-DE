---
description: Allgemeine Fragen zur Datenerfassung und -integration und Probleme.
seo-description: Allgemeine Fragen zur Datenerfassung und -integration und Probleme.
seo-title: Häufig gestellte Fragen zur Datenerfassung und Produktintegration
solution: Audience Manager
title: Häufig gestellte Fragen zur Datenerfassung und Produktintegration
uuid: fa 8 e 79 f 4-99 cb -41 fd -8 a 85-d 4 f 92 d 03 c 7 a 5
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Data Collection and Product Integration FAQ{#data-collection-and-product-integration-faq}

Allgemeine Fragen zur Datenerfassung und -integration und Probleme.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Wie kann ich den eingehenden Traffic vom[!UICONTROL DCS]Traffic in[!UICONTROL DCS]Protokolldateiexporten unterscheiden?**

Traits onboarded via [!UICONTROL Inbound] are populated by [!UICONTROL Inbound] the same way they get populated by [!UICONTROL DCS]. There are a few different ways to tell that traffic came from [!UICONTROL Inbound]:

* Remote-IP wird auf 68.67.173.18 eingestellt.
* Domänen werden auf 5325 gesetzt
* Region wird auf 0 gesetzt

<br> 

**Können Sie eine Liste der IP-Adressen angeben, die ich für dpm. demdex. net Whitelist nennen kann?**

Leider ist es nicht möglich. These IPs are assigned dynamically, by geographic region, through [!DNL Amazon Web Services]. As a result, [!DNL Audience Manager] does not control the range of IPs that can be assigned to this address.

<br> 

**Kann ich eine IP-Adresse angeben, die ich für Ihren eingehenden und ausgehenden FTP-Server Whitelist verwende?**

Ja, siehe unten.

| Element | Adresse |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Welche Codeplatzierungs- und Seitenladerforderungen gelten für eine[!UICONTROL DIL]/[!DNL Analytics]Datenintegration?**

To bring [!DNL Analytics] data into [!DNL Audience Manager], load [!UICONTROL DIL] after the `s_code` module but *before* the `s.t()` function. Fügen Sie beispielsweise in dieser Reihenfolge den Code ein oder stellen Sie sicher, dass er geladen wird:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] module

3. [!DNL Analytics]`s.t()`-Funktion 

As a best practice, set up your [!DNL Audience Manager]- [!DNL Analytics] integration with either of these 2 methods:

* Put [!UICONTROL DIL] directly in the `s_code`.

* Serve [!UICONTROL DIL] and the `s_code` through [!DNL Adobe Launch] or [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Warum fehlen meine[!DNL Analytics]Variablen bei[!DNL Audience Manager]einem Ereignisaufruf?**

Dies geschieht normalerweise, wenn:

* You serve [!UICONTROL DIL] through a tag management system that loads it asynchronously with other code elements on the page.
* The `s.t()` function loads before [!UICONTROL DIL].

<br> 

**Welche Versionen[!DNL Analytics][!UICONTROL DIL]von arbeiten?**

You must use [!DNL Analytics] version 20.2 (or higher) and the [!DNL Adobe AppMeasurement AS] library version 3.5.2 (or higher) to work with [!UICONTROL DIL]. If you don't know your [!DNL Analytics] or [!DNL AppMeasurement] version, check the [!DNL Analytics] call that gets made from the page. Versionsinformationen wie folgt:

This customer uses [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

This customer uses [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Kann ich Seitendaten erfassen, wenn ich[!DNL Analytics]kein Kunde bin?**

Ja. The [!UICONTROL DIL] module helps you collect page data even if you're not using [!DNL Analytics]. When set up properly, [!UICONTROL DIL] can capture data from and about:

* Meta-Tags
* Urls und URL-Header
* Suchmaschinentypen
* Keywords

Additionally, clients can deploy a simple onsite object and populate it with key-value pairs that you want [!UICONTROL DIL] to collect data on. This lets you add and remove specific audience data points on your site without any [!DNL Audience Management] updates. Work with your Partner Solutions representative to properly set this up and ensure the [!DNL DIL] module references the page object correctly.

<br> 

**Können[!UICONTROL DIL]Daten erfasst[!DNL Google Analytics]werden?**

Ja. [!UICONTROL DIL] kann einige [!DNL Google Analytics] (GA) Elemente sammeln und diese Daten an [!DNL Audience Manager]sie übergeben. Siehe:

* [GA. submituniversalanalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA. init](../dil/dil-modules.md#ga-init)

<br> 

**Kann ich Rohdaten erhalten und[!DNL Audience Manager]wie granular es ist?**

Yes, [!DNL Audience Manager] can provide you with data collected for users we've seen on your inventory. Dazu gehören:

* The unique user ID (UUID) assigned by [!DNL Audience Manager]
* Eigenschaften und Segment-IDs
* Nicht verwendete Signale
* Zeitstempel
* Seiten-urls

<br> 

**Ich möchte Daten auf einer Site erfassen und Benutzer über DFP auf einer anderen Site als Ziel auswählen. Do I need to deploy code on the other property if I don't want to collect data from that location?**

Nein. Wenn die Datenerfassung auf der zweiten Site keine Anforderung ist, müssen Sie DIL dort nicht bereitstellen. Solange Sie über DFP auf den Bestand auf der zweiten Site zugreifen können, können Sie die Datenerfassung über die erste Site und das Ziel über DFP durchführen.

<br> 

**Was ist der beste Drittanbieter-Datenanbieter?**

Jeder Anbieter führt eine eindeutige Tabelle durch, sodass die Antwort davon abhängt, wonach Sie suchen. Wir können Überlappungsberichte (ohne Kosten) aktivieren, um zu verstehen, welcher Anbieter für Sie am besten funktioniert.

<br> 

**Wie werden Cookies[!DNL Audience Manager]gesetzt und Variablen an DFP weitergeleitet?**

[!DNL Audience Manager] legt 2 Cookies fest: Eine sendet Segmentvariablen an das DFP-Anzeigentag und die anderen stellen unsere eindeutige Benutzer-ID (UUID) ein, die auch von DFP gelesen wird. Durch Hinzufügen der UUID zum Anzeigen-Tag können wir die Berichterstattung und die Zielgruppenerkennung auf Benutzerebene durchführen.

<br> 

**Können wir eine DSP-Information zu Punkten im Konversionstrichter senden, die von einem Benutzer erreicht wurde?**

Ja. Wir können Trichterdaten senden, aber die DSP muss über die technische Funktion verfügen, um sie zu verwenden. Ein DSP muss bestätigen, dass sie mehrere Segmente verarbeiten können. Wenn dies nicht der Fall ist, müssen wir möglicherweise spezifische Segmente erstellen, um einen Benutzer basierend auf ihrem Umrechnungsfortschritt aus anderen Segmenten abzurufen (z. B. fertig gestellte Schritt 1 und 2, aber nicht Schritt 3). Sie können diese Informationen an eine DSP senden, damit sie Benutzer gezielt ansprechen, sie auf eine bestimmte Landingpage weiterleiten oder spezifische kreative Elemente anzeigen können.

<br> 

**Wie kann ich bestätigen, dass die per FTP gesendeten Daten von der Erfassung abgerufen[!DNL Audience Manager]wurden?**

A file has been picked up when the extension changes from `.sync` to `.processed`. In diesem Fall befindet sich die Datei in der Erfassungswarteschlange. Außerdem kann Ihr Kundenbetreuer bestätigen, dass eine Datei hochgeladen wurde.

<br> 

**Ich möchte die Funktionalität der[DCS-API testen](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Ich sende Ereignisaufrufe wie die unten dargestellte. The calls contain[Declared IDs](../features/declared-ids.md)and signals, which should realize some traits and segments I have already set up. Can I use the[!UICONTROL General Reports]and[!UICONTROL Trend Reports]to verify if the trait and segment populations are increasing?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, do not rely on the [!UICONTROL General Reports] and [!UICONTROL Trend Reports] in this case.

Die Berichte berechnen Populationen basierend auf nicht authentifizierten Profildatensätzen (uuids), die wir im Backend zu dem Zeitpunkt sehen, zu dem die Berichte erstellt werden.

On a first call to the [!UICONTROL DCS], the declared IDs are *not* linked to any UUID (i.e. no [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) is present on the client side). The [!UICONTROL DCS] will randomly generate a UUID and set a [!DNL demdex] cookie and pass it on in the response call, but it will not transmit the UUID to the backend.

>[!NOTE]
>
>Die generierte UUID wird nur in unserem Back-Backend-Datenspeicher bereitgestellt, sobald das Gerät, auf dem das Cookie gesetzt wurde, weitere Aktivitäten auslöst.

Aus diesem Grund werden die Berichte nicht die von den deklarierten IDs in Ihrem Aufruf ausgelösten Ereignisse widergespiegelt. We recommend you use UUID, ECID (formerly MID) or mobile device IDs in event test calls to the [!UICONTROL DCS]. Then, you can verify the trait and segment realizations in the [!UICONTROL General Reports] and in the [!UICONTROL Trend Reports].

See also, the [Index of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**Wie lange dauert es, bis Benutzerprofile über[mehrere Regionen hinweg synchronisiert](../api/dcs-intro/dcs-api-reference/dcs-regions.md)werden?**

Normalerweise dauert es bis zu 24 Stunden, bis ein Benutzerprofil über mehrere Regionen hinweg synchronisiert wird. In seltenen Fällen kann der Prozess jedoch bis zu 48 Stunden dauern.

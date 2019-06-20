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


# Häufig gestellte Fragen zur Datenerfassung und Produktintegration{#data-collection-and-product-integration-faq}

Allgemeine Fragen zur Datenerfassung und -integration und Probleme.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Wie kann ich den eingehenden Traffic vom[!UICONTROL DCS]Traffic in[!UICONTROL DCS]Protokolldateiexporten unterscheiden?**

Eigenschaften, die über [!UICONTROL Inbound] die Eingabe erfasst werden, werden auf [!UICONTROL Inbound] die gleiche Weise gefüllt wie [!UICONTROL DCS]gefüllt. Es gibt verschiedene Möglichkeiten, zu erkennen, dass Traffic von [!UICONTROL Inbound]:

* Remote-IP wird auf 68.67.173.18 eingestellt.
* Domänen werden auf 5325 gesetzt
* Region wird auf 0 gesetzt

<br> 

**Können Sie eine Liste der IP-Adressen angeben, die ich für dpm. demdex. net Whitelist nennen kann?**

Leider ist es nicht möglich. Diese ips werden dynamisch, nach geografischer Region, durch [!DNL Amazon Web Services]. Daher wird der [!DNL Audience Manager] Bereich der ips, der dieser Adresse zugewiesen werden kann, nicht gesteuert.

<br> 

**Kann ich eine IP-Adresse angeben, die ich für Ihren eingehenden und ausgehenden FTP-Server Whitelist verwende?**

Ja, siehe unten.

| Element | Adresse |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Welche Codeplatzierungs- und Seitenladerforderungen gelten für eine[!UICONTROL DIL]/[!DNL Analytics]Datenintegration?**

Laden [!DNL Analytics] Sie Daten [!DNL Audience Manager][!UICONTROL DIL] nach dem `s_code` Modul, aber *vor* der `s.t()` Funktion in die Daten ein. Fügen Sie beispielsweise in dieser Reihenfolge den Code ein oder stellen Sie sicher, dass er geladen wird:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] module

3. [!DNL Analytics]`s.t()`-Funktion 

Es empfiehlt sich, Ihre [!DNL Audience Manager]- [!DNL Analytics] Integration mit einer der beiden folgenden Methoden einzurichten:

* Direkt in [!UICONTROL DIL]`s_code`.

* Dient zur Bereitstellung [!UICONTROL DIL] und `s_code` bis [!DNL Adobe Launch][!DNL Adobe DTM].

Siehe DIL-API ( [Data Integration Library](../dil/dil-overview.md)).

<br> 

**Warum fehlen meine[!DNL Analytics]Variablen bei[!DNL Audience Manager]einem Ereignisaufruf?**

Dies geschieht normalerweise, wenn:

* Sie arbeiten [!UICONTROL DIL] über ein Tag-Management-System, das es asynchron mit anderen Code-Elementen auf der Seite lädt.
* Die `s.t()` Funktion wird zuvor [!UICONTROL DIL]geladen.

<br> 

**Welche Versionen[!DNL Analytics][!UICONTROL DIL]von arbeiten?**

Sie müssen [!DNL Analytics] mit Version 20.2 (oder höher) und der [!DNL Adobe AppMeasurement AS] Bibliothek Version 3.5.2 (oder höher) arbeiten [!UICONTROL DIL]. Wenn Sie Ihre [!DNL Analytics] oder [!DNL AppMeasurement] Ihre Version nicht kennen, überprüfen Sie den [!DNL Analytics] Aufruf, der von der Seite gesendet wird. Versionsinformationen wie folgt:

Der Kunde verwendet [!DNL Analytics] Version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Der Kunde verwendet [!DNL AppMeasurement] Version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Kann ich Seitendaten erfassen, wenn ich[!DNL Analytics]kein Kunde bin?**

Ja. Das [!UICONTROL DIL] Modul unterstützt Sie bei der Erfassung von Seitendaten, auch wenn Sie nicht verwenden [!DNL Analytics]. Bei ordnungsgemäßer Einrichtung [!UICONTROL DIL] können Sie Daten aus folgenden Elementen erfassen:

* Meta-Tags
* Urls und URL-Header
* Suchmaschinentypen
* Keywords

Kunden können außerdem ein einfaches Onsite-Objekt bereitstellen und es mit Schlüssel/Wert-Paaren füllen, die Sie Daten erfassen möchten [!UICONTROL DIL] . Dadurch können Sie spezifische Zielgruppendatenpunkte auf Ihrer Site ohne [!DNL Audience Management] Aktualisierungen hinzufügen und entfernen. Wenden Sie sich an Ihren Partner-Lösungsvertreter, um diese Einstellung korrekt einzurichten und sicherzustellen, dass das [!DNL DIL] Modul ordnungsgemäß auf das Seitenobjekt verweist.

<br> 

**Können[!UICONTROL DIL]Daten erfasst[!DNL Google Analytics]werden?**

Ja. [!UICONTROL DIL] kann einige [!DNL Google Analytics] (GA) Elemente sammeln und diese Daten an [!DNL Audience Manager]sie übergeben. Siehe:

* [GA. submituniversalanalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA. init](../dil/dil-modules.md#ga-init)

<br> 

**Kann ich Rohdaten erhalten und[!DNL Audience Manager]wie granular es ist?**

Ja, [!DNL Audience Manager] können Sie Daten bereitstellen, die für Benutzer erfasst wurden, die wir im Bestand gesehen haben. Dazu gehören:

* Die eindeutige Benutzer-ID (UUID), die von [!DNL Audience Manager]
* Eigenschaften und Segment-IDs
* Nicht verwendete Signale
* Zeitstempel
* Seiten-urls

<br> 

**Ich möchte Daten auf einer Site erfassen und Benutzer über DFP auf einer anderen Site als Ziel auswählen. Muss ich Code für die andere Eigenschaft bereitstellen, wenn ich keine Daten von diesem Speicherort erfassen möchte?**

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

Wenn sich die Erweiterung von der `.sync` Erweiterung ändert, wurde eine Datei aufgenommen `.processed`. In diesem Fall befindet sich die Datei in der Erfassungswarteschlange. Außerdem kann Ihr Kundenbetreuer bestätigen, dass eine Datei hochgeladen wurde.

<br> 

**Ich möchte die Funktionalität der[DCS-API testen](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Ich sende Ereignisaufrufe wie die unten dargestellte. Die Aufrufe enthalten[deklarierte IDs](../features/declared-ids.md)und Signale, die einige Eigenschaften und Segmente bereitstellen sollten, die ich bereits eingerichtet habe. Kann ich[!UICONTROL General Reports]zu überprüfen,[!UICONTROL Trend Reports]ob die Eigenschaften und Segmentpopulationen sich erhöhen?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Nein, verlassen Sie sich nicht auf und [!UICONTROL General Reports][!UICONTROL Trend Reports] in diesem Fall.

Die Berichte berechnen Populationen basierend auf nicht authentifizierten Profildatensätzen (uuids), die wir im Backend zu dem Zeitpunkt sehen, zu dem die Berichte erstellt werden.

Bei einem ersten Aufruf von werden [!UICONTROL DCS]die deklarierten IDs *nicht* mit keiner UUID verknüpft (d. h. kein [demdex-Cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) ist auf Clientseite vorhanden). Sie [!UICONTROL DCS] generiert eine UUID zufällig und setzt ein [!DNL demdex] Cookie ein und übergibt es im Antwortanruf. Die UUID wird jedoch nicht an das Backend übertragen.

>[!NOTE]
>
>Die generierte UUID wird nur in unserem Back-Backend-Datenspeicher bereitgestellt, sobald das Gerät, auf dem das Cookie gesetzt wurde, weitere Aktivitäten auslöst.

Aus diesem Grund werden die Berichte nicht die von den deklarierten IDs in Ihrem Aufruf ausgelösten Ereignisse widergespiegelt. Wir empfehlen, in Ereignistest-Aufrufen an die UUID, ECID (früher MID) oder Mobile Geräte-IDs zu verwenden [!UICONTROL DCS]. Anschließend können Sie die Eigenschaften und Segmentrealizationen im [!UICONTROL General Reports] und im Abschnitt [!UICONTROL Trend Reports]überprüfen.

Siehe auch Index [of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**Wie lange dauert es, bis Benutzerprofile über[mehrere Regionen hinweg synchronisiert](../api/dcs-intro/dcs-api-reference/dcs-regions.md)werden?**

Normalerweise dauert es bis zu 24 Stunden, bis ein Benutzerprofil über mehrere Regionen hinweg synchronisiert wird. In seltenen Fällen kann der Prozess jedoch bis zu 48 Stunden dauern.

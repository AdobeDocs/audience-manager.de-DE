---
description: Allgemeine Fragen und Probleme zur Datenerfassung und Integration.
seo-description: Allgemeine Fragen und Probleme zur Datenerfassung und Integration.
seo-title: Häufig gestellte Fragen zur Datenerfassung und Produktintegration
solution: Audience Manager
title: Häufig gestellte Fragen zur Datenerfassung und Produktintegration
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 1%

---


# Häufig gestellte Fragen zur Datenerfassung und Produktintegration{#data-collection-and-product-integration-faq}

Allgemeine Fragen und Probleme zur Datenerfassung und Integration.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Wie kann ich den eingehenden Traffic von dem[!DNL DCS]Traffic in[!DNL DCS]Protokolldateiexporten unterscheiden?**

Eigenschaften, über die [!UICONTROL Inbound] sie eingebettet sind, werden auf [!UICONTROL Inbound] dieselbe Weise aufgefüllt, wie sie von [!DNL DCS]ihnen aufgefüllt werden. Es gibt einige verschiedene Möglichkeiten, zu erkennen, dass Traffic von [!UICONTROL Inbound]:

* Remote IP wird auf 68.67.173.18 eingestellt
* DomainID wird auf 5325 eingestellt
* Region wird auf 0 gesetzt

<br> 

**Können Sie mir eine Liste von IP-Adressen geben, die ich zu einer zulassungsliste für dpm.demdex.net hinzufügen kann?**

Leider können wir das nicht. Diese IPs werden dynamisch, nach geografischer Region, über [!DNL Amazon Web Services]zugewiesen. Das bedeutet, dass [!DNL Audience Manager] nicht der IP-Bereich gesteuert wird, der dieser Adresse zugewiesen werden kann.

<br> 

**Können Sie mir eine IP-Adresse angeben, die ich zu einer zulassungsliste für Ihren eingehenden und ausgehenden sFTP-Server hinzufügen kann?**

Ja, siehe unten.

| Element | Adresse |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Welches sind die Anforderungen an die Codeplatzierung und das Laden der Seite für eine[!UICONTROL DIL]/[!DNL Analytics]Datenintegration?**

Um [!DNL Analytics] Daten in [!DNL Audience Manager]zu laden, laden Sie [!UICONTROL DIL] nach dem `s_code` Modul, aber *vor* der `s.t()` Funktion. Fügen Sie beispielsweise Ihren Code in der folgenden Reihenfolge ein oder stellen Sie sicher, dass er geladen wird:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] module

3. [!DNL Analytics]`s.t()`-Funktion 

Richten Sie als Best Practice Ihre [!DNL Audience Manager]- [!DNL Analytics] Integration mit einer der beiden folgenden Methoden ein:

* Stell [!UICONTROL DIL] direkt in die `s_code`.

* Serve [!UICONTROL DIL] und die `s_code` durch [!DNL Adobe Experience Platform Launch] oder [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Warum fehlen meine[!DNL Analytics]Variablen bei einem[!DNL Audience Manager]Ereignis-Aufruf?**

Dies geschieht in der Regel, wenn:

* Die Bereitstellung erfolgt [!UICONTROL DIL] über ein Tag-Management-System, das es asynchron mit anderen Codeelementen auf der Seite lädt.
* Die `s.t()` Funktion wird vor dem Laden geladen [!UICONTROL DIL].

<br> 

**Mit welchen Versionen von[!DNL Analytics]Arbeit[!UICONTROL DIL]?**

Sie müssen die [!DNL Analytics] Version 20.2 (oder höher) und die [!DNL Adobe AppMeasurement AS] Bibliotheksversion 3.5.2 (oder höher) verwenden, um damit zu arbeiten [!UICONTROL DIL]. Wenn Sie Ihre [!DNL Analytics] oder [!DNL AppMeasurement] Version nicht kennen, überprüfen Sie den [!DNL Analytics] Aufruf, der von der Seite erfolgt. Versionsinformationen siehe:

Dieser Kunde verwendet [!DNL Analytics] Version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Dieser Kunde verwendet [!DNL AppMeasurement] Version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Kann ich Seitendaten erfassen, wenn ich kein[!DNL Analytics]Kunde bin?**

Ja. Das [!UICONTROL DIL] Modul hilft Ihnen bei der Erfassung von Seitendaten, auch wenn Sie nicht verwenden [!DNL Analytics]. Bei ordnungsgemäßer Einrichtung [!UICONTROL DIL] können Sie Daten aus und über Folgendes erfassen:

* Meta-Tags
* URLs und URL-Kopfzeilen
* Suchmaschinentypen
* Keywords

Darüber hinaus können Kunden ein einfaches Onsite-Objekt bereitstellen und es mit Schlüssel-Wert-Paaren füllen, auf denen Sie Daten erfassen [!UICONTROL DIL] möchten. Auf diese Weise können Sie bestimmte Datenpunkte zu Ihrer Audience ohne [!DNL Audience Management] Aktualisierungen hinzufügen und entfernen. Wenden Sie sich an Ihren Partner Solutions-Kundenbetreuer, um dies korrekt einzurichten und sicherzustellen, dass das [!DNL DIL] Modul das Seitenobjekt korrekt referenziert.

<br> 

**Kann[!UICONTROL DIL]man Daten aus[!DNL Google Analytics]Daten erfassen?**

Ja. [!UICONTROL DIL] kann einige [!DNL Google Analytics] (GA) Elemente erfassen und diese Daten an [!DNL Audience Manager]weiterleiten. Siehe:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Kann ich Rohdaten abrufen[!DNL Audience Manager]und wie detailliert ist das?**

Ja, Sie [!DNL Audience Manager] können Daten bereitstellen, die für Benutzer gesammelt wurden, die wir in Ihrem Bestand gesehen haben. Dazu gehören:

* Die eindeutige Benutzer-ID (UUID), die von [!DNL Audience Manager]
* Eigenschaften- und Segment-IDs
* Nicht verwendete Signale
* Zeitstempel
* Seiten-URLs

<br> 

**Ich möchte Daten zu einer Site und Zielgruppe über DFP auf einer anderen Site erfassen. Muss ich Code für die andere Eigenschaft bereitstellen, wenn ich an diesem Speicherort keine Daten erfassen möchte?**

Nein. Wenn die Datenerfassung auf der zweiten Site nicht erforderlich ist, müssen Sie dort kein DIL bereitstellen. Solange Sie über DFP Zugriff auf den Bestand auf der zweiten Site haben, können Sie die Datenerfassung von der ersten Site und Zielgruppe über DFP nutzen.

<br> 

**Was ist der beste Drittanbieter für Daten?**

Jeder Anbieter bringt etwas Einzigartiges in die Tabelle, daher hängt die Antwort davon ab, was Sie suchen. Wir können überschneidenden Berichte (kostenlos) aktivieren, um Ihnen zu vermitteln, welcher Anbieter für Sie am besten geeignet ist.

<br> 

**Wie werden Cookies gesetzt und Variablen an DFP übergeben?[!DNL Audience Manager]**

[!DNL Audience Manager] setzt 2 Cookies: Eine sendet Segmentvariablen an das DFP-Tag und die andere setzt unsere Unique User ID (UUID), die auch von DFP gelesen wird. Durch Hinzufügen der UUID zum Anzeigen-Tag können wir Berichte und Audiencen auf Benutzerebene ermitteln.

<br> 

**Können wir DSP-Informationen über Punkte im Konversionstrichter senden, die von einem Benutzer erreicht wurden?**

Ja. Wir können Trichterdaten senden, aber das DSP muss über die technische Fähigkeit verfügen, diese zu verwenden. Ein DSP muss bestätigen, dass mehrere Segmente verarbeitet werden können. Wenn dies nicht möglich ist, müssen wir möglicherweise bestimmte Segmente erstellen, um einen Benutzer basierend auf seinem Konvertierungsfortschritt aus anderen Segmenten zu entfernen (z. B. abgeschlossene Schritte 1 und 2, aber nicht Schritt 3). Möglicherweise möchten Sie diese Informationen an ein DSP senden, damit diese Benutzer zielgerichtet ansprechen, zu einer bestimmten Landingpage weiterleiten oder bestimmte Kreative anzeigen können.

<br> 

**Wie kann ich bestätigen, dass die per FTP gesendeten Daten von[!DNL Audience Manager]mir abgerufen wurden?**

Eine Datei wurde aufgenommen, wenn sich die Erweiterung von `.sync` zu `.processed`ändert. In diesem Fall befindet sich die Datei in der Erfassungswarteschlange. Außerdem kann Ihr Kundenbetreuer bestätigen, wann eine Datei hochgeladen wurde.

<br> 

**Ich möchte die Funktionalität der[DCS-API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)testen. Ich schicke Ereignis-Anrufe wie die unten abgebildete. Die Aufrufe enthalten[deklarierte IDs](../features/declared-ids.md)und Signale, die einige Eigenschaften und Segmente realisieren sollten, die ich bereits eingerichtet habe. Kann ich die Variablen[!UICONTROL General Reports][!UICONTROL Trend Reports]und verwenden, um zu überprüfen, ob die Eigenschaften- und Segmentpopulationen zunehmen?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Nein, verlassen Sie sich nicht auf die [!UICONTROL General Reports] und [!UICONTROL Trend Reports] in diesem Fall.

Die Berichte berechnen Populationen anhand der nicht authentifizierten Profil Records (UUIDs), die wir im Backend zum Zeitpunkt der Berichterstellung sehen.

Bei einem ersten Aufruf an die [!DNL DCS]werden die deklarierten IDs *nicht* mit einer UUID verknüpft (d. h. kein [demdex-Cookie](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) auf der Clientseite vorhanden). Der [!DNL DCS] generiert nach dem Zufallsprinzip eine UUID, setzt ein [!DNL demdex] Cookie und gibt sie im Antwortaufruf weiter. Die UUID wird jedoch nicht an das Backend übertragen.

>[!NOTE]
>
>Die generierte UUID wird erst dann in unserer Backend-Daten-Datenspeicherung materialisiert, wenn das Gerät, auf dem das Cookie gesetzt wird, eine weitere Aktivität auslöst.

Aus diesem Grund spiegeln die Berichte nicht die Ereignis wider, die von den deklarierten IDs in Ihrem Aufruf ausgelöst werden. Es wird empfohlen, UUID-, ECID- (ehemals MID) oder Mobilgeräte-IDs in Ereignis-Testaufrufen für die [!DNL DCS]App zu verwenden. Anschließend können Sie die Eigenschaften- und Segmentrealisierungen im [!UICONTROL General Reports] und im [!UICONTROL Trend Reports].

Siehe auch [Index der Audience Manager-IDs](../reference/ids-in-aam.md).

<br> 

**Wie lange dauert die Synchronisierung von Profilen über[Regionen](../api/dcs-intro/dcs-api-reference/dcs-regions.md)hinweg?**

Die regionsübergreifende Synchronisierung eines Profils dauert in der Regel bis zu 24 Stunden. In seltenen Fällen kann der Prozess jedoch bis zu 48 Stunden dauern.

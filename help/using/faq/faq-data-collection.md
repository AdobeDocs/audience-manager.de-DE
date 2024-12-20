---
description: Häufige Fragen und Probleme im Zusammenhang mit der Datenerfassung und Integration.
seo-description: Common data collection and integration questions and issues.
seo-title: Data Collection and Product Integration FAQ
solution: Audience Manager
title: Häufig gestellte Fragen zur Datenerfassung und Produktintegration
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP-Adresse; SFTP-IP-Adresse; FTP-Adresse
feature: Administration
exl-id: 2951ab0c-6f1c-4126-b83e-ce4a33c0d4ab
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '1211'
ht-degree: 78%

---

# Häufig gestellte Fragen zur Datenerfassung und Produktintegration{#data-collection-and-product-integration-faq}

Häufige Fragen und Probleme im Zusammenhang mit der Datenerfassung und Integration.

<br> 

**Wie kann ich beim Export von [!DNL DCS]-Protokolldateien den eingehenden Traffic vom [!DNL DCS]-Traffic unterscheiden?**

Eigenschaften, die über [!UICONTROL Inbound] integriert wurden, werden von [!UICONTROL Inbound] auf dieselbe Weise aufgefüllt, wie von [!DNL DCS]. Es gibt verschiedene Möglichkeiten, um festzustellen, ob der Traffic von [!UICONTROL Inbound] stammt:

* Remote IP wird auf 68.67.173.18 gesetzt
* DomainID wird auf 5325 gesetzt
* Region wird auf 0 gesetzt

<br>

**Können Sie mir eine Liste von IP-Adressen bereitstellen, die ich einer Zulassungsliste für dpm.demdex.net hinzufügen kann?**

Leider ist das nicht möglich. Diese IPs werden dynamisch nach geografischen Regionen über [!DNL Amazon Web Services] zugewiesen. Infolgedessen hat [!DNL Audience Manager] keine Kontrolle über den Bereich der IPs, die dieser Adresse zugewiesen werden können.

 

**Können Sie mir eine IP-Adresse bereitstellen, die ich einer Zulassungsliste für Ihren eingehenden und ausgehenden SFTP-Server hinzufügen kann?**

Ja, siehe unten.

| Server | IP-Adressen |
| ---------|----------|
| ftp-in-gtw.demdex.com | 52.3.74.119; 3.233.68.222 |
| ftp-out-gtw.demdex.com | 23.22.232.252; 18.211.109.184 |

 

Die folgenden SFTP-Server werden nicht mehr unterstützt. Mit diesen Servern werden keine neuen Konten bereitgestellt.

| Server | IP-Adresse |
|---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**Wie konfiguriere ich meine Audience Manager-Instanz für die Verwendung der neuen SFTP-Server?**

Wenden Sie sich an Ihren [!DNL Audience Manager] oder an die Kundenunterstützung, damit diese Ihre neuen SFTP-Konten konfigurieren können.

 

**Welche Authentifizierungsmethoden werden für die neuen SFTP-Server unterstützt?**

Die neuen SFTP-Server (`ftp-in-gtw` und `ftp-out-gtw`) unterstützen [!DNL OpenSSH Key-Based Authentication]. Wir können die [!DNL SSH] für Sie generieren oder Sie können uns Ihren eigenen öffentlichen Schlüssel zur Verfügung stellen.

 

**Was sind die Anforderungen für die Codeplatzierung und das Laden von Seiten für eine [!UICONTROL DIL]/[!DNL Analytics]-Datenintegration?**

Laden Sie [!UICONTROL DIL] nach dem `s_code`-Modul, jedoch *vor* der Funktion `s.t()`, um [!DNL Analytics]-Daten in [!DNL Audience Manager] zu übernehmen. Platzieren Sie Ihren Code beispielsweise in dieser Reihenfolge oder stellen Sie sicher, dass er in dieser Reihenfolge geladen wird:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL]-Modul

3. [!DNL Analytics] `s.t()`-Funktion 

Richten Sie Ihre [!DNL Audience Manager]-[!DNL Analytics]-Integration mit einer dieser beiden Methoden als Best Practice ein:

* Platzieren Sie [!UICONTROL DIL] direkt in den `s_code`.

* Servieren Sie [!UICONTROL DIL] und die `s_code` durch [!DNL Adobe Experience Platform Tags].

Siehe [Data Integration Library (DIL)-API](../dil/dil-overview.md).

 

**Warum fehlen meine [!DNL Analytics]-Variablen bei einem [!DNL Audience Manager]-Ereignisaufruf?**

Dies geschieht normalerweise, wenn:

* Sie [!UICONTROL DIL] über ein Tag-Management-System bedienen, das diese asynchron mit anderen Code-Elementen auf der Seite lädt.
* Die `s.t()`-Funktion vor[!UICONTROL DIL] geladen wird.

 

**Welche Versionen von [!DNL Analytics] funktionieren mit [!UICONTROL DIL]?**

Sie müssen [!DNL Analytics] Version 20.2 (oder höher) und die [!DNL Adobe AppMeasurement AS]-Bibliothek Version 3.5.2 (oder höher) verwenden, um mit [!UICONTROL DIL] arbeiten zu können. Wenn Sie Ihre [!DNL Analytics]- oder [!DNL AppMeasurement]-Version nicht kennen, überprüfen Sie den [!DNL Analytics]-Aufruf, der auf der Seite ausgeführt wird. Die Versionsinformationen werden unten angezeigt:

Dieser Kunde verwendet [!DNL Analytics] Version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Dieser Kunde verwendet [!DNL AppMeasurement] Version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br>

**Kann ich Seitendaten erfassen, wenn ich kein [!DNL Analytics]-Kunde bin?**

Ja. Mit dem [!UICONTROL DIL]-Modul können Sie Seitendaten erfassen, auch wenn Sie [!DNL Analytics] nicht verwenden. Bei ordnungsgemäßer Einrichtung kann [!UICONTROL DIL] Daten von und über Folgendes erfassen:

* Meta-Tags
* URLs und URL-Kopfzeilen
* Suchmaschinentypen
* Keywords

Darüber hinaus können Clients ein einfaches On-site-Objekt bereitstellen und es mit Schlüssel-Wert-Paaren füllen, für die [!UICONTROL DIL] Daten erfassen soll. Auf diese Weise können Sie bestimmte Zielgruppendatenpunkte auf Ihrer Site hinzufügen und entfernen, ohne dass [!DNL Audience Management]t-Updates erforderlich sind. Arbeiten Sie mit Ihrem Partner Solutions-Support-Mitarbeiter zusammen, um dies ordnungsgemäß einzurichten und sicherzustellen, dass das [!DNL DIL]-Modul das Seitenobjekt korrekt referenziert.

<br>

**Kann [!UICONTROL DIL] Daten von [!DNL Google Analytics] erfassen?**

Ja. [!UICONTROL DIL] kann einige [!DNL Google Analytics] (GA)-Elemente erfassen und diese Daten an [!DNL Audience Manager] übergeben. Siehe:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br>

**Kann ich Rohdaten von [!DNL Audience Manager] abrufen und wie detailliert sind sie?**

Ja, [!DNL Audience Manager] kann Ihnen Daten zur Verfügung stellen, die für Benutzer erfasst wurden, die wir in Ihrem Inventar gesehen haben. Dazu gehören:

* Die von [!DNL Audience Manager] zugewiesene Unique User ID (UUID)
* Eigenschaften- und Segment-IDs
* Nicht verwendete Signale
* Zeitstempel
* Seiten-URLs

<br>

**Ich möchte Daten auf einer Site erfassen und Benutzer über [!DNL Google Ad Manager] auf einer anderen Site ansprechen. Muss ich Code für die andere Eigenschaft bereitstellen, wenn ich keine Daten von dieser Site erfassen möchte?**

Nein. Wenn die Datenerfassung auf der zweiten Site nicht erforderlich ist, müssen Sie die DIL dort nicht bereitstellen. Sofern Sie über [!DNL Google Ad Manager] Zugriff auf das Inventar auf der zweiten Site haben, können Sie die Datenerfassung von der ersten Site und dem Ziel über [!DNL Google Ad Manager] verwenden.

<br>

**Was ist der beste Drittanbieter von Daten?**

Jeder Anbieter bringt etwas Einzigartiges mit, daher hängt die Antwort davon ab, wonach Sie suchen. Wir können Überlagerungsberichte (kostenlos) aktivieren, um Ihnen bei der Entscheidung zu helfen, welcher Anbieter für Sie am besten geeignet ist.

<br>

**Wie setzt [!DNL Audience Manager] Cookies und übergibt Variablen an [!DNL Google Ad Manager]?**

[!DNL Audience Manager] setzt 2 Cookies: Einer sendet Segmentvariablen an das [!DNL Google Ad Manager] Ad-Tag und der andere setzt unsere Unique User ID (UUID), die auch von [!DNL Google Ad Manager] gelesen wird. Durch Hinzufügen der UUID zum Anzeigen-Tag Berichte können wir Berichte und Zielgruppenermittlung auf Benutzerebene durchführen. 

<br>

**Können wir einer DSP Information über Punkte im Konversionstrichter senden, die ein Benutzer erreicht hat?**

Ja. Wir können Trichterdaten senden, aber die DSP muss über technisch in der Lage sein, diese zu verwenden. Eine DSP muss bestätigen, dass sie mehrere Segmente verarbeiten kann. Wenn dies nicht möglich ist, müssen wir möglicherweise spezifische Segmente erstellen, um einen Benutzer anhand seines Konversionsfortschritts aus anderen Segmenten zu entfernen (z. B. Schritte 1 und 2 abgeschlossen, aber nicht Schritt 3). Möglicherweise möchten Sie diese Informationen an eine DSP senden, damit diese Benutzer zielgerichtet ansprechen, zu einer bestimmten Landingpage weiterleiten oder bestimmte kreative Inhalte anzeigen kann.

<br>

**Wie kann ich bestätigen, dass über FTP gesendete Daten von [!DNL Audience Manager] erfasst wurden?**

Eine Datei wurde erfasst, wenn sich die Erweiterung von `.sync` in `.processed` ändert. In diesem Fall befindet sich die Datei in der Erfassungswarteschlange. Außerdem kann Ihr Kundenbetreuer bestätigen, wann eine Datei hochgeladen wurde.

<br>

**Ich möchte die Funktionalität der [DCS-API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md) testen. Ich sende Ereignisaufrufe wie den unten gezeigten. Die Aufrufe enthalten [deklarierte IDs](../features/declared-ids.md) und Signale, die einige Eigenschaften und Segmente realisieren sollten, die ich bereits eingerichtet habe. Kann ich die [!UICONTROL General Reports] und [!UICONTROL Trend Reports] verwenden, um zu überprüfen, ob die Eigenschafts- und Segmentpopulationen zunehmen?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Nein, verlassen Sie sich in diesem Fall nicht auf die [!UICONTROL General Reports] und [!UICONTROL Trend Reports].

Die Berichte berechnen Populationen basierend auf den nicht authentifizierten Profildatensätzen (UUIDs), die zum Zeitpunkt der Berichterstellung im Backend angezeigt werden.

Bei einem ersten Aufruf des [!DNL DCS] werden die deklarierten IDs *nicht* mit einer UUID verknüpft (d. h. auf der Client-Seite ist kein [demdex-Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) vorhanden). Der [!DNL DCS] generiert eine UUID nach dem Zufallsprinzip, setzt ein [!DNL demdex]-Cookie und gibt es im Antwortaufruf weiter. Er überträgt jedoch die UUID nicht an das Backend.

>[!NOTE]
>
>Die generierte UUID wird erst dann in unserem Backend-Datenspeicher gesichert, wenn das Gerät, auf dem das Cookie gesetzt wurde, weitere Aktivitäten auslöst.

Aus diesem Grund spiegeln die Berichte nicht die Ereignisse wider, die durch die deklarierten IDs in Ihrem Aufruf ausgelöst wurden. Es wird empfohlen, bei Ereignistest aufrufen an den [!DNL DCS] UUID-, ECID- (ehemals MID) oder Mobilgeräte-IDs zu verwenden. Anschließend können Sie die Merkmale und Segmentrealisierungen in den [!UICONTROL General Reports] und in den [!UICONTROL Trend Reports] überprüfen.

Weitere Informationen finden Sie unter [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br>

**Wie lange dauert die [regionsübergreifende](../api/dcs-intro/dcs-api-reference/dcs-regions.md) Synchronisierung von Benutzerprofilen?**

Die regionsübergreifende Synchronisierung eines Profils dauert in der Regel bis zu 24 Stunden. In seltenen Fällen kann der Prozess jedoch bis zu 48 Stunden dauern.

 

**Was passiert mit inaktiven Amazon S3-Benutzerzugriffsschlüsseln?**

Adobe stellt Audience Manager-Kunden Benutzerzugriffsschlüssel für die Audience Manager-[!DNL Amazon S3] bereit. Aus Sicherheitsgründen werden die Schlüssel nach 100 Tagen Inaktivität automatisch deaktiviert.

Wenden Sie sich an den Kunden-Support, um Ihre Zugriffsschlüssel erneut zu aktivieren oder neue Schlüssel anzufordern.

---
description: Eine Übersicht über die Funktion "Addressable Audience"und Anwendungsfälle.
keywords: DIL
seo-description: Eine Übersicht über die Funktion "Addressable Audience"und Anwendungsfälle.
seo-title: Addressable Audiences
solution: Audience Manager
title: Addressable Audiences
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 1%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Eine Übersicht über die [!UICONTROL Addressable Audience] Funktionen und Anwendungsfälle.

## Was ist eine [!UICONTROL Addressable Audience]? {#addressable-audience-description}

Die [!UICONTROL Addressable Audiences] Funktion zeigt die Überschneidung zwischen den Audiencen, die Sie in all Ihren Eigenschaften sehen, in denen Daten gesammelt werden, und dem ausgewählten Ziel [!DNL Audience Manager] an. Um Ihnen zu helfen, dieses Konzept zu verstehen, schauen Sie sich die folgende Abbildung an. Die Überschneidung zwischen den einzelnen Kreisen stellt die verschiedenen Arten adressierbarer Audiencen dar.

![](assets/addressableAudienceVenn.png)


| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] für [!UICONTROL Destination] | Eine Anzahl aller Geräte, die während des Rückblickzeitraums mit allen [!DNL Audience Manager] Kunden auf Plattformebene interagiert haben und die mit Ihrer Auswahl übereinstimmen können [!UICONTROL destination]. <br><br>Diese Metrik ist nützlich, da sie Ihnen Folgendes zeigt: <ul><li>Die Größe der Gesamtsumme, [!UICONTROL addressable audience] die bei einem bestimmten Targeting erreicht werden [!DNL Audience Manager] kann [!UICONTROL destination].</li><li>Wie groß der [!DNL Audience Manager] Profil-Pool für eine Targeting-Plattform und die Größe ihrer Audiencen ist.</li></ul> |
| [!UICONTROL Customer Total Audience] | Eine Anzahl von Geräten, die während des Lookback-Fensters entweder eine [!UICONTROL rule-based trait] auf Ihren Eigenschaften oder eine [!UICONTROL onboarded trait] aus Ihren Offlinedateien realisiert haben. |
| [!UICONTROL Addressable Audience Match Rate] | Eine Anzahl von Überschneidungen von Geräten, die während des Lookback-Fensters eine [!UICONTROL rule-based trait] oder eine [!UICONTROL onboarded trait] während des Lookback-Fensters implementiert haben, sowie Geräten, bei denen eine ID-Synchronisierung mit der ausgewählten [!UICONTROL destination] unabhängig von der Synchronisierungszeit erfolgt.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>Sie haben während des Lookback-Fensters entweder eine [!UICONTROL rule-based] oder [!UICONTROL onboarded trait] eine `AND`</li><li>Verwenden Sie eine ID-Synchronisierung mit der gewählten [!UICONTROL destination] unabhängig vom Zeitpunkt der Synchronisierung.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] ausgedrückt als Prozentsatz. |
| [!UICONTROL Total Segment Population] | Zählung aller Geräte, die während des Rückblickzeitraums [!UICONTROL segment] in Ihrem Bericht Mitglied waren. |
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzer, die während der Rückblickphase des Berichts zur [!UICONTROL segment] Gruppe gehörten und eine aktive ID-Synchronisierung auf Ihrer Site haben. [!UICONTROL Segments] können Ihre eigenen Erstanbieterdaten sowie Zweit- und Drittanbieterdaten einschließen, indem sie im [!UICONTROL traits] Audience Marketplace [](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)erfasst werden. <br><br>Tipp: Bei Verwendung mit der 1-Tage-Rückblickzeit kann diese Metrik Ihnen helfen, den aktuellen Status Ihrer Metrik zu verstehen [!UICONTROL segments]. Dies liegt daran, dass die [!UICONTROL Segment Addressable Audience] Metrik die Benutzer darstellt, die während des Vortages in einem [!UICONTROL segment] Bericht geblieben sind. Kombinieren Sie dies mit der Tatsache, dass [!DNL Audience Manager] Aktualisierungen [!UICONTROL Addressable Audiences] täglich durchgeführt werden, und kombinieren Sie diese Metrik und den Lookback-Zeitraum, um den aktuellsten Schnappschuss Ihrer [!UICONTROL segments]Daten zu erhalten. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] ausgedrückt als Prozentsatz. |

## [!UICONTROL Addressable Audiences]Schnittstelle:{#addressable-audience-interface}

Die [!UICONTROL Addressable Audience] Funktion verwandelt dieses abstrakte Konzept in quantifizierbare Daten. In [!DNL Audience Manager]dieser Funktion werden Überschneidungen zwischen Audiencen und Datenvisualisierungen angezeigt, die auf einen Blick neben numerischen Daten in Tabellenform Informationen bereitstellen.

[!UICONTROL Addressable Audiences] befindet sich in **[!UICONTROL Audience Data > Destinations]**. Wählen Sie **[!UICONTROL Integrated Platforms > Device-Based]** aus, um die Metriken für adressierbare Audiencen anzuzeigen.

![](assets/addressable-audiences-landing.png)

Die drei Metriken, die Sie auf der [!UICONTROL Addressable Audiences] Landingpage sehen können, repräsentieren:

| Metrik | Beschreibung |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Diese Metrik stellt die [!UICONTROL Customer Addressable Audience] (in der obigen Tabelle beschrieben) *für die letzten 30 Tage dar.* |
| **[!UICONTROL Match Rate]** | Diese Metrik stellt die [!UICONTROL Addressable Audience Match Rate] (in der obigen Tabelle beschrieben) *für die letzten 30 Tage* dar. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Eine Anzahl aller Geräte, die während des Rückblickzeitraums mit allen [!DNL Audience Manager] Kunden auf Plattformebene interagiert haben und die mit diesem abgestimmt werden können [!UICONTROL destination]. Weitere Informationen finden Sie unter Metriken auf [Platform-Ebene](/help/using/features/addressable-audiences.md#platform-level-metrics) . |

Klicken Sie auf den Namen einer Audience, [!UICONTROL server-to-server destination] um die Daten Ihrer adressierbaren  Ansicht. Beachten Sie, dass diese Funktion [!UICONTROL server-to-server destinations] nur Daten zurückgibt und für den Zugriff Administratorberechtigungen erforderlich sind.

![](assets/addressableAudiences.png)

Die Überprüfung dieser Daten kann Ihnen bei Folgendem helfen:

* **Prognosen und Planung:** [!UICONTROL Segment Addressable Audience] mit Daten erhalten Sie mehr Granularität in den Segmenten, die Sie zur Audience-Targeting und Aktivierung an ein Ziel senden möchten.

* **Leistungsüberprüfungen:** Die [!UICONTROL Addressable Audiences] Funktion ist auch ein Tool zur Fehlerbehebung. Sie können damit die Performance der Kampagne überprüfen, die Reichweite der Kampagne verstehen und mit Targeting-/Aktivierungen-Partnern abgleichen, wenn die erwarteten Ergebnisse nicht angezeigt werden.

### Anzeigen von Daten von Drittanbietern und Auswirkungen auf Übereinstimmungsraten

Vor dem Kauf von Daten von Drittanbietern zur Audience können Kunden die Überschneidung mit anderen Datenanbietern überprüfen. Auf diese Weise können Sie vor dem Kauf neuer Daten eine fundierte Entscheidung treffen. Die ID-Synchronisierung für erworbene Drittanbieterdaten beruht nicht nur auf der Überschneidung Ihrer Daten, sondern auch auf den Fußspuren von Drittanbietern mit allen anderen [!DNL Audience Manager] Kunden. Ihr [!DNL Adobe] Berater kann Sie bei der Ermittlung zusätzlicher relevanter Datenquellen unterstützen, um die Kampagnen für die Suche zu optimieren.

### Mobilbenutzer und Übereinstimmungsraten

Beim Versuch, eine Verbindung zu [!DNL Safari] einem Benutzer mit einer mobilen App herzustellen, bestehen Lücken, wenn kein Drittanbieter [!DNL cookies] vorhanden ist. Dadurch ist es schwierig, Benutzer mit einigen Partnern zu synchronisieren, da nur die [!DNL Adobe] IDs für synchronisierte Drittanbieter in den Medien-Versandlogs bereitgestellt [!DNL cookies] werden. Dies ist ein Grund, warum Sie möglicherweise [niedrige Übereinstimmungsraten](../features/addressable-audiences.md#low-match-rates) für Ihre [!UICONTROL destinations]sehen.

## Datumsbereiche in [!UICONTROL Addressable Audiences] und [!UICONTROL Destinations] {#date-ranges}

In den folgenden Abschnitten erfahren Sie, wie die verfügbaren Datumsbereiche aussehen und wie die Daten aus jedem Intervall in den Berichten für einen [!UICONTROL Addressable Audience] oder [!UICONTROL Destination]einen Zeitraum ausfallen.

## Verfügbare Datumsbereiche und Zeitzonen {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Berichte für Ihre [!UICONTROL Addressable Audiences] und [Ziele](../features/destinations/destinations.md) verwenden dieselben Datumsbereichsintervalle. Zu den Datumsbereichsoptionen zählen:

* [!UICONTROL Last 1 Day] (Dieses Intervall läuft von Mitternacht bis Mitternacht des vorherigen 24-Stunden-Zeitraums. Es handelt sich nicht um eine reale oder aktuelle Metrik.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle Daten und Datumsbereiche werden in der [!DNL UTC] Zeitzone festgelegt. Siehe [Zeitzonen in Audience Manager](../reference/aam-time-zones.md).

## Daten in Datumsbereich-Intervallen {#date-range-intervals}

Die [!UICONTROL Addressable Audience] und [!UICONTROL Destination] Metriken geben die Anzahl der individuellen Benutzer für das ausgewählte Zeitintervall zurück. Ein Besucher wird beispielsweise nur einmal gezählt, auch wenn er Ihre Site mehrmals aufsucht. Der erste Besuch ist der individuelle Besuch und wird aufgezeichnet. Die nachfolgenden Besuche geben Besuche zurück und werden nicht gezählt, da sie nicht eindeutig sind.

Datumsbereiche enthalten Daten für das ausgewählte Zeitintervall oder älter. Und die Daten werden aus jedem Berichtintervall gelöscht, sobald die Zeit vergeht. Nehmen wir beispielsweise an, Sie sehen 2 Besucher nach Auswahl der [!UICONTROL Last 30 Days] Option. Die Berichte enthalten folgende Besucher:

* *Wird* in die Ergebnisse einbezogen, die von den längeren Zeitintervallen (60 Tage, 90 Tage und Lebensdauer) zurückgegeben werden.
* *Wird* nicht in kürzeren Intervallen vor der [!UICONTROL Last 30 Day] Option (aktuell, 7 Tage und 14 Tage) eingeschlossen.

Und am 31. Tag erscheinen diese Besucher nur an den 60 Tagen, 90 Tagen und [!UICONTROL Lifetime] Ergebnissen. Sie sind aus dem 30-Tage-Intervall gealtert. Besucher verlieren nicht das [!UICONTROL Lifetime] Intervall.

## [!UICONTROL Addressable Audiences] Metriken {#addressable-audience-metrics}

In diesem Abschnitt werden die von [!UICONTROL Addressable Audiences]Ihnen bereitgestellten Metriktypen beschrieben.

### Metriken auf Kundenebene {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Diese Metriken geben Daten zu Eigenschaften zurück, die realisiert werden, wenn Besucher Ihre Site aufrufen oder eingehende Datendateien an [!DNL Audience Manager]senden. Diese Metrik bietet eine umfassende Ansicht der Kontogröße für Ihre Audience.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Anzahl der Überschneidungen von Geräten, die während des Lookback-Fensters eine [!UICONTROL rule-based trait] oder eine [!UICONTROL onboarded trait] Verbindung hergestellt haben, und Geräten, bei denen eine ID-Synchronisierung mit dem ausgewählten Ziel erfolgt ist, unabhängig vom Zeitpunkt der Synchronisierung.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>Sie haben während des Lookback-Fensters entweder eine [!UICONTROL rule-based] oder [!UICONTROL onboarded trait] eine `AND`</li><li>Verwenden Sie eine ID-Synchronisierung mit der gewählten [!UICONTROL destination] unabhängig vom Zeitpunkt der Synchronisierung.</li></ul> |
| [!UICONTROL Customer Total Audience] | Eine Anzahl von Geräten, die während des Lookback-Fensters entweder eine [!UICONTROL rule-based trait] auf Ihren Eigenschaften oder eine [!UICONTROL onboarded trait] aus Ihren Offlinedateien realisiert haben. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] / [!UICONTROL Customer Total Audience] ausgedrückt als Prozentsatz. |

### Übereinstimmungsmetriken auf Segmentebene {#segment-level-metrics}

Diese Metriken geben Daten zur [!UICONTROL segment] Mitgliedschaft zurück. Sie bieten eine detailliertere und genauere Ansicht der Audience für jede Ihrer [!UICONTROL segments]Anwendungen.

>[!NOTE]
>
>Die Art und Weise, wie das Lookback-Fenster auf der [!UICONTROL segment] Ebene angewendet wird, unterscheidet sich von der auf der Kundenebene. Besucher können vor [!UICONTROL trait] 10 Tagen auf die Site kommen und dort eine Site realisieren, und sie könnten sich [!UICONTROL segment] seitdem für eine Mitgliedschaft qualifizieren und vor 2 Tagen aus der [!UICONTROL segment] Site aussteigen. Wenn der 7-Tage-Lookback angewendet wird, werden diese Besucher auf der [!UICONTROL segment] Ebene des Kunden gezählt, nicht jedoch auf der Kundenebene.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzer, die während der Rückblickphase des Berichts zur [!UICONTROL segment] Gruppe gehörten und eine aktive ID-Synchronisierung auf Ihrer Site haben. Segmente können Ihre eigenen Erstanbieter-Daten sowie Drittanbieter- und Drittanbieter-Daten enthalten, wenn sie im [!UICONTROL traits] Audience Marketplace [](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)erfasst werden.<br><br>Tipp: Bei Verwendung mit der 1-Tage-Rückblickzeit kann diese Metrik Ihnen helfen, den aktuellen Status Ihrer Metrik zu verstehen [!UICONTROL segments]. Dies liegt daran, dass die [!UICONTROL Segment Addressable Audience] Metrik die Benutzer darstellt, die während des Vortages in einem [!UICONTROL segment] Besuch geblieben sind. Kombinieren Sie dies mit der Tatsache, dass [!DNL Audience Manager] Aktualisierungen [!UICONTROL Addressable Audiences] täglich durchgeführt werden, und kombinieren Sie diese Metrik und den Lookback-Zeitraum, um den aktuellsten Schnappschuss Ihrer [!UICONTROL segments]Daten zu erhalten. |
| [!UICONTROL Total Segment Population] | Zählung aller Geräte, die während des Rückblickzeitraums [!UICONTROL segment] in Ihrem Bericht Mitglied waren. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] / [!UICONTROL Total Segment Population] ausgedrückt als Prozentsatz. |

### Metriken auf Platform {#platform-level-metrics}

Diese Metrik gibt Daten zu Aktivitäten zurück, die über alle [!DNL Audience Manager] Kunden hinweg erfasst wurden. Sie bieten eine umfassendere Ansicht der Audience des Kunden im Vergleich zu den zusammengefassten [!DNL Audience Manager] Kunden.

| Metrik | Beschreibung |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Eine Anzahl aller Geräte, die während des Rückblickzeitraums mit allen [!DNL Audience Manager] Kunden auf Plattformebene interagiert haben und die mit Ihrer Auswahl übereinstimmen können [!UICONTROL destination]. <br><br>Diese Metrik ist nützlich, da sie Ihnen Folgendes zeigt:<ul><li>Die Größe des Ziels, [!UICONTROL total addressable audience] das auf ein bestimmtes Targeting-Ziel zutreffen [!DNL Audience Manager] kann.</li><li>Wie groß der [!DNL Audience Manager] Profil-Pool für eine Targeting-Plattform und die Größe ihrer Audiencen ist.</li></ul> |

## Vergleichen [!UICONTROL Customer] und [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Sie sollten die [!UICONTROL Customer Addressable Audience] und die [!UICONTROL Segment Addressable Audience] Metriken nicht vergleichen, um festzustellen, ob eine bedeutsamer ist als die andere. Dabei handelt es sich um separate, unterschiedliche und unabhängige Metriken. Wie in den obigen Definitionen beschrieben, wird jede davon aus verschiedenen Datensätzen abgeleitet. Daher sollten Sie keine Schlussfolgerungen daraus ziehen, wenn eine Metrik größer als die andere ist. Sie können beim Vergleich nur Folgendes sagen:

* [!UICONTROL Customer Addressable Audiences] basiert auf [!UICONTROL trait] Erkenntnissen *für Ihre eigenen Erstanbieterdaten*. Diese Metrik bietet eine umfassende und umfassende Ansicht Ihrer Integration mit einem Datenpartner.

* [!UICONTROL Segment Addressable Audiences] basiert auf Segmentqualifikationen *für Ihre eigenen Erstanbieterdaten sowie auf Zweit- und Drittanbieterdaten*. Diese Metrik bietet eine granulare, genauere Ansicht Ihrer [!UICONTROL addressable audiences] in einer Targeting-Plattform.

## Ursachen der niedrigen Übereinstimmungsraten für [!UICONTROL Addressable Audiences] {#low-match-rates}

Häufige Elemente, die für niedrige [!UICONTROL Addressable Audience] Übereinstimmungsraten oder Diskrepanzen in den gemeldeten Zahlen verantwortlich sind.

| Ursache | Beschreibung |
|---|---|
| Mobile Traffic | Die meisten [!UICONTROL server-to-server] Integrationen basieren auf Synchronisierungsprozessen, die von Drittanbietern unterstützt werden [!DNL cookies]. Mobil-Umgebung verwenden jedoch keine Drittanbieter [!DNL cookies]. Daher erscheinen Ihre [!UICONTROL Addressable Audiences] Zahlen im Vergleich zur [!UICONTROL segment] Größe möglicherweise niedrig. <br><br>Ab Januar 2018 können Sie mobile Audiencen in demselben [!DNL Google] und in demselben [!DNL Adobe Advertising Cloud] für [!UICONTROL cookie-based] Audiencen eingerichteten Zielort aktivieren. Dies bedeutet, dass Sie [!UICONTROL segments] mit einer kombinierten [!DNL cookie] und mobilen ID-Mitgliedschaft an Ihre [!DNL Google] und [!DNL Advertising Cloud] Ziele senden können. Beachten Sie jedoch, dass [!UICONTROL Addressable Audiences] nur die Überschneidung zwischen [!DNL cookie] IDs und Zielen angezeigt wird. [!DNL Audience Manager] sendet 100 % der mobilen Audiencen an [!UICONTROL destinations], aber mobile Audiencen werden nicht anhand der [!UICONTROL Addressable Audience] Metrik gemessen. <br><br>**Hinweis **: Nehmen wir zum Beispiel ein[!UICONTROL segment]mit 1.000.000 Einwohnern. Wenn Sie dies[!UICONTROL segment]einem[!DNL Google]oder[!DNL Adobe Advertising Cloud]Ziel zuordnen, werden möglicherweise 700.000 Geräte und ein Wert[!UICONTROL Addressable Audience][!UICONTROL Match Rate]von 70 % angezeigt. Die Mitgliedschaft bei 700.000 besteht aus[!DNL cookie]IDs, die eine ID-Synchronisierung mit der[!UICONTROL destination]haben. Sie[!UICONTROL Addressable Audience]könnten sogar viel höher sein, da adressierbare mobile IDs in dieser Metrik nicht angezeigt werden. |
| [!DNL Safari]Traffic- | [!DNL Safari] blockiert Drittanbieter [!DNL cookies]. Dadurch wird verhindert, dass IDs [!DNL Audience Manager] mit der [!UICONTROL destination]synchronisiert werden. Mit der Einführung von [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)können Sie erwarten, dass Sie [!UICONTROL addressable audiences] keine [!DNL Safari] Benutzer einbeziehen. |
| Verfolgte Medienimpressionen | Aufgrund der Best Practices für den Anzeigenserver werden ID-Synchronisierungen nicht in Anzeigen-Tags vorgenommen. Kunden, die eine große Anzahl an Offsite-Anzeigen betreiben, synchronisieren die Benutzer nicht mit Drittanbieterintegrationen in diesen Umgebung. Darüber hinaus könnten durch eine große Menge erfasster Daten zu Medienimpressionen [!UICONTROL addressable audience] Zahlen reduziert werden. |

## Fehlerbehebung mit [!UICONTROL Addressable Audiences] {#troubleshooting}

Zusätzlich zu den Übereinstimmungsraten für Überlagerungen können Sie diese auch [!UICONTROL Addressable Audiences] als Fehlerbehebungswerkzeug verwenden.

Nehmen wir beispielsweise an, Sie senden ein Segment an ein Segment, das niedrige Berichte [!UICONTROL destination] [!UICONTROL destination] anzeigt. Wenn Sie die [!UICONTROL Addressable Audience] Ergebnisse überprüfen, wird Ihnen angezeigt, ob es sich um ein technisches Problem oder nur um einen Fall niedriger Übereinstimmungsraten handelt. Eine niedrige Übereinstimmungsrate zeigt, dass Ihre Segmente nicht [!UICONTROL destination] besonders gut sind. Ein Unterschied in den [!UICONTROL total addressable audience] Zahlen zwischen [!DNL Audience Manager] und [!UICONTROL destination] zeigt jedoch ein Integrations-, Synchronisierungs- oder anderes technisches Problem an. Wenden Sie sich in diesen Fällen an Ihren Kundenbetreuer.

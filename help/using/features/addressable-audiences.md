---
description: Eine Übersicht über die Funktion "Addressable Audience"und Anwendungsfälle.
keywords: DIL
seo-description: Eine Übersicht über die Funktion "Addressable Audience"und Anwendungsfälle.
seo-title: Ansprechbare Zielgruppen
solution: Audience Manager
title: Ansprechbare Zielgruppen
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Eine Übersicht über die Funktionen und Anwendungsfälle.[!UICONTROL Addressable Audience]

## Was ist eine [!UICONTROL Addressable Audience]? {#addressable-audience-description}

Die [!UICONTROL Addressable Audiences]-Funktion zeigt die Überschneidung zwischen den Audiencen, die Sie in all Ihren Eigenschaften sehen, in denen [!DNL Audience Manager] Daten sammelt, und dem ausgewählten Ziel. Um Ihnen zu helfen, dieses Konzept zu verstehen, schauen Sie sich die folgende Abbildung an. Die Überschneidung zwischen den einzelnen Kreisen stellt die verschiedenen Arten adressierbarer Audiencen dar.

![](assets/addressableAudienceVenn.png)


| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] für  [!UICONTROL Destination] | Ein Zähler aller Geräte, die während der Berichtausblickszeit mit allen [!DNL Audience Manager]-Kunden auf Plattformebene interagiert haben und die mit Ihrem ausgewählten [!UICONTROL destination] übereinstimmen können. <br><br>Diese Metrik ist nützlich, da sie Ihnen Folgendes zeigt: <ul><li>Die Größe der Gesamtsumme [!UICONTROL addressable audience], die [!DNL Audience Manager] für ein bestimmtes Targeting [!UICONTROL destination] erreichen kann.</li><li>Wie groß der [!DNL Audience Manager]-Profil-Pool für eine Targeting-Plattform und die Größe ihrer Audiencen ist.</li></ul> |
| [!UICONTROL Customer Total Audience] | Eine Anzahl von Geräten, die während des Lookback-Fensters entweder ein [!UICONTROL rule-based trait] in Ihren Eigenschaften oder ein [!UICONTROL onboarded trait] aus Ihren Offlinedateien realisiert haben. |
| [!UICONTROL Addressable Audience Match Rate] | Anzahl der Überschneidungen von Geräten, die während des Lookback-Fensters eine [!UICONTROL rule-based trait]- oder eine [!UICONTROL onboarded trait]-ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination] durchgeführt haben, unabhängig vom Zeitpunkt der Synchronisierung.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>Haben während des Lookback-Fensters `AND` entweder ein [!UICONTROL rule-based] oder ein [!UICONTROL onboarded trait] realisiert</li><li>Verwenden Sie eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination], unabhängig vom Zeitpunkt der Synchronisierung.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] /  [!UICONTROL Customer Total Audience] ausgedrückt als Prozentsatz. |
| [!UICONTROL Total Segment Population] | Zähler aller Geräte, die während der Berichtausblickszeit zu Ihrem [!UICONTROL segment] gehören. |
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzer, die während der Rückblickzeit des Berichts zu [!UICONTROL segment] gehörten und eine aktive ID-Synchronisierung auf Ihrer Site haben. [!UICONTROL Segments] können Ihre eigenen Erstanbieterdaten sowie Zweit- und Drittanbieterdaten einschließen, indem sie im  [!UICONTROL traits] Audience Marketplace  [erfasst werden](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Tipp: Bei Verwendung mit der 1-Tage-Rückblickzeit kann diese Metrik Ihnen helfen, den aktuellen Status Ihrer Metrik zu verstehen  [!UICONTROL segments]. Dies liegt daran, dass die Metrik [!UICONTROL Segment Addressable Audience] die Benutzer darstellt, die am Vortag in einem [!UICONTROL segment] geblieben sind. Kombinieren Sie dies mit der Tatsache, dass [!DNL Audience Manager] [!UICONTROL Addressable Audiences] täglich aktualisiert wird, wobei diese Metrik und der Lookback-Zeitraum die aktuellste Momentaufnahme Ihres [!UICONTROL segments]-Berichts liefern. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] /  [!UICONTROL Total Segment Population] ausgedrückt als Prozentsatz. |

## [!UICONTROL Addressable Audiences]Schnittstelle:{#addressable-audience-interface}

Die Funktion [!UICONTROL Addressable Audience] wandelt dieses abstrakte Konzept in quantifizierbare Daten um. In [!DNL Audience Manager] zeigt diese Funktion die Überschneidung von Audiencen mit Datenvisualisierungen an, die auf einen Blick neben numerischen Daten in Tabellenform Informationen bereitstellen.

[!UICONTROL Addressable Audiences] befindet sich in  **[!UICONTROL Audience Data > Destinations]**. Wählen Sie **[!UICONTROL Integrated Platforms > Device-Based]** aus, um die Metriken für adressierbare Audiencen anzuzeigen.

![](assets/addressable-audiences-landing.png)

Die drei Metriken, die Sie auf der [!UICONTROL Addressable Audiences]-Landingpage sehen können, stellen Folgendes dar:

| Metrik | Beschreibung |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Diese Metrik stellt die [!UICONTROL Customer Addressable Audience] (in der Tabelle oben beschrieben) *für die letzten 30 Tage dar.* |
| **[!UICONTROL Match Rate]** | Diese Metrik stellt die [!UICONTROL Addressable Audience Match Rate] (in der Tabelle oben beschrieben) *für die letzten 30 Tage* dar. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Ein Zähler aller Geräte, die während der Berichtausblickszeit mit allen [!DNL Audience Manager]-Kunden auf Plattformebene interagiert haben und mit diesem [!UICONTROL destination] abgeglichen werden könnten. Weitere Informationen finden Sie unter [Metriken auf Plattformebene](/help/using/features/addressable-audiences.md#platform-level-metrics). |

Klicken Sie auf den Namen eines [!UICONTROL server-to-server destination], um Ihre adressierbaren Audiencen-Daten Ansicht. Beachten Sie, dass diese Funktion nur Daten für [!UICONTROL server-to-server destinations] zurückgibt und für den Zugriff Administratorberechtigungen erforderlich sind.

![](assets/addressableAudiences.png)

Die Überprüfung dieser Daten kann Ihnen bei Folgendem helfen:

* **Prognosen und Planen:** [!UICONTROL Segment Addressable Audience] Daten geben Ihnen mehr Granularität in den Segmenten, die Sie zu Audiencen-Targeting und Aktivierung an ein Ziel senden möchten.

* **Leistungsüberprüfungen:** Die  [!UICONTROL Addressable Audiences] Funktion ist auch ein Tool zur Fehlerbehebung. Sie können damit die Performance der Kampagne überprüfen, die Reichweite der Kampagne verstehen und mit Targeting-/Aktivierungen-Partnern abgleichen, wenn die erwarteten Ergebnisse nicht angezeigt werden.

### Anzeigen von Daten von Drittanbietern und Auswirkungen auf Übereinstimmungsraten

Vor dem Kauf von Daten von Drittanbietern zur Audience können Kunden die Überschneidung mit anderen Datenanbietern überprüfen. Auf diese Weise können Sie vor dem Kauf neuer Daten eine fundierte Entscheidung treffen. Die ID-Synchronisierung für erworbene Drittanbieterdaten beruht nicht nur auf der Überschneidung Ihrer Daten, sondern auch auf den Fußspuren von Drittanbietern mit allen anderen [!DNL Audience Manager]-Kunden. Ihr [!DNL Adobe]-Berater kann Sie bei der Identifizierung zusätzlicher relevanter Datenquellen unterstützen, um die Kampagnen zu optimieren.

### Mobilbenutzer und Übereinstimmungsraten

Es gibt Lücken beim Verbinden von [!DNL Safari]- oder mobilen App-Benutzern, bei denen kein Drittanbieter [!DNL cookies] vorhanden ist. Dadurch ist es schwierig, Benutzer mit einigen Partnern zu synchronisieren, da nur die [!DNL Adobe]-IDs für synchronisierte Drittanbieter [!DNL cookies] in den Media-Versandlogs bereitgestellt werden. Aus diesem Grund könnten Sie [niedrige Übereinstimmungsraten](../features/addressable-audiences.md#low-match-rates) für [!UICONTROL destinations] sehen.

## Datumsbereiche in [!UICONTROL Addressable Audiences] und [!UICONTROL Destinations] {#date-ranges}

Lesen Sie die folgenden Abschnitte, um verfügbare Datumsbereiche anzuzeigen und zu ermitteln, wie die Daten aus jedem Intervall in den Berichten für ein [!UICONTROL Addressable Audience] oder [!UICONTROL Destination] ausfallen.

## Verfügbare Datumsbereiche und Zeitzonen {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Berichte für [!UICONTROL Addressable Audiences] und [Ziele](../features/destinations/destinations.md) verwenden dieselben Datumsbereichsintervalle. Zu den Datumsbereichsoptionen zählen:

* [!UICONTROL Last 1 Day] (Dieses Intervall läuft von Mitternacht bis Mitternacht des vorherigen 24-Stunden-Zeitraums. Es handelt sich nicht um eine reale oder aktuelle Metrik.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle Daten und Datumsbereiche werden in der Zeitzone [!DNL UTC] festgelegt. Siehe [Zeitzonen in Audience Manager](../reference/aam-time-zones.md).

## Daten in Datumsbereich-Intervallen {#date-range-intervals}

Die Metriken [!UICONTROL Addressable Audience] und [!UICONTROL Destination] geben die Anzahl der Unique Users für das ausgewählte Zeitintervall zurück. Ein Besucher wird beispielsweise nur einmal gezählt, auch wenn er Ihre Site mehrmals aufsucht. Der erste Besuch ist der individuelle Besuch und wird aufgezeichnet. Die nachfolgenden Besuche geben Besuche zurück und werden nicht gezählt, da sie nicht eindeutig sind.

Datumsbereiche enthalten Daten für das ausgewählte Zeitintervall oder älter. Und die Daten werden aus jedem Berichtintervall gelöscht, sobald die Zeit vergeht. Nehmen wir beispielsweise an, Sie sehen 2 Besucher nach Auswahl der Option [!UICONTROL Last 30 Days]. Die Berichte enthalten folgende Besucher:

* *Wird* in den Ergebnissen berücksichtigt, die von den längeren Zeitintervallen (60 Tage, 90 Tage und Lebensdauer) zurückgegeben werden.
* *In kürzeren Intervallen, die der* Option vorausgehen (aktuell, 7 Tage und 14 Tage), wird nicht  [!UICONTROL Last 30 Day] ausgeschlossen.

Und am 31. Tag erscheinen diese Besucher nur in den Ergebnissen von 60 Tagen, 90 Tagen und [!UICONTROL Lifetime]. Sie sind aus dem 30-Tage-Intervall gealtert. Besucher werden nicht aus dem [!UICONTROL Lifetime]-Intervall entfernt.

## [!UICONTROL Addressable Audiences] Metriken {#addressable-audience-metrics}

In diesem Abschnitt werden die von [!UICONTROL Addressable Audiences] bereitgestellten Metriktypen beschrieben.

### Metriken auf Kundenebene {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Diese Metriken geben Daten zu Eigenschaften zurück, die realisiert werden, wenn Besucher Ihre Site aufrufen oder eingehende Datendateien an [!DNL Audience Manager] senden. Diese Metrik bietet eine umfassende Ansicht der Kontogröße für Ihre Audience.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Anzahl der Überschneidungen von Geräten, die während des Lookback-Fensters entweder ein [!UICONTROL rule-based trait] oder ein [!UICONTROL onboarded trait] erkannt haben, und Geräten, bei denen eine ID-Synchronisierung mit dem ausgewählten Ziel unabhängig von der Zeit der Synchronisierung erfolgt ist.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>Haben während des Lookback-Fensters `AND` entweder ein [!UICONTROL rule-based] oder ein [!UICONTROL onboarded trait] realisiert</li><li>Verwenden Sie eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination], unabhängig vom Zeitpunkt der Synchronisierung.</li></ul> |
| [!UICONTROL Customer Total Audience] | Eine Anzahl von Geräten, die während des Lookback-Fensters entweder ein [!UICONTROL rule-based trait] in Ihren Eigenschaften oder ein [!UICONTROL onboarded trait] aus Ihren Offlinedateien realisiert haben. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] /  [!UICONTROL Customer Total Audience] ausgedrückt als Prozentsatz. |

### Übereinstimmungsmetriken auf Segmentebene {#segment-level-metrics}

Diese Metriken geben Daten zu [!UICONTROL segment]-Mitgliedschaft zurück. Sie bieten eine detailliertere und genauere Ansicht der Audience für jedes Ihrer [!UICONTROL segments].

>[!NOTE]
>
>Die Art und Weise, wie das Lookback-Fenster auf der [!UICONTROL segment]-Ebene angewendet wird, unterscheidet sich von der auf Kundenebene. Besucher können vor 10 Tagen zu der Site kommen und eine [!UICONTROL trait] implementieren, und sie könnten sich seitdem für eine [!UICONTROL segment] qualifizieren und die [!UICONTROL segment] vor 2 Tagen verlassen. Wenn der 7-Tage-Lookback angewendet wird, werden diese Besucher auf der [!UICONTROL segment]-Ebene gezählt, nicht jedoch auf Kundenebene.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzer, die während der Rückblickzeit des Berichts zu [!UICONTROL segment] gehörten und eine aktive ID-Synchronisierung auf Ihrer Site haben. Segmente können Ihre eigenen Erstanbieter-Daten sowie Zweitanbieter- und Drittanbieter-Daten enthalten, indem sie [!UICONTROL traits] im [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) erfasst werden.<br><br>Tipp: Bei Verwendung mit der 1-Tage-Rückblickzeit kann diese Metrik Ihnen helfen, den aktuellen Status Ihrer Metrik zu verstehen  [!UICONTROL segments]. Dies liegt daran, dass die Metrik [!UICONTROL Segment Addressable Audience] die Benutzer darstellt, die am Vortag in einem [!UICONTROL segment] geblieben sind. Kombinieren Sie dies mit der Tatsache, dass [!DNL Audience Manager] [!UICONTROL Addressable Audiences] täglich aktualisiert wird, wobei diese Metrik und der Lookback-Zeitraum die aktuellste Momentaufnahme Ihres [!UICONTROL segments]-Berichts liefern. |
| [!UICONTROL Total Segment Population] | Zähler aller Geräte, die während der Berichtausblickszeit zu Ihrem [!UICONTROL segment] gehören. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] /  [!UICONTROL Total Segment Population] ausgedrückt als Prozentsatz. |

### Metriken auf Plattformebene {#platform-level-metrics}

Diese Metrik gibt Daten zu Aktivitäten zurück, die über alle [!DNL Audience Manager]-Kunden hinweg erfasst wurden. Sie können eine umfassendere Ansicht der Audience des Kunden im Vergleich zu den zusammengefassten [!DNL Audience Manager]-Kunden bieten.

| Metrik | Beschreibung |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Ein Zähler aller Geräte, die während der Berichtausblickszeit mit allen [!DNL Audience Manager]-Kunden auf Plattformebene interagiert haben und die mit Ihrem ausgewählten [!UICONTROL destination] übereinstimmen können. <br><br>Diese Metrik ist nützlich, da sie Ihnen Folgendes zeigt:<ul><li>Die Größe von [!UICONTROL total addressable audience], die [!DNL Audience Manager] für ein bestimmtes Targeting-Ziel erreicht werden kann.</li><li>Wie groß der [!DNL Audience Manager]-Profil-Pool für eine Targeting-Plattform und die Größe ihrer Audiencen ist.</li></ul> |

## Vergleich von [!UICONTROL Customer] und [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Sie sollten die Metriken [!UICONTROL Customer Addressable Audience] und [!UICONTROL Segment Addressable Audience] nicht vergleichen, um festzustellen, ob eine bedeutsamer ist als die andere. Dabei handelt es sich um separate, unterschiedliche und unabhängige Metriken. Wie in den obigen Definitionen beschrieben, wird jede davon aus verschiedenen Datensätzen abgeleitet. Daher sollten Sie keine Schlussfolgerungen daraus ziehen, wenn eine Metrik größer als die andere ist. Sie können beim Vergleich nur Folgendes sagen:

* [!UICONTROL Customer Addressable Audiences] basiert auf  [!UICONTROL trait] Erkenntnissen  *für Ihre eigenen Erstanbieterdaten*. Diese Metrik bietet eine umfassende und umfassende Ansicht Ihrer Integration mit einem Datenpartner.

* [!UICONTROL Segment Addressable Audiences] basiert auf Segmentqualifikationen  *für Ihre eigenen Erstanbieterdaten sowie auf Zweit- und Drittanbieterdaten*. Diese Metrik bietet eine granulare, genauere Ansicht Ihrer [!UICONTROL addressable audiences] in einer Targeting-Plattform.

## Ursachen für niedrige Übereinstimmungsraten für [!UICONTROL Addressable Audiences] {#low-match-rates}

Allgemeine Elemente, die für niedrige Übereinstimmungsraten oder Diskrepanzen in gemeldeten Zahlen verantwortlich sind.[!UICONTROL Addressable Audience]

| Ursache | Beschreibung |
|---|---|
| Mobile Traffic | Die meisten [!UICONTROL server-to-server]-Integrationen basieren auf Synchronisierungsprozessen, die von Drittanbietern [!DNL cookies] unterstützt werden. Mobil-Umgebung verwenden jedoch kein Drittanbieter [!DNL cookies]. Die [!UICONTROL Addressable Audiences]-Zahlen können daher im Vergleich zu [!UICONTROL segment] niedrig erscheinen. <br><br>Ab Januar 2018 können Sie mobile Audiencen in demselben  [!DNL Google] und denselben  [!DNL Adobe Advertising Cloud] Zielen aktivieren, die für  [!UICONTROL cookie-based] Audiencen eingerichtet wurden. Das bedeutet, dass Sie [!UICONTROL segments] mit kombinierter [!DNL cookie]- und Mobil-ID-Mitgliedschaft an Ihre [!DNL Google]- und [!DNL Advertising Cloud]-Ziele senden können. Beachten Sie jedoch, dass [!UICONTROL Addressable Audiences] nur die Überschneidung zwischen [!DNL cookie]-IDs und -Zielen anzeigt. [!DNL Audience Manager] sendet 100 % der mobilen Audiencen an  [!UICONTROL destinations], aber mobile Audiencen werden nicht anhand der  [!UICONTROL Addressable Audience] Metrik gemessen. <br><br>**Hinweis**: Nehmen wir zum Beispiel ein  [!UICONTROL segment] mit 1.000.000 Einwohnern. Wenn Sie dieses [!UICONTROL segment] einem [!DNL Google]- oder [!DNL Adobe Advertising Cloud]-Ziel zuordnen, wird möglicherweise ein [!UICONTROL Addressable Audience] von 700.000 Geräten und ein [!UICONTROL Match Rate] von 70 % angezeigt. Die Mitgliedschaft bei 700.000 besteht aus [!DNL cookie]-IDs, die eine ID-Synchronisierung mit dem [!UICONTROL destination] haben. Ihre [!UICONTROL Addressable Audience]-Variablen könnten sogar viel höher sein, da adressierbare mobile IDs in dieser Metrik nicht angezeigt werden. |
| [!DNL Safari]Traffic- | [!DNL Safari] blockiert Drittanbieter  [!DNL cookies]. Dadurch wird verhindert, dass [!DNL Audience Manager] IDs mit dem [!UICONTROL destination] synchronisiert werden. Mit der Einführung von [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/) können Sie erwarten, dass Ihre [!UICONTROL addressable audiences]-Benutzer nicht [!DNL Safari] enthalten. |
| Verfolgte Medienimpressionen | Aufgrund der Best Practices für den Anzeigenserver werden ID-Synchronisierungen nicht in Anzeigen-Tags vorgenommen. Kunden, die eine große Anzahl an Offsite-Anzeigen betreiben, synchronisieren die Benutzer nicht mit Drittanbieterintegrationen in diesen Umgebung. Darüber hinaus könnten durch eine große Menge erfasster Medienimpressionsdaten die Zahlen von [!UICONTROL addressable audience] verringert werden. |

## Fehlerbehebung mit [!UICONTROL Addressable Audiences] {#troubleshooting}

Zusätzlich zu den Übereinstimmungsraten können Sie [!UICONTROL Addressable Audiences] auch als Fehlerbehebungswerkzeug verwenden.

Beispiel: Sie senden ein Segment an ein [!UICONTROL destination] und [!UICONTROL destination] zeigt niedrige Berichte an. Wenn Sie die [!UICONTROL Addressable Audience] Ergebnisse überprüfen, wird Ihnen angezeigt, ob dies ein technisches Problem oder nur ein Fall von niedrigen Übereinstimmungsraten ist. Eine niedrige Übereinstimmungsrate zeigt an, dass [!UICONTROL destination] für Ihre ausgewählten Segmente nicht besonders gut ist. Ein Unterschied in den [!UICONTROL total addressable audience]-Zahlen zwischen [!DNL Audience Manager] und [!UICONTROL destination] deutet jedoch auf eine Integration, Synchronisierung oder ein anderes technisches Problem hin. Wenden Sie sich in diesen Fällen an Ihren Kundenbetreuer.

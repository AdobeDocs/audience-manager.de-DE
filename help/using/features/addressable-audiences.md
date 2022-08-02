---
description: Eine Übersicht über die Funktion "Addressable Audience"und die Anwendungsfälle.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Ansprechbare Zielgruppen
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Eine Übersicht über die [!UICONTROL Addressable Audience] Funktionen und Anwendungsbeispiele.

## Was ist eine [!UICONTROL Addressable Audience]? {#addressable-audience-description}

Die [!UICONTROL Addressable Audiences] zeigt Ihnen die Überschneidung zwischen den Zielgruppen, die Sie in all Ihren Eigenschaften sehen, in denen [!DNL Audience Manager] erfasst Daten und Ihr ausgewähltes Ziel. Sehen Sie sich die folgende Abbildung an, um dieses Konzept zu verstehen. Die Überschneidung zwischen den einzelnen Kreisen stellt die verschiedenen Arten von adressierbaren Zielgruppen dar.

![](assets/addressableAudienceVenn.png)


| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] für [!UICONTROL Destination] | Zählung aller Geräte, die mit allen [!DNL Audience Manager] Kunden auf Plattformebene während des Rückblickzeitraums des Berichts, der mit Ihrer Auswahl abgeglichen werden kann [!UICONTROL destination]. <br><br>Diese Metrik ist nützlich, da sie Folgendes anzeigt: <ul><li>Die Gesamtgröße [!UICONTROL addressable audience] dass [!DNL Audience Manager] Zielgruppenbestimmung [!UICONTROL destination].</li><li>Wie groß die [!DNL Audience Manager] Profilpool dient der Erstellung von Zielgruppen und der Größe ihrer Zielgruppen.</li></ul> |
| [!UICONTROL Customer Total Audience] | Anzahl der Geräte, die entweder eine [!UICONTROL rule-based trait] in Ihren Eigenschaften oder einer [!UICONTROL onboarded trait] aus Ihren Offline-Dateien während des Lookback-Fensters. |
| [!UICONTROL Customer Addressable Audience] | Anzahl der Überschneidungen von Geräten, die entweder eine [!UICONTROL rule-based trait] oder [!UICONTROL onboarded trait] während des Lookback-Fensters und der Geräte, bei denen eine ID-Synchronisierung mit der ausgewählten [!UICONTROL destination] unabhängig vom Zeitpunkt der Synchronisierung.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>Sie haben entweder [!UICONTROL rule-based] oder [!UICONTROL onboarded trait] während des Rückblickfensters `AND`</li><li>Sie haben eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination] unabhängig vom Zeitpunkt der Synchronisierung.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] als Prozentsatz angegeben. |
| [!UICONTROL Total Segment Population] | Zählung aller Geräte, die Mitglied Ihrer [!UICONTROL segment] während des Rückblickzeitraums des Berichts. |
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzer, die zur [!UICONTROL segment] während des Rückblickzeitraums des Berichts und eine aktive ID-Synchronisierung auf Ihrer Site durchführen. [!UICONTROL Segments] kann Ihre eigenen Erstanbieterdaten sowie Zweit- und Drittanbieterdaten über [!UICONTROL traits] im [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Tipp: Bei Verwendung mit dem 1-tägigen Rückblickzeitraum kann diese Metrik Ihnen dabei helfen, den aktuellen Status Ihrer [!UICONTROL segments]. Dies liegt daran, dass die Variable [!UICONTROL Segment Addressable Audience] Metrik stellt die Benutzer dar, die in einer [!UICONTROL segment] über den Vortag. Kombinieren Sie dies mit der Tatsache, dass [!DNL Audience Manager] aktualisiert [!UICONTROL Addressable Audiences] täglich, bietet die Kombination dieser Metrik und des Lookback-Zeitraums die aktuellste Momentaufnahme Ihrer [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] als Prozentsatz angegeben. |

## [!UICONTROL Addressable Audiences] Schnittstelle {#addressable-audience-interface}

Die [!UICONTROL Addressable Audience] -Funktion wandelt dieses abstrakte Konzept in quantifizierbare Daten um. In [!DNL Audience Manager], zeigt diese Funktion Zielgruppenüberschneidungen mit Datenvisualisierungen an, die einen Überblick über Informationen sowie numerische Daten in Tabellenform bieten.

[!UICONTROL Addressable Audiences] befindet sich in **[!UICONTROL Audience Data > Destinations]**. Auswählen **[!UICONTROL Integrated Platforms > Device-Based]** um adressierbare Zielgruppenmetriken anzuzeigen.

![](assets/addressable-audiences-landing.png)

Die drei Metriken, die Sie auf der [!UICONTROL Addressable Audiences] Landingpage-Darstellung:

| Metrik | Beschreibung |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Diese Metrik stellt die [!UICONTROL Customer Addressable Audience] (siehe Tabelle oben) *für die letzten 30 Tage.* |
| **[!UICONTROL Match Rate]** | Diese Metrik stellt die [!UICONTROL Addressable Audience Match Rate] (siehe Tabelle oben) *für die letzten 30 Tage*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Zählung aller Geräte, die mit allen [!DNL Audience Manager] Kunden auf Plattformebene während des Rückblickzeitraums des Berichts, der damit abgeglichen werden kann [!UICONTROL destination]. Siehe [Metriken auf Plattformebene](/help/using/features/addressable-audiences.md#platform-level-metrics) für weitere Informationen. |

Klicken Sie auf den Namen eines [!UICONTROL server-to-server destination] , um Ihre adressierbaren Zielgruppendaten anzuzeigen. Beachten Sie, dass diese Funktion Daten für [!UICONTROL server-to-server destinations] Nur und Zugriff erfordert Administratorberechtigungen.

![](assets/addressableAudiences.png)

Die Überprüfung dieser Daten hilft Ihnen bei Folgendem:

* **Prognosen und Planung:** [!UICONTROL Segment Addressable Audience] -Daten erhalten Sie mehr Granularität in den Segmenten, die Sie zur Zielgruppenbestimmung und Aktivierung an ein Ziel senden möchten.

* **Leistungsüberprüfungen:** Die [!UICONTROL Addressable Audiences] ist auch ein Tool zur Fehlerbehebung. Sie können damit die Kampagnenleistung überprüfen, die Reichweite der Kampagne verstehen und mit Targeting-/Aktivierungspartnern vergleichen, wenn die erwarteten Ergebnisse nicht angezeigt werden.

### Anzeigen von Daten von Drittanbietern und Auswirkungen für Übereinstimmungsraten

Vor dem Kauf von Drittanbieterdaten für die Zielgruppenerfassung können Kunden die Überschneidung mit anderen Datenanbietern überprüfen. Auf diese Weise können Sie vor dem Kauf neuer Daten eine fundierte Entscheidung treffen. Die ID-Synchronisierungen für erworbene Drittanbieterdaten basieren nicht nur auf der Überschneidung Ihrer Daten, sondern auch auf den Fußabdrücken von Drittanbietern mit allen anderen [!DNL Audience Manager] -Kunden. Ihre [!DNL Adobe] -Berater können Ihnen dabei helfen, zusätzliche relevante Datenquellen zu identifizieren, um Prospektionskampagnen zu optimieren.

### Mobilbenutzer und Übereinstimmungsraten

Beim Verbindungsversuch gibt es Lücken [!DNL Safari] oder Benutzer mobiler Apps ohne Drittanbieter [!DNL cookies] vorhanden. Dies erschwert die Synchronisierung von Benutzern mit einigen Partnern, da nur diese [!DNL Adobe] IDs für synchronisierte Drittanbieter [!DNL cookies] werden in den Medien-Versandlogs angegeben. Dies ist der Grund, warum Sie [niedrige Übereinstimmungsraten](../features/addressable-audiences.md#low-match-rates) für Ihre [!UICONTROL destinations].

## Datumsbereiche in [!UICONTROL Addressable Audiences] und [!UICONTROL Destinations] {#date-ranges}

In den folgenden Abschnitten finden Sie verfügbare Datumsbereiche und erfahren, wie Daten aus jedem Intervall in den Berichten für eine [!UICONTROL Addressable Audience] oder [!UICONTROL Destination].

## Verfügbare Datumsbereiche und Zeitzonen {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Berichte für Ihre [!UICONTROL Addressable Audiences] und [Ziele](../features/destinations/destinations.md) Verwenden Sie dieselben Datumsbereichsintervalle. Zu den Datumsbereichsoptionen gehören:

* [!UICONTROL Last 1 Day] (Dieses Intervall erstreckt sich von Mitternacht bis Mitternacht des vorherigen 24-Stunden-Zeitraums. Es handelt sich nicht um eine reale oder aktuelle Metrik.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle Daten und Datumsbereiche werden in der Variablen [!DNL UTC] Zeitzone. Siehe [Zeitzonen im Audience Manager](../reference/aam-time-zones.md).

## Daten in Datumsbereichsintervallen {#date-range-intervals}

Die [!UICONTROL Addressable Audience] und [!UICONTROL Destination] Metriken geben die Anzahl der Unique Users für das ausgewählte Zeitintervall zurück. Beispielsweise wird ein Besucher nur einmal gezählt, auch wenn er Ihre Site mehrmals besucht. Der erste Besuch ist der eindeutige Besuch und wird aufgezeichnet. Die nachfolgenden Besuche geben Besuche zurück und werden nicht gezählt, da sie nicht eindeutig sind.

Datumsbereiche enthalten Daten für das ausgewählte Zeitintervall oder älter. Und die Daten werden aus jedem Berichtsintervall im Zeitverlauf abgerufen. Nehmen wir beispielsweise an, dass nach Auswahl der [!UICONTROL Last 30 Days] -Option. Diese Besucher:

* *wird* in die Ergebnisse aufgenommen, die von den längeren Zeitintervallen (60 Tage, 90 Tage und Lebensdauer) zurückgegeben werden.
* *Wird nicht* in den kürzeren Intervallen, die der [!UICONTROL Last 30 Day] (Aktuell, 7 Tage und 14 Tage).

Und am 31. Tag erscheinen diese Besucher nur an 60 Tagen, 90 Tagen und [!UICONTROL Lifetime] Ergebnisse. Sie sind aus dem 30-Tage-Intervall gealtert. Besucher werden nicht von der [!UICONTROL Lifetime] Intervall.

## [!UICONTROL Addressable Audiences] Metriken {#addressable-audience-metrics}

In diesem Abschnitt werden die Metriktypen beschrieben, die von [!UICONTROL Addressable Audiences].

### Metriken auf Kundenebene {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Diese Metriken geben Daten zu Eigenschaften zurück, die realisiert werden, wenn Besucher Ihre Site besuchen oder wenn Sie eingehende Datendateien an senden [!DNL Audience Manager]. Diese Metrik bietet einen umfassenden Überblick über die Zielgruppengröße für Ihr Konto.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Anzahl der Überschneidungen von Geräten, die entweder eine [!UICONTROL rule-based trait] oder [!UICONTROL onboarded trait] während des Rückblickfensters und der Geräte, auf denen wir eine ID-Synchronisierung mit dem ausgewählten Ziel haben, unabhängig vom Zeitpunkt der Synchronisierung.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>Sie haben entweder [!UICONTROL rule-based] oder [!UICONTROL onboarded trait] während des Rückblickfensters `AND`</li><li>Sie haben eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination] unabhängig vom Zeitpunkt der Synchronisierung.</li></ul> |
| [!UICONTROL Customer Total Audience] | Anzahl der Geräte, die entweder eine [!UICONTROL rule-based trait] in Ihren Eigenschaften oder einer [!UICONTROL onboarded trait] aus Ihren Offline-Dateien während des Lookback-Fensters. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] als Prozentsatz angegeben. |

### Übereinstimmungsmetriken auf Segmentebene {#segment-level-metrics}

Diese Metriken geben Daten zu [!UICONTROL segment] Mitgliedschaft. Sie bieten eine detailliertere und genauere Ansicht der Zielgruppengröße für jeden Ihrer [!UICONTROL segments].

>[!NOTE]
>
>Die Art und Weise, wie das Rückblickfenster auf die [!UICONTROL segment] -Ebene unterscheidet sich von der auf Kundenebene. Besucher können zur Site kommen und eine [!UICONTROL trait] Vor 10 Tagen, und sie konnten sich für eine [!UICONTROL segment] seitdem und brachen die [!UICONTROL segment] Vor 2 Tagen. Wenn der 7-tägige Rückblick angewendet wird, werden diese Besucher auf die [!UICONTROL segment] Ebene, aber nicht auf Kundenebene.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzer, die zur [!UICONTROL segment] während des Rückblickzeitraums des Berichts und eine aktive ID-Synchronisierung auf Ihrer Site durchführen. Segmente können Ihre eigenen Erstanbieterdaten sowie Daten von Zweit- und Drittanbietern über [!UICONTROL traits] im [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Tipp: Bei Verwendung mit dem 1-tägigen Rückblickzeitraum kann diese Metrik Ihnen dabei helfen, den aktuellen Status Ihrer [!UICONTROL segments]. Dies liegt daran, dass die Variable [!UICONTROL Segment Addressable Audience] Metrik stellt die Benutzer dar, die in einer [!UICONTROL segment] über den Vortag. Kombinieren Sie dies mit der Tatsache, dass [!DNL Audience Manager] aktualisiert [!UICONTROL Addressable Audiences] täglich, bietet die Kombination dieser Metrik und des Lookback-Zeitraums die aktuellste Momentaufnahme Ihrer [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Zählung aller Geräte, die Mitglied Ihrer [!UICONTROL segment] während des Rückblickzeitraums des Berichts. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] als Prozentsatz angegeben. |

### Metriken auf Plattformebene {#platform-level-metrics}

Diese Metrik gibt Daten zu Aktivitäten zurück, die über alle [!DNL Audience Manager] -Kunden. Sie können eine umfassendere Sicht auf die Zielgruppe des Kunden im Vergleich zum aggregierten [!DNL Audience Manager] -Kunden.

| Metrik | Beschreibung |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Zählung aller Geräte, die mit allen [!DNL Audience Manager] Kunden auf Plattformebene während des Rückblickzeitraums des Berichts, der mit Ihrer Auswahl abgeglichen werden kann [!UICONTROL destination]. <br><br>Diese Metrik ist nützlich, da sie Folgendes anzeigt:<ul><li>Die Größe der [!UICONTROL total addressable audience] dass [!DNL Audience Manager] kann auf ein bestimmtes Targeting-Ziel zugreifen.</li><li>Wie groß die [!DNL Audience Manager] Profilpool dient der Erstellung von Zielgruppen und der Größe ihrer Zielgruppen.</li></ul> |

## Vergleich [!UICONTROL Customer] und [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Du solltest die [!UICONTROL Customer Addressable Audience] und [!UICONTROL Segment Addressable Audience] Metriken, um festzustellen, ob eine Metrik wichtiger ist als die andere. Hierbei handelt es sich um separate, unterschiedliche und unabhängige Metriken. Wie in den obigen Definitionen beschrieben, wird jede dieser Daten aus verschiedenen Datensätzen abgeleitet. Daher sollten Sie vermeiden, Schlussfolgerungen abzuleiten, wenn eine Metrik größer als die andere ist. Sie können beim Vergleich nur Folgendes sagen:

* [!UICONTROL Customer Addressable Audiences] basiert auf [!UICONTROL trait] Realisierungen *für Ihre eigenen Erstanbieterdaten*. Diese Metrik bietet einen umfassenden, umfassenden Überblick über Ihre Integration mit einem Datenpartner.

* [!UICONTROL Segment Addressable Audiences] basiert auf Segmentqualifikationen *für Ihre eigenen Erstanbieterdaten sowie Zweit- und Drittanbieterdaten*. Diese Metrik bietet eine granulare, genauere Ansicht Ihrer [!UICONTROL addressable audiences] in einer Targeting-Plattform.

## Gründe für geringe Übereinstimmungsraten für [!UICONTROL Addressable Audiences] {#low-match-rates}

Häufige Elemente, die für niedrige [!UICONTROL Addressable Audience] Übereinstimmungsraten oder Diskrepanzen in den gemeldeten Zahlen.

| Ursache | Beschreibung |
|---|---|
| Mobil-Traffic | Am meisten [!UICONTROL server-to-server] Integrationen basieren auf Synchronisierungsprozessen, die von Drittanbietern erleichtert werden [!DNL cookies]. Mobile Umgebungen verwenden jedoch keine Drittanbieter [!DNL cookies]. Dadurch wird Ihre [!UICONTROL Addressable Audiences] Zahlen können im Vergleich zu [!UICONTROL segment] Größe. <br><br>Ab Januar 2018 können Sie mobile Zielgruppen in derselben [!DNL Google] und [!DNL Adobe Advertising Cloud] Ziele, die für [!UICONTROL cookie-based] Zielgruppen. Dies bedeutet, dass Sie [!UICONTROL segments] mit kombinierter [!DNL cookie] und die Mobile ID-Mitgliedschaft in Ihrer [!DNL Google] und [!DNL Advertising Cloud] Ziele, beachten Sie, dass [!UICONTROL Addressable Audiences] nur Überschneidungen anzeigen zwischen [!DNL cookie] IDs und Ziele. [!DNL Audience Manager] sendet 100 % der mobilen Zielgruppen an [!UICONTROL destinations], aber mobile Zielgruppen werden nicht durch die [!UICONTROL Addressable Audience] Metrik. <br><br>**Hinweis**: Nehmen Sie beispielsweise eine [!UICONTROL segment] mit einer Bevölkerung von 1 000 000 Menschen. Wenn Sie dies zuordnen [!UICONTROL segment] zu [!DNL Google] oder [!DNL Adobe Advertising Cloud] Ziel, wird möglicherweise eine [!UICONTROL Addressable Audience] von 700.000 Geräten und [!UICONTROL Match Rate] 70 %. Die Mitgliedschaft von 700.000 besteht aus [!DNL cookie] IDs, die eine ID-Synchronisierung mit der [!UICONTROL destination]. Ihre [!UICONTROL Addressable Audience] kann sogar viel höher sein, da adressierbare mobile IDs nicht in dieser Metrik angezeigt werden. |
| [!DNL Safari]Traffic- | [!DNL Safari] blockiert Drittanbieter [!DNL cookies]. Dies verhindert [!DNL Audience Manager] aus der Synchronisierung von IDs mit der [!UICONTROL destination]. Mit der Einführung von [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)können Sie [!UICONTROL addressable audiences] nicht einschließen [!DNL Safari] Benutzer. |
| Getrackte Medienimpressionen | Aufgrund der Best Practices für den Adserver werden ID-Synchronisierungen nicht in Anzeigen-Tags vorgenommen. Kunden, die eine große Menge an Offsite-Werbung betreiben, synchronisieren Benutzer nicht mit Drittanbieter-Integrationen in diesen Umgebungen. Außerdem kann eine große Menge erfasster Medien-Impressionsdaten die [!UICONTROL addressable audience] Zahlen. |

## Fehlerbehebung mit [!UICONTROL Addressable Audiences] {#troubleshooting}

Zusätzlich zu den Übereinstimmungsraten können Sie auch [!UICONTROL Addressable Audiences] als Tool zur Fehlerbehebung.

Angenommen, Sie senden ein Segment an eine [!UICONTROL destination] und [!UICONTROL destination] zeigt niedrige Berichtszahlen an. Überprüfen der [!UICONTROL Addressable Audience] -Ergebnisse zeigen Ihnen, ob es sich um ein technisches Problem oder nur um einen Fall niedriger Übereinstimmungsraten handelt. Eine niedrige Übereinstimmungsrate zeigt Ihre [!UICONTROL destination] ist nicht besonders gut für Ihre ausgewählten Segmente. Ein Unterschied in der [!UICONTROL total addressable audience] Zahlen zwischen [!DNL Audience Manager] und [!UICONTROL destination] weist auf ein Integrations-, Synchronisations- oder anderes technisches Problem hin. Wenden Sie sich in diesen Fällen an Ihren Kundenbetreuer.

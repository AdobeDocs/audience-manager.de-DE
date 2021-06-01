---
description: Eine Übersicht über die Funktion "Addressable Audience"und die Anwendungsfälle.
keywords: DIL
seo-description: Eine Übersicht über die Funktion "Addressable Audience"und die Anwendungsfälle.
seo-title: Ansprechbare Zielgruppen
solution: Audience Manager
title: Ansprechbare Zielgruppen
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Übereinstimmungsraten
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 1%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Eine Übersicht über die Funktionen und Anwendungsfälle von [!UICONTROL Addressable Audience].

## Was ist eine [!UICONTROL Addressable Audience]? {#addressable-audience-description}

Die Funktion [!UICONTROL Addressable Audiences] zeigt die Überschneidung zwischen den Zielgruppen, die Sie in all Ihren Eigenschaften sehen, in denen [!DNL Audience Manager] Daten und Ihr ausgewähltes Ziel erfasst. Sehen Sie sich die folgende Abbildung an, um dieses Konzept zu verstehen. Die Überschneidung zwischen den einzelnen Kreisen stellt die verschiedenen Arten von adressierbaren Zielgruppen dar.

![](assets/addressableAudienceVenn.png)


| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] für  [!UICONTROL Destination] | Zählung aller Geräte, die während des Rückblickzeitraums des Berichts mit allen [!DNL Audience Manager]-Kunden auf Plattformebene interagiert haben und die mit Ihrem ausgewählten [!UICONTROL destination] übereinstimmen können. <br><br>Diese Metrik ist nützlich, da sie Folgendes anzeigt: <ul><li>Die Gesamtgröße [!UICONTROL addressable audience], die [!DNL Audience Manager] für ein bestimmtes Targeting [!UICONTROL destination] erreichen kann.</li><li>Wie groß der Profilpool [!DNL Audience Manager] für eine Zielplattform ist und wie groß seine Zielgruppen sind.</li></ul> |
| [!UICONTROL Customer Total Audience] | Zählung der Geräte, die während des Rückblickfensters entweder eine [!UICONTROL rule-based trait] für Ihre Eigenschaften oder eine [!UICONTROL onboarded trait] aus Ihren Offline-Dateien realisiert haben. |
| [!UICONTROL Addressable Audience Match Rate] | Zählung der Überschneidungen von Geräten, die während des Rückblickfensters entweder eine [!UICONTROL rule-based trait] oder eine [!UICONTROL onboarded trait] realisiert haben, sowie Geräten, bei denen eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination] stattfindet, unabhängig vom Zeitpunkt der Synchronisierung.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>während des Lookback-Fensters `AND` entweder einen [!UICONTROL rule-based] oder einen [!UICONTROL onboarded trait] realisiert haben</li><li>Führen Sie unabhängig vom Zeitpunkt der Synchronisierung eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination] durch.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ in Prozent  [!UICONTROL Customer Total Audience] ausgedrückt. |
| [!UICONTROL Total Segment Population] | Zählung aller Geräte, die während des Rückblickzeitraums des Berichts zu Ihrem [!UICONTROL segment] gehörten. |
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzer, die während des Rückblickzeitraums des Berichts zu [!UICONTROL segment] gehörten und eine aktive ID-Synchronisierung auf Ihrer Site haben. [!UICONTROL Segments] kann Ihre eigenen Erstanbieterdaten sowie Zweit- und Drittanbieterdaten enthalten, die über das  [!UICONTROL traits] erworbene  [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) abgerufen werden. <br><br>Tipp: Bei Verwendung mit dem 1-Tage-Rückblickzeitraum kann diese Metrik Ihnen dabei helfen, den aktuellen Status Ihrer  [!UICONTROL segments]zu verstehen. Dies liegt daran, dass die Metrik [!UICONTROL Segment Addressable Audience] die Benutzer darstellt, die während des Vortags in einem [!UICONTROL segment] geblieben sind. Kombinieren Sie dies mit der Tatsache, dass [!DNL Audience Manager] [!UICONTROL Addressable Audiences] täglich aktualisiert. Durch Kombination dieser Metrik und des Lookback-Zeitraums erhalten Sie die aktuellste Momentaufnahme Ihrer [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ in Prozent  [!UICONTROL Total Segment Population] ausgedrückt. |

## [!UICONTROL Addressable Audiences]Schnittstelle:{#addressable-audience-interface}

Die Funktion [!UICONTROL Addressable Audience] wandelt dieses abstrakte Konzept in quantifizierbare Daten um. In [!DNL Audience Manager] zeigt diese Funktion Zielgruppenüberschneidungen mit Datenvisualisierungen an, die einen Überblick über Informationen und numerische Daten in Tabellenform bieten.

[!UICONTROL Addressable Audiences] befindet sich in  **[!UICONTROL Audience Data > Destinations]**. Wählen Sie **[!UICONTROL Integrated Platforms > Device-Based]** aus, um adressierbare Zielgruppenmetriken anzuzeigen.

![](assets/addressable-audiences-landing.png)

Die drei Metriken, die Sie auf der Landingpage [!UICONTROL Addressable Audiences] sehen können, stellen Folgendes dar:

| Metrik | Beschreibung |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Diese Metrik stellt den [!UICONTROL Customer Addressable Audience] (in der obigen Tabelle beschrieben) *für die letzten 30 Tage dar.* |
| **[!UICONTROL Match Rate]** | Diese Metrik stellt den [!UICONTROL Addressable Audience Match Rate] (in der obigen Tabelle beschrieben) *für die letzten 30 Tage* dar. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Zählung aller Geräte, die während des Rückblickzeitraums des Berichts mit allen [!DNL Audience Manager]-Kunden auf Plattformebene interagiert haben und die mit diesem [!UICONTROL destination] abgeglichen werden können. Weitere Informationen finden Sie unter [Metriken auf Plattformebene](/help/using/features/addressable-audiences.md#platform-level-metrics) . |

Klicken Sie auf den Namen eines [!UICONTROL server-to-server destination] , um Ihre adressierbaren Zielgruppendaten anzuzeigen. Beachten Sie, dass diese Funktion nur Daten für [!UICONTROL server-to-server destinations] zurückgibt und für den Zugriff Administratorberechtigungen erforderlich sind.

![](assets/addressableAudiences.png)

Die Überprüfung dieser Daten hilft Ihnen bei Folgendem:

* **Prognosen und Planung:** [!UICONTROL Segment Addressable Audience] -Daten liefern Ihnen mehr Granularität in den Segmenten, die Sie zur Zielgruppenbestimmung und Aktivierung an ein Ziel senden möchten.

* **Leistungsüberprüfungen:** Die  [!UICONTROL Addressable Audiences] Funktion ist auch ein Tool zur Fehlerbehebung. Sie können damit die Kampagnenleistung überprüfen, die Reichweite der Kampagne verstehen und mit Targeting-/Aktivierungspartnern vergleichen, wenn die erwarteten Ergebnisse nicht angezeigt werden.

### Anzeigen von Daten von Drittanbietern und Auswirkungen für Übereinstimmungsraten

Vor dem Kauf von Drittanbieterdaten für die Zielgruppenerfassung können Kunden die Überschneidung mit anderen Datenanbietern überprüfen. Auf diese Weise können Sie vor dem Kauf neuer Daten eine fundierte Entscheidung treffen. Die ID-Synchronisierungen für erworbene Drittanbieterdaten beruhen nicht nur auf der Überschneidung Ihrer Daten, sondern auch auf den Fußabdrücken von Drittanbietern gegenüber allen anderen [!DNL Audience Manager]-Kunden. Ihr [!DNL Adobe]-Berater kann Ihnen dabei helfen, zusätzliche relevante Datenquellen zu identifizieren, um Prospektionskampagnen zu optimieren.

### Mobilbenutzer und Übereinstimmungsraten

Es gibt Lücken beim Versuch, [!DNL Safari] oder Benutzer mobiler Apps zu verbinden, bei denen kein Drittanbieter [!DNL cookies] vorhanden ist. Dies erschwert die Synchronisierung von Benutzern mit einigen Partnern, da nur die [!DNL Adobe] IDs für synchronisierte Drittanbieter [!DNL cookies] in den Medien-Versandlogs enthalten sind. Aus diesem Grund können Sie [niedrige Übereinstimmungsraten](../features/addressable-audiences.md#low-match-rates) für [!UICONTROL destinations] sehen.

## Datumsbereiche in [!UICONTROL Addressable Audiences] und [!UICONTROL Destinations] {#date-ranges}

In den folgenden Abschnitten finden Sie verfügbare Datumsbereiche und Informationen dazu, wie Daten aus jedem Intervall in den Berichten für [!UICONTROL Addressable Audience] oder [!UICONTROL Destination] zurückliegen.

## Verfügbare Datumsbereiche und Zeitzonen {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Berichte für [!UICONTROL Addressable Audiences] und [Ziele](../features/destinations/destinations.md) verwenden dieselben Datumsbereichsintervalle. Zu den Datumsbereichsoptionen gehören:

* [!UICONTROL Last 1 Day] (Dieses Intervall erstreckt sich von Mitternacht bis Mitternacht des vorherigen 24-Stunden-Zeitraums. Es handelt sich nicht um eine reale oder aktuelle Metrik.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle Daten und Datumsbereiche werden in der Zeitzone [!DNL UTC] festgelegt. Siehe [Zeitzonen in Audience Manager](../reference/aam-time-zones.md).

## Daten in Datumsbereichsintervallen {#date-range-intervals}

Die Metriken [!UICONTROL Addressable Audience] und [!UICONTROL Destination] geben die Anzahl der Unique Users für das ausgewählte Zeitintervall zurück. Beispielsweise wird ein Besucher nur einmal gezählt, auch wenn er Ihre Site mehrmals besucht. Der erste Besuch ist der eindeutige Besuch und wird aufgezeichnet. Die nachfolgenden Besuche geben Besuche zurück und werden nicht gezählt, da sie nicht eindeutig sind.

Datumsbereiche enthalten Daten für das ausgewählte Zeitintervall oder älter. Und die Daten werden aus jedem Berichtsintervall im Zeitverlauf abgerufen. Nehmen wir beispielsweise an, dass nach Auswahl der Option [!UICONTROL Last 30 Days] zwei Besucher angezeigt werden. Diese Besucher:

* *Wird* in den Ergebnissen enthalten sein, die von den längeren Zeitintervallen (60 Tage, 90 Tage und Lebensdauer) zurückgegeben werden.
* *Wird nicht in den kürzeren Intervallen* eingeschlossen, die der  [!UICONTROL Last 30 Day] Option vorangehen (aktuell, 7 Tage und 14 Tage).

Und am 31. Tag erscheinen diese Besucher nur in den Ergebnissen von 60 Tagen, 90 Tagen und [!UICONTROL Lifetime]. Sie sind aus dem 30-Tage-Intervall gealtert. Besucher werden nicht aus dem [!UICONTROL Lifetime]-Intervall veraltert.

## [!UICONTROL Addressable Audiences] Metriken {#addressable-audience-metrics}

In diesem Abschnitt werden die Metriktypen beschrieben, die von [!UICONTROL Addressable Audiences] bereitgestellt werden.

### Metriken auf Kundenebene {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Diese Metriken geben Daten zu Eigenschaften zurück, die realisiert werden, wenn Besucher Ihre Site besuchen oder wenn Sie eingehende Datendateien an [!DNL Audience Manager] senden. Diese Metrik bietet einen umfassenden Überblick über die Zielgruppengröße für Ihr Konto.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Zählung der Überschneidungen von Geräten, die während des Rückblickfensters entweder eine [!UICONTROL rule-based trait] oder eine [!UICONTROL onboarded trait] realisiert haben, sowie Geräten, bei denen eine ID-Synchronisierung mit dem ausgewählten Ziel unabhängig vom Zeitpunkt der Synchronisierung erfolgt ist.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>während des Lookback-Fensters `AND` entweder einen [!UICONTROL rule-based] oder einen [!UICONTROL onboarded trait] realisiert haben</li><li>Führen Sie unabhängig vom Zeitpunkt der Synchronisierung eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination] durch.</li></ul> |
| [!UICONTROL Customer Total Audience] | Zählung der Geräte, die während des Rückblickfensters entweder eine [!UICONTROL rule-based trait] für Ihre Eigenschaften oder eine [!UICONTROL onboarded trait] aus Ihren Offline-Dateien realisiert haben. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ in Prozent  [!UICONTROL Customer Total Audience] ausgedrückt. |

### Übereinstimmungsmetriken auf Segmentebene {#segment-level-metrics}

Diese Metriken geben Daten zur Mitgliedschaft [!UICONTROL segment] zurück. Sie bieten eine detailliertere und genauere Ansicht der Zielgruppengröße für jedes Ihrer [!UICONTROL segments].

>[!NOTE]
>
>Die Art und Weise, wie das Lookback-Fenster auf der Ebene [!UICONTROL segment] angewendet wird, unterscheidet sich von der auf Kundenebene. Besucher können vor 10 Tagen zur Site kommen und ein [!UICONTROL trait] -Zeichen realisieren. Seitdem könnten sie sich für ein [!UICONTROL segment] qualifizieren und vor 2 Tagen aus dem [!UICONTROL segment] aussteigen. Wenn der 7-tägige Lookback angewendet wird, werden diese Besucher auf der Ebene [!UICONTROL segment] gezählt, jedoch nicht auf Kundenebene.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzer, die während des Rückblickzeitraums des Berichts zu [!UICONTROL segment] gehörten und eine aktive ID-Synchronisierung auf Ihrer Site haben. Segmente können Ihre eigenen Erstanbieterdaten sowie Daten von Zweit- und Drittanbietern über [!UICONTROL traits] enthalten, die im [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) erworben wurden.<br><br>Tipp: Bei Verwendung mit dem 1-Tage-Rückblickzeitraum kann diese Metrik Ihnen dabei helfen, den aktuellen Status Ihrer  [!UICONTROL segments]zu verstehen. Dies liegt daran, dass die Metrik [!UICONTROL Segment Addressable Audience] die Benutzer darstellt, die während des Vortags in einem [!UICONTROL segment] geblieben sind. Kombinieren Sie dies mit der Tatsache, dass [!DNL Audience Manager] [!UICONTROL Addressable Audiences] täglich aktualisiert. Durch Kombination dieser Metrik und des Lookback-Zeitraums erhalten Sie die aktuellste Momentaufnahme Ihrer [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Zählung aller Geräte, die während des Rückblickzeitraums des Berichts zu Ihrem [!UICONTROL segment] gehörten. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ in Prozent  [!UICONTROL Total Segment Population] ausgedrückt. |

### Metriken auf Plattformebene {#platform-level-metrics}

Diese Metrik gibt Daten zu Aktivitäten zurück, die über alle [!DNL Audience Manager] -Kunden erfasst wurden. Sie können eine umfassendere Sicht auf die Zielgruppe des Kunden im Vergleich zu den aggregierten [!DNL Audience Manager] -Kunden bieten.

| Metrik | Beschreibung |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Zählung aller Geräte, die während des Rückblickzeitraums des Berichts mit allen [!DNL Audience Manager]-Kunden auf Plattformebene interagiert haben und die mit Ihrem ausgewählten [!UICONTROL destination] übereinstimmen können. <br><br>Diese Metrik ist nützlich, da sie Folgendes anzeigt:<ul><li>Die Größe von [!UICONTROL total addressable audience], die [!DNL Audience Manager] für ein bestimmtes Targeting-Ziel erreichen kann.</li><li>Wie groß der Profilpool [!DNL Audience Manager] für eine Zielplattform ist und wie groß seine Zielgruppen sind.</li></ul> |

## Vergleich von [!UICONTROL Customer] und [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Sie sollten die Metriken [!UICONTROL Customer Addressable Audience] und [!UICONTROL Segment Addressable Audience] nicht vergleichen, um festzustellen, ob eine Metrik wichtiger ist als die andere. Hierbei handelt es sich um separate, unterschiedliche und unabhängige Metriken. Wie in den obigen Definitionen beschrieben, wird jede dieser Daten aus verschiedenen Datensätzen abgeleitet. Daher sollten Sie vermeiden, Schlussfolgerungen abzuleiten, wenn eine Metrik größer als die andere ist. Sie können beim Vergleich nur Folgendes sagen:

* [!UICONTROL Customer Addressable Audiences] basiert auf  [!UICONTROL trait] Realisierungen  *für Ihre eigenen Erstanbieterdaten*. Diese Metrik bietet einen umfassenden, umfassenden Überblick über Ihre Integration mit einem Datenpartner.

* [!UICONTROL Segment Addressable Audiences] basiert auf Segmentqualifikationen  *für Ihre eigenen Erstanbieterdaten sowie auf Zweit- und Drittanbieterdaten*. Diese Metrik bietet eine granulare, genauere Ansicht Ihrer [!UICONTROL addressable audiences] in einer Targeting-Plattform.

## Gründe für niedrige Übereinstimmungsraten für [!UICONTROL Addressable Audiences] {#low-match-rates}

Häufige Elemente, die für niedrige [!UICONTROL Addressable Audience] Übereinstimmungsraten oder Diskrepanzen in den gemeldeten Zahlen verantwortlich sind.

| Ursache | Beschreibung |
|---|---|
| Mobil-Traffic | Die meisten [!UICONTROL server-to-server]-Integrationen basieren auf Synchronisierungsprozessen, die von Drittanbietern [!DNL cookies] unterstützt werden. Mobile Umgebungen verwenden jedoch keine Drittanbieter [!DNL cookies]. Daher können Ihre [!UICONTROL Addressable Audiences]-Zahlen im Vergleich zur [!UICONTROL segment]-Größe niedrig erscheinen. <br><br>Ab Januar 2018 können Sie mobile Zielgruppen in denselben  [!DNL Google] und denselben  [!DNL Adobe Advertising Cloud] Zielen aktivieren, die für  [!UICONTROL cookie-based] Zielgruppen eingerichtet sind. Das bedeutet, dass Sie [!UICONTROL segments] mit kombinierter [!DNL cookie] und mobiler ID-Mitgliedschaft an Ihre [!DNL Google]- und [!DNL Advertising Cloud]-Ziele senden können. Beachten Sie jedoch, dass [!UICONTROL Addressable Audiences] nur die Überschneidung zwischen [!DNL cookie]-IDs und -Zielen anzeigt. [!DNL Audience Manager] sendet 100 % der mobilen Zielgruppen an  [!UICONTROL destinations], mobile Zielgruppen werden jedoch nicht anhand der  [!UICONTROL Addressable Audience] Metrik gemessen. <br><br>**Hinweis**: Nehmen wir beispielsweise eine  [!UICONTROL segment] mit einer Bevölkerung von 1.000.000. Wenn Sie dieses [!UICONTROL segment] einem [!DNL Google]- oder [!DNL Adobe Advertising Cloud]-Ziel zuordnen, wird möglicherweise ein [!UICONTROL Addressable Audience] von 700.000 Geräten und ein [!UICONTROL Match Rate] von 70 % angezeigt. Die Mitgliedschaft von 700.000 besteht aus [!DNL cookie] IDs, die eine ID-Synchronisierung mit [!UICONTROL destination] haben. Ihr [!UICONTROL Addressable Audience] könnte sogar viel höher sein, da adressierbare mobile IDs nicht in dieser Metrik angezeigt werden. |
| [!DNL Safari]Traffic- | [!DNL Safari] blockiert Drittanbieter  [!DNL cookies]. Dadurch wird verhindert, dass [!DNL Audience Manager] IDs mit [!UICONTROL destination] synchronisiert werden. Mit der Einführung von [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/) können Sie erwarten, dass Ihre [!UICONTROL addressable audiences] keine [!DNL Safari] Benutzer enthält. |
| Getrackte Medienimpressionen | Aufgrund der Best Practices für den Adserver werden ID-Synchronisierungen nicht in Anzeigen-Tags vorgenommen. Kunden, die eine große Menge an Offsite-Werbung betreiben, synchronisieren Benutzer nicht mit Drittanbieter-Integrationen in diesen Umgebungen. Außerdem kann eine große Menge erfasster Medien-Impressionsdaten die Anzahl der [!UICONTROL addressable audience] verringern. |

## Fehlerbehebung mit [!UICONTROL Addressable Audiences] {#troubleshooting}

Zusätzlich zu den Übereinstimmungsraten, die angezeigt werden, können Sie auch [!UICONTROL Addressable Audiences] als Tool zur Fehlerbehebung verwenden.

Angenommen, Sie senden ein Segment an ein [!UICONTROL destination] und [!UICONTROL destination] zeigt niedrige Berichtszahlen an. Wenn Sie die [!UICONTROL Addressable Audience] Ergebnisse überprüfen, wird Ihnen angezeigt, ob es sich um ein technisches Problem oder nur um einen Fall niedriger Übereinstimmungsraten handelt. Eine niedrige Übereinstimmungsrate zeigt an, dass Ihr [!UICONTROL destination] nicht besonders gut für Ihre ausgewählten Segmente ist. Ein Unterschied in den [!UICONTROL total addressable audience]-Zahlen zwischen [!DNL Audience Manager] und [!UICONTROL destination] weist jedoch auf eine Integration, Synchronisierung oder ein anderes technisches Problem hin. Wenden Sie sich in diesen Fällen an Ihren Kundenbetreuer.

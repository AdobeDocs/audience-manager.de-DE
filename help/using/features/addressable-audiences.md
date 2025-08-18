---
description: Eine Übersicht über die Funktion und die Anwendungsfälle für adressierbare Zielgruppen.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Addressable Audiences
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1831'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Eine Übersicht über die [!UICONTROL Addressable Audience] Funktion und Anwendungsfälle.

## Was ist ein [!UICONTROL Addressable Audience]? {#addressable-audience-description}

Die [!UICONTROL Addressable Audiences] Funktion zeigt die Überschneidung zwischen den Zielgruppen, die Sie in all Ihren Eigenschaften sehen, in denen [!DNL Audience Manager] Daten erfasst, und dem ausgewählten Ziel. Sehen Sie sich die folgende Abbildung an, um dieses Konzept besser zu verstehen. Die Überschneidung zwischen den einzelnen Kreisen stellt die verschiedenen Typen adressierbarer Zielgruppen dar.

![](assets/addressableAudienceVenn.png)


| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] für eine [!UICONTROL Destination] | Eine Anzahl aller Geräte, die während des Lookback-Zeitraums des Berichts auf Plattformebene mit allen [!DNL Audience Manager] Kunden interagiert haben und die Ihren ausgewählten [!UICONTROL destination] zugeordnet werden können. <br><br>Diese Metrik ist nützlich, da sie Folgendes anzeigt: <ul><li>Die Gesamtgröße der [!UICONTROL addressable audience], die [!DNL Audience Manager] auf einer bestimmten [!UICONTROL destination] erreichen können.</li><li>Wie groß der [!DNL Audience Manager]-Profil-Pool für eine Targeting-Plattform ist und die Größe der Zielgruppen.</li></ul> |
| [!UICONTROL Customer Total Audience] | Anzahl der Geräte, die während des Lookback-Fensters entweder eine [!UICONTROL rule-based trait] in Ihren Eigenschaften oder eine [!UICONTROL onboarded trait] aus Ihren Offline-Dateien realisiert haben. |
| [!UICONTROL Customer Addressable Audience] | Zählung der Überschneidungen von Geräten, die während des Lookback-Fensters entweder eine [!UICONTROL rule-based trait] oder eine [!UICONTROL onboarded trait] realisiert haben, und Geräten, bei denen eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination] erfolgt, unabhängig vom Zeitpunkt der Synchronisierung.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>Während des Lookback-Fensters entweder ein [!UICONTROL rule-based] oder ein [!UICONTROL onboarded trait] realisiert haben `AND`</li><li>Es muss unabhängig vom Zeitpunkt der Synchronisierung eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination] erfolgen.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] als Prozentsatz ausgedrückt. |
| [!UICONTROL Total Segment Population] | Eine Zählung aller Geräte, die während des Lookback-Zeitraums zu Ihrem [!UICONTROL segment] gehörten. |
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzenden, die während des Lookback-Zeitraums des Berichts zur [!UICONTROL segment] gehört haben und über eine aktive ID-Synchronisierung auf Ihrer Site verfügen. [!UICONTROL Segments] können Ihre eigenen Erstanbieterdaten sowie Zweit- und Drittanbieterdaten über [!UICONTROL traits] einbeziehen, die in der [Audience Marketplace erfasst ](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Tipp: Bei Verwendung mit der eintägigen Lookback-Phase kann diese Metrik Ihnen dabei helfen, den aktuellen Status Ihrer [!UICONTROL segments] zu verstehen. Dies liegt daran, dass die Metrik [!UICONTROL Segment Addressable Audience] die Benutzenden darstellt, die den gesamten Vortag in einem [!UICONTROL segment] verblieben sind. [!DNL Audience Manager] Kombinieren Sie dies mit der Tatsache, dass [!UICONTROL Addressable Audiences] täglich aktualisiert wird, und kombinieren Sie diese Metrik und den Lookback-Zeitraum, um die aktuellste Momentaufnahme Ihrer [!UICONTROL segments] zu erhalten. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] als Prozentsatz ausgedrückt. |

## [!UICONTROL Addressable Audiences] {#addressable-audience-interface}

Die [!UICONTROL Addressable Audience] Funktion wandelt dieses abstrakte Konzept in quantifizierbare Daten um. [!DNL Audience Manager] zeigt diese Funktion Zielgruppenüberschneidungen mit Datenvisualisierungen an, die Informationen auf einen Blick zusammen mit numerischen Daten in tabellarischer Form bereitstellen.

[!UICONTROL Addressable Audiences] befindet sich in **[!UICONTROL Audience Data > Destinations]**. Wählen Sie **[!UICONTROL Integrated Platforms > Device-Based]** aus, um adressierbare Zielgruppenmetriken anzuzeigen.

![](assets/addressable-audiences-landing.png)

Die drei Metriken, die Sie auf der [!UICONTROL Addressable Audiences] Landingpage sehen können, stellen Folgendes dar:

| Metrik | Beschreibung |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Diese Metrik stellt die [!UICONTROL Customer Addressable Audience] (wie in der obigen Tabelle beschrieben) *der letzten 30 Tage) dar* |
| **[!UICONTROL Match Rate]** | Diese Metrik stellt die [!UICONTROL Addressable Audience Match Rate] (wie in der obigen Tabelle beschrieben) *für die letzten 30 Tage* dar. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Eine Zählung aller Geräte, die während des Lookback-Zeitraums des Berichts auf Plattformebene mit allen [!DNL Audience Manager] Kunden interagiert haben und die dieser [!UICONTROL destination] zugeordnet werden könnten. Weitere Informationen finden [ unter ](/help/using/features/addressable-audiences.md#platform-level-metrics) auf Plattformebene . |

Klicken Sie auf den Namen eines [!UICONTROL server-to-server destination], um Ihre adressierbaren Zielgruppendaten anzuzeigen. Beachten Sie, dass diese Funktion nur Daten für [!UICONTROL server-to-server destinations] zurückgibt und der Zugriff Administratorberechtigungen erfordert.

![](assets/addressableAudiences.png)

Die Überprüfung dieser Daten kann Ihnen bei Folgendem helfen:

* **Prognose und Planung:** [!UICONTROL Segment Addressable Audience] Daten bieten Ihnen mehr Granularität bei den Segmenten, die Sie zur Zielgruppenbestimmung und Aktivierung an ein Ziel senden möchten.

* **Leistungsprüfungen:** Die [!UICONTROL Addressable Audiences] Funktion ist auch ein Tool zur Fehlerbehebung. Damit können Sie die Leistung von Kampagnen überprüfen, die Reichweite von Kampagnen verstehen und mit Targeting-/Aktivierungspartnern abgleichen, wenn Sie nicht die erwarteten Ergebnisse sehen.

### Kundenakquise mit Drittanbieterdaten und Auswirkungen auf die Übereinstimmungsraten

Vor dem Kauf von Drittanbieterdaten für die Zielgruppenerfassung können Kunden die Überschneidung mit anderen Datenanbietern überprüfen. Auf diese Weise können Sie vor dem Kauf neuer Daten eine fundierte Entscheidung treffen. Die ID-Synchronisierung für erworbene Drittanbieterdaten beruht nicht nur auf der Überschneidung Ihrer Daten, sondern auch auf den Kundenabdrücken von Drittanbietern bei allen anderen [!DNL Audience Manager]. Ihr [!DNL Adobe] Berater kann Ihnen dabei helfen, zusätzliche relevante Datenquellen zu identifizieren, um Interessenskampagnen zu optimieren.

### Mobile Benutzer und Übereinstimmungsraten

Es gibt Lücken beim Versuch, [!DNL Safari]- oder Mobile-App-Benutzer zu verbinden, wenn keine Drittanbieter-[!DNL cookies] vorhanden sind. Dies erschwert die Synchronisierung von Benutzern mit einigen Partnern, da in den Medienbereitstellungsprotokollen nur die [!DNL Adobe]-IDs für synchronisierte [!DNL cookies] von Drittanbietern angegeben werden. Dies ist ein Grund, warum für Ihre [ möglicherweise ](../features/addressable-audiences.md#low-match-rates)niedrige Übereinstimmungsraten[!UICONTROL destinations] angezeigt werden.

## Datumsbereiche in [!UICONTROL Addressable Audiences] und [!UICONTROL Destinations] {#date-ranges}

In den folgenden Abschnitten finden Sie Informationen zu den verfügbaren Datumsbereichen und dazu, wie die Daten aus den einzelnen Intervallen in den Berichten für eine [!UICONTROL Addressable Audience] oder [!UICONTROL Destination] altern.

## Verfügbare Datumsbereiche und Zeitzonen {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Berichte für Ihre [!UICONTROL Addressable Audiences] und [Ziele](../features/destinations/destinations.md) verwenden dieselben Datumsbereichsintervalle. Zu den Datumsbereichsoptionen gehören:

* [!UICONTROL Last 1 Day] (Dieses Intervall läuft von Mitternacht bis Mitternacht des vorherigen 24-Stunden-Zeitraums. Es handelt sich nicht um eine Echtzeit- oder aktuelle Zeitmetrik.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle Datumsangaben und Datumsbereiche werden in der [!DNL UTC] Zeitzone festgelegt. Siehe [Zeitzonen in Audience Manager](../reference/aam-time-zones.md).

## Daten in Datumsbereichsintervallen {#date-range-intervals}

Die [!UICONTROL Addressable Audience]- und [!UICONTROL Destination]-Metriken geben die Anzahl der eindeutigen Benutzer für das ausgewählte Zeitintervall zurück. Beispielsweise wird eine Besucherin oder ein Besucher nur einmal gezählt, auch wenn sie bzw. er mehrmals zu Ihrer Site kommt. Der erste Besuch ist der eindeutige Besuch und wird aufgezeichnet. Die nachfolgenden Besuche sind wiederkehrende Besuche und werden nicht gezählt, da sie nicht eindeutig sind.

Datumsbereiche enthalten Daten für das ausgewählte Zeitintervall oder älter. Außerdem altern die Daten aus jedem Berichtsintervall im Zeitverlauf. Nehmen wir beispielsweise an, dass nach Auswahl der Option [!UICONTROL Last 30 Days] zwei Besucher angezeigt werden. In den Berichten haben diese Besucher Folgendes erreicht:

* *Wird* in die Ergebnisse aufgenommen, die von den längeren Zeitintervallen (60 Tage, 90 Tage und Lebensdauer) zurückgegeben werden.
* *Wird nicht* in den kürzeren Intervallen eingeschlossen, die der [!UICONTROL Last 30 Day]-Option vorangehen (aktuell, 7 Tage und 14 Tage).

Und am Tag 31 werden diese Besucher nur am 60. Tag, 90. Tag und [!UICONTROL Lifetime] angezeigt. Sie sind innerhalb des 30-Tage-Intervalls gealtert. Besucher altern nicht außerhalb des [!UICONTROL Lifetime] Intervalls.

## [!UICONTROL Addressable Audiences] Metriken {#addressable-audience-metrics}

In diesem Abschnitt werden die von [!UICONTROL Addressable Audiences] bereitgestellten Metriktypen beschrieben.

### Metriken auf Kundenebene {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Diese Metriken geben Daten zu Eigenschaften zurück, die realisiert werden, wenn Besucher auf Ihre Website kommen oder wenn Sie eingehende Datendateien an [!DNL Audience Manager] senden. Diese Metriken bieten eine umfassende Ansicht der Zielgruppengröße für Ihr Konto.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Zählung der Überschneidungen von Geräten, die während des Lookback-Fensters entweder eine [!UICONTROL rule-based trait] oder eine [!UICONTROL onboarded trait] realisiert haben, und Geräten, bei denen wir eine ID-Synchronisierung mit dem ausgewählten Ziel haben, unabhängig vom Zeitpunkt der Synchronisierung.<br><br>Diese Metrik stellt Geräte dar, die:<ul><li>Während des Lookback-Fensters entweder ein [!UICONTROL rule-based] oder ein [!UICONTROL onboarded trait] realisiert haben `AND`</li><li>Es muss unabhängig vom Zeitpunkt der Synchronisierung eine ID-Synchronisierung mit dem ausgewählten [!UICONTROL destination] erfolgen.</li></ul> |
| [!UICONTROL Customer Total Audience] | Anzahl der Geräte, die während des Lookback-Fensters entweder eine [!UICONTROL rule-based trait] in Ihren Eigenschaften oder eine [!UICONTROL onboarded trait] aus Ihren Offline-Dateien realisiert haben. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ÷ [!UICONTROL Customer Total Audience] als Prozentsatz ausgedrückt. |

### Match-Metriken auf Segmentebene {#segment-level-metrics}

Diese Metriken geben Daten zur [!UICONTROL segment] zurück. Sie bieten eine detailliertere und genauere Ansicht der Zielgruppengröße für jede Ihrer [!UICONTROL segments].

>[!NOTE]
>
>Die Art und Weise, wie das Lookback-Fenster auf [!UICONTROL segment] angewendet wird, unterscheidet sich von der auf Kundenebene. Besucher können auf die Website kommen und eine [!UICONTROL trait] vor 10 Tagen realisieren, und sie konnten sich für eine [!UICONTROL segment] seither qualifizieren und die [!UICONTROL segment] vor 2 Tagen abbrechen. Wenn der 7-tägige Lookback angewendet wird, werden diese Besucher auf [!UICONTROL segment], aber nicht auf Kundenebene gezählt.

| Metrik | Beschreibung |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Die Anzahl der Benutzenden, die während des Lookback-Zeitraums des Berichts zur [!UICONTROL segment] gehört haben und über eine aktive ID-Synchronisierung auf Ihrer Site verfügen. Segmente können Ihre eigenen Erstanbieterdaten sowie Zweit- und Drittanbieterdaten über [!UICONTROL traits] enthalten, die in der [Audience Marketplace erfasst ](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Tipp: Bei Verwendung mit der eintägigen Lookback-Phase kann diese Metrik Ihnen dabei helfen, den aktuellen Status Ihrer [!UICONTROL segments] zu verstehen. Dies liegt daran, dass die Metrik [!UICONTROL Segment Addressable Audience] die Benutzenden darstellt, die den gesamten Vortag in einem [!UICONTROL segment] verblieben sind. [!DNL Audience Manager] Kombinieren Sie dies mit der Tatsache, dass [!UICONTROL Addressable Audiences] täglich aktualisiert wird, und kombinieren Sie diese Metrik und den Lookback-Zeitraum, um die aktuellste Momentaufnahme Ihrer [!UICONTROL segments] zu erhalten. |
| [!UICONTROL Total Segment Population] | Eine Zählung aller Geräte, die während des Lookback-Zeitraums zu Ihrem [!UICONTROL segment] gehörten. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ÷ [!UICONTROL Total Segment Population] als Prozentsatz ausgedrückt. |

### Metriken auf Plattformebene {#platform-level-metrics}

Diese Metrik gibt Daten zu Aktivitäten zurück, die über alle [!DNL Audience Manager] Kunden hinweg erfasst wurden. Sie können einen breiteren Überblick über die Zielgruppe des Kunden im Vergleich zu den aggregierten [!DNL Audience Manager]-Kunden bieten.

| Metrik | Beschreibung |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Eine Anzahl aller Geräte, die während des Lookback-Zeitraums des Berichts auf Plattformebene mit allen [!DNL Audience Manager] Kunden interagiert haben und die Ihren ausgewählten [!UICONTROL destination] zugeordnet werden können. <br><br>Diese Metrik ist nützlich, da sie Folgendes anzeigt:<ul><li>Die Größe der [!UICONTROL total addressable audience], die [!DNL Audience Manager] für ein bestimmtes Zielgruppenziel erreichen können.</li><li>Wie groß der [!DNL Audience Manager]-Profil-Pool für eine Targeting-Plattform ist und die Größe der Zielgruppen.</li></ul> |

## Vergleichen von [!UICONTROL Customer] und [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Sie sollten die [!UICONTROL Customer Addressable Audience]- und [!UICONTROL Segment Addressable Audience]-Metriken nicht vergleichen, um festzustellen, ob eine Metrik signifikanter ist als die andere. Dies sind separate, unterschiedliche und unabhängige Metriken. Wie in den obigen Definitionen beschrieben, wird jede dieser Variablen aus verschiedenen Datensätzen abgeleitet. Daher sollten Sie es vermeiden, Schlussfolgerungen abzuleiten, wenn eine Metrik größer ist als die andere. Alles, was Sie sagen können, wenn Sie diese vergleichen, ist, dass:

* [!UICONTROL Customer Addressable Audiences] basiert auf [!UICONTROL trait] Erkenntnissen *für Ihre eigenen First-Party-Daten*. Diese Metrik bietet eine umfassende Übersicht über Ihre Integration mit einem Datenpartner.

* [!UICONTROL Segment Addressable Audiences] basiert auf Segmentqualifikationen *für Ihre eigenen Erstanbieterdaten sowie Zweit- und Drittanbieterdaten*. Diese Metrik bietet eine granulare, genauere Ansicht Ihrer [!UICONTROL addressable audiences] in einer Targeting-Plattform.

## Ursachen für niedrige Übereinstimmungsraten für [!UICONTROL Addressable Audiences] {#low-match-rates}

Häufige Elemente, die für niedrige [!UICONTROL Addressable Audience] oder Diskrepanzen bei den gemeldeten Zahlen verantwortlich sind.

| Ursache | Beschreibung |
|---|---|
| Mobiler Datenverkehr | Die meisten [!UICONTROL server-to-server]-Integrationen basieren auf Synchronisierungsprozessen, die durch [!DNL cookies] von Drittanbietern ermöglicht werden. In mobilen Umgebungen werden jedoch keine [!DNL cookies] von Drittanbietern verwendet. Daher können Ihre [!UICONTROL Addressable Audiences] im Vergleich zur [!UICONTROL segment] gering aussehen. <br><br>Ab Januar 2018 können Sie mobile Zielgruppen in denselben [!DNL Google] und [!DNL Adobe Advertising Cloud] Zielen aktivieren, die für [!UICONTROL cookie-based] Zielgruppen eingerichtet sind. Das bedeutet, dass Sie [!UICONTROL segments] mit kombinierter [!DNL cookie]- und Mobile-ID-Mitgliedschaft an Ihre [!DNL Google]- und [!DNL Advertising Cloud] senden können. Beachten Sie jedoch, dass [!UICONTROL Addressable Audiences] nur die Überschneidung zwischen [!DNL cookie]-IDs und Zielen anzeigen. [!DNL Audience Manager] sendet 100 % der mobilen Zielgruppen an [!UICONTROL destinations], aber mobile Zielgruppen werden nicht anhand der [!UICONTROL Addressable Audience]-Metrik gemessen. <br><br>**Hinweis**: Nehmen wir zum Beispiel eine [!UICONTROL segment] mit einer Bevölkerung von 1.000.000. Wenn Sie dieses [!UICONTROL segment] einem [!DNL Google] oder [!DNL Adobe Advertising Cloud] Ziel zuordnen, sehen Sie möglicherweise eine [!UICONTROL Addressable Audience] von 700.000 Geräten und eine [!UICONTROL Match Rate] von 70 %. Die Mitgliedschaft von 700.000 besteht aus [!DNL cookie] IDs, die eine ID-Synchronisierung mit dem [!UICONTROL destination] aufweisen. Ihre [!UICONTROL Addressable Audience] könnte tatsächlich viel höher sein, da adressierbare Mobile IDs in dieser Metrik nicht angezeigt werden. |
| [!DNL Safari] Traffic | [!DNL Safari] blockiert [!DNL cookies] von Drittanbietern. Dadurch wird verhindert, dass [!DNL Audience Manager] IDs mit dem [!UICONTROL destination] synchronisieren. Mit der Einführung von [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/) können Sie davon ausgehen, dass Ihre [!UICONTROL addressable audiences] keine [!DNL Safari] Benutzer enthält. |
| Impressions von getrackten Medien | Aufgrund der Best Practices für den Anzeigen-Server werden keine ID-Synchronisierungen innerhalb von Anzeigen-Tags durchgeführt. Kunden, die eine große Menge an Offsite-Werbung betreiben, synchronisieren Benutzer nicht mit Integrationen von Drittanbietern in diesen Umgebungen. Außerdem könnte eine große Menge an erfassten Medien-Impressionsdaten die [!UICONTROL addressable audience] verringern. |

## Fehlerbehebung mit [!UICONTROL Addressable Audiences] {#troubleshooting}

Zusätzlich zu den Übereinstimmungsraten können Sie auch [!UICONTROL Addressable Audiences] als Werkzeug zur Fehlerbehebung verwenden.

Angenommen, Sie senden ein Segment an einen [!UICONTROL destination], der [!UICONTROL destination] niedrige Berichtszahlen anzeigt. Die Überprüfung der [!UICONTROL Addressable Audience] zeigt Ihnen, ob es sich um ein technisches Problem oder nur um niedrige Übereinstimmungsraten handelt. Eine niedrige Übereinstimmungsrate zeigt, dass Ihre [!UICONTROL destination] für Ihre ausgewählten Segmente nicht besonders gut ist. Ein Unterschied in den [!UICONTROL total addressable audience] zwischen [!DNL Audience Manager] und [!UICONTROL destination] deutet jedoch auf ein Integrations-, Synchronisations- oder anderes technisches Problem hin. Wenden Sie sich in diesen Fällen an Ihren Account Manager.

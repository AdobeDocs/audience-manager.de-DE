---
description: Ein allgemeiner Bericht gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.
seo-description: Ein allgemeiner Bericht in Audience Manager gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.
seo-title: Allgemeine Berichte in Audience Manager
solution: Audience Manager
title: Allgemeine Berichte
uuid: 0 cea 75 a 0-969 e -4 ee 3-971 a -60 b 911711 e 52
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# General Reports{#general-reports}

A [!UICONTROL General] report returns performance data on traits, segments, and destinations.

## Überblick {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] verwendet ( [!UICONTROL Role Based Access Control][!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf die [!UICONTROL General] Berichte auszudehnen. Benutzer können nur Eigenschaften und Segmente in Berichten anzeigen, die sie zur Ansicht berechtigt haben. [!UICONTROL RBAC] können Sie steuern, welche Berichtsdaten interne Teams anzeigen können. Beispielsweise kann eine Agentur, die verschiedene Advertiserkonten verwaltet, Berechtigungen für Benutzergruppen konfigurieren, damit ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht anzeigen kann.

Run a [!UICONTROL General] report when you need to:

* Überprüfen Sie die Leistung nach Eigenschaften, Segment oder Ziel.
* Verfolgen Sie Impressionen (Gesamt und Eindeutig) bei 1, 7, 14, 30, 60, 90 Tagen und Lebensdauerintervallen.
* Überprüfen Sie die Gesamtzahl und die eindeutigen Ladezahlen.
* Vergleichen Sie Eigenschaften und Segmentleistung.
* Finden Sie starke oder schlechte Leistungseigenschaften und Segmente heraus, analysieren Sie die Nachfrage oder vergleichen Sie Load/Fire-Daten mit Drittanbieterberichten.
* Exportieren Sie Daten (. csv-Format) für weitere Analysen und Freigabe.

The following illustration provides a high-level overview of key elements in the [!UICONTROL General] report.

![](assets/general_reports.png)

1. Konfigurieren Sie die folgenden Optionen:

   * **Berichtstyp:** Wählen Sie den gewünschten Berichtstyp (Eigenschaften, Segment oder Ziel) aus.

   * **Für Datumsangaben:** Geben Sie den Datumsbereich für den Bericht an.

2. Suchen Sie nach einer Eigenschaft, einem Segment oder einem Ziel nach Namen oder ID.
3. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
4. Generieren Sie den Bericht, der in einer exportierbaren Tabelle angezeigt werden soll.

## Run a General Report {#run-general-report}

This section describes how to run a [!UICONTROL General] report and set time and other performance options.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: Trait, Segment, or Destination.
1. *Bedingt* Klicken Sie auf das Datumsfeld, um einen Kalender anzuzeigen, und wählen Sie dann das Enddatum Ihres Berichts aus, wenn Sie ein anderes Datum als heute angeben möchten.
1. Suchen Sie nach einer Eigenschaft, einem Segment oder einem Ziel nach Namen oder ID.
1. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
1. Klicken Sie auf **[!UICONTROL Run Report]**.

   Die Ergebnisse werden in einer exportierbaren Tabelle angezeigt. Klicken Sie auf die Spaltenüberschriften, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.
1. Select the desired option button at the top of the report to filter data by performance ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], or [!UICONTROL Total Trait Population]) or by time (1, 7, 14, 30, 60, 90-day range or lifetime).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] berechnet.[!UICONTROL Rule-based Traits]

1. *Optionaler* Klick **[!UICONTROL Export to CSV]**. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

## General Reports Results Explained {#general-reports-explained}

The numbers in the [!UICONTROL General Reports] are generated directly from our [!UICONTROL User Profile Store]. The results reflect the number of users that [!DNL Audience Manager] contained in the backend at the time these reporting numbers were generated.

* Diese Zahlen enthalten keine Besucher-IDs mit übermäßiges Traffic. Der Traffic von Bots wird vor Erreichen unseres Backend-Systems gefiltert. Außerdem wird einige Bot-Traffic während eines wöchentlichen Bereinigungsauftrags im Backend verworfen.
* If you onboard data via inbound processing keyed off the [!DNL Audience Manager] UUID, and these IDs include users that are no longer active in our system, these inactive [!DNL Audience Manager] UUIDs never reach the [!UICONTROL User Profile Store] and are not reported.
* [!UICONTROL Total Trait Realizations] berechnet.[!UICONTROL Rule-based Traits]

## General Reports Results for Traits {#general-report-results-traits}

The metrics below are available when you run a General report and select **[!UICONTROL Trait]** as the report type:

**Eindeutige Eigenschaftsrealizationen**

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. Wenn ein Benutzer Ihre Homepage beispielsweise dreimal am 10.01. besucht hat, wird eine eindeutige Merkmalisierung angezeigt.

**Gesamteigenschaften von Eigenschaften**

Diese Metrik stellt die Gesamtanzahl der Eigenschaften dar, die für die Eigenschaft im ausgewählten Zeitraum ausgelöst werden. Wenn ein Benutzer z. B. Ihre Homepage besucht hat und dann zu Ihren Tech-News-Nachrichten und Ihren Sportnews-Abschnitten navigiert, würde er im allgemeinen Bericht als drei vollständige Eigenschaftenrealizationen und eine eindeutige Merkmalisierung erscheinen.

**Gesamtanzahl der Eigenschaften**

Diese Metrik stellt die Gesamtanzahl der uuids von Audience Manager dar, die derzeit für die Eigenschaft qualifiziert sind. Verwenden Sie diese Zahl, um zu verstehen, wie viele Benutzer Sie für die Segmentierung und das Targeting insgesamt verwenden können. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Beispielsweise würde ein Benutzer, der Ihre Homepage dreimal besucht und anschließend nie wieder zurückkehrt, jeden Tag bis 120 Tage lang als Benutzer in dieser Population weiterbleiben. Bei einem Tag von 120 Tagen würden sie aus der Population entfernt. Read our [Trait Qualification Reference](../features/traits/trait-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

Die unten stehende Abbildung zeigt die Ergebnisse eines allgemeinen Berichts für den Trait-Berichtstyp.

![](assets/general_reports_metrics.png)

## General Reports Results for Segments {#general-report-results-segments}

The metrics below are available when you run a General report and select **[!UICONTROL Segment]** as the report type:

**Segmentpopulation in Echtzeit**

Diese Metrik stellt die tatsächliche Anzahl individueller Besucher dar, die in Echtzeit für den angegebenen Zeitraum angesehen wurden und für das Segment qualifiziert waren, wenn sie von Audience Manager gesehen wurden.

**Segmentpopulation insgesamt**

Diese Metrik stellt die Gesamtanzahl der uuids von Audience Manager dar, die für das Segment im ausgewählten Look-Back-Zeitraum qualifiziert sind. Ihre Gesamtsegmentpopulation von 1 Tag stellt Ihre genaueste Benutzerbasis für das Targeting dar.

>[!NOTE]
>
>Select **[!UICONTROL Include Destination Mappings]** to see a breakdown of segment population for activated destinations.

Die folgende Abbildung zeigt die Ergebnisse der Ausführung eines allgemeinen Berichts für den Berichtstyp &quot;Segmente&quot; .

![](assets/general_reports_segment_metrics.png)

## General Reports Results for Destinations {#general-report-results-destinations}

The metrics below are available when you run a General report and select **[!UICONTROL Destination]** as the report type:

**Segmentpopulation in Echtzeit**

Diese Metrik stellt die tatsächliche Anzahl individueller Besucher dar, die in Echtzeit für den angegebenen Zeitraum angesehen wurden und für das Segment qualifiziert waren, wenn sie von Audience Manager gesehen wurden.

**Segmentpopulation insgesamt**

Diese Metrik stellt die Gesamtzahl der uuids von Audience Manager dar, die zu einem Segment innerhalb des Suchzeitraums gehören und an ein Ziel gesendet wurden.

Die unten stehende Abbildung zeigt die Ergebnisse eines allgemeinen Berichts für den Berichtstyp Ziele.

![](assets/general_reports_destinations.png)

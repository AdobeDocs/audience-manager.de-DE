---
description: Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.
seo-description: Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.
seo-title: Trendberichte
solution: Audience Manager
title: Trendberichte
uuid: bedbe 7 d 4-7 cbb -4403-9104-312 f 9230 aea 1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Trend Reports{#trend-reports}

Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.

## Überblick {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] verwendet ( [!UICONTROL Role Based Access Control][!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf die [!UICONTROL Trend] Berichte auszudehnen. Benutzer können nur Eigenschaften und Segmente in Berichten anzeigen, die sie zur Ansicht berechtigt haben. [!UICONTROL RBAC] können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Beispielsweise kann eine Agentur, die verschiedene Advertiserkonten verwaltet, Berechtigungen für Benutzergruppen konfigurieren, damit ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht anzeigen kann.

Run a [!UICONTROL Trend] report when you need to:

* Überprüfen Sie Trenddaten nach Eigenschaften und Segmenten.
* Verfolgen Sie Trends nach 1, 7, 14, 30, 60 und 90 Tagen.
* Vergleichen Sie Eigenschaften und Segmenttrends im Laufe der Zeit.
* Identifizieren Sie starke oder schlechte Leistungseigenschaften und Segmente.
* Exportieren Sie Daten (. csv-Format) für weitere Analysen und Freigabe.

The following illustration provides a high-level overview of key elements in the [!UICONTROL Trend] report.

![](assets/trend_reports.png)

1. Konfigurieren Sie die folgenden Optionen:

   **Berichtstyp:** Wählen Sie den gewünschten Berichtstyp (Eigenschaften oder Segment) aus.

   **Datumsbereich:** Geben Sie den Datumsbereich für den Bericht an (Start- und Enddatum).

   **Anzeigeintervall:** Geben Sie das Anzeigeintervall (1, 7, 14, 30, 60 und 90 Tage) an.

2. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
3. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.
4. Erstellen Sie den Bericht, um die Daten im grafischen Format anzuzeigen oder den Bericht in das CSV-Format zu exportieren.

## Run a Trend Report {#run-trend-report}

This procedure describes how to run a [!UICONTROL Trend] report.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: **[!UICONTROL Trait]** or **[!UICONTROL Segment]**.
1. Klicken Sie auf die Datumsfelder, um einen Kalender anzuzeigen, und wählen Sie dann die Start- und Enddaten für Ihren Bericht aus.
1. Geben Sie das Anzeigeintervall an: um 1, 7, 14, 30, 60 oder 90 Tage.
1. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
1. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.

   For best performance, run a [!UICONTROL Trend] report on fewer than 20 traits or segments at a time.
1. Click **[!UICONTROL Graph Traits]** or **[!UICONTROL Graph Segments]**, depending on which type of report you are viewing (Traits or Segments).

   Diese Optionen ignorieren alle Ordner und Diagramme nur einzeln ausgewählte Eigenschaften oder Segmente.

   Oder

   Click **[!UICONTROL Export to CSV]** to export the trait or segment data and all folders in CSV format for further analysis and sharing. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] berechnet.[!UICONTROL Rule-based Traits]

1. (Optional) Bewegen Sie den Mauszeiger über einzelne Eigenschaften oder Segmente, um die Anzahl der Besuche und das Datum für jeden Datenpunkt anzuzeigen.

   Sie können in der Tabelle auf die Spaltenüberschriften klicken, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.

For [!UICONTROL Trended Trait] reports, zeroes indicate that [!DNL Audience Manager] did not collect data for that day. Leere Einträge weisen darauf hin, dass die Eigenschaft nicht vorhanden war. Das folgende Beispiel zeigt Beispiele für beide Arten von Einträgen:

![](assets/trended_data.png)

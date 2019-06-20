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


# Trendberichte{#trend-reports}

Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.

## Überblick {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] verwendet ( [!UICONTROL Role Based Access Control][!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf die [!UICONTROL Trend] Berichte auszudehnen. Benutzer können nur Eigenschaften und Segmente in Berichten anzeigen, die sie zur Ansicht berechtigt haben. [!UICONTROL RBAC] können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Beispielsweise kann eine Agentur, die verschiedene Advertiserkonten verwaltet, Berechtigungen für Benutzergruppen konfigurieren, damit ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht anzeigen kann.

Führen Sie einen [!UICONTROL Trend] Bericht aus, wenn Sie Folgendes benötigen:

* Überprüfen Sie Trenddaten nach Eigenschaften und Segmenten.
* Verfolgen Sie Trends nach 1, 7, 14, 30, 60 und 90 Tagen.
* Vergleichen Sie Eigenschaften und Segmenttrends im Laufe der Zeit.
* Identifizieren Sie starke oder schlechte Leistungseigenschaften und Segmente.
* Exportieren Sie Daten (. csv-Format) für weitere Analysen und Freigabe.

Die folgende Abbildung zeigt eine allgemeine Übersicht über wichtige Elemente im [!UICONTROL Trend] Bericht.

![](assets/trend_reports.png)

1. Konfigurieren Sie die folgenden Optionen:

   **Berichtstyp:** Wählen Sie den gewünschten Berichtstyp (Eigenschaften oder Segment) aus.

   **Datumsbereich:** Geben Sie den Datumsbereich für den Bericht an (Start- und Enddatum).

   **Anzeigeintervall:** Geben Sie das Anzeigeintervall (1, 7, 14, 30, 60 und 90 Tage) an.

2. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
3. Ziehen Sie in der Ordnerliste die gewünschten Eigenschaften oder Segmente per Drag &amp; Drop an das [!UICONTROL Selections] Bedienfeld auf der rechten Seite.
4. Erstellen Sie den Bericht, um die Daten im grafischen Format anzuzeigen oder den Bericht in das CSV-Format zu exportieren.

## Trendbericht ausführen {#run-trend-report}

Dieser Vorgang beschreibt, wie Sie einen [!UICONTROL Trend] Bericht ausführen.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Klicken Sie im **[!UICONTROL Analytics]** Dashboard **[!UICONTROL Trend Reports]** auf.
1. Wählen Sie aus der **[!UICONTROL Report Type]** Dropdownliste den gewünschten Typ aus: **[!UICONTROL Trait]** oder **[!UICONTROL Segment]**.
1. Klicken Sie auf die Datumsfelder, um einen Kalender anzuzeigen, und wählen Sie dann die Start- und Enddaten für Ihren Bericht aus.
1. Geben Sie das Anzeigeintervall an: um 1, 7, 14, 30, 60 oder 90 Tage.
1. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
1. Ziehen Sie in der Ordnerliste die gewünschten Eigenschaften oder Segmente per Drag &amp; Drop an das [!UICONTROL Selections] Bedienfeld auf der rechten Seite.

   Um eine optimale Leistung zu erzielen, führen Sie einen [!UICONTROL Trend] Bericht auf weniger als 20 Eigenschaften oder Segmenten gleichzeitig aus.
1. Klicken **[!UICONTROL Graph Traits]** Sie auf oder **[!UICONTROL Graph Segments]** je nachdem, welchen Berichtstyp Sie anzeigen (Eigenschaften oder Segmente).

   Diese Optionen ignorieren alle Ordner und Diagramme nur einzeln ausgewählte Eigenschaften oder Segmente.

   Oder

   Klicken **[!UICONTROL Export to CSV]** Sie, um die Eigenschaften oder Segmentdaten sowie alle Ordner im CSV-Format zur weiteren Analyse und Freigabe zu exportieren. Dadurch werden die [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]und [!UICONTROL Total Trait Population] alle Tage exportiert.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] are calculated for [!UICONTROL Rule-based Traits] only.

1. (Optional) Bewegen Sie den Mauszeiger über einzelne Eigenschaften oder Segmente, um die Anzahl der Besuche und das Datum für jeden Datenpunkt anzuzeigen.

   Sie können in der Tabelle auf die Spaltenüberschriften klicken, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.

Bei [!UICONTROL Trended Trait] Berichten weisen Nullen darauf hin, dass [!DNL Audience Manager] keine Daten für diesen Tag gesammelt wurden. Leere Einträge weisen darauf hin, dass die Eigenschaft nicht vorhanden war. Das folgende Beispiel zeigt Beispiele für beide Arten von Einträgen:

![](assets/trended_data.png)

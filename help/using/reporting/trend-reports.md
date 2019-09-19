---
description: Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.
seo-description: Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.
seo-title: Trendberichte
solution: Audience Manager
title: Trendberichte
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Trendberichte{#trend-reports}

Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.

## Überblick {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] verwendet [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um die Benutzergruppenberechtigungen auf die [!UICONTROL Trend] Berichte auszudehnen. Benutzer können nur die Eigenschaften und Segmente in Berichten anzeigen, die sie anzeigen dürfen. [!UICONTROL RBAC] -Funktion können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Eine Agentur, die verschiedene Advertiser-Konten verwaltet, kann z. B. Benutzergruppenberechtigungen so konfigurieren, dass einem Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht angezeigt werden.

Führen Sie einen [!UICONTROL Trend] Bericht aus, wenn Sie:

* Überprüfen Sie Trenddaten nach Eigenschaften und Segmenten.
* Verfolgen Sie Trends in Intervallen von 1, 7, 14, 30, 60 und 90 Tagen.
* Vergleichen Sie Eigenschaften- und Segmenttrends im Zeitverlauf.
* Identifizieren Sie leistungsstarke oder schlechte Eigenschaften und Segmente.
* Exportieren Sie Daten (.csv-Format) zur weiteren Analyse und Freigabe.

Die folgende Abbildung zeigt einen Überblick über die wichtigsten Elemente des [!UICONTROL Trend] Berichts auf hoher Ebene.

![](assets/trend_reports.png)

1. Konfigurieren Sie die folgenden Optionen:

   **** Berichtstyp: Wählen Sie den gewünschten Berichtstyp aus (Eigenschaft oder Segment).

   **** Datumsbereich: Geben Sie den Datumsbereich für den Bericht an (Start- und Enddatum).

   **** Anzeigenintervall: Geben Sie das Anzeigeintervall an (Intervall zwischen 1, 7, 14, 30, 60 und 90 Tagen).

2. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
3. Ziehen Sie aus der Ordnerliste die Eigenschaften oder Segmente, die Sie in den Bericht aufnehmen möchten, in das [!UICONTROL Selections] Bedienfeld auf der rechten Seite.
4. Generieren Sie den Bericht, um ihn als Daten im grafischen Format anzuzeigen, oder exportieren Sie ihn in das CSV-Format.

## Run a Trend Report {#run-trend-report}

Dieser Vorgang beschreibt, wie Sie einen [!UICONTROL Trend] Bericht ausführen.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. Wählen Sie aus der **[!UICONTROL Report Type]** Dropdownliste den gewünschten Typ aus: **[!UICONTROL Trait]** oder **[!UICONTROL Segment]**.
1. Klicken Sie auf die Datumsfelder, um einen Kalender anzuzeigen, und wählen Sie dann die Start- und Enddaten für Ihren Bericht aus.
1. Legen Sie das Anzeigenintervall fest: bis zu 1, 7, 14, 30, 60 oder 90 Tage.
1. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
1. Ziehen Sie aus der Ordnerliste die Eigenschaften oder Segmente, die Sie in den Bericht aufnehmen möchten, in das [!UICONTROL Selections] Bedienfeld auf der rechten Seite.

   Um eine optimale Leistung zu erzielen, führen Sie einen [!UICONTROL Trend] Bericht mit weniger als 20 Eigenschaften oder Segmenten gleichzeitig aus.
1. Klicken Sie auf **[!UICONTROL Graph Traits]** oder **[!UICONTROL Graph Segments]**, je nachdem, welchen Berichtstyp Sie anzeigen (Eigenschaften oder Segmente).

   Diese Optionen ignorieren alle Ordner und Diagramme nur einzeln ausgewählte Eigenschaften oder Segmente.

   Oder

   Klicken Sie auf , **[!UICONTROL Export to CSV]** um die Eigenschaften- oder Segmentdaten und alle Ordner im CSV-Format für weitere Analysen und Freigabe zu exportieren. Dadurch werden die [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]und [!UICONTROL Total Trait Population] für alle Tagesbereiche exportiert.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] werden [!UICONTROL Rule-based Traits] nur berechnet.

1. (Optional) Bewegen Sie den Mauszeiger über einzelne Eigenschaften oder Segmente, um die Anzahl der Besuche und das Datum für jeden Datenpunkt anzuzeigen.

   Sie können auf die Spaltenüberschriften in der Tabelle klicken, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.

Bei [!UICONTROL Trended Trait] Berichten geben Nullen an, dass für diesen Tag keine Daten erfasst [!DNL Audience Manager] wurden. Leere Einträge weisen darauf hin, dass die Eigenschaft nicht vorhanden war. Das folgende Beispiel zeigt Beispiele für beide Einsendungstypen:

![](assets/trended_data.png)

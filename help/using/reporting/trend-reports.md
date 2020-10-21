---
description: Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.
seo-description: Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.
seo-title: Trend-Berichte
solution: Audience Manager
title: Trend-Berichte
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: general & trend reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 1%

---


# Trend-Berichte{#trend-reports}

Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.

## Überblick {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] verwendet [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um die Benutzergruppenberechtigungen auf die [!UICONTROL Trend] Berichte auszudehnen. Benutzer können nur die Eigenschaften und Segmente in Berichten anzeigen, für die sie über die Berechtigung zur Ansicht verfügen. [!UICONTROL RBAC] Mit dieser Funktion können Sie steuern, welche Berichte-Daten interne Teams zur Ansicht bereitstellen können.

Eine Agentur, die verschiedene Advertiser-Konten verwaltet, kann beispielsweise Benutzergruppenberechtigungen so konfigurieren, dass ein Team, das das Konto des Advertiser A verwaltet, die Daten des Berichte von Advertiser B nicht sehen kann.

Führen Sie einen [!UICONTROL Trend] Bericht aus, wenn Sie:

* Überprüfen Sie Trenddaten nach Eigenschaften und Segmenten.
* Verfolgen Sie Trends in Intervallen von 1, 7, 14, 30, 60 und 90 Tagen.
* Vergleichen Sie Eigenschaften- und Segmenttrends im Zeitverlauf.
* Identifizieren Sie leistungsstarke oder schlechte Eigenschaften und Segmente.
* Exportieren Sie Daten (.csv-Format) zur weiteren Analyse und Freigabe.

Die folgende Abbildung zeigt einen Überblick über die wichtigsten Elemente des [!UICONTROL Trend] Berichts auf hoher Ebene.

![](assets/trend_reports.png)

1. Konfigurieren Sie die folgenden Optionen:
   **Berichtstyp:** Wählen Sie den gewünschten Berichtstyp aus (Eigenschaft oder Segment).
   **Datumsbereich:** Geben Sie den Datumsbereich für den Bericht an (Beginn- und Enddatum).
   **Anzeigenintervall:** Geben Sie das Anzeigeintervall an (Intervall zwischen 1, 7, 14, 30, 60 und 90 Tagen).
1. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
1. Ziehen Sie die Eigenschaften oder Segmente, die Sie in Berichten anzeigen möchten, aus der Liste in das [!UICONTROL Selections] Bedienfeld auf der rechten Seite.
1. Generieren Sie den Bericht, um ihn als Daten im grafischen Format anzuzeigen, oder exportieren Sie ihn in das CSV-Format.

## Run a Trend Report {#run-trend-report}

Dieser Vorgang beschreibt, wie Sie einen [!UICONTROL Trend] Bericht ausführen.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. Wählen Sie in der **[!UICONTROL Report Type]** Dropdown-Liste den gewünschten Typ aus: **[!UICONTROL Trait]** oder **[!UICONTROL Segment]**.
1. Klicken Sie auf die Datumsfelder, um einen Kalender anzuzeigen, und wählen Sie dann die Start- und Enddaten für Ihren Bericht aus.
1. Legen Sie das Anzeigenintervall fest: bis zu 1, 7, 14, 30, 60 oder 90 Tage.
1. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
1. Ziehen Sie die Eigenschaften oder Segmente, die Sie in Berichten anzeigen möchten, aus der Liste in das [!UICONTROL Selections] Bedienfeld auf der rechten Seite.
   * Um eine optimale Leistung zu erzielen, führen Sie einen [!UICONTROL Trend] Bericht mit weniger als 20 Eigenschaften oder Segmenten gleichzeitig aus.
1. Klicken Sie auf **[!UICONTROL Graph Traits]** oder **[!UICONTROL Graph Segments]**, je nachdem, welchen Berichtstyp Sie anzeigen (Eigenschaften oder Segmente). Diese Optionen ignorieren alle Ordner und Diagramme nur einzeln ausgewählte Eigenschaften oder Segmente.

   Oder

   Klicken Sie auf , **[!UICONTROL Export to CSV]** um die Eigenschaften- oder Segmentdaten und alle Ordner im CSV-Format für weitere Analyse und Freigabe zu exportieren. Dadurch werden die [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]und [!UICONTROL Total Trait Population] für alle Tagesbereiche exportiert.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] werden [!UICONTROL Rule-based Traits] nur berechnet.

1. (Optional) Bewegen Sie den Mauszeiger über einzelne Eigenschaften oder Segmente, um die Anzahl der Besuche und das Datum für jeden Datenpunkt anzuzeigen. Sie können auf die Spaltenüberschriften in der Tabelle klicken, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.

## Trendberichtsergebnisse für Eigenschaften {#trend-report-results-traits}

Die folgenden Filter stehen zur Verfügung, wenn Sie einen Bericht ausführen [!UICONTROL Trend Report] und **[!UICONTROL Trait]** als Berichtstyp auswählen.

Beim Filtern der Ergebnisse nach [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der anonymen Besucher, die innerhalb des ausgewählten Zeitraums die Eigenschaft ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der anonymen Mäuse-Eigenschaften innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl der anonymen Besucher, die diese Eigenschaft auf ihrem Profil haben.

Beim Filtern der Ergebnisse nach [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der authentifizierten Besucher, die innerhalb des ausgewählten Zeitraums die Eigenschaft ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der authentifizierten Eigenschaften innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl der authentifizierten Besucher, die diese Eigenschaft auf ihrem Profil haben.

![trend-report-properties](assets/trend-report-traits.png)

Zeroes geben an, dass für diesen Tag keine Daten gesammelt [!DNL Audience Manager] wurden. Leere Einträge weisen darauf hin, dass die Eigenschaft nicht vorhanden war.

Sehen Sie sich das unten stehende Video an, um einen detaillierten Überblick über die Funktionsweise geräteübergreifender Metriken zu erhalten.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Trendberichtsergebnisse für Segmente {#segment-report-results-traits}

Die folgenden Filter stehen zur Verfügung, wenn Sie einen Bericht ausführen [!UICONTROL Trend Report] und **[!UICONTROL Segments]** als Berichtstyp auswählen.

* **[!UICONTROL Real-time Segment Population]**: die Anzahl der Besucher, die innerhalb des ausgewählten Zeitraums für das Segment qualifiziert sind.
* **[!UICONTROL Total Segment Population]**: die Gesamtzahl der für das Segment qualifizierten Besucher.

![trend-report-segmente](assets/trend-report-segments.png)
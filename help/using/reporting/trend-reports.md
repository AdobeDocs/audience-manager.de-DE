---
description: Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: Trendberichte
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Trendberichte{#trend-reports}

Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.

## Überblick {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] verwendet [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf die [!UICONTROL Trend] Berichte zu erweitern. Benutzende können in Berichten nur die Eigenschaften und Segmente sehen, für die sie über Anzeigeberechtigungen verfügen. Mit [!UICONTROL RBAC] Funktion können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Beispielsweise kann eine Agentur, die verschiedene Advertiser-Konten verwaltet, Benutzergruppenberechtigungen so konfigurieren, dass ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht sehen kann.

Führen Sie einen [!UICONTROL Trend] aus, wenn Sie Folgendes tun müssen:

* Überprüfen Sie Trenddaten nach Eigenschaften und Segmenten.
* Verfolgen Sie Trends in Intervallen von 1, 7, 14, 30, 60 und 90 Tagen.
* Vergleich von Eigenschaften- und Segmenttrends im Zeitverlauf.
* Identifizieren Sie starke oder schlechte Leistungsmerkmale und Segmente.
* Exportieren Sie Daten (.csv-Format) für weitere Analysen und die Freigabe.

Die folgende Abbildung bietet einen allgemeinen Überblick über die wichtigsten Elemente im [!UICONTROL Trend].

![](assets/trend_reports.png)

1. Konfigurieren Sie die folgenden Optionen:
   **Berichtstyp** Wählen Sie den gewünschten Berichtstyp aus (Eigenschaft oder Segment).
   **Datumsbereich:** Sie den Datumsbereich für den Bericht an (Start- und Enddatum).
   **Anzeigeintervall:** Geben Sie das Anzeigeintervall (1, 7, 14, 30, 60 und 90-Tage-Intervalle) an.
1. Nach einer Eigenschaft oder einem Segment anhand von Name oder ID suchen.
1. Ziehen Sie aus der Ordnerliste die Eigenschaften oder Segmente, für die Sie einen Bericht erstellen möchten, per Drag-and-Drop in das Bedienfeld [!UICONTROL Selections] auf der rechten Seite.
1. Generieren Sie den Bericht, der in Daten im grafischen Format angezeigt werden soll, oder exportieren Sie den Bericht in das CSV-Format.

## Trendbericht ausführen {#run-trend-report}

In diesem Verfahren wird beschrieben, wie Sie einen [!UICONTROL Trend] ausführen.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Klicken Sie im **[!UICONTROL Analytics]**-Dashboard auf **[!UICONTROL Trend Reports]**.
1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Report Type]** den gewünschten Typ aus: **[!UICONTROL Trait]** oder **[!UICONTROL Segment]**.
1. Klicken Sie auf die Datumsfelder, um einen Kalender anzuzeigen, und wählen Sie dann das Anfangs- und Enddatum für Ihren Bericht aus.
1. Legen Sie das Anzeigeintervall fest: um 1, 7, 14, 30, 60 oder 90 Tage.
1. Nach einer Eigenschaft oder einem Segment anhand von Name oder ID suchen.
1. Ziehen Sie aus der Ordnerliste die Eigenschaften oder Segmente, für die Sie einen Bericht erstellen möchten, per Drag-and-Drop in das Bedienfeld [!UICONTROL Selections] auf der rechten Seite.
   * Um eine optimale Leistung zu erzielen, führen Sie einen [!UICONTROL Trend]-Bericht mit weniger als 20 Eigenschaften oder Segmenten gleichzeitig aus.
1. Klicken Sie auf **[!UICONTROL Graph Traits]** oder **[!UICONTROL Graph Segments]**, je nachdem, welchen Berichtstyp Sie anzeigen (Eigenschaften oder Segmente). Diese Optionen ignorieren alle Ordner und Diagramme nur einzeln ausgewählte Eigenschaften oder Segmente.

   Or

   Klicken Sie auf **[!UICONTROL Export to CSV]** , um die Trait- oder Segmentdaten und alle Ordner im CSV-Format zur weiteren Analyse und Freigabe zu exportieren. Dadurch werden [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] und [!UICONTROL Total Trait Population] für alle Tagesbereiche exportiert.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] werden nur für [!UICONTROL Rule-based Traits] berechnet.

1. (Optional) Bewegen Sie den Mauszeiger über einzelne Eigenschaften oder Segmente, um die Anzahl der Besuche und das Datum für jeden Datenpunkt anzuzeigen. Sie können auf die Spaltenüberschriften in der Tabelle klicken, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.

## Trend-Berichtsergebnisse für Eigenschaften {#trend-report-results-traits}

Die folgenden Filter sind verfügbar, wenn Sie eine [!UICONTROL Trend Report] ausführen und als Berichtstyp **[!UICONTROL Trait]** auswählen.

Beim Filtern der Ergebnisse nach [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der Besucherinnen und Besucher Ihres anonymen Geräts, die die Eigenschaft innerhalb des ausgewählten Zeitraums zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der Realisierungen anonymer Mauseigenschaften innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl der anonymen Gerätebesucher, die diese Eigenschaft in ihrem Profil haben.

Beim Filtern der Ergebnisse nach [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der authentifizierten Besucher, die das Merkmal innerhalb des ausgewählten Zeitraums zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der authentifizierten Eigenschaftsrealisierungen innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl der authentifizierten Besucher, die diese Eigenschaft in ihrem Profil haben.

![trend-report-traits](assets/trend-report-traits.png)

Nullen geben an, dass [!DNL Audience Manager] keine Daten für diesen Tag erfasst haben. Leere Einträge geben an, dass die Eigenschaft nicht vorhanden war.

Sehen Sie sich das folgende Video an, um einen detaillierten Überblick über die Funktionsweise geräteübergreifender Metriken zu erhalten.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=de)

## Trend-Berichtsergebnisse für Segmente {#segment-report-results-traits}

Die folgenden Filter sind verfügbar, wenn Sie eine [!UICONTROL Trend Report] ausführen und als Berichtstyp **[!UICONTROL Segments]** auswählen.

* **[!UICONTROL Real-time Segment Population]**: Die Anzahl der Besucher, die sich für das Segment innerhalb des ausgewählten Zeitraums qualifiziert haben.
* **[!UICONTROL Total Segment Population]**: Die Gesamtzahl der Besucher, die sich für das Segment qualifiziert haben.

![trend-report-segments](assets/trend-report-segments.png)

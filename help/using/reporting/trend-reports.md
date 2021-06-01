---
description: Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.
seo-description: Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.
seo-title: Trend-Berichte
solution: Audience Manager
title: Trend-Berichte
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: Allgemeine und Trend-Berichte
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---

# Trend-Berichte{#trend-reports}

Ein Trendbericht gibt Trenddaten zu Eigenschaften und Segmenten zurück.

## Überblick {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] verwendet  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf die  [!UICONTROL Trend] Berichte zu erweitern. Benutzer können nur die Eigenschaften und Segmente in Berichten sehen, die sie anzeigen können. [!UICONTROL RBAC] -Funktion können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Eine Agentur, die verschiedene Advertiser-Konten verwaltet, kann beispielsweise Benutzergruppenberechtigungen so konfigurieren, dass ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht sehen kann.

Führen Sie einen [!UICONTROL Trend] -Bericht aus, wenn Sie:

* Überprüfen Sie Trenddaten nach Eigenschaften und Segmenten.
* Verfolgen Sie Trends in Intervallen von 1, 7, 14, 30, 60 und 90 Tagen.
* Vergleichen Sie Eigenschaften- und Segmenttrends im Zeitverlauf.
* Ermitteln Sie starke oder schlechte Leistungsmerkmale und -segmente.
* Exportieren Sie Daten (.csv-Format) zur weiteren Analyse und Freigabe.

Die folgende Abbildung bietet einen allgemeinen Überblick über die Schlüsselelemente im [!UICONTROL Trend] -Bericht.

![](assets/trend_reports.png)

1. Konfigurieren Sie die folgenden Optionen:
   **Berichtstyp:** Wählen Sie den gewünschten Berichtstyp aus (Eigenschaft oder Segment).
   **Datumsbereich:** Geben Sie den Datumsbereich für den Bericht an (Startdatum und Enddatum).
   **Anzeigeintervall:** Geben Sie das Anzeigeintervall an (Intervalle 1, 7, 14, 30, 60 und 90 Tage).
1. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
1. Ziehen Sie aus der Ordnerliste die Eigenschaften oder Segmente, die Sie melden möchten, in das Bedienfeld [!UICONTROL Selections] auf der rechten Seite.
1. Erstellen Sie den Bericht zur Anzeige in Daten im grafischen Format oder exportieren Sie ihn in das CSV-Format.

## Trendbericht ausführen {#run-trend-report}

Dieser Vorgang beschreibt, wie Sie einen [!UICONTROL Trend] -Bericht ausführen.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Klicken Sie im Dashboard **[!UICONTROL Analytics]** auf **[!UICONTROL Trend Reports]**.
1. Wählen Sie aus der Dropdownliste **[!UICONTROL Report Type]** den gewünschten Typ aus: **[!UICONTROL Trait]** oder **[!UICONTROL Segment]**.
1. Klicken Sie auf die Datumsfelder, um einen Kalender anzuzeigen, und wählen Sie dann das Start- und Enddatum für Ihren Bericht aus.
1. Geben Sie das Anzeigeintervall an: um 1, 7, 14, 30, 60 oder 90 Tage.
1. Suchen Sie nach einer Eigenschaft oder einem Segment nach Name oder ID.
1. Ziehen Sie aus der Ordnerliste die Eigenschaften oder Segmente, die Sie melden möchten, in das Bedienfeld [!UICONTROL Selections] auf der rechten Seite.
   * Führen Sie für optimale Leistung einen [!UICONTROL Trend] -Bericht für weniger als 20 Eigenschaften oder Segmente gleichzeitig aus.
1. Klicken Sie je nach angezeigtem Berichtstyp (Eigenschaften oder Segmente) auf **[!UICONTROL Graph Traits]** oder **[!UICONTROL Graph Segments]**. Diese Optionen ignorieren alle Ordner und Diagramme, die nur einzeln ausgewählte Eigenschaften oder Segmente aufweisen.

   Oder

   Klicken Sie auf **[!UICONTROL Export to CSV]** , um die Eigenschaften- oder Segmentdaten und alle Ordner im CSV-Format für die weitere Analyse und Freigabe zu exportieren. Dadurch werden [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] und [!UICONTROL Total Trait Population] für alle Tagesbereiche exportiert.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] werden  [!UICONTROL Rule-based Traits] nur berechnet.

1. (Optional) Bewegen Sie den Mauszeiger über einzelne Eigenschaften oder Segmente, um die Anzahl der Besuche und das Datum für jeden Datenpunkt anzuzeigen. Sie können auf die Spaltenüberschriften in der Tabelle klicken, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.

## Trendberichtsergebnisse für Eigenschaften {#trend-report-results-traits}

Die folgenden Filter sind verfügbar, wenn Sie einen [!UICONTROL Trend Report] ausführen und **[!UICONTROL Trait]** als Berichtstyp auswählen.

Beim Filtern der Ergebnisse nach [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl Ihrer anonymen Gerätebesucher, die die Eigenschaft innerhalb des ausgewählten Zeitraums zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der Realisierungen von anonymen Mauseigenschaften innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl der anonymen Gerätebesucher, deren Profil diese Eigenschaft aufweist.

Beim Filtern der Ergebnisse nach [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl Ihrer authentifizierten Besucher, die ihrem Profil die Eigenschaft innerhalb des ausgewählten Zeitraums hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der authentifizierten Merkmalrealisierungen innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl Ihrer authentifizierten Besucher, die diese Eigenschaft in ihrem Profil haben.

![trend-report-traits](assets/trend-report-traits.png)

Die Zeroes geben an, dass [!DNL Audience Manager] keine Daten für diesen Tag erfasst hat. Leere Einträge zeigen an, dass die Eigenschaft nicht vorhanden war.

Sehen Sie sich das Video unten an, um sich ausführlich anzusehen, wie geräteübergreifende Metriken funktionieren.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Trendberichtsergebnisse für Segmente {#segment-report-results-traits}

Die folgenden Filter sind verfügbar, wenn Sie einen [!UICONTROL Trend Report] ausführen und **[!UICONTROL Segments]** als Berichtstyp auswählen.

* **[!UICONTROL Real-time Segment Population]**: die Anzahl der für das Segment innerhalb des ausgewählten Zeitraums qualifizierten Besucher.
* **[!UICONTROL Total Segment Population]**: die Gesamtzahl der für das Segment qualifizierten Besucher.

![Trend-Berichtsegmente](assets/trend-report-segments.png)

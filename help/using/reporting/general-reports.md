---
description: Ein allgemeiner Bericht gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.
seo-description: A General report in Audience Manager returns performance data on traits, segments, and destinations.
seo-title: General Reports in Audience Manager
solution: Audience Manager
title: Allgemeine Berichte
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: General & Trend Reports
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 0%

---

# Allgemeine Berichte{#general-reports}

Ein [!UICONTROL General] Bericht gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.

## Überblick {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] verwendet [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf die [!UICONTROL General] Berichte zu erweitern. Benutzende können in Berichten nur die Eigenschaften und Segmente sehen, für die sie über Anzeigeberechtigungen verfügen. Mit [!UICONTROL RBAC] Funktion können Sie steuern, welche Berichtsdaten interne Teams anzeigen können. Beispielsweise kann eine Agentur, die verschiedene Advertiser-Konten verwaltet, Benutzergruppenberechtigungen so konfigurieren, dass ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht sehen kann.

Führen Sie einen [!UICONTROL General] aus, wenn Sie Folgendes tun müssen:

* Überprüfen der Leistung nach Eigenschaft, Segment oder Ziel.
* Verfolgen Sie Impressionen (insgesamt und eindeutig) in Intervallen von 1, 7, 14, 30, 60 und 90 Tagen.
* Überprüfen Sie die Gesamtanzahl und die Anzahl der eindeutigen Lasten.
* Vergleichen Sie die Eigenschaften- und Segmentleistung.
* Identifizieren Sie starke oder schlechte Leistungsmerkmale und Segmente, analysieren Sie den Bedarf oder vergleichen Sie Auslastungs-/Löschdaten mit Drittanbieterberichten.
* Exportieren Sie Daten (.csv-Format) für weitere Analysen und die Freigabe.

Die folgende Abbildung bietet einen allgemeinen Überblick über die wichtigsten Elemente im [!UICONTROL General].

![](assets/general_reports.png)

1. Konfigurieren Sie die folgenden Optionen:

   * **Berichtstyp** Wählen Sie den gewünschten Berichtstyp aus (Eigenschaft, Segment oder Ziel).

   * **Für Datumsangaben bis** Geben Sie den Datumsbereich für den Bericht an.

2. Nach einer Eigenschaft, einem Segment oder einem Ziel anhand von Name oder ID suchen.
3. Ziehen Sie aus der Ordnerliste die Eigenschaften, Segmente oder Ziele, die Sie melden möchten, per Drag-and-Drop in das Bedienfeld [!UICONTROL Selections] auf der rechten Seite.
4. Generieren Sie den Bericht, der in einer exportierbaren Tabelle angezeigt werden soll.

## Allgemeinen Bericht ausführen {#run-general-report}

In diesem Abschnitt wird beschrieben, wie Sie einen [!UICONTROL General]-Bericht ausführen und die Zeit sowie andere Leistungsoptionen festlegen.

<!-- 

t_run_general_report.xml

 -->

1. Klicken Sie im **[!UICONTROL Analytics]**-Dashboard auf **[!UICONTROL General Reports]**.
1. Wählen Sie aus der Dropdown-Liste **[!UICONTROL Report Type]** den gewünschten Typ aus: Eigenschaft, Segment oder Ziel.
1. *Bedingt* Klicken Sie auf das Datumsfeld, um einen Kalender anzuzeigen, und wählen Sie dann das Enddatum für Ihren Bericht aus, wenn Sie ein anderes Datum als das heutige angeben möchten.
1. Nach einer Eigenschaft, einem Segment oder einem Ziel anhand von Name oder ID suchen.
1. Ziehen Sie aus der Ordnerliste die Eigenschaften, Segmente oder Ziele, die Sie melden möchten, per Drag-and-Drop in das Bedienfeld [!UICONTROL Selections] auf der rechten Seite.
1. Klicken Sie auf **[!UICONTROL Run Report]**.

   Die Ergebnisse werden in einer exportierbaren Tabelle angezeigt. Klicken Sie auf die Spaltenüberschriften, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.
1. Wählen Sie die gewünschte Optionsschaltfläche oben im Bericht aus, um Daten nach Leistung ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] oder [!UICONTROL Total Trait Population]) oder nach Zeit (1, 7, 14, 30, 60 oder 90 Tage) zu filtern.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] werden nur für [!UICONTROL Rule-based Traits] berechnet.

1. *Optional* Klicken Sie auf **[!UICONTROL Export to CSV]**. Dadurch werden [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] und [!UICONTROL Total Trait Population] für alle Tagesbereiche exportiert.

## Erläuterung der Ergebnisse von allgemeinen Berichten {#general-reports-explained}

Die Zahlen im [!UICONTROL General Reports] werden direkt aus unseren [!UICONTROL User Profile Store] generiert. Die Ergebnisse spiegeln die Anzahl der Benutzerinnen und Benutzer wider, die zum Zeitpunkt der Berichterstellung im Backend enthalten [!DNL Audience Manager].

* Diese Zahlen enthalten keine Besucher-IDs mit übermäßigem Traffic. Der Traffic von Bots wird gefiltert, bevor er unser Backend-System erreicht. Außerdem wird ein Teil des Bot-Traffics während eines wöchentlichen Bereinigungsauftrags im Backend verworfen.
* Wenn Sie Daten über die eingehende Verarbeitung integrieren, die über die [!DNL Audience Manager]-UUID verschlüsselt ist, und diese IDs Benutzer enthalten, die nicht mehr in Ihrem System aktiv sind, erreichen diese inaktiven [!DNL Audience Manager]-UUIDs nie die [!UICONTROL User Profile Store] und werden nicht gemeldet.
* [!UICONTROL Total Trait Realizations] werden nur für [!UICONTROL Rule-based Traits] berechnet.

## Allgemeine Berichte zu Ergebnissen für Eigenschaften {#general-report-results-traits}

Die folgenden Filter sind verfügbar, wenn Sie einen allgemeinen Bericht ausführen und als Berichtstyp **[!UICONTROL Trait]** auswählen.

Beim Filtern der Ergebnisse nach [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der Besucherinnen und Besucher Ihres anonymen Geräts, die die Eigenschaft innerhalb des ausgewählten Zeitraums zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der anonymen Realisierungen von Eigenschaften innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl der anonymen Gerätebesucher, die diese Eigenschaft in ihrem Profil haben.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

Beim Filtern der Ergebnisse nach [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl der authentifizierten Besucher, die das Merkmal innerhalb des ausgewählten Zeitraums zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der authentifizierten Eigenschaftsrealisierungen innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl der authentifizierten Besucher, die diese Eigenschaft in ihrem Profil haben.

![general-report-traits-cross-device](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## Ergebnisse der allgemeinen Berichte für Segmente {#general-report-results-segments}

Die folgenden Metriken sind verfügbar, wenn Sie einen allgemeinen Bericht ausführen und als Berichtstyp **[!UICONTROL Segment]** auswählen:

### Echtzeit-Segmentpopulation

Diese Metrik stellt die tatsächliche Anzahl der Unique Visitors dar, die im angegebenen Zeitraum in Echtzeit gesehen und für das Segment qualifiziert wurden, als sie von Audience Manager gesehen wurden.

### Segmentpopulation insgesamt

Diese Metrik stellt die Gesamtzahl der Audience Manager-UUIDs dar, die innerhalb des von Ihnen ausgewählten Lookback-Zeitraums für das Segment qualifiziert sind. Die 1-tägige Gesamtsegmentpopulation stellt die genaueste Benutzerbasis für die Zielgruppenbestimmung dar.

>[!NOTE]
>
>Wählen Sie **[!UICONTROL Include Destination Mappings]** aus, um eine Aufschlüsselung der Segmentpopulation für aktivierte Ziele anzuzeigen.

Die folgende Abbildung zeigt die Ergebnisse der Ausführung eines allgemeinen Berichts für den Berichtstyp Segment .

![](assets/general_reports_segment_metrics.png)

## Ergebnisse der allgemeinen Berichte für Ziele {#general-report-results-destinations}

Die folgenden Metriken sind verfügbar, wenn Sie einen allgemeinen Bericht ausführen und als Berichtstyp **[!UICONTROL Destination]** auswählen:

**Echtzeit-Segmentpopulation**

Diese Metrik stellt die tatsächliche Anzahl der Unique Visitors dar, die im angegebenen Zeitraum in Echtzeit gesehen und für das Segment qualifiziert wurden, als sie von Audience Manager gesehen wurden.

**Segmentpopulation insgesamt**

Diese Metrik stellt die Gesamtzahl der Audience Manager-UUIDs dar, die innerhalb des Lookback-Zeitraums zu einem Segment gehören und an ein Ziel gesendet wurden.

Die folgende Abbildung zeigt die Ergebnisse der Ausführung eines allgemeinen Berichts für den Berichtstyp „Ziele“.

![](assets/general_reports_destinations.png)

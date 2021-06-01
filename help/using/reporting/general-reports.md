---
description: Ein Allgemeiner Bericht gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.
seo-description: Ein Allgemeiner Bericht in Audience Manager gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.
seo-title: Allgemeine Berichte in Audience Manager
solution: Audience Manager
title: Allgemeine Berichte
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: Allgemeine und Trend-Berichte
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '869'
ht-degree: 1%

---

# Allgemeine Berichte{#general-reports}

Ein [!UICONTROL General] -Bericht gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.

## Überblick {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] verwendet  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf die  [!UICONTROL General] Berichte zu erweitern. Benutzer können nur die Eigenschaften und Segmente in Berichten sehen, die sie anzeigen können. [!UICONTROL RBAC] -Funktion können Sie steuern, welche Berichtsdaten interne Teams anzeigen können. Eine Agentur, die verschiedene Advertiser-Konten verwaltet, kann beispielsweise Benutzergruppenberechtigungen so konfigurieren, dass ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht sehen kann.

Führen Sie einen [!UICONTROL General] -Bericht aus, wenn Sie:

* Überprüfen Sie die Leistung nach Eigenschaft, Segment oder Ziel.
* Verfolgen Sie Impressionen (insgesamt und eindeutig) in Intervallen von 1, 7, 14, 30, 60 und 90 Tagen.
* Überprüfen Sie die Gesamtanzahl und die eindeutige Anzahl der Ladevorgänge.
* Vergleich der Eigenschaften- und Segmentleistung.
* Ermitteln Sie starke oder schlechte Leistungseigenschaften und -segmente, analysieren Sie die Nachfrage oder vergleichen Sie die Last-/Auslösedaten mit Drittanbieterberichten.
* Exportieren Sie Daten (.csv-Format) zur weiteren Analyse und Freigabe.

Die folgende Abbildung bietet einen allgemeinen Überblick über die Schlüsselelemente im [!UICONTROL General] -Bericht.

![](assets/general_reports.png)

1. Konfigurieren Sie die folgenden Optionen:

   * **Berichtstyp:** Wählen Sie den gewünschten Berichtstyp aus (Eigenschaft, Segment oder Ziel).

   * **Für Datumsangaben bis:** Geben Sie den Datumsbereich für den Bericht an.

2. Suchen Sie nach einer Eigenschaft, einem Segment oder einem Ziel anhand des Namens oder der ID.
3. Ziehen Sie aus der Ordnerliste die Eigenschaften, Segmente oder Ziele, die Sie melden möchten, in das Bedienfeld [!UICONTROL Selections] auf der rechten Seite.
4. Erstellen Sie den Bericht zur Anzeige in einer exportierbaren Tabelle.

## Ausführen eines allgemeinen Berichts {#run-general-report}

In diesem Abschnitt wird beschrieben, wie Sie einen [!UICONTROL General] -Bericht ausführen und Zeit- und andere Leistungsoptionen festlegen.

<!-- 

t_run_general_report.xml

 -->

1. Klicken Sie im Dashboard **[!UICONTROL Analytics]** auf **[!UICONTROL General Reports]**.
1. Wählen Sie aus der Dropdownliste **[!UICONTROL Report Type]** den gewünschten Typ aus: Eigenschaft, Segment oder Ziel.
1. ** BedingtKlicken Sie auf das Datumsfeld, um einen Kalender anzuzeigen, und wählen Sie dann das Enddatum für Ihren Bericht aus, wenn Sie ein anderes Datum als das heutige angeben möchten.
1. Suchen Sie nach einer Eigenschaft, einem Segment oder einem Ziel anhand des Namens oder der ID.
1. Ziehen Sie aus der Ordnerliste die Eigenschaften, Segmente oder Ziele, die Sie melden möchten, in das Bedienfeld [!UICONTROL Selections] auf der rechten Seite.
1. Klicken **[!UICONTROL Run Report]**.

   Die Ergebnisse werden in einer exportierbaren Tabelle angezeigt. Klicken Sie auf die Spaltenüberschriften, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.
1. Wählen Sie die gewünschte Optionsschaltfläche oben im Bericht aus, um die Daten nach Leistung ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] oder [!UICONTROL Total Trait Population]) oder nach Zeit (1, 7, 14, 30, 60 oder 90 Tage) zu filtern.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] werden  [!UICONTROL Rule-based Traits] nur berechnet.

1. ** OptionalKlicken Sie auf  **[!UICONTROL Export to CSV]**. Dadurch werden [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] und [!UICONTROL Total Trait Population] für alle Tagesbereiche exportiert.

## Allgemeine Berichtsergebnisse - Erklärung {#general-reports-explained}

Die Zahlen in [!UICONTROL General Reports] werden direkt von [!UICONTROL User Profile Store] generiert. Die Ergebnisse spiegeln die Anzahl der Benutzer wider, die zum Zeitpunkt der Generierung dieser Berichtszahlen [!DNL Audience Manager] im Backend waren.

* Diese Zahlen enthalten keine Besucher-IDs mit übermäßigem Traffic. Der Traffic von Bots wird gefiltert, bevor wir unser Backend-System erreichen. Außerdem wird während eines wöchentlichen Bereinigungsauftrags im Backend ein Teil des Bot-Traffics verworfen.
* Wenn Sie Daten über eine eingehende Verarbeitung integrieren, die mit der [!DNL Audience Manager]-UUID versehen ist und diese IDs Benutzer enthalten, die nicht mehr in unserem System aktiv sind, erreichen diese inaktiven [!DNL Audience Manager] UUIDs nie die [!UICONTROL User Profile Store] und werden nicht gemeldet.
* [!UICONTROL Total Trait Realizations] werden  [!UICONTROL Rule-based Traits] nur berechnet.

## Allgemeine Berichtsergebnisse für Eigenschaften {#general-report-results-traits}

Die folgenden Filter sind verfügbar, wenn Sie einen allgemeinen Bericht ausführen und **[!UICONTROL Trait]** als Berichtstyp auswählen.

Beim Filtern der Ergebnisse nach [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl Ihrer anonymen Gerätebesucher, die die Eigenschaft innerhalb des ausgewählten Zeitraums zu ihrem Profil hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der anonymen Realisierungen von Eigenschaften innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl der anonymen Gerätebesucher, deren Profil diese Eigenschaft aufweist.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

Beim Filtern der Ergebnisse nach [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] ist die Anzahl Ihrer authentifizierten Besucher, die ihrem Profil die Eigenschaft innerhalb des ausgewählten Zeitraums hinzugefügt haben.
* [!UICONTROL Total Trait Realization] ist die Gesamtzahl der authentifizierten Merkmalrealisierungen innerhalb des ausgewählten Zeitraums.
* [!UICONTROL Total Trait Population] ist die Anzahl Ihrer authentifizierten Besucher, die diese Eigenschaft in ihrem Profil haben.

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


## Allgemeine Berichtsergebnisse für Segmente {#general-report-results-segments}

Die folgenden Metriken sind verfügbar, wenn Sie einen allgemeinen Bericht ausführen und **[!UICONTROL Segment]** als Berichtstyp auswählen:

### Segmentpopulation in Echtzeit

Diese Metrik stellt die tatsächliche Anzahl Unique Visitors dar, die in Echtzeit über den angegebenen Zeitraum gesehen wurden und die zum Zeitpunkt der Segmenterkennung durch den Audience Manager qualifiziert waren.

### Segmentpopulation insgesamt

Diese Metrik stellt die Gesamtzahl der Audience Manager-UUIDs dar, die für das Segment innerhalb des von Ihnen ausgewählten Rückblickzeitraums qualifiziert sind. Ihre Segmentpopulation mit 1 Tag stellt Ihre genaueste Benutzerbasis für das Targeting dar.

>[!NOTE]
>
>Wählen Sie **[!UICONTROL Include Destination Mappings]** aus, um eine Aufschlüsselung der Segmentpopulation für aktivierte Ziele anzuzeigen.

Die folgende Abbildung zeigt die Ergebnisse der Ausführung eines allgemeinen Berichts für den Berichtstyp Segment .

![](assets/general_reports_segment_metrics.png)

## Allgemeine Berichte - Ergebnisse für Ziele {#general-report-results-destinations}

Die folgenden Metriken sind verfügbar, wenn Sie einen allgemeinen Bericht ausführen und **[!UICONTROL Destination]** als Berichtstyp auswählen:

**Segmentpopulation in Echtzeit**

Diese Metrik stellt die tatsächliche Anzahl Unique Visitors dar, die in Echtzeit über den angegebenen Zeitraum gesehen wurden und die zum Zeitpunkt der Segmenterkennung durch den Audience Manager qualifiziert waren.

**Segmentpopulation insgesamt**

Diese Metrik stellt die Gesamtzahl der Audience Manager-UUIDs dar, die zu einem Segment innerhalb des Rückblickzeitraums gehören und an ein Ziel gesendet wurden.

Die folgende Abbildung zeigt die Ergebnisse der Ausführung eines allgemeinen Berichts für den Berichtstyp Ziele .

![](assets/general_reports_destinations.png)

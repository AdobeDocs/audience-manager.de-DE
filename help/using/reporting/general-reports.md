---
description: Ein allgemeiner Bericht gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.
seo-description: Ein allgemeiner Bericht in Audience Manager gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.
seo-title: Allgemeine Berichte in Audience Manager
solution: Audience Manager
title: Allgemeine Berichte
uuid: 0 cea 75 a 0-969 e -4 ee 3-971 a -60 b 911711 e 52
translation-type: tm+mt
source-git-commit: 1c626c770208150d209d93f666b581113ada8de9

---


# Allgemeine Berichte{#general-reports}

Ein [!UICONTROL General] Bericht gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.

## Überblick {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] verwendet ( [!UICONTROL Role Based Access Control][!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf die [!UICONTROL General] Berichte auszudehnen. Benutzer können nur Eigenschaften und Segmente in Berichten anzeigen, die sie zur Ansicht berechtigt haben. [!UICONTROL RBAC] können Sie steuern, welche Berichtsdaten interne Teams anzeigen können. Beispielsweise kann eine Agentur, die verschiedene Advertiserkonten verwaltet, Berechtigungen für Benutzergruppen konfigurieren, damit ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht anzeigen kann.

Führen Sie einen [!UICONTROL General] Bericht aus, wenn Sie Folgendes benötigen:

* Überprüfen Sie die Leistung nach Eigenschaften, Segment oder Ziel.
* Verfolgen Sie Impressionen (Gesamt und Eindeutig) bei 1, 7, 14, 30, 60 und 90 Tagen.
* Überprüfen Sie die Gesamtzahl und die eindeutigen Ladezahlen.
* Vergleichen Sie Eigenschaften und Segmentleistung.
* Finden Sie starke oder schlechte Leistungseigenschaften und Segmente heraus, analysieren Sie die Nachfrage oder vergleichen Sie Load/Fire-Daten mit Drittanbieterberichten.
* Exportieren Sie Daten (. csv-Format) für weitere Analysen und Freigabe.

Die folgende Abbildung zeigt eine allgemeine Übersicht über wichtige Elemente im [!UICONTROL General] Bericht.

![](assets/general_reports.png)

1. Konfigurieren Sie die folgenden Optionen:

   * **Berichtstyp:** Wählen Sie den gewünschten Berichtstyp (Eigenschaften, Segment oder Ziel) aus.

   * **Für Datumsangaben:** Geben Sie den Datumsbereich für den Bericht an.

2. Suchen Sie nach einer Eigenschaft, einem Segment oder einem Ziel nach Namen oder ID.
3. Ziehen Sie in der Ordnerliste die Eigenschaften, Segmente oder Ziele, die Sie dem [!UICONTROL Selections] Bedienfeld auf der rechten Seite berichten möchten, per Drag &amp; Drop.
4. Generieren Sie den Bericht, der in einer exportierbaren Tabelle angezeigt werden soll.

## Run a General Report {#run-general-report}

In diesem Abschnitt wird beschrieben, wie Sie einen [!UICONTROL General] Bericht ausführen und die Zeit und andere Leistungsoptionen festlegen.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. Wählen Sie aus der **[!UICONTROL Report Type]** Dropdownliste den gewünschten Typ aus: Eigenschaften, Segmente oder Ziel.
1. *Bedingt* Klicken Sie auf das Datumsfeld, um einen Kalender anzuzeigen, und wählen Sie dann das Enddatum Ihres Berichts aus, wenn Sie ein anderes Datum als heute angeben möchten.
1. Suchen Sie nach einer Eigenschaft, einem Segment oder einem Ziel nach Namen oder ID.
1. Ziehen Sie in der Ordnerliste die Eigenschaften, Segmente oder Ziele, die Sie dem [!UICONTROL Selections] Bedienfeld auf der rechten Seite berichten möchten, per Drag &amp; Drop.
1. Klicken Sie auf **[!UICONTROL Run Report]**.

   Die Ergebnisse werden in einer exportierbaren Tabelle angezeigt. Klicken Sie auf die Spaltenüberschriften, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.
1. Wählen Sie die gewünschte Optionsschaltfläche oben im Bericht aus, um Daten nach Leistung ( [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Realizations], oder [!UICONTROL Total Trait Population]) oder nach Zeit (1, 7, 14, 30, 60 oder 90 Tage) zu filtern.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] berechnet.[!UICONTROL Rule-based Traits]

1. *Optionaler* Klick **[!UICONTROL Export to CSV]**. Dadurch werden die [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]und [!UICONTROL Total Trait Population] alle Tage exportiert.

## Allgemeine Berichtsergebnisse {#general-reports-explained}

Die Zahlen in [!UICONTROL General Reports] werden direkt von unserer [!UICONTROL User Profile Store]generiert. Die Ergebnisse spiegeln die Anzahl der Benutzer wider, die [!DNL Audience Manager] zum Zeitpunkt der Erstellung dieser Berichtszahlen im Backend enthalten waren.

* Diese Zahlen enthalten keine Besucher-IDs mit übermäßiges Traffic. Der Traffic von Bots wird vor Erreichen unseres Backend-Systems gefiltert. Außerdem wird einige Bot-Traffic während eines wöchentlichen Bereinigungsauftrags im Backend verworfen.
* Wenn Sie Daten über die eingehende Verarbeitung über die [!DNL Audience Manager] UUID deaktivieren und diese IDs Benutzer enthalten, die in unserem System nicht mehr aktiv sind, erreichen diese inaktiven [!DNL Audience Manager] uuids niemals und [!UICONTROL User Profile Store] werden nicht gemeldet.
* [!UICONTROL Total Trait Realizations] berechnet.[!UICONTROL Rule-based Traits]

## Allgemeine Berichtsergebnisse für Eigenschaften {#general-report-results-traits}

Die folgenden Metriken stehen zur Verfügung, wenn Sie einen allgemeinen Bericht ausführen und als **[!UICONTROL Trait]** Berichtstyp auswählen:

**Eindeutige Eigenschaftsrealizationen**

Diese Metrik stellt die eindeutige Anzahl der [Unique User IDs (Unique User IDs) von Audience Manager dar](../reference/ids-in-aam.md) , die für die Eigenschaft im ausgewählten Zeitraum qualifiziert sind. Wenn ein Benutzer Ihre Homepage beispielsweise dreimal am 10.01. besucht hat, wird eine eindeutige Merkmalisierung angezeigt.

**Gesamteigenschaften von Eigenschaften**

Diese Metrik stellt die Gesamtanzahl der Eigenschaften dar, die für die Eigenschaft im ausgewählten Zeitraum ausgelöst werden. Wenn ein Benutzer z. B. Ihre Homepage besucht hat und dann zu Ihren Tech-News-Nachrichten und Ihren Sportnews-Abschnitten navigiert, würde er im allgemeinen Bericht als drei vollständige Eigenschaftenrealizationen und eine eindeutige Merkmalisierung erscheinen.

**Gesamtanzahl der Eigenschaften**

Diese Metrik stellt die Gesamtanzahl der uuids von Audience Manager dar, die derzeit für die Eigenschaft qualifiziert sind. Verwenden Sie diese Zahl, um zu verstehen, wie viele Benutzer Sie für die Segmentierung und das Targeting insgesamt verwenden können. In der Regel bleiben Benutzer 120 [Tage](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)lang Teil einer Eigenschaft. Beispielsweise würde ein Benutzer, der Ihre Homepage dreimal besucht und anschließend nie wieder zurückkehrt, jeden Tag bis 120 Tage lang als Benutzer in dieser Population weiterbleiben. Bei einem Tag von 120 Tagen würden sie aus der Population entfernt. Lesen Sie unsere [Trait-Qualifizierungsreferenz](../features/traits/trait-qualification-reference.md) für weitere Beispiele zum Unterschied zwischen den individuellen Eigenschaften und der Gesamtanzahl der Eigenschaften.

Die unten stehende Abbildung zeigt die Ergebnisse eines allgemeinen Berichts für den Trait-Berichtstyp.

![](assets/general_reports_metrics.png)

## Allgemeine Berichtsergebnisse für Segmente {#general-report-results-segments}

Die folgenden Metriken stehen zur Verfügung, wenn Sie einen allgemeinen Bericht ausführen und als **[!UICONTROL Segment]** Berichtstyp auswählen:

**Segmentpopulation in Echtzeit**

Diese Metrik stellt die tatsächliche Anzahl individueller Besucher dar, die in Echtzeit für den angegebenen Zeitraum angesehen wurden und für das Segment qualifiziert waren, wenn sie von Audience Manager gesehen wurden.

**Segmentpopulation insgesamt**

Diese Metrik stellt die Gesamtanzahl der uuids von Audience Manager dar, die für das Segment im ausgewählten Look-Back-Zeitraum qualifiziert sind. Ihre Gesamtsegmentpopulation von 1 Tag stellt Ihre genaueste Benutzerbasis für das Targeting dar.

>[!NOTE]
>
>Wählen **[!UICONTROL Include Destination Mappings]** Sie diese Option, um eine Aufschlüsselung der Segmentpopulation für aktivierte Ziele anzuzeigen.

Die folgende Abbildung zeigt die Ergebnisse der Ausführung eines allgemeinen Berichts für den Berichtstyp "Segmente" .

![](assets/general_reports_segment_metrics.png)

## Allgemeine Berichtsergebnisse für Ziele {#general-report-results-destinations}

Die folgenden Metriken stehen zur Verfügung, wenn Sie einen allgemeinen Bericht ausführen und als **[!UICONTROL Destination]** Berichtstyp auswählen:

**Segmentpopulation in Echtzeit**

Diese Metrik stellt die tatsächliche Anzahl individueller Besucher dar, die in Echtzeit für den angegebenen Zeitraum angesehen wurden und für das Segment qualifiziert waren, wenn sie von Audience Manager gesehen wurden.

**Segmentpopulation insgesamt**

Diese Metrik stellt die Gesamtzahl der uuids von Audience Manager dar, die zu einem Segment innerhalb des Suchzeitraums gehören und an ein Ziel gesendet wurden.

Die unten stehende Abbildung zeigt die Ergebnisse eines allgemeinen Berichts für den Berichtstyp Ziele.

![](assets/general_reports_destinations.png)

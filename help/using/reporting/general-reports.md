---
description: Ein Allgemeiner Bericht gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.
seo-description: Ein Allgemeiner Bericht in Audience Manager gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.
seo-title: Allgemeine Berichte im Audience Manager
solution: Audience Manager
title: Allgemeine Berichte
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Allgemeine Berichte{#general-reports}

Ein [!UICONTROL General] Bericht gibt Leistungsdaten zu Eigenschaften, Segmenten und Zielen zurück.

## Überblick {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] verwendet [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um die Benutzergruppenberechtigungen auf die [!UICONTROL General] Berichte auszudehnen. Benutzer können nur die Eigenschaften und Segmente in Berichten anzeigen, für die sie über die Berechtigung zur Ansicht verfügen. [!UICONTROL RBAC] Mit dieser Funktion können Sie steuern, welche Berichte-Daten interne Teams zur Ansicht bereitstellen können. Eine Agentur, die verschiedene Advertiser-Konten verwaltet, kann beispielsweise Benutzergruppenberechtigungen so konfigurieren, dass ein Team, das das Konto des Advertiser A verwaltet, die Daten des Berichte von Advertiser B nicht sehen kann.

Führen Sie einen [!UICONTROL General] Bericht aus, wenn Sie:

* Überprüfen Sie die Leistung nach Eigenschaften, Segmenten oder Ziel.
* Verfolgen Sie Impressionen (insgesamt und eindeutig) in Intervallen von 1, 7, 14, 30, 60 und 90 Tagen.
* Überprüfen Sie die Gesamtzahl und die Anzahl individueller Lasten.
* Vergleich der Eigenschaften- und Segmentleistung.
* Identifizieren Sie leistungsstarke oder schlechte Eigenschaften und Segmente, analysieren Sie die Nachfrage oder vergleichen Sie Daten zu Auslastung und Feuer mit Berichten von Drittanbietern.
* Exportieren Sie Daten (.csv-Format) zur weiteren Analyse und Freigabe.

Die folgende Abbildung zeigt einen Überblick über die wichtigsten Elemente des [!UICONTROL General] Berichts auf hoher Ebene.

![](assets/general_reports.png)

1. Konfigurieren Sie die folgenden Optionen:

   * **Berichtstyp:** Wählen Sie den gewünschten Berichtstyp aus (Eigenschaft, Segment oder Ziel).

   * **Für Datumsangaben bis:** Geben Sie den Datumsbereich für den Bericht an.

2. Suchen Sie nach einer Eigenschaft, einem Segment oder einem Ziel anhand des Namens oder der ID.
3. Ziehen Sie die Eigenschaften, Segmente oder Ziele, die Sie in Berichten anzeigen möchten, aus der Liste des Ordners in das [!UICONTROL Selections] Bedienfeld auf der rechten Seite.
4. Erstellen Sie den Bericht, der in einer exportierbaren Tabelle angezeigt werden soll.

## Run a General Report {#run-general-report}

In diesem Abschnitt wird beschrieben, wie Sie einen [!UICONTROL General] Bericht ausführen und Zeit- und andere Leistungsoptionen festlegen.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. Wählen Sie in der **[!UICONTROL Report Type]** Dropdown-Liste den gewünschten Typ aus: Eigenschaft, Segment oder Ziel.
1. *Bedingt* Klicken Sie auf das Datumsfeld, um einen Kalender anzuzeigen, und wählen Sie dann das Enddatum für Ihren Bericht aus, wenn Sie ein anderes Datum als das heutige angeben möchten.
1. Suchen Sie nach einer Eigenschaft, einem Segment oder einem Ziel anhand des Namens oder der ID.
1. Ziehen Sie die Eigenschaften, Segmente oder Ziele, die Sie in Berichten anzeigen möchten, aus der Liste des Ordners in das [!UICONTROL Selections] Bedienfeld auf der rechten Seite.
1. Klicken **[!UICONTROL Run Report]**.

   Die Ergebnisse werden in einer exportierbaren Tabelle angezeigt. Klicken Sie auf die Spaltenüberschriften, um die Ergebnisse in auf- oder absteigender Reihenfolge zu sortieren.
1. Wählen Sie die gewünschte Optionsschaltfläche oben im Bericht aus, um Daten nach Leistung ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]oder [!UICONTROL Total Trait Population]) oder nach Zeit (1, 7, 14, 30, 60 oder 90 Tage) zu filtern.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] werden [!UICONTROL Rule-based Traits] nur berechnet.

1. *Optional* klicken **[!UICONTROL Export to CSV]**. Dadurch werden die [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]und [!UICONTROL Total Trait Population] für alle Tagesbereiche exportiert.

## Allgemeine Berichte - Erläuterung {#general-reports-explained}

Die Zahlen in der [!UICONTROL General Reports] werden direkt aus unserer [!UICONTROL User Profile Store]. Die Ergebnisse spiegeln die Anzahl der Berichte wider, die zum Zeitpunkt der Generierung dieser Nummern im Backend [!DNL Audience Manager] enthalten waren.

* Diese Zahlen enthalten keine Besucher-IDs mit übermäßigem Traffic. Der Traffic von Bots wird gefiltert, bevor wir unser Backend-System erreichen. Außerdem wird während eines wöchentlichen Bereinigungsauftrags im Backend ein Teil des Bot-Traffics verworfen.
* Wenn Sie Daten über eine eingehende Verarbeitung mit einem Schlüsselwort aus der [!DNL Audience Manager] UUID an Bord mitführen und diese IDs Benutzer enthalten, die nicht mehr in unserem System aktiv sind, erreichen diese inaktiven [!DNL Audience Manager] UUIDs nie den Wert [!UICONTROL User Profile Store] und werden nicht gemeldet.
* [!UICONTROL Total Trait Realizations] werden [!UICONTROL Rule-based Traits] nur berechnet.

## Allgemeine Berichte - Ergebnisse für Eigenschaften {#general-report-results-traits}

Die folgenden Metriken stehen zur Verfügung, wenn Sie einen allgemeinen Bericht ausführen und **[!UICONTROL Trait]** als Berichtstyp auswählen:

**Eindeutige Eigenschaften**

Diese Metrik stellt die eindeutige Anzahl der Unique User IDs (UUID) [von](../reference/ids-in-aam.md) Audience Manager dar, die für die Eigenschaft in Ihrem ausgewählten Zeitraum qualifiziert sind. Wenn ein Benutzer Ihre Homepage beispielsweise dreimal am 10.10.2010 besucht, wird eine Unique Trait Realization angezeigt.

**Eigenschaften insgesamt**

Diese Metrik stellt die Gesamtanzahl der ausgelösten Eigenschaften für die Eigenschaft im ausgewählten Zeitraum dar. Wenn ein Benutzer z. B. Ihre Homepage besuchte und dann zu Ihren Tech-Nachrichten- und Sportnachrichten-Bereichen navigierte, wurden diese im Bericht &quot;Allgemein&quot;als drei Gesamtmerkmalen und eine einzigartige Erkenntnis angezeigt.

**Gesamtzahl der Eigenschaften**

Diese Metrik stellt die Gesamtanzahl der Audience Manager-UUIDs dar, die derzeit für die Eigenschaft qualifiziert sind. Verwenden Sie diese Zahl, um die Gesamtanzahl der Benutzer zu verstehen, die Sie für die Segmentierung und das Targeting verwenden können. Normalerweise bleiben Benutzer [120 Tage](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)lang Teil einer Eigenschaft. Beispielsweise würde ein Benutzer, der Ihre Homepage heute dreimal besucht und nie danach zurückkehrt, bis zu 120 Tagen täglich als Benutzer in dieser Population bleiben. Bei 120 Tagen würden sie aus der Bevölkerung entfernt. Lesen Sie unsere [Eigenschaften- und Segmentqualifizierungsreferenz](../features/traits/trait-and-segment-qualification-reference.md) für weitere Beispiele zum Unterschied zwischen individuellen Eigenschaften und der Gesamtanzahl der Eigenschaften.

Die folgende Abbildung zeigt die Ergebnisse der Ausführung eines allgemeinen Berichts für den Berichtstyp &quot;Eigenschaft&quot;.

![](assets/general_reports_metrics.png)

## Allgemeine Berichtsergebnisse für Segmente {#general-report-results-segments}

Die folgenden Metriken stehen zur Verfügung, wenn Sie einen allgemeinen Bericht ausführen und **[!UICONTROL Segment]** als Berichtstyp auswählen:

**Population von Echtzeit-Segmenten**

Diese Metrik stellt die tatsächliche Anzahl individueller Besucher dar, die in Echtzeit während des angegebenen Zeitraums gesehen wurden und die zu dem Zeitpunkt für das Segment qualifiziert waren, zu dem sie von Audience Manager gesehen wurden.

**Segmentpopulation insgesamt**

Diese Metrik stellt die Gesamtanzahl der Audience Manager-UUIDs dar, die für das Segment innerhalb der von Ihnen gewählten Rückblickzeit qualifiziert sind. Ihre Segmentpopulation mit 1 Tag stellt Ihre genaueste Benutzerbasis für das Targeting dar.

>[!NOTE]
>
>Wählen Sie **[!UICONTROL Include Destination Mappings]** aus, um eine Unterteilung der Segmentpopulation für aktivierte Ziele anzuzeigen.

Die folgende Abbildung zeigt die Ergebnisse der Ausführung eines allgemeinen Berichts für den Berichtstyp Segment.

![](assets/general_reports_segment_metrics.png)

## Allgemeine Berichte - Ergebnisse für Ziele {#general-report-results-destinations}

Die folgenden Metriken stehen zur Verfügung, wenn Sie einen allgemeinen Bericht ausführen und **[!UICONTROL Destination]** als Berichtstyp auswählen:

**Population von Echtzeit-Segmenten**

Diese Metrik stellt die tatsächliche Anzahl individueller Besucher dar, die in Echtzeit während des angegebenen Zeitraums gesehen wurden und die zu dem Zeitpunkt für das Segment qualifiziert waren, zu dem sie von Audience Manager gesehen wurden.

**Segmentpopulation insgesamt**

Diese Metrik stellt die Gesamtanzahl der Audience Manager-UUIDs dar, die innerhalb des Rückblickzeitraums zu einem Segment gehören und an ein Ziel gesendet wurden.

Die folgende Abbildung zeigt die Ergebnisse der Ausführung eines allgemeinen Berichts für den Berichtstyp &quot;Ziele&quot;.

![](assets/general_reports_destinations.png)

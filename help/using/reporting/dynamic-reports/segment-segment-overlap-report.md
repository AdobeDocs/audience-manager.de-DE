---
description: Gibt Daten dazu zurück, wie viele eindeutige Benutzer Ihre Segmente gemeinsam nutzen.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: Bericht zur Überschneidung von Segmenten
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 6%

---

# Bericht zur Überschneidung von Segmenten{#segment-to-segment-overlap-report}

Gibt Daten dazu zurück, wie viele eindeutige Benutzer Ihre Segmente gemeinsam nutzen.

>[!NOTE]
>
>Die Überschneidungsberichte in Audience Manager entsprechen den RBAC-Prinzipien. Sie können nur Segmente aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), der Sie angehören.

<!-- 

c_segment_segment_overlap.xml

 -->

## Überblick

Der [!UICONTROL Segment-to-Segment Overlap] Bericht kann Ihnen dabei helfen:

* Identifizieren Sie Segmente mit hoher oder geringer Überschneidung, je nach Ihren Anforderungen. Eigenschaften mit hoher Überschneidung liefern eine zielgerichtete Zielgruppe, aber weniger Unique Visitors. Eigenschaften mit geringer Überschneidung können nützlich sein, um einen größeren Unique-Visitor-Satz zu erreichen.
* Suchen Sie nach unerwarteten Überschneidungen und verwenden Sie diese Informationen zum Erstellen neuer, leistungsstarker Segmente.

## Beispielbericht

Die folgende Abbildung bietet einen allgemeinen Überblick über den [!UICONTROL Segment-to-Segment Overlap].

>[!NOTE]
>
>Der [!UICONTROL Segment-to-Segment Overlap] gibt ein leeres Feld zurück, wenn dasselbe Segment mit sich selbst verglichen wird.

![](assets/segment-to-segment-overlap.png)

## Drilldown zu einzelnen Datenpunkten

Wählen Sie einen einzelnen Punkt aus, um Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## POP-Felder für Überschneidungsdaten von Segmenten zu Segmenten definiert {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

Das Popup für den [!UICONTROL Segment-to-Segment Overlap] enthält die folgenden Metriken. Beachten Sie, dass die Metrik Eindeutig in der Tabelle Ihre *Echtzeit-Benutzer* darstellt.

| Metrik | Beschreibung |
|---|---|
| **[!UICONTROL Base Segment ID]** | Eindeutige numerische ID für das Segment, das in den Berichtsergebnissen angezeigt wird. Erscheint als Zeilen-ID für das Segment. |
| **[!UICONTROL Base Segment Name]** | Name des Segments, das in der Berichtsergebniszeile angezeigt wird. |
| **[!UICONTROL Overlapping Segment ID]** | Eindeutige numerische ID für das Segment, das Sie beim Ausführen des Berichts auswählen. Erscheint als Spalten-ID für das Segment. |
| **[!UICONTROL Overlapping Segment Name]** | Name des Segments, das Sie beim Ausführen des Berichts auswählen. Erscheint in der Spalte Berichtsergebnisse. |
| **[!UICONTROL Base Segment Uniques]** | Die Anzahl der Unique Visitors in Ihrem Basissegment. |
| **[!UICONTROL Base Segment Uniques]** | Die Anzahl der Unique Visitors in Ihrem sich überschneidenden Segment. |
| **[!UICONTROL Overlapping Uniques]** | Die Anzahl der Unique Visitors, die von den einzelnen Segmenten gemeinsam genutzt werden. |
| **[!UICONTROL Overlap %]** | Um die Überschneidung (%) zu erhalten, verwendet der Audience Manager die folgende Formel: Überlappende eindeutige Segmente / (Basissegmenteindeutige Segmente + Überlappende Segmenteindeutigkeiten - Überlappende eindeutige Segmente) |



>[!MORELIKETHIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
>* [In interaktiven Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Berichtssymbole und Tools - Erklärung](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überlagerungsberichte: Aktualisierungszeitplan und Mindestsegmentgröße](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datenstichproben- und Fehlerquoten in Berichten zu ausgewählten Audience Managern…](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)

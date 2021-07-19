---
description: Gibt Daten zurück, wie viele Unique Users für Ihre Segmente freigegeben wurden.
seo-description: Gibt Daten zurück, wie viele Unique Users für Ihre Segmente freigegeben wurden.
seo-title: Überlagerungsbericht zwischen Segmenten
solution: Audience Manager
title: Überlagerungsbericht zwischen Segmenten
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Überlagerungsberichte
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 11%

---

# Überlagerungsbericht zwischen Segmenten{#segment-to-segment-overlap-report}

Gibt Daten zurück, wie viele Unique Users für Ihre Segmente freigegeben wurden.

>[!NOTE]
>
>Die Überlagerungsberichte in Audience Manager folgen den RBAC-Grundsätzen. Sie können nur Segmente aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), zu der Sie gehören.

<!-- 

c_segment_segment_overlap.xml

 -->

## Überblick

Der Bericht [!UICONTROL Segment-to-Segment Overlap] kann Ihnen dabei helfen,

* Identifizieren Sie Segmente mit hoher oder niedriger Überschneidung, je nach Ihren Anforderungen. Eigenschaften mit hoher Überschneidung geben Ihnen eine zielgerichtete Zielgruppe, aber weniger Unique Visitors. Eigenschaften mit geringer Überschneidung können nützlich sein, um einen größeren Unique Visitor-Satz zu erreichen.
* Ermitteln Sie unerwartete Überschneidungen und verwenden Sie diese Informationen, um neue Hochleistungssegmente zu erstellen.

## Beispielbericht

Die folgende Abbildung bietet einen allgemeinen Überblick über den Bericht [!UICONTROL Segment-to-Segment Overlap].

>[!NOTE]
>
>Der Bericht [!UICONTROL Segment-to-Segment Overlap] gibt ein leeres Feld zurück, wenn er dasselbe Segment mit sich vergleicht.

![](assets/segment-to-segment-overlap.png)

## Drilldown für einzelne Datenpunkte

Wählen Sie einen einzelnen Punkt aus, um die Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Überlagerungsdaten-Populationsfelder zwischen Segmenten definiert {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

Das Popup-Fenster für den Bericht [!UICONTROL Segment-to-Segment Overlap] enthält die folgenden Metriken. Beachten Sie, dass die eindeutige Metrik in der Tabelle Ihre *Echtzeitbenutzer* darstellt.

| Metrik | Beschreibung |
|---|---|
| **[!UICONTROL Base Segment ID]** | Eindeutige numerische ID für das Segment, das in den Berichtsergebnissen angezeigt wird. Wird als Zeilen-ID für das Segment angezeigt. |
| **[!UICONTROL Base Segment Name]** | Name des Segments, das in der Zeile mit den Berichtsergebnissen angezeigt wird. |
| **[!UICONTROL Overlapping Segment ID]** | Eindeutige numerische ID für das Segment, das Sie beim Ausführen des Berichts auswählen. Wird als Spaltenkennung für das Segment angezeigt. |
| **[!UICONTROL Overlapping Segment Name]** | Name des Segments, das Sie beim Ausführen des Berichts auswählen. Wird in der Spalte Berichtsergebnisse angezeigt. |
| **[!UICONTROL Base Segment Uniques]** | Die Anzahl der Unique Visitors in Ihrem Basissegment. |
| **[!UICONTROL Base Segment Uniques]** | Die Anzahl der Unique Visitors in Ihrem überlappenden Segment. |
| **[!UICONTROL Overlapping Uniques]** | Die Anzahl der Unique Visitors, die zwischen verglichenen Segmenten freigegeben wurden. |
| **[!UICONTROL Overlap %]** | Um die Überschneidungsrate in % zu erhalten, verwendet Audience Manager die folgende Formel: Überlappende Individuen / (Basissegment-Individuen + Überlappende Segmentindividualitäten - Überlappende Individuen) |



>[!MORELIKETHIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
* [In interaktiven Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
* [Berichtssymbole und -werkzeuge - Erklärung](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
* [Überlagerungsberichte: Aktualisierungszeitplan und Mindestsegmentgröße](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
* [Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten...](../../reporting/report-sampling.md)
* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)


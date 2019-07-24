---
description: Gibt Daten zurück, wie viele Unique Users zwischen Ihren Segmenten gezählt werden.
seo-description: Gibt Daten zurück, wie viele Unique Users zwischen Ihren Segmenten gezählt werden.
seo-title: Überschneidungsbericht zwischen Segmenten
solution: Audience Manager
title: Überschneidungsbericht zwischen Segmenten
uuid: 0339 eb 6 c -6355-44 a 3-9 c 46-f 159485449 d 1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# Überschneidungsbericht zwischen Segmenten{#segment-to-segment-overlap-report}

Gibt Daten zurück, wie viele Unique Users zwischen Ihren Segmenten gezählt werden.

>[!NOTE]
>
>Die Überlappungsberichte in Audience Manager berücksichtigen RBAC-Prinzipien. You can only see segments from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_segment_overlap.xml

 -->

## Überblick

The [!UICONTROL Segment-to-Segment Overlap] report can help you:

* Identifizieren Sie Segmente mit hoher oder niedriger Überschneidung, je nach Ihren Anforderungen. Eigenschaften mit hoher Überlappung bieten eine zielgruppe, aber weniger individuelle Besucher. Eigenschaften mit geringer Überlappung können hilfreich sein, um einen größeren, individuellen Besucher zu erreichen.
* Finden Sie unerwartete Überlappungen heraus und verwenden Sie diese Informationen, um neue, leistungsstarke Segmente zu erstellen.

## Beispielbericht

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Segment Overlap] report.

>[!NOTE]
>
>The [!UICONTROL Segment-to-Segment Overlap] report returns an empty field when it compares the same segment to itself.

![](assets/segment-to-segment-overlap.png)

## Drilldown für einzelne Datenpunkte

Wählen Sie einen einzelnen Punkt aus, um die Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Segment-to-Segment Overlap Data Pop Fields Defined {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

The popup for the [!UICONTROL Segment-to-Segment Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

| Metrik | Beschreibung |
|---|---|
| **[!UICONTROL Segment ID1]** | Eindeutige numerische ID für das Segment, das in den Berichtsergebnissen angezeigt wird. Erscheint als die Zeile-ID für das Segment. |
| **[!UICONTROL Segment ID2]** | Eindeutige numerische ID für das Segment, das Sie beim Ausführen des Berichts auswählen. Erscheint als die Spalte-ID für das Segment. |
| **[!UICONTROL Segment Name1]** | Name des Segments, das in der Berichtergebniszeile angezeigt wird. |
| **[!UICONTROL Segment Name2]** | Name des Segments, das Sie beim Ausführen des Berichts auswählen. Erscheint in der Berichtergebnisspalte. |
| **[!UICONTROL Overlap %]** | Um die Überschneidung % zu erhalten, verwendet Audience Manager die folgende Formel: Überlappende Uniques/(Basissegmente Individuelle Werte + Überlappende Segmente - Überlappende Uniques) |
| **[!UICONTROL Overlap Uniques]** | Die Anzahl der Unique Visitors, die zwischen Vergleichssegmenten freigegeben wurden. |
| **[!UICONTROL Segment Uniques1]** | Die Anzahl individueller Besucher in Segment 1. |
| **[!UICONTROL Segment Uniques2]** | Die Anzahl individueller Besucher in Segment 2. |

>[!MORE_ LIKE_ THIS]
>
>* [Berichtsergebnisse mit den Datenreglern filtern](../../reporting/dynamic-reports/data-sliders.md)
>* [In interaktiven Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Erklärung der Berichtsymbole und Tools](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überlappungsberichte: Zeitplan und Mindestgröße des Segments aktualisieren](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datenstichproben und Fehlersätze in ausgewählten Audience Manager-Berichten…](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlappungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)
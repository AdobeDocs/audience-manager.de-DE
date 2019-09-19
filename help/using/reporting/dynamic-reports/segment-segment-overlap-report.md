---
description: Gibt Daten darüber zurück, wie viele Unique Users für Ihre Segmente freigegeben wurden.
seo-description: Gibt Daten darüber zurück, wie viele Unique Users für Ihre Segmente freigegeben wurden.
seo-title: Überschneidungsbericht zwischen Segmenten
solution: Audience Manager
title: Überschneidungsbericht zwischen Segmenten
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# Überschneidungsbericht zwischen Segmenten{#segment-to-segment-overlap-report}

Gibt Daten darüber zurück, wie viele Unique Users für Ihre Segmente freigegeben wurden.

>[!NOTE]
>
>Die Überschneidungsberichte in Audience Manager folgen den RBAC-Grundsätzen. Sie können nur Segmente aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md) , der Sie angehören.

<!-- 

c_segment_segment_overlap.xml

 -->

## Überblick

Der [!UICONTROL Segment-to-Segment Overlap] Bericht hilft Ihnen bei Folgendem:

* Identifizieren Sie Segmente mit hoher oder niedriger Überschneidung, je nach Ihren Anforderungen. Eigenschaften mit hoher Überschneidung geben Ihnen eine zielgerichtete Zielgruppe, aber weniger individuelle Besucher. Eigenschaften mit geringer Überschneidung können nützlich sein, um einen größeren, individuellen Besuchersatz zu erreichen.
* Finden Sie unerwartete Überschneidungen und verwenden Sie diese Informationen, um neue, leistungsstarke Segmente zu erstellen.

## Beispielbericht

Die folgende Abbildung zeigt einen Überblick über den [!UICONTROL Segment-to-Segment Overlap] Bericht auf hoher Ebene.

>[!NOTE]
>
>Der [!UICONTROL Segment-to-Segment Overlap] Bericht gibt ein leeres Feld zurück, wenn dasselbe Segment mit sich selbst verglichen wird.

![](assets/segment-to-segment-overlap.png)

## Drilldown für einzelne Datenpunkte

Wählen Sie einen einzelnen Punkt aus, um die Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Von Segment zu Segment überschneidende Datenpop-Felder definiert {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

Das Popup für den [!UICONTROL Segment-to-Segment Overlap] Bericht enthält die folgenden Metriken. Beachten Sie, dass die Metrik "Individuelle Werte"in der Tabelle Ihre *Echtzeit-Benutzer* darstellt.

| Metrik | Beschreibung |
|---|---|
| **[!UICONTROL Segment ID1]** | Eindeutige numerische ID für das Segment, das in den Berichtsergebnissen angezeigt wird. Erscheint als Zeilen-ID für das Segment. |
| **[!UICONTROL Segment ID2]** | Eindeutige numerische ID für das Segment, das Sie beim Ausführen des Berichts auswählen. Erscheint als Spalte-ID für das Segment. |
| **[!UICONTROL Segment Name1]** | Name des Segments, das in der Berichtsergebniszeile angezeigt wird. |
| **[!UICONTROL Segment Name2]** | Name des Segments, das Sie beim Ausführen des Berichts auswählen. Wird in der Berichtsergebnisspalte angezeigt. |
| **[!UICONTROL Overlap %]** | Um die Überschneidung % zu erhalten, verwendet Audience Manager die folgende Formel: Überschneidende individuelle Elemente / (Basis-Segment-Uniques + Überschneidende Segment-Uniques - Überschneidende Uniques) |
| **[!UICONTROL Overlap Uniques]** | Die Anzahl der Unique Visitors, die zwischen verglichenen Segmenten freigegeben wurden. |
| **[!UICONTROL Segment Uniques1]** | Die Anzahl der individuellen Besucher in Segment 1. |
| **[!UICONTROL Segment Uniques2]** | Die Anzahl der individuellen Besucher in Segment 2. |

>[!MORE_LIKE_THIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
>* [In interaktiven Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Berichtssymbole und -werkzeuge erläutert](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überschneidungsberichte: Zeitplan und Mindestsegmentgröße aktualisieren](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datenstichproben und Fehlerquoten in ausgewählten Audience Manager-Berichten...](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)
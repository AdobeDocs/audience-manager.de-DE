---
description: Gibt Daten zur Anzahl der Unique Users zurück, die für alle Erstanbieter- und Drittanbieter-Eigenschaften freigegeben wurden.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: Überlagerungsbericht zwischen Eigenschaften
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Überlagerungsbericht zwischen Eigenschaften{#trait-to-trait-overlap-report}

Gibt Daten zur Anzahl der Unique Users zurück, die für alle Erstanbieter- und Drittanbieter-Eigenschaften freigegeben wurden.

>[!NOTE]
>
>Die Überlagerungsberichte in Audience Manager folgen den RBAC-Grundsätzen. Sie können Eigenschaften nur aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), der Sie angehören.

<!-- 

c_overlap_reports.xml

 -->

## Überblick

Der Bericht &quot;[!UICONTROL Trait-to-Trait Overlap]&quot;gibt Daten zu den % der Unique Users zurück, die für alle Ihre eigenen Eigenschaften und Ihre Eigenschaften von Drittanbietern freigegeben wurden. Als Optimierungstool hilft Ihnen dieser Bericht bei Folgendem:

* Erstellen Sie je nach Bedarf Segmente mit hoher oder niedriger Überschneidung. Eigenschaften mit hoher Überschneidung geben Ihnen eine zielgerichtete Zielgruppe, aber weniger Unique Visitors. Eigenschaften mit geringer Überschneidung können nützlich sein, um einen größeren Unique Visitor-Satz zu erreichen.
* Validieren von Eigenschaftsdaten von Drittanbietern: Eine starke Überschneidung ähnlicher Erstanbieter- und Drittanbieter-Eigenschaften deutet darauf hin, dass die Eigenschaft Ihres Datenpartners korrekt und vertrauenswürdig ist. Umgekehrt kann eine geringe Überschneidung darauf hindeuten, dass eine Eigenschaft eines Drittanbieters möglicherweise nicht die gleichen Informationen wie Ihre eigene, ähnliche Eigenschaft eines Erstanbieters enthält.
* Finden Sie unerwartete Überschneidungen zwischen Eigenschaften und verwenden Sie diese Informationen, um innovative Segmente zu erstellen.

## Beispielbericht

Die folgende Abbildung bietet einen allgemeinen Überblick über die Elemente im [!UICONTROL Trait-to-Trait Overlap] -Bericht.

>[!NOTE]
>
>Der Bericht [!UICONTROL Trait-to-Trait Overlap] gibt ein leeres Feld zurück, wenn er dieselbe Eigenschaft mit sich vergleicht.

>[!NOTE]
>
>Ordnereigenschaften stehen in Überschneidungsberichten von Eigenschaften nicht zum Vergleich zur Verfügung. Durch die Erstellung eines Segments, das eine bestimmte Ordnereigenschaft verwendet, können Sie Analysen über den Bericht [Segment-zu-Merkmal-Überschneidung](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md) durchführen.

![](assets/trait-to-trait-overlap.png)

## Drilldown für einzelne Datenpunkte

Wählen Sie einen einzelnen Punkt aus, um die Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Überlagerungsdatenfelder zwischen Eigenschaften definiert {#field-definitions}

Beschreibt die Metriken, die beim Klicken auf einen einzelnen Datenpunkt im Popup-Fenster angezeigt werden.

<!-- 

r_t2t_data_pop.xml

 -->

Das Popup-Fenster für den Bericht [!UICONTROL Trait-to-Trait Overlap] enthält die folgenden Metriken. Beachten Sie, dass die eindeutige Metrik in der Tabelle Ihre *Echtzeitbenutzer* darstellt.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlap %</span></b> </td> 
   <td colname="col2"> Zeigt die % der eindeutigen Überschneidung zwischen verglichenen Eigenschaften (Überschneidung von individuellen/individuellen Eigenschaften). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Source-Datentyp</span></b> </td> 
   <td colname="col2">Definiert den Typ der Datenquelle, zu der eine Eigenschaft gehört. Kann Folgendes sein: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Erstanbieter (Ihre eigene Eigenschaft). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Drittanbieter (von einem externen Datenpartner/Anbieter). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überlappende Eigenschaften-ID</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für die überlappende Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überschneidender Eigenschaftsname</span></b> </td> 
   <td colname="col2"> Name der überlappenden Eigenschaft. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschafts-ID 2</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für die Eigenschaft in Ihrer Basisdatenquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsname 2</span></b> </td> 
   <td colname="col2"> Name der Eigenschaft in Ihrer Basisdatenquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überlagerungen Individuelle Werte</span></b> </td> 
   <td colname="col2"> <p>Um die Überschneidungsrate in % zu erhalten, verwendet Audience Manager die folgende Formel:</p> <p>Überlappende Individuen / (Basiseigenschaft Individuelle Eigenschaften + Überlappende Eigenschaften Individuelle Werte - Überlappende Individuen)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überschneidende Eigenschaftsindividuellen </span></b> </td> 
   <td colname="col2"> Die Anzahl der Unique Visitors aus der überlappenden Eigenschaft. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Grundlegende Eigenschaftsvariablen</span></b> </td> 
   <td colname="col2"> Die Anzahl der Unique Visitors aus der Basiseigenschaft. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
>* [In dynamischen Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Berichtssymbole und -tools - Erklärung](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überlagerungsberichte: Aktualisierungszeitplan und Mindestsegmentgröße](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten...](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)

---
description: Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die für alle Erst- und Drittanbieter-Eigenschaften freigegeben wurden.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: Bericht zur Überschneidung von Eigenschaft zu Eigenschaft
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Bericht zur Überschneidung von Eigenschaft zu Eigenschaft{#trait-to-trait-overlap-report}

Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die für alle Erst- und Drittanbieter-Eigenschaften freigegeben wurden.

>[!NOTE]
>
>Die Überschneidungsberichte in Audience Manager entsprechen den RBAC-Prinzipien. Sie können nur Eigenschaften aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), der Sie angehören.

<!-- 

c_overlap_reports.xml

 -->

## Überblick

Der [!UICONTROL Trait-to-Trait Overlap] Bericht gibt Daten zu den % der eindeutigen Benutzenden zurück, die für alle Ihre eigenen Eigenschaften und die Eigenschaften von Drittanbietern freigegeben sind. Als Optimierungs-Tool hilft Ihnen dieser Bericht bei Folgendem:

* Erstellen Sie je nach Bedarf Segmente mit hoher oder geringer Überschneidung. Eigenschaften mit hoher Überschneidung liefern eine zielgerichtete Zielgruppe, aber weniger Unique Visitors. Eigenschaften mit geringer Überschneidung können nützlich sein, um einen größeren Unique-Visitor-Satz zu erreichen.
* Validieren von Drittanbieter-Eigenschaftendaten: Eine starke Überschneidung zwischen ähnlichen Erst- und Drittanbieter-Eigenschaften deutet darauf hin, dass das Merkmal Ihres Datenpartners genau und vertrauenswürdig ist. Umgekehrt kann eine geringe Überschneidung darauf hinweisen, dass eine Drittanbietereigenschaft möglicherweise nicht dieselben Informationen enthält wie Ihre eigene, ähnliche Erstanbieter-Eigenschaft.
* Finden Sie unerwartete Überschneidungen zwischen Eigenschaften und verwenden Sie diese Informationen zum Erstellen innovativer Segmente.

## Beispielbericht

Die folgende Abbildung bietet einen allgemeinen Überblick über die Elemente im [!UICONTROL Trait-to-Trait Overlap].

>[!NOTE]
>
>Der [!UICONTROL Trait-to-Trait Overlap] gibt ein leeres Feld zurück, wenn dasselbe Merkmal mit sich selbst verglichen wird.

>[!NOTE]
>
>Ordnereigenschaften können nicht in Berichten mit einer Überschneidung von Eigenschaft zu Eigenschaft verglichen werden. Durch Erstellen eines Segments mit einer bestimmten Ordnereigenschaft können Sie eine Analyse über den Bericht [Segment-zu-Eigenschaft-Überschneidung“ ](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md).

![](assets/trait-to-trait-overlap.png)

## Drilldown zu einzelnen Datenpunkten

Wählen Sie einen einzelnen Punkt aus, um Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## POP-Felder für Überschneidungsdaten von Eigenschaft zu Eigenschaft definiert {#field-definitions}

Beschreibt die Metriken, die beim Klicken auf einen einzelnen Datenpunkt im Popup-Fenster angezeigt werden.

<!-- 

r_t2t_data_pop.xml

 -->

Das Popup für den [!UICONTROL Trait-to-Trait Overlap] enthält die folgenden Metriken. Beachten Sie, dass die Metrik Eindeutig in der Tabelle Ihre *Echtzeit-Benutzer* darstellt.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überschneidung %</span></b> </td> 
   <td colname="col2"> Zeigt den Prozentsatz der eindeutigen Überschneidung zwischen verglichenen Eigenschaften (eindeutige Überschneidung/eindeutige Eigenschaften). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Data Source-Typ</span></b> </td> 
   <td colname="col2">Definiert den Typ der Datenquelle, zu der eine Eigenschaft gehört. Kann entweder sein: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Erstanbieter (Ihre eigene Eigenschaft). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Drittanbieter (von einem externen Datenpartner/Anbieter). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> ID der sich überlappenden Eigenschaft</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für die überlappende Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Name der überlappenden Eigenschaft</span></b> </td> 
   <td colname="col2"> Name der sich überschneidenden Eigenschaft. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle">-Merkmal-ID 2</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für das Merkmal in Ihrer Basisdatenquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsname 2</span></b> </td> 
   <td colname="col2"> Name des Merkmals in Ihrer Basisdatenquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überschneidungskennzeichen</span></b> </td> 
   <td colname="col2"> <p>Um die Überschneidung % zu erhalten, verwendet der Audience Manager die folgende Formel:</p> <p>Überlappende eindeutige Werte / (Grundeigenschaft eindeutig + Überlappende Eigenschaftseindeutigkeiten - Überlappende eindeutige Werte)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> sich überschneidende Eigenschaften sind eindeutig</span></b> </td> 
   <td colname="col2"> Die Anzahl der Unique Visitors aus der sich überschneidenden Eigenschaft. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Basiseigenschaft ist eindeutig</span></b> </td> 
   <td colname="col2"> Die Anzahl der Unique Visitors aus der Basiseigenschaft. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
>* [In dynamischen Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Berichtssymbole und Tools - Erklärung](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überlagerungsberichte: Aktualisierungszeitplan und Mindestsegmentgröße](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datenstichproben- und Fehlerquoten in Berichten zu ausgewählten Audience Managern…](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)

---
description: Gibt Daten zur Anzahl der Unique Users zurück, die für alle Ihre Erstanbieter- und Drittanbieter-Eigenschaften freigegeben wurden.
seo-description: Gibt Daten zur Anzahl der Unique Users zurück, die für alle Ihre Erstanbieter- und Drittanbieter-Eigenschaften freigegeben wurden.
seo-title: Überlagerungsbericht zwischen Eigenschaften
solution: Audience Manager
title: Überlagerungsbericht zwischen Eigenschaften
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 8%

---

# Überlagerungsbericht zwischen Eigenschaften{#trait-to-trait-overlap-report}

Gibt Daten zur Anzahl der Unique Users zurück, die für alle Ihre Erstanbieter- und Drittanbieter-Eigenschaften freigegeben wurden.

>[!NOTE]
>
>Die Überschneidungsberichte in Audience Manager folgen den RBAC-Grundsätzen. Sie können nur Eigenschaften aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), der Sie angehören.

<!-- 

c_overlap_reports.xml

 -->

## Überblick

Der [!UICONTROL Trait-to-Trait Overlap]-Bericht gibt Daten zu dem % der Unique Users zurück, die für all Ihre eigenen Eigenschaften und Eigenschaften von Drittanbietern freigegeben wurden. Als Optimierungstool hilft Ihnen dieser Bericht:

* Erstellen Sie Segmente mit hoher oder niedriger Überschneidung, je nach Bedarf. Eigenschaften mit hoher Überschneidung geben Ihnen eine zielgerichtete Audience, aber weniger individuelle Besucher. Eigenschaften mit geringer Überschneidung können nützlich sein, um einen größeren, eindeutigen Besucher zu erreichen.
* Validieren von Drittanbieter-Eigenschaftendaten: Eine starke Überschneidung von ähnlichen Eigenschaften von Erstanbietern und Drittanbietern deutet darauf hin, dass die Eigenschaften Ihres Datenpartners korrekt und vertrauenswürdig sind. Umgekehrt kann eine geringe Überschneidung darauf hindeuten, dass eine Eigenschaft eines Drittanbieters möglicherweise nicht die gleichen Informationen wie Ihre eigene, ähnliche Eigenschaft eines Erstanbieters enthält.
* Finden Sie unerwartete Überschneidungen zwischen Eigenschaften und verwenden Sie diese Informationen, um innovative Segmente zu erstellen.

## Beispielbericht

Die folgende Abbildung zeigt eine allgemeine Übersicht über Elemente im [!UICONTROL Trait-to-Trait Overlap]-Bericht.

>[!NOTE]
>
>Der Bericht [!UICONTROL Trait-to-Trait Overlap] gibt ein leeres Feld zurück, wenn er dieselbe Eigenschaft mit sich selbst vergleicht.

![](assets/trait-to-trait-overlap.png)

## Drilldown für einzelne Datenpunkte

Wählen Sie in einem Popup-Fenster einen individuellen Punkt für die Datendetails der Ansicht aus. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Eigenschaften-zu-Eigenschaften-Überschneidungsfelder für Daten-Pop-Felder definiert {#field-definitions}

Beschreibt die Metriken, die im Popup-Fenster angezeigt werden, wenn Sie auf einen einzelnen Datenpunkt klicken.

<!-- 

r_t2t_data_pop.xml

 -->

Das Popup für den [!UICONTROL Trait-to-Trait Overlap]-Bericht enthält die folgenden Metriken. Beachten Sie, dass die Metrik &quot;Individuelle Werte&quot;in der Tabelle Ihre *Echtzeit-Benutzer* darstellt.

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
   <td colname="col2"> Zeigt die % der eindeutigen Überschneidung zwischen den verglichenen Eigenschaften (Überschneidung von Uniques/Eigenschaften). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Datenquelle-Typ</span></b> </td> 
   <td colname="col2">Definiert den Typ der Datenquelle, zu der ein Merkmal gehört. Kann entweder: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Erstanbieter (eigene Eigenschaft). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Drittanbieter (von einem externen Datenpartner/Anbieter). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überschneidende Eigenschaften-ID</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für die überlappende Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überschneidender Eigenschaftsname</span></b> </td> 
   <td colname="col2"> Name der überlappenden Eigenschaft. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaften-ID 2</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für die Eigenschaft in Ihrer Basisdatenquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsname 2</span></b> </td> 
   <td colname="col2"> Name der Eigenschaft in Ihrer Basisdatenquelle. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Individuelle Überschneidungen</span></b> </td> 
   <td colname="col2"> <p>Um die Überschneidung in % zu erhalten, verwendet Audience Manager die folgende Formel:</p> <p>Überschneidende individuelle Elemente / (Basiseigenschaftsmerkmale + Überschneidende Eigenschaftsmerkmale - Überschneidende individuelle Elemente)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überschneidende Eigenschaften</span></b> </td> 
   <td colname="col2"> Die Anzahl der eindeutigen Besucher aus der überlappenden Eigenschaft. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Basiseigenschaften - Individuelle Werte</span></b> </td> 
   <td colname="col2"> Die Anzahl der eindeutigen Besucher aus der Basiseigenschaft. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
>* [In dynamischen Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Berichtssymbole und -werkzeuge erläutert](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überlagerungsberichte: Aktualisierungszeitplan und Mindestsegmentgröße](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten...](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)


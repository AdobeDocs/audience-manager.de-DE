---
description: Gibt Daten zur Anzahl der Unique Users zurück, die für eine bestimmte Eigenschaft und für ein ganzes Segment freigegeben wurden.
seo-description: Gibt Daten zur Anzahl der Unique Users zurück, die für eine bestimmte Eigenschaft und für ein ganzes Segment freigegeben wurden.
seo-title: Überlagerungsbericht zwischen Segmenten und Eigenschaften
solution: Audience Manager
title: Überlagerungsbericht zwischen Segmenten und Eigenschaften
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Überlagerungsberichte
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 5%

---

# Überlagerungsbericht zwischen Segmenten und Eigenschaften{#segment-to-trait-overlap-report}

Gibt Daten zur Anzahl der Unique Users zurück, die für eine bestimmte Eigenschaft und für ein ganzes Segment freigegeben wurden.

>[!NOTE]
>
>Die Überlagerungsberichte in Audience Manager folgen den RBAC-Grundsätzen. Sie können nur Segmente und Eigenschaften aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), zu der Sie gehören.

<!-- 

c_segment_trait_overlap.xml

 -->

## Überblick

Als Optimierungstool helfen Ihnen die [!UICONTROL Segment to Trait Overlap]-Berichte beim Erstellen hochgradig fokussierter Segmente oder beim Erweitern der Segmentreichweite. Sie können beispielsweise fokussierte Segmente und Eigenschaften mit hoher Überschneidung erstellen, um eine bestimmte Zielgruppe zu erreichen. Eine große Überschneidung kann jedoch weniger Unique Users (weniger Reichweite) bedeuten. Ausführen dieses Berichts, um die Reichweite zu erweitern, indem Eigenschaften mit vielen Segmentüberschneidungen entfernt und durch Eigenschaften mit geringerer Überschneidung ersetzt werden.

### Beispielbericht

Die folgende Abbildung bietet einen allgemeinen Überblick über den Bericht [!UICONTROL Segment-to-Trait Overlap].

![](assets/segment-to-trait-overlap.png)

### Drilldown für einzelne Datenpunkte

Wählen Sie einen einzelnen Punkt aus, um die Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Vergleichen von Segmenten mit Eigenschaften {#comparing-segments-to-traits}

Beschreibt, wie Sie Segmente und Eigenschaften vergleichen können, um aussagekräftige Informationen aus den Ergebnissen abzuleiten.

<!-- 

c_compare_s2t.xml

 -->

### Vergleich von Eigenschafts- und Segmentindividuellen: Beispiel

Auf den ersten Blick mag es unlogisch erscheinen, Segmente mit Eigenschaften zu vergleichen und zu versuchen, Schlussfolgerungen aus den Ergebnissen zu ziehen. Schließlich sind Segmente und Eigenschaften unterschiedlich. Wie können also aus unterschiedlichen Elementen abgeleitete Daten eine Bedeutung haben? In diesem Fall vergleichen wir jedoch nicht Eigenschaften und Segmente, sondern die Anzahl der Unique Visitors, die zwischen ihnen geteilt werden. Die Anzahl der freigegebenen Unique Visitors bietet den gemeinsamen Wert, der einen Vergleich zwischen Segmenten und Eigenschaften ermöglicht.

Das folgende Diagramm zeigt die Beziehung zwischen einer Eigenschaft und dem Segment, zu dem sie gehört. In diesem Fall haben wir eine Eigenschaft mit 10 Besuchern und ein Segment mit 1.000 Besuchern. Sie teilen 3 Unique Visitors gemeinsam.

![](assets/s2t.png)

Die Unique Visitor-Anzahl ist der gemeinsame konstante Wert, der von diesen verschiedenen Objektklassen gemeinsam verwendet wird. Daher können Sie die Unique Visitor-Beziehung zwischen ihnen wie folgt ermitteln:

* Die Eigenschaft teilt 30 % ihrer Unique Visitors mit dem Segment (3/10 = 0,30).
* Das Segment teilt 0,3 % seiner Unique Visitors mit der Eigenschaft (3/1.000 = 0.003)

### Wert in Segment- zu Eigenschaftenvergleichen suchen

Wenn Sie sich die Überschneidung zwischen Eigenschaften und Segmenten ansehen, können Sie den gesamten verfügbaren Besucherpool (Prognose) schätzen oder ineffiziente Segmente mit zu großer Überschneidung finden.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Anwendungsfall </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Prognosen</b> </td> 
   <td colname="col2"> <p>Um den verfügbaren Besucherpool zu ermitteln, summieren Sie die Differenz zwischen der Eigenschaftensumme (weniger Überschneidungen) und der Segmentsumme (weniger Überschneidungen). </p> <p>Diese Kombination aus Segmenteigenschaften könnte bis zu 1004 neue Benutzer erreichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ineffiziente Segmente suchen</b> </td> 
   <td colname="col2"> <p>Wenn eine Eigenschaft Teil einer <span class="wintitle"> UND</span> -Gruppe in einer Segmentdefinition ist, befinden sich die Unique Visitors, die diese Eigenschaft aufweisen, bereits im Segment und können dem Segment nicht hinzugefügt werden. Sie können diesen Bericht verwenden, um relevante Eigenschaften mit geringer Überschneidung zu finden und sie zur Segmentdefinition hinzuzufügen, wodurch die Reichweite dieses Segment-Zielgruppenpools erhöht wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Grundlegendes zu den Datenfiltern im Überlagerungsbericht zwischen Segmenten und Eigenschaften {#data-filters-s2t-report}

Beschreibt, wie die Regler für die Eigenschaften und die Segmenteindeutigen Überschneidungen % funktionieren.

<!-- 

r_s2t_sliders.xml

 -->

Mit dem Bericht [!UICONTROL Segment-to-Trait overlap] können Sie zwei Schieberegler verwenden, um Daten nach der Überschneidung % nach Eigenschaft oder Segment zu filtern.

* **[!UICONTROL Filter Trait Uniques %:]** Filtert Daten nach dem Prozentsatz der Unique Visitors, die zwischen der Eigenschaft und dem Segment freigegeben wurden.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtert Daten nach dem Prozentsatz der Unique Visitors, die zwischen dem Segment und der Eigenschaft gemeinsam verwendet werden.

### Beispiel

Die folgende Abbildung zeigt den Unterschied zwischen den eindeutigen % der Eigenschaft und den eindeutigen % des Segments. In diesem Fall teilen sich die Eigenschaften und Segmente 3 Unique Visitors. Proportionen:

* Die Eigenschaft teilt 30 % ihrer Unique Visitors mit dem Segment (3/10 = 0,30).
* Das Segment teilt 0,3 % seiner Unique Visitors mit der Eigenschaft (3/1.000 = 0.003)

![](assets/s2t.png)

## Definierte Datenpop-Felder für Segment-zu-Merkmal {#fields-defined}

Beschreibt die Metriken, die im Popup-Fenster angezeigt werden, wenn Sie auf einen einzelnen Datenpunkt klicken.

<!-- 

r_s2t_data_pop.xml

 -->

Das Popup-Fenster für den Bericht [!UICONTROL Segment-to-Trait Overlap] enthält die folgenden Metriken. Beachten Sie, dass die eindeutige Metrik in der Tabelle Ihre *Echtzeitbenutzer* darstellt.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segment-ID</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für das Segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsdatenquelle  </span></b> </td> 
   <td colname="col2"> Name des Eigenschaftseigentümers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Datenquellentyp</span></b> </td> 
   <td colname="col2">Definiert den Typ des Anbieters, zu dem eine Eigenschaft gehört. Kann Folgendes sein: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Erstanbieter (Ihre eigene Eigenschaft). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Drittanbieter (von einem externen Datenpartner/Anbieter). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschafts-ID</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für die Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsname</span></b> </td> 
   <td colname="col2"> Name der Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überlagerung einzelner Eigenschaften %</span></b> </td> 
   <td colname="col2"> % der Unique Visitors, die eine Eigenschaft mit dem Segment teilt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmentüberlagerung %</span></b> </td> 
   <td colname="col2"> % der Unique Visitors, die ein Segment mit einer Eigenschaft teilt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Unique Overlap</span></b> </td> 
   <td colname="col2"> Anzahl der Unique Visitors, die zwischen dem Segment und der Eigenschaft freigegeben wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eindeutige Segmente</span></b> </td> 
   <td colname="col2"> Anzahl der Unique Visitors im Segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eindeutige Eigenschaften</span></b> </td> 
   <td colname="col2"> Anzahl der Unique Visitors in der Eigenschaft. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
* [In interaktiven Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
* [Berichtssymbole und -werkzeuge - Erklärung](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
* [Überlagerungsberichte: Aktualisierungszeitplan und Mindestsegmentgröße](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
* [Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten...](../../reporting/report-sampling.md)
* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)


---
description: Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die eine bestimmte Eigenschaft und ein ganzes Segment gemeinsam haben.
seo-description: Returns data on the number of unique users shared between a particular trait and an entire segment.
seo-title: Segment-to-Trait Overlap Report
solution: Audience Manager
title: Bericht zur Segment-zu-Merkmal-Überschneidung
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%

---

# Bericht zur Segment-zu-Merkmal-Überschneidung{#segment-to-trait-overlap-report}

Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die eine bestimmte Eigenschaft und ein ganzes Segment gemeinsam haben.

>[!NOTE]
>
>Die Überschneidungsberichte in Audience Manager entsprechen den RBAC-Prinzipien. Sie können nur Segmente und Eigenschaften aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), der Sie angehören.

<!-- 

c_segment_trait_overlap.xml

 -->

## Überblick

Als Optimierungs-Tool können Sie mit den [!UICONTROL Segment to Trait Overlap]-Berichten hochfokussierte Segmente erstellen oder die Segmentreichweite erweitern. Sie können beispielsweise zielgerichtete Segmente und Eigenschaften mit hoher Überschneidung erstellen, um eine bestimmte Zielgruppe zu erreichen. Viele Überschneidungen führen jedoch möglicherweise zu weniger Unique Users (geringerer Reichweite). Die Ausführung dieses Berichts hilft Ihnen, die Reichweite zu erweitern, indem Sie Eigenschaften mit vielen Segmentüberschneidungen entfernen und sie durch Eigenschaften ersetzen, die weniger Überschneidungen aufweisen.

### Beispielbericht

Die folgende Abbildung bietet einen allgemeinen Überblick über den [!UICONTROL Segment-to-Trait Overlap].

![](assets/segment-to-trait-overlap.png)

### Drilldown zu einzelnen Datenpunkten

Wählen Sie einen einzelnen Punkt aus, um Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Vergleichen von Segmenten mit Eigenschaften {#comparing-segments-to-traits}

Beschreibt, wie Sie Segmente und Eigenschaften vergleichen können, um aussagekräftige Informationen aus den Ergebnissen abzuleiten.

<!-- 

c_compare_s2t.xml

 -->

### Vergleich von Eigenschafts- und Segmenteindeutigkeiten: Beispiel

Auf den ersten Blick mag es unlogisch erscheinen, Segmente mit Eigenschaften zu vergleichen und zu versuchen, Schlussfolgerungen aus den Ergebnissen zu ziehen. Schließlich sind Segmente und Eigenschaften unterschiedlich, wie können also aus unterschiedlichen Elementen abgeleitete Daten eine Bedeutung haben? In diesem Fall vergleichen wir jedoch nicht Eigenschaften und Segmente, sondern die Anzahl der Unique Visitors, die zwischen ihnen freigegeben werden. Die Anzahl freigegebener Unique Visitors stellt den allgemeinen Wert bereit, der einen Vergleich von Segmenten mit Merkmalen ermöglicht.

Das folgende Diagramm veranschaulicht die Beziehung zwischen einer Eigenschaft und dem Segment, zu dem sie gehört. In diesem Fall haben wir eine Eigenschaft mit 10 Besuchern und ein Segment mit 1.000 Besuchern. Sie teilen sich drei Unique Visitors.

![](assets/s2t.png)

Die Anzahl der Unique Visitors ist der gemeinsame, konstante Wert, der von diesen verschiedenen Objektklassen gemeinsam verwendet wird. Daher können Sie die Unique-Visitor-Beziehung zwischen ihnen wie folgt ermitteln:

* Die Eigenschaft teilt 30 % ihrer Unique Visitors mit dem Segment (3/10 = 0,30).
* Das Segment nutzt 0,3 % seiner Unique Visitors gemeinsam mit der Eigenschaft (3/1.000 = 0,003)

### Suchen von Werten in Segmentvergleichen zu Eigenschaften

Die Untersuchung der Überschneidung zwischen Eigenschaften und Segmenten kann Ihnen dabei helfen, den insgesamt verfügbaren Besucherpool zu schätzen (Prognose) oder ineffiziente Segmente mit zu großen Überschneidungen zu finden.

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
   <td colname="col2"> <p>Um den verfügbaren Besucherpool zu ermitteln, addieren Sie die Differenz zwischen der Eigenschaftssumme (weniger Überschneidungen) und der Segmentsumme (weniger Überschneidungen). </p> <p>Diese Segment-Trait-Kombination könnte bis zu 1004 neue Benutzende erreichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ineffiziente Segmente suchen</b> </td> 
   <td colname="col2"> <p>Wenn eine Eigenschaft Teil einer <span class="wintitle"> AND</span>-Gruppe in einer Segmentdefinition ist, sind die Unique Visitors, die diese Eigenschaft haben, bereits im Segment und nicht zum Hinzufügen zum Segment verfügbar. Sie können diesen Bericht verwenden, um relevante Eigenschaften mit geringer Überschneidung zu finden und sie zur Segmentdefinition hinzuzufügen, wodurch die Reichweite dieses Segmentzielgruppen-Pools erhöht wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Grundlegendes zu den Datenfiltern im Bericht „Segment-zu-Eigenschaft-Überschneidung“ {#data-filters-s2t-report}

Beschreibt, wie die Schieberegler für die eindeutige Überschneidung von Eigenschaften und Segmenten % funktionieren.

<!-- 

r_s2t_sliders.xml

 -->

Mit dem [!UICONTROL Segment-to-Trait overlap] Bericht können Sie zwei Schieberegler verwenden, um Daten nach der Überschneidung % nach Eigenschaft oder Segment zu filtern.

* **[!UICONTROL Filter Trait Uniques %:]** Filtert Daten nach dem Prozentsatz der Unique Visitors, die zwischen der Eigenschaft und dem Segment geteilt werden.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtert Daten nach dem Prozentsatz der Unique Visitors, die das Segment und die Eigenschaft gemeinsam haben.

### Beispiel

Das folgende Diagramm veranschaulicht den Unterschied zwischen den eindeutigen Eigenschaften % und den eindeutigen Segmentwerten %. In diesem Fall haben das Merkmal und das Segment 3 Unique Visitors gemeinsam. Als Proportionen:

* Die Eigenschaft teilt 30 % ihrer Unique Visitors mit dem Segment (3/10 = 0,30).
* Das Segment nutzt 0,3 % seiner Unique Visitors gemeinsam mit der Eigenschaft (3/1.000 = 0,003)

![](assets/s2t.png)

## POP-Felder für Segment-zu-Eigenschaft definiert {#fields-defined}

Beschreibt die Metriken, die beim Klicken auf einen einzelnen Datenpunkt im Popup-Fenster angezeigt werden.

<!-- 

r_s2t_data_pop.xml

 -->

Das Popup für den [!UICONTROL Segment-to-Trait Overlap] enthält die folgenden Metriken. Beachten Sie, dass die Metrik Eindeutig in der Tabelle Ihre *Echtzeit-Benutzer* darstellt.

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
   <td colname="col1"><b><span class="wintitle">-Eigenschaftsdaten - Source </span></b> </td> 
   <td colname="col2"> Name des Eigentümers der Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Data Source-Typ</span></b> </td> 
   <td colname="col2">Definiert den Typ des Anbieters, zu dem eine Eigenschaft gehört. Kann entweder sein: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Erstanbieter (Ihre eigene Eigenschaft). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Drittanbieter (von einem externen Datenpartner/Anbieter). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle">-ID</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für die Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsname</span></b> </td> 
   <td colname="col2"> Name des Merkmals. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Eindeutige <b><span class="wintitle">-Eigenschaften überschneiden sich %</span></b> </td> 
   <td colname="col2"> % der Unique Visitors, die eine Eigenschaft mit dem Segment teilt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> eindeutige Segmentüberschneidungen %</span></b> </td> 
   <td colname="col2"> % der Unique Visitors, die ein Segment mit einer Eigenschaft teilt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überschneidungskennzeichen</span></b> </td> 
   <td colname="col2"> Anzahl der Unique Visitors, die zwischen dem Segment und der Eigenschaft geteilt werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segment ist eindeutig</span></b> </td> 
   <td colname="col2"> Anzahl der Unique Visitors im Segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaft ist einzigartig</span></b> </td> 
   <td colname="col2"> Anzahl der Unique Visitors im Trait. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
>* [In interaktiven Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Berichtssymbole und Tools - Erklärung](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überlagerungsberichte: Aktualisierungszeitplan und Mindestsegmentgröße](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datenstichproben- und Fehlerquoten in ausgewählten Audience Manager-Berichten…](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)

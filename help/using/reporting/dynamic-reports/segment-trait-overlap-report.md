---
description: Gibt Daten zur Anzahl der Unique Users zurück, die zwischen einer bestimmten Eigenschaft und einem ganzen Segment freigegeben wurden.
seo-description: Gibt Daten zur Anzahl der Unique Users zurück, die zwischen einer bestimmten Eigenschaft und einem ganzen Segment freigegeben wurden.
seo-title: Überlagerungsbericht zwischen Segmenten und Eigenschaften
solution: Audience Manager
title: Überlagerungsbericht zwischen Segmenten und Eigenschaften
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 5%

---


# Überlagerungsbericht zwischen Segmenten und Eigenschaften{#segment-to-trait-overlap-report}

Gibt Daten zur Anzahl der Unique Users zurück, die zwischen einer bestimmten Eigenschaft und einem ganzen Segment freigegeben wurden.

>[!NOTE]
>
>Die Überschneidungsberichte in Audience Manager folgen den RBAC-Grundsätzen. Sie können nur Segmente und Eigenschaften aus Datenquellen anzeigen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), zu der Sie gehören.

<!-- 

c_segment_trait_overlap.xml

 -->

## Überblick

Als Optimierungstool unterstützen Sie die [!UICONTROL Segment to Trait Overlap]-Berichte beim Erstellen hochgradig fokussierter Segmente oder beim Erweitern der Segmentreichweite. Sie können beispielsweise fokussierte Segmente und Eigenschaften mit hoher Überschneidung erstellen, um eine bestimmte Audience zu erreichen. Eine große Überschneidung kann jedoch weniger Unique Users bedeuten (weniger Reichweite). Ausführen dieses Berichts, um die Reichweite zu vergrößern, indem Eigenschaften mit einer großen Segmentüberschneidung entfernt und durch Eigenschaften ersetzt werden, die weniger überlappen.

### Beispielbericht

In der folgenden Abbildung wird ein Überblick über den [!UICONTROL Segment-to-Trait Overlap]-Bericht auf hoher Ebene gegeben.

![](assets/segment-to-trait-overlap.png)

### Drilldown für einzelne Datenpunkte

Wählen Sie in einem Popup-Fenster einen individuellen Punkt für die Datendetails der Ansicht aus. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Vergleichen von Segmenten mit Eigenschaften {#comparing-segments-to-traits}

Beschreibt, wie Sie Segmente und Eigenschaften vergleichen können, um aussagekräftige Informationen aus den Ergebnissen abzuleiten.

<!-- 

c_compare_s2t.xml

 -->

### Vergleich von Eigenschaften- und Segmentindividualitäten: Beispiel

Auf den ersten Blick mag es unlogisch erscheinen, Segmente mit Eigenschaften zu vergleichen und zu versuchen, Schlussfolgerungen aus den Ergebnissen zu ziehen. Schließlich sind Segmente und Eigenschaften unterschiedlich. Wie können also aus unterschiedlichen Elementen abgeleitete Daten eine Bedeutung haben? In diesem Fall vergleichen wir jedoch nicht Eigenschaften und Segmente, sondern die Anzahl der individuellen Besucher, die zwischen ihnen geteilt werden. Die Anzahl der freigegebenen eindeutigen Besucher stellt den gemeinsamen Wert bereit, der einen Segmentvergleich möglich macht.

Das folgende Diagramm zeigt die Beziehung zwischen einer Eigenschaft und dem Segment, zu dem sie gehört. In diesem Fall haben wir eine Eigenschaft mit 10 Besuchern und ein Segment mit 1.000 Besuchern. Sie haben drei gemeinsame Besucher.

![](assets/s2t.png)

Die Anzahl der eindeutigen Besucher ist der gemeinsame konstante Wert, der zwischen diesen verschiedenen Objektklassen verwendet wird. Daher können Sie die Beziehung zwischen ihnen zu individuellen Besuchern wie folgt ermitteln:

* Die Eigenschaft teilt 30 % ihrer individuellen Besucher mit dem Segment (3/10 = 0,30).
* Das Segment teilt 0,3 % seiner individuellen Besucher mit der Eigenschaft (3/1.000 = 0.003)

### Wert im Segment als Eigenschaftsvergleich suchen

Wenn Sie sich die Überschneidung zwischen Eigenschaften und Segmenten ansehen, können Sie den gesamten verfügbaren Besucher-Pool (Prognose) abschätzen oder ineffiziente Segmente mit zu großer Überschneidung finden.

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
   <td colname="col2"> <p>Um den verfügbaren Segmentpool zu ermitteln, summieren Sie die Differenz zwischen der Eigenschaftssumme (ohne Überschneidung) und der Segmentsumme (ohne Überschneidung). </p> <p>Diese Kombination aus Segmenteigenschaften könnte bis zu 1004 neue Benutzer erreichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ineffiziente Segmente suchen</b> </td> 
   <td colname="col2"> <p>Wenn eine Eigenschaft in einer Segmentdefinition zu einer Gruppe <span class="wintitle"> UND</span> gehört, befinden sich die eindeutigen Besucher mit dieser Eigenschaft bereits im Segment und können dem Segment nicht hinzugefügt werden. Sie können diesen Bericht verwenden, um relevante Eigenschaften mit geringer Überschneidung zu finden und sie zur Segmentdefinition hinzuzufügen, wodurch die Reichweite des Segmentpools für die Audience erhöht wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Die Filter der Daten im Bericht &quot;Segment-zu-Eigenschaften-Überschneidung {#data-filters-s2t-report}&quot;

Beschreibt, wie die eindeutigen Überschneidungsregler für Eigenschaften und Segmente funktionieren.

<!-- 

r_s2t_sliders.xml

 -->

Mit dem Bericht [!UICONTROL Segment-to-Trait overlap] können Sie zwei Schieberegler verwenden, um Daten nach Überschneidung % nach Eigenschaft oder Segment zu filtern.

* **[!UICONTROL Filter Trait Uniques %:]** Daten zu Filtern nach % der eindeutigen Besucher, die zwischen der Eigenschaft und dem Segment freigegeben wurden.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Daten zu Filtern nach dem Prozentsatz der Unique Besuchers, die zwischen dem Segment und der Eigenschaft gemeinsam genutzt werden.

### Beispiel

Die folgende Abbildung zeigt die Differenz zwischen den individuellen Eigenschaften % und dem Segment %. In diesem Fall weisen die Eigenschaften und Segmente 3 eindeutige Besucher auf. Proportionen:

* Die Eigenschaft teilt 30 % ihrer individuellen Besucher mit dem Segment (3/10 = 0,30).
* Das Segment teilt 0,3 % seiner individuellen Besucher mit der Eigenschaft (3/1.000 = 0.003)

![](assets/s2t.png)

## Datenpop-Felder für Segment-zu-Eigenschaften definiert {#fields-defined}

Beschreibt die Metriken, die im Popup-Fenster angezeigt werden, wenn Sie auf einen einzelnen Datenpunkt klicken.

<!-- 

r_s2t_data_pop.xml

 -->

Das Popup für den [!UICONTROL Segment-to-Trait Overlap]-Bericht enthält die folgenden Metriken. Beachten Sie, dass die Metrik &quot;Individuelle Werte&quot;in der Tabelle Ihre *Echtzeit-Benutzer* darstellt.

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
   <td colname="col2"> Name des Eigenschafteninhabers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Datenquelle-Typ</span></b> </td> 
   <td colname="col2">Definiert den Provider-Typ, zu dem eine Eigenschaft gehört. Kann entweder: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Erstanbieter (eigene Eigenschaft). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Drittanbieter (von einem externen Datenpartner/Anbieter). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaften-ID</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für die Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsname</span></b> </td> 
   <td colname="col2"> Name der Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschafts-Überschneidung %</span></b> </td> 
   <td colname="col2"> % der individuellen Besucher, die eine Eigenschaft mit dem Segment teilt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmentspezifische Überschneidung %</span></b> </td> 
   <td colname="col2"> % der individuellen Besucher, die ein Segment mit einer Eigenschaft teilt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Individuelle Überschneidungen</span></b> </td> 
   <td colname="col2"> Anzahl der eindeutigen Besucher, die für das Segment und die Eigenschaft freigegeben wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmentindividualisierung</span></b> </td> 
   <td colname="col2"> Anzahl der eindeutigen Besucher im Segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsvariablen</span></b> </td> 
   <td colname="col2"> Anzahl der eindeutigen Besucher in der Eigenschaft. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
>* [In interaktiven Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Berichtssymbole und -werkzeuge erläutert](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überlagerungsberichte: Aktualisierungszeitplan und Mindestsegmentgröße](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten...](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)
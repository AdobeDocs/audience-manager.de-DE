---
description: Gibt Daten zur Anzahl der Unique Users zurück, die zwischen einer bestimmten Eigenschaft und einem ganzen Segment freigegeben wurden.
seo-description: Gibt Daten zur Anzahl der Unique Users zurück, die zwischen einer bestimmten Eigenschaft und einem ganzen Segment freigegeben wurden.
seo-title: Überschneidungsbericht zwischen Segmenten und Eigenschaften
solution: Audience Manager
title: Überschneidungsbericht zwischen Segmenten und Eigenschaften
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Überschneidungsbericht zwischen Segmenten und Eigenschaften{#segment-to-trait-overlap-report}

Gibt Daten zur Anzahl der Unique Users zurück, die zwischen einer bestimmten Eigenschaft und einem ganzen Segment freigegeben wurden.

>[!NOTE]
>
>Die Überschneidungsberichte in Audience Manager folgen den RBAC-Grundsätzen. Sie können nur Segmente und Eigenschaften aus Datenquellen anzeigen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md) , der Sie angehören.

<!-- 

c_segment_trait_overlap.xml

 -->

## Überblick

Als Optimierungstool unterstützen Sie die [!UICONTROL Segment to Trait Overlap] Berichte bei der Erstellung hochgradig fokussierter Segmente oder der Erweiterung der Segmentreichweite. Sie können beispielsweise fokussierte Segmente und Eigenschaften mit hoher Überschneidung erstellen, um eine bestimmte Zielgruppe zu erreichen. Eine große Überschneidung kann jedoch weniger Unique Users bedeuten (weniger Reichweite). Ausführen dieses Berichts, um die Reichweite zu vergrößern, indem Eigenschaften mit einer großen Segmentüberschneidung entfernt und durch Eigenschaften ersetzt werden, die weniger überlappen.

### Beispielbericht

Die folgende Abbildung zeigt einen Überblick über den [!UICONTROL Segment-to-Trait Overlap] Bericht auf hoher Ebene.

![](assets/segment-to-trait-overlap.png)

### Drilldown für einzelne Datenpunkte

Wählen Sie einen einzelnen Punkt aus, um die Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Segmente mit Eigenschaften vergleichen {#comparing-segments-to-traits}

Beschreibt, wie Sie Segmente und Eigenschaften vergleichen können, um aussagekräftige Informationen aus den Ergebnissen abzuleiten.

<!-- 

c_compare_s2t.xml

 -->

### Vergleich von Eigenschaften- und Segmentindividualitäten: Beispiel

Auf den ersten Blick mag es unlogisch erscheinen, Segmente mit Eigenschaften zu vergleichen und zu versuchen, Schlussfolgerungen aus den Ergebnissen zu ziehen. Schließlich sind Segmente und Eigenschaften unterschiedlich. Wie können also aus unterschiedlichen Elementen abgeleitete Daten eine Bedeutung haben? In diesem Fall vergleichen wir jedoch nicht Eigenschaften und Segmente, sondern die Anzahl der Unique Visitors, die zwischen ihnen geteilt werden. Die Anzahl freigegebener individueller Besucher stellt den gemeinsamen Wert bereit, der einen Vergleich der Eigenschaften eines Segments ermöglicht.

Das folgende Diagramm zeigt die Beziehung zwischen einer Eigenschaft und dem Segment, zu dem sie gehört. In diesem Fall haben wir eine Eigenschaft mit 10 Besuchern und ein Segment mit 1.000 Besuchern. Sie teilen 3 individuelle Besucher gemeinsam.

![](assets/s2t.png)

Die Unique Visitor-Anzahl ist der gemeinsame, konstante Wert, der zwischen diesen verschiedenen Objektklassen geteilt wird. Daher können Sie die individuelle Besucherbeziehung zwischen ihnen wie folgt ermitteln:

* Die Eigenschaft teilt 30 % ihrer Unique Visitors mit dem Segment (3/10 = 0,30).
* Das Segment teilt 0,3 % seiner Unique Visitors mit der Eigenschaft (3/1.000 = 0.003)

### Wert im Segment als Eigenschaftsvergleich suchen

Wenn Sie sich die Überschneidung zwischen Eigenschaften und Segmenten ansehen, können Sie den gesamten verfügbaren Besucherpool (Prognose) abschätzen oder ineffiziente Segmente mit zu großer Überschneidung finden.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nutzungsszenario </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Prognosen</b> </td> 
   <td colname="col2"> <p>Um den verfügbaren Besucherpool zu ermitteln, summieren Sie die Differenz zwischen der Eigenschaftensumme (weniger Überschneidung) und der Segmentsumme (weniger Überschneidung). </p> <p>Diese Kombination aus Segmenteigenschaften könnte bis zu 1004 neue Benutzer erreichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ineffiziente Segmente suchen</b> </td> 
   <td colname="col2"> <p>Wenn eine Eigenschaft Teil einer <span class="wintitle"> UND</span> -Gruppe in einer Segmentdefinition ist, befinden sich die Unique Visitors mit dieser Eigenschaft bereits im Segment und können dem Segment nicht hinzugefügt werden. Sie können diesen Bericht verwenden, um relevante Eigenschaften mit geringer Überschneidung zu finden und sie der Segmentdefinition hinzuzufügen, wodurch die Reichweite des Segmentzielgruppenpools erhöht wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Die Datenfilter im Bericht "Segment-zu-Eigenschaften-Überschneidung" {#data-filters-s2t-report}

Beschreibt, wie die eindeutigen Überschneidungsregler für Eigenschaften und Segmente funktionieren.

<!-- 

r_s2t_sliders.xml

 -->

Mit dem [!UICONTROL Segment-to-Trait overlap] Bericht können Sie zwei Schieberegler verwenden, um Daten nach der Überschneidung % nach Eigenschaften oder Segment zu filtern.

* **[!UICONTROL Filter Trait Uniques %:]** Filtert Daten nach dem Prozentsatz der Unique Visitors, die zwischen der Eigenschaft und dem Segment freigegeben wurden.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtert Daten nach dem Prozentsatz der Unique Visitors, die zwischen dem Segment und der Eigenschaft gemeinsam verwendet werden.

### Beispiel 

Die folgende Abbildung zeigt die Differenz zwischen den individuellen Eigenschaften % und dem Segment %. In diesem Fall weisen Eigenschaften und Segmente 3 individuelle Besucher auf. Proportionen:

* Die Eigenschaft teilt 30 % ihrer Unique Visitors mit dem Segment (3/10 = 0,30).
* Das Segment teilt 0,3 % seiner Unique Visitors mit der Eigenschaft (3/1.000 = 0.003)

![](assets/s2t.png)

## Zu Eigenart definierte Felder für Daten-Popupfelder {#fields-defined}

Beschreibt die Metriken, die beim Klicken auf einen einzelnen Datenpunkt im Popup-Fenster angezeigt werden.

<!-- 

r_s2t_data_pop.xml

 -->

Das Popup für den [!UICONTROL Segment-to-Trait Overlap] Bericht enthält die folgenden Metriken. Beachten Sie, dass die Metrik "Individuelle Werte"in der Tabelle Ihre *Echtzeit-Benutzer* darstellt.

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
   <td colname="col1"><b><span class="wintitle"> Name des Datenanbieters</span></b> </td> 
   <td colname="col2"> Name des Segmenteigentümers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Datenanbietertyp</span></b> </td> 
   <td colname="col2">Definiert den Provider-Typ, zu dem eine Eigenschaft gehört. Kann entweder: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Erstanbieter (eigene Eigenschaft). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Drittanbieter (von einem externen Datenpartner/Anbieter). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SID</span></b> </td> 
   <td colname="col2"> Eindeutige numerische ID für das Segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SID-Name</span></b> </td> 
   <td colname="col2"> Name des Segments. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaftsüberschneidung %</span></b> </td> 
   <td colname="col2"> % der Unique Visitors, die eine Eigenschaft mit dem Segment teilen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmentspezifische Überschneidung %</span></b> </td> 
   <td colname="col2"> % der Unique Visitors teilen ein Segment mit einer Eigenschaft. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Individuelle Überschneidungen</span></b> </td> 
   <td colname="col2"> Anzahl der Unique Visitors, die für das Segment und die Eigenschaft freigegeben wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmentspezifische</span></b> </td> 
   <td colname="col2"> Anzahl der individuellen Besucher im Segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Eigenschaften</span></b> </td> 
   <td colname="col2"> Anzahl der individuellen Besucher in der Eigenschaft. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtern von Berichtsergebnissen mit den Datenreglern](../../reporting/dynamic-reports/data-sliders.md)
>* [In interaktiven Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Berichtssymbole und -werkzeuge erläutert](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überschneidungsberichte: Zeitplan und Mindestsegmentgröße aktualisieren](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datenstichproben und Fehlerquoten in ausgewählten Audience Manager-Berichten...](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlagerungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)
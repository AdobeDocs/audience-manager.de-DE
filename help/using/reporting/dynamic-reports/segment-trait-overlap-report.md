---
description: Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die zwischen einer bestimmten Eigenschaft und einem ganzen Segment freigegeben wurden.
seo-description: Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die zwischen einer bestimmten Eigenschaft und einem ganzen Segment freigegeben wurden.
seo-title: Überschneidungsbericht zwischen Segmenten und Eigenschaften
solution: Audience Manager
title: Überschneidungsbericht zwischen Segmenten und Eigenschaften
uuid: a 6 b 3 dd 21-332 e -449 f-aa 1-2 beb 47 f 1794 e
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Überschneidungsbericht zwischen Segmenten und Eigenschaften{#segment-to-trait-overlap-report}

Gibt Daten zur Anzahl der eindeutigen Benutzer zurück, die zwischen einer bestimmten Eigenschaft und einem ganzen Segment freigegeben wurden.

>[!NOTE]
>
>Die Überlappungsberichte in Audience Manager berücksichtigen RBAC-Prinzipien. Sie können nur Segmente und Eigenschaften aus Datenquellen anzeigen, auf die Sie auf Basis der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md) zugreifen können, zu der Sie gehören.

<!-- 

c_segment_trait_overlap.xml

 -->

## Überblick

Als Optimierungswerkzeug können Sie mit den [!UICONTROL Segment to Trait Overlap] Berichten besonders fokussierte Segmente erstellen oder die Segmentreichweite erweitern. Sie können beispielsweise fokussierte Segmente und Eigenschaften mit hoher Überlappung erstellen, um eine bestimmte Zielgruppe zu erreichen. Viele Überlappungen bedeuten jedoch möglicherweise weniger individuelle Benutzer (weniger Reichweite). Ausführen des Berichts zur Erweiterung der Reichweite durch Entfernen von Eigenschaften mit vielen Segmenten überlappen und durch Eigenschaften ersetzen, die weniger Überlappung aufweisen.

### Beispielbericht

Die folgende Abbildung zeigt einen Überblick über den [!UICONTROL Segment-to-Trait Overlap] Bericht.

![](assets/segment-to-trait-overlap.png)

### Drilldown für einzelne Datenpunkte

Wählen Sie einen einzelnen Punkt aus, um die Datendetails in einem Popup-Fenster anzuzeigen. Durch Ihre Klickaktionen werden die im Bericht angezeigten Daten automatisch aktualisiert.

## Vergleichen von Segmenten mit Eigenschaften {#comparing-segments-to-traits}

Beschreibt, wie Sie Segmente und Eigenschaften vergleichen können, um aussagekräftige Informationen aus den Ergebnissen abzuleiten.

<!-- 

c_compare_s2t.xml

 -->

### Vergleich von Eigenschaften und Segmentindividuellen Segmenten: Ein Beispiel

Auf den ersten Blick scheint es unlogisch, Segmente mit Eigenschaften zu vergleichen und zu versuchen, Schlüsse aus den Ergebnissen zu ziehen. Nach allen sind Segmente und Eigenschaften unterschiedlich. Wie können aus unterschiedlichen Elementen abgeleitete Daten also wirklich Bedeutung haben? In diesem Fall vergleichen wir jedoch keine Eigenschaften und Segmente, sondern die Anzahl der individuellen Besucher, die zwischen ihnen gezählt werden. Die Anzahl der geteilten Unique Visitor bietet den gemeinsamen Wert, der ein Segment zum Vergleich von Eigenschaften macht.

Das folgende Diagramm zeigt die Beziehung zwischen einer Eigenschaft und dem Segment, zu dem sie gehört. In diesem Fall haben wir eine Eigenschaft mit 10 Besuchern und ein Segment mit 1.000 Besuchern. Sie teilen 3 Unique Visitors gemeinsam.

![](assets/s2t.png)

Die Unique Visitor-Anzahl ist der allgemeine, konstante Wert, der zwischen diesen verschiedenen Objektklassen freigegeben wird. Daher können Sie die Unique Visitor-Beziehung wie folgt bestimmen:

* Die Eigenschaft hat 30% der individuellen Besucher mit dem Segment (3/10 = 0,30).
* Das Segment teilt 0,3% seiner individuellen Besucher mit der Eigenschaft (3/1.000 = 0.003).

### Wert in Segment zu Eigenschaftsvergleichen suchen

Die Betrachtung der Überlappung zwischen Eigenschaften und Segmenten kann Ihnen dabei helfen, den gesamten verfügbaren Besucherpool (Prognosen) zu schätzen oder ineffiziente Segmente mit zu viel Überlappung zu finden.

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
   <td colname="col2"> <p>Um den verfügbaren Besucherpool zu ermitteln, summieren Sie den Unterschied zwischen der Gesamtsumme (weniger Überlappung) und der Segmentsumme (weniger Überlappung). </p> <p>Diese Kombination aus Segmenten kann bis zu 1004 neue Benutzer erreichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ineffiziente Segmente suchen</b> </td> 
   <td colname="col2"> <p>Wenn eine Eigenschaft Teil einer <span class="wintitle"> UND</span> -Gruppe in einer Segmentdefinition ist, sind die individuellen Besucher, die über diese Eigenschaft verfügen, bereits im Segment enthalten und nicht zum Hinzufügen zum Segment verfügbar. Sie können diesen Bericht verwenden, um relevante Eigenschaften mit geringer Überlappung zu finden und diese zur Segmentdefinition hinzuzufügen, wodurch die Reichweite des Zielgruppenpools erhöht wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Grundlegendes zu den Datenfiltern im Bericht &quot;Segmente zu Trait-Überlagerungen « {#data-filters-s2t-report}

Beschreibt, wie die Eigenschaftenüberlappung und das eindeutige Segment % regler funktionieren.

<!-- 

r_s2t_sliders.xml

 -->

Mit [!UICONTROL Segment-to-Trait overlap] dem Bericht können Sie zwei Schieberegler verwenden, um Daten durch die Überlappung % nach Merkmal oder Segment zu filtern.

* **[!UICONTROL Filter Trait Uniques %:]** Filtert Daten nach den % der Unique Visitors, die zwischen der Eigenschaft und dem Segment freigegeben wurden.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtert Daten nach Prozentsatz der individuellen Besucher zwischen dem Segment und der Eigenschaft.

### Beispiel 

Das folgende Diagramm zeigt den Unterschied zwischen dem Eigenschaftenmerkmal % und dem Segment %. In diesem Fall geben die Eigenschaft und das Segment 3 Unique Visitors frei. Als Proportionen:

* Die Eigenschaft hat 30% der individuellen Besucher mit dem Segment (3/10 = 0,30).
* Das Segment teilt 0,3% seiner individuellen Besucher mit der Eigenschaft (3/1.000 = 0.003).

![](assets/s2t.png)

## Datumsfelder für Segment-zu-Trait-Daten definiert {#fields-defined}

Beschreibt die im Popup-Fenster angezeigten Metriken, wenn Sie auf einen einzelnen Datenpunkt klicken.

<!-- 

r_s2t_data_pop.xml

 -->

Das Popup für den [!UICONTROL Segment-to-Trait Overlap] Bericht enthält die folgenden Metriken. Beachten Sie, dass die Metrik &quot;Individuelle Werte&quot; in der Tabelle Ihre *Echtzeitbenutzer repräsentiert*.

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
   <td colname="col1"><b><span class="wintitle"> Datenanbieter-Name</span></b> </td> 
   <td colname="col2"> Name des Segmentinhabers. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Datenprovider-Typ</span></b> </td> 
   <td colname="col2">Definiert den Typ des Anbieters, zu dem ein Merkmal gehört. Kann entweder: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Erstanbieter (eigene Eigenschaft). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Drittanbieter (von einem externen Partner/Anbieter). </li> 
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
   <td colname="col1"><b><span class="wintitle"> Trait Uniques Overlap %</span></b> </td> 
   <td colname="col2"> % der individuellen Besucher, die mit dem Segment geteilt werden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmentübergreifende Überlappung %</span></b> </td> 
   <td colname="col2"> % der individuellen Besucher, die ein Segment mit einer Eigenschaft teilen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Überlappende Uniques</span></b> </td> 
   <td colname="col2"> Anzahl der Unique Visitors, die zwischen dem Segment und der Eigenschaft freigegeben wurden. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmentaufbau</span></b> </td> 
   <td colname="col2"> Anzahl der individuellen Besucher im Segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Uniques</span></b> </td> 
   <td colname="col2"> Anzahl der individuellen Besucher in der Eigenschaft. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Berichtsergebnisse mit den Datenreglern filtern](../../reporting/dynamic-reports/data-sliders.md)
>* [In interaktiven Berichten verwendete Formen, Farben und Größen](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Erklärung der Berichtsymbole und Tools](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Überlappungsberichte: Zeitplan und Mindestgröße des Segments aktualisieren](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datenstichproben und Fehlersätze in ausgewählten Audience Manager-Berichten…](../../reporting/report-sampling.md)
>* [CSV-Dateien für Überlappungsberichte](../../reporting/dynamic-reports/overlap-csv-files.md)
---
description: Sie können eine CSV-Datei für einen Überlagerungsbericht anfordern, wenn dieser Bericht das Limit von 1 Million Datensätzen erreicht. Ein Bericht kann diese Grenze erreicht haben, wenn die Meldung "Unerwarteter Fehler ist aufgetreten"angezeigt wird. Wenden Sie sich an die Kundenunterstützung, um eine komprimierte CSV-Datei anzufordern, die Sie importieren und in Ihrem eigenen Datenbanksystem verwenden können. Dateien sind für Berichte zur Segmentüberschneidung, Segment-zu-Merkmal-Überschneidung und zur Eigenschaftenüberschneidung verfügbar.
seo-description: You can request a .csv file for an Overlap Report when that report reaches its 1-million record limit. A report may have reached this limit when you see an "Unexpected error has occurred" message. Contact Customer Care to request a compressed .csv file, which you can import and work with in your own database system. Files are available for segment-to-segment, segment-to-trait, and trait-to-trait overlap reports.
seo-title: CSV Files for Overlap Reports
solution: Audience Manager
title: CSV-Dateien für Überlagerungsberichte
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: Overlap Reports
exl-id: 759c39cb-64ec-47dd-a3a4-027408aa6b5e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 2%

---

# CSV-Dateien für Überlagerungsberichte{#csv-files-for-overlap-reports}

Sie können eine CSV-Datei für einen Überlagerungsbericht anfordern, wenn dieser Bericht das Limit von 1 Million Datensätzen erreicht. Ein Bericht kann diese Grenze erreicht haben, wenn die Meldung &quot;Unerwarteter Fehler ist aufgetreten&quot;angezeigt wird. Wenden Sie sich an die Kundenunterstützung, um eine komprimierte CSV-Datei anzufordern, die Sie importieren und in Ihrem eigenen Datenbanksystem verwenden können. Dateien sind für Berichte zur Segmentüberschneidung, Segment-zu-Merkmal-Überschneidung und zur Eigenschaftenüberschneidung verfügbar.

## Dateinamenmetadaten {#file-name-metadata}

In der folgenden Tabelle werden die Dateibenennungskonventionen und Dateierweiterungen beschrieben, die in einer überlappenden .csv -Datei verwendet werden. In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metadatenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dateierweiterung </p> </td> 
   <td colname="col2"> <p>Überlagerungsberichtsdateien sind gzip-komprimiert und haben eine <code> .gz</code> -Dateierweiterung. Nach der Dekomprimierung müssen Sie die Erweiterung <code> .csv</code> zur Datei hinzufügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dateiname </p> </td> 
   <td colname="col2"> <p>Syntax für Dateinamen: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segmentdateien: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Dateien von Segment zu Eigenschaft: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Dateien mit Eigenschaften: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datumsbereich </p> </td> 
   <td colname="col2"> <p>Der Datumsbereich für einen Bericht ist eine fünfstellige ID, die Folgendes enthält: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> für einen 7-Tage-Bericht. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> für einen 30-tägigen Bericht. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mehrere Dateien </p> </td> 
   <td colname="col2"> <p>Wenn ein Bericht mehrere Dateien enthält, wird die letzte Ziffer im Dateinamen erhöht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Beispiele </p> </td> 
   <td colname="col2"> <p>Beispiele für Dateinamen für einen einzelnen Bericht: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Einzelne 7-Tage-Datei: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Einzelne 30-Tage-Datei: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Beispiele für Dateinamen für einen Bericht mit mehreren Dateien: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dateiinhalt {#file-contents}

In der -Datei werden die Zeichenfolgendaten in doppelte Anführungszeichen gesetzt. Siehe nachfolgende nachgeahmte Daten. Dies wurde aus Gründen der Kürze und der Bildschirmgröße abgeschnitten.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Berichtdatensätze zwischen Segmenten {#segment-segment-records}

Eine Datendatei für Ihren [Überlagerungsbericht zwischen Segmenten](segment-segment-overlap-report.md) enthält die folgenden Datensätze.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beschriftung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>Die ID des Segments, das Sie mit dem Grundliniensegment vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Segments, das Sie mit den Basissegmenten vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>Die ID Ihres Grundliniensegments. Das Grundliniensegment ist das Segment, das Sie mit anderen Segmenten vergleichen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Grundliniensegments, das Sie mit anderen Segmenten vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Sie können Berichte für 7- und 30-tägige Lookback-Intervalle abrufen. Der <code> rangeid</code> entspricht den unten dargestellten Zeitintervallen. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 Tage </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Das Verarbeitungsdatum für einen Bericht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users im Segment, das Sie mit dem Grundliniensegment vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users im Basissegment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Gesamtanzahl der Überschneidungen von Unique Users zwischen dem Grundliniensegment und den anderen zum Vergleich ausgewählten Segmenten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>Die %-Überschneidung von Unique Users zwischen dem Grundliniensegment und den anderen zum Vergleich ausgewählten Segmenten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Berichtdatensätze zwischen Segmenten und Eigenschaften {#segment-trait-records}

Eine Datendatei für Ihren [Überlagerungsbericht zwischen Segmenten und Eigenschaften](segment-trait-overlap-report.md) enthält die folgenden Datensätze.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beschriftung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p>Eigenschaft-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>Eigenschaftsname. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>Die Datenanbieter-ID. Zu den IDs gehören: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Name des Datenanbieters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Sie können Berichte für 7- und 30-tägige Lookback-Intervalle abrufen. Der <code> rangeid</code> entspricht den unten dargestellten Zeitintervallen. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 Tage </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Das Verarbeitungsdatum für einen Bericht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users im ausgewählten Segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users in einer Eigenschaft. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users, die für die ausgewählten Segmente und Eigenschaften freigegeben wurden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% der Unique Users, die sich zwischen Eigenschaft und Segment überschneiden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% der Unique Users, die sich zwischen Segment und Eigenschaft überschneiden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Berichtdatensätze zwischen Eigenschaften {#trait-trait-records}

Eine Datendatei für Ihren [Überlagerungsbericht zwischen Eigenschaften](trait-trait-overlap-report.md) enthält die folgenden Datensätze.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beschriftung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>Die ID der Eigenschaft, die Sie mit der Grundlinie vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Der Name der Eigenschaft, die Sie mit der Grundlinie vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>Die ID Ihrer Grundlinie. Die Grundlinieneigenschaft ist die Eigenschaft, die Sie mit anderen Eigenschaften vergleichen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Der Name der Grundlinie, die Sie mit anderen Eigenschaften vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>Die Datenanbieter-ID. Zu den IDs gehören: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Name des Datenanbieters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Sie können Berichte für 7- und 30-tägige Lookback-Intervalle abrufen. Der <code> rangeid</code> entspricht den unten dargestellten Zeitintervallen. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 Tage </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Das Verarbeitungsdatum für einen Bericht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users, die für die ausgewählten Eigenschaften freigegeben wurden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users in einer Basiseigenschaft. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users, die für die ausgewählten Eigenschaften freigegeben wurden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% der Unique Users, die sich zwischen den ausgewählten Eigenschaften überschneiden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% der Unique Users, die sich zwischen den ausgewählten Eigenschaften überschneiden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
 </tbody> 
</table>

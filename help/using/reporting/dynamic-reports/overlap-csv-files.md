---
description: Sie können eine CSV-Datei für einen Overlap Report anfordern, wenn dieser Bericht die Rekordgrenze von 1 Million erreicht. Ein Bericht hat diese Grenze möglicherweise erreicht, wenn die Meldung "Unerwarteter Fehler ist aufgetreten"angezeigt wird. Wenden Sie sich an den Kundendienst, um eine komprimierte .csv-Datei anzufordern, die Sie in Ihr eigenes Datenbanksystem importieren und damit arbeiten können. Dateien stehen für Berichte zur Überschneidung von Segment zu Segment, Segment zu Eigenschaften und Eigenschaften zur Verfügung.
seo-description: Sie können eine CSV-Datei für einen Overlap Report anfordern, wenn dieser Bericht die Rekordgrenze von 1 Million erreicht. Ein Bericht hat diese Grenze möglicherweise erreicht, wenn die Meldung "Unerwarteter Fehler ist aufgetreten"angezeigt wird. Wenden Sie sich an den Kundendienst, um eine komprimierte .csv-Datei anzufordern, die Sie in Ihr eigenes Datenbanksystem importieren und damit arbeiten können. Dateien stehen für Berichte zur Überschneidung von Segment zu Segment, Segment zu Eigenschaften und Eigenschaften zur Verfügung.
seo-title: CSV-Dateien für Überlagerungsberichte
solution: Audience Manager
title: CSV-Dateien für Überlagerungsberichte
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: overlap reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 9%

---


# CSV-Dateien für Überlagerungsberichte{#csv-files-for-overlap-reports}

Sie können eine CSV-Datei für einen Overlap Report anfordern, wenn dieser Bericht die Rekordgrenze von 1 Million erreicht. Ein Bericht hat diese Grenze möglicherweise erreicht, wenn die Meldung &quot;Unerwarteter Fehler ist aufgetreten&quot;angezeigt wird. Wenden Sie sich an den Kundendienst, um eine komprimierte .csv-Datei anzufordern, die Sie in Ihr eigenes Datenbanksystem importieren und damit arbeiten können. Dateien stehen für Berichte zur Überschneidung von Segment zu Segment, Segment zu Eigenschaften und Eigenschaften zur Verfügung.

## Dateinamenmetadaten {#file-name-metadata}

In der folgenden Liste werden die Dateibenennungsregeln und Dateierweiterungen beschrieben, die in einer überlappenden .csv-Datei verwendet werden. In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metadatenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Datei Extension </p> </td> 
   <td colname="col2"> <p>Überlagerungsberichtsdateien sind gzip-komprimiert und haben eine <code> .gz</code> Dateierweiterung. Nach der Dekomprimierung müssen Sie der Datei die Erweiterung <code> .csv</code> hinzufügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dateiname </p> </td> 
   <td colname="col2"> <p>Dateinamensyntax: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segment-zu-Segment-Dateien: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Segment-zu-Eigenschaftendateien: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Eigenschaften-zu-Eigenschaften-Dateien: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datumsbereich </p> </td> 
   <td colname="col2"> <p>Der Datumsbereich für einen Bericht ist eine fünfstellige ID, die Folgendes umfasst: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> für einen 7-Tage-Bericht. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> für einen 30-Tage-Bericht. </li> 
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
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Einzelne Datei mit 7 Tagen: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Einzelne Datei mit 30 Tagen: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
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

In der Dublette sind Zeichenfolgendaten in Anführungszeichen gesetzt. Siehe die Musterdaten unten. Dies wurde abgeschnitten, um die Schnelligkeit zu erhöhen und den Bildschirm einzupassen.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Segmente-zu-Segment-Berichtdatensätze {#segment-segment-records}

Eine Datendatei für Ihren [Segment-zu-Segment-Überschneidungsbericht](segment-segment-overlap-report.md) enthält die folgenden Datensätze.

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
   <td colname="col2"> <p>Die ID des Segments, das Sie mit dem Basissegment vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Segments, das Sie mit den Grundsegmenten vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>Die ID Ihres Ausgangssegments. Das Grundliniensegment ist das Segment, das Sie mit anderen Segmenten vergleichen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Grundliniensegments, das Sie mit anderen Segmenten vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Sie können Berichte für 7- und 30-Tage-Rückblickintervalle abrufen. Das <code> rangeid</code> entspricht den unten angegebenen Zeitintervallen. </p> <p> 
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
   <td colname="col2"> <p>Die Anzahl der Unique Users im Segment, das Sie mit dem Basissegment vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users im Basissegment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Gesamtanzahl der Überschneidungen individueller Benutzer zwischen dem Ausgangssegment und den anderen zum Vergleich ausgewählten Segmenten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>Die %-Überschneidung individueller Benutzer zwischen dem Grundliniensegment und den anderen zum Vergleich ausgewählten Segmenten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Report Records von Segment zu Eigenschaft {#segment-trait-records}

Eine Datendatei für den Bericht [Segment-zu-Eigenschaften-Überschneidung](segment-trait-overlap-report.md) enthält die folgenden Datensätze.

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
   <td colname="col2"> <p>Eigenschaften-ID. </p> </td> 
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
   <td colname="col2"> <p>Sie können Berichte für 7- und 30-Tage-Rückblickintervalle abrufen. Das <code> rangeid</code> entspricht den unten angegebenen Zeitintervallen. </p> <p> 
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
   <td colname="col2"> <p>Die Anzahl der Unique Users in einer Eigenschaft. Diese Zahl wird im UI-Bericht im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users, die für die ausgewählten Segmente und Eigenschaften freigegeben wurden. Diese Zahl wird im UI-Bericht im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% der Unique Users, die sich zwischen Eigenschaft und Segment überschneiden. Diese Zahl wird im UI-Bericht im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% der Uniques-Benutzer, die sich zwischen Segment und Eigenschaft überschneiden. Diese Zahl wird im UI-Bericht im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Eigenschaften-zu-Eigenschaften-Berichtdatensätze {#trait-trait-records}

Eine Datendatei für den Bericht [Eigenschafts-Überschneidung](trait-trait-overlap-report.md) enthält die folgenden Datensätze.

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
   <td colname="col2"> <p>Die ID des Merkmals, das Sie mit dem Grundmerkmal vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Der Name der Eigenschaft, die Sie mit der Grundlinie vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>Die ID Ihres Grundmerkmals. Die Grundeigenschaft ist die Eigenschaft, die Sie mit anderen Eigenschaften vergleichen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Grundmerkmals, das Sie mit anderen Eigenschaften vergleichen. </p> </td> 
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
   <td colname="col2"> <p>Sie können Berichte für 7- und 30-Tage-Rückblickintervalle abrufen. Das <code> rangeid</code> entspricht den unten angegebenen Zeitintervallen. </p> <p> 
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
   <td colname="col2"> <p>Die Anzahl der Unique Users, die für die ausgewählten Eigenschaften freigegeben wurden. Diese Zahl wird im UI-Bericht im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users in einer Basiseigenschaft. Diese Zahl wird im UI-Bericht im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Users, die für die ausgewählten Eigenschaften freigegeben wurden. Diese Zahl wird im UI-Bericht im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% der Unique Users, die sich zwischen den ausgewählten Eigenschaften überschneiden. Diese Zahl wird im UI-Bericht im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% der individuellen Benutzer, die sich zwischen den ausgewählten Eigenschaften überschneiden. Diese Zahl wird im UI-Bericht im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
 </tbody> 
</table>

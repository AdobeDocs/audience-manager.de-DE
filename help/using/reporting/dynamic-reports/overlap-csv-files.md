---
description: Sie können eine CSV-Datei für einen Overlap Report anfordern, wenn dieser Bericht die Rekordgrenze von 1 Million erreicht. Ein Bericht hat diesen Grenzwert möglicherweise erreicht, wenn der Meldung "Unerwarteter Fehler ist aufgetreten" angezeigt wird. Wenden Sie sich an den Kundendienst, um eine komprimierte. csv-Datei anzufordern, die Sie importieren und in Ihrem eigenen Datenbanksystem arbeiten können. Dateien sind für Segmente zu Segmenten, Segmenten, Segmenten und Eigenschaften verfügbar.
seo-description: Sie können eine CSV-Datei für einen Overlap Report anfordern, wenn dieser Bericht die Rekordgrenze von 1 Million erreicht. Ein Bericht hat diesen Grenzwert möglicherweise erreicht, wenn der Meldung "Unerwarteter Fehler ist aufgetreten" angezeigt wird. Wenden Sie sich an den Kundendienst, um eine komprimierte. csv-Datei anzufordern, die Sie importieren und in Ihrem eigenen Datenbanksystem arbeiten können. Dateien sind für Segmente zu Segmenten, Segmenten, Segmenten und Eigenschaften verfügbar.
seo-title: CSV-Dateien für Überlappungsberichte
solution: Audience Manager
title: CSV-Dateien für Überlappungsberichte
uuid: 047 e 440 e -00 c 5-4 d 06-a 809-51 d 776326 cd 6
translation-type: tm+mt
source-git-commit: d13b32999c5af4d20f33a92dfa805d7fe0babb2d

---


# CSV-Dateien für Überlappungsberichte{#csv-files-for-overlap-reports}

Sie können eine CSV-Datei für einen Overlap Report anfordern, wenn dieser Bericht die Rekordgrenze von 1 Million erreicht. Ein Bericht hat diesen Grenzwert möglicherweise erreicht, wenn der Meldung &quot;Unerwarteter Fehler ist aufgetreten&quot; angezeigt wird. Wenden Sie sich an den Kundendienst, um eine komprimierte. csv-Datei anzufordern, die Sie importieren und in Ihrem eigenen Datenbanksystem arbeiten können. Dateien sind für Segmente zu Segmenten, Segmenten, Segmenten und Eigenschaften verfügbar.

## Dateinamenmetadaten {#file-name-metadata}

In der folgenden Tabelle sind die Dateibenennungskonventionen und Dateierweiterungen aufgeführt, die in einer überlappenden. csv-Datei verwendet werden. In den Beispielen gibt *kursiv einen* Variablenplatzhalter an.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metadatenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Datei Erweiterung </p> </td> 
   <td colname="col2"> <p>Überlappungsberichtsdateien sind gzip komprimiert und haben eine <code> .gz</code> Dateierweiterung. Sie müssen die <code> . csv</code> -Erweiterung der Datei nach der Dekomprimierung hinzufügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dateiname </p> </td> 
   <td colname="col2"> <p>Syntax für Dateiname: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segmentsegmentdateien: <code>Bereich "S 2 S_ overlap_<i>partner ID</i>_<i>jjjjj-mm</i>_ tt_<i>date «</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Segmentzu-Eigenschaften-Dateien: <code>Bereich "S 2 T_ overlap_<i>partner ID</i>_<i>jjjjj-mm</i>_ tt_<i>date «</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Trait-to-Trait-Dateien: <code>T 2 T_ overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>datumsbereich</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datumsbereich </p> </td> 
   <td colname="col2"> <p>Der Datumsbereich für einen Bericht ist eine fünfstellige ID, die Folgendes enthält: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> für einen 7-Tage-Bericht. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> für einen 30-Tage-Bericht. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mehrere Dateien </p> </td> 
   <td colname="col2"> <p>Wir erhöhen die letzte Ziffer im Dateinamen, wenn ein Bericht mehrere Dateien enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Beispiele </p> </td> 
   <td colname="col2"> <p>Beispiele für Dateinamen für einen einzelnen Bericht: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Einzelne, 7-Tage-Datei: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
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

In der Datei sind Zeichenfolgendaten in doppelte Anführungszeichen eingeschlossen. Siehe die unten stehenden Daten. Dies wurde für die Darstellung abgeschnitten und passend zum Bildschirm.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Datensätze zum Segmentvergleich {#segment-segment-records}

Eine Datendatei für Ihr [Segment-zu-Segment-Überlappungsbericht](segment-segment-overlap-report.md) enthält die folgenden Datensätze.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beschriftung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id 1</code> </p> </td> 
   <td colname="col2"> <p>Die ID des Segments, das Sie mit dem Grundliniensegment vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name 1</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Segments, das Sie mit den Grundliniensegmenten vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id 2</code> </p> </td> 
   <td colname="col2"> <p>Die ID Ihres Grundliniensegments. Das Grundliniensegment ist das Segment, das Sie mit anderen Segmenten vergleichen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name 2</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Ausgangssegments, das Sie mit anderen Segmenten vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Sie können Berichte für einen Zeitraum von 7 und 30 Tagen abrufen. Die <code> rangeid</code> entspricht den unten aufgeführten Zeitintervallen. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7-Tage </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Das Verarbeitungsdatum eines Berichts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ unique uniques 1</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Unique Users im Segment, die Sie mit dem Grundliniensegment vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques 2</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Unique Users im Grundliniensegment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ unique uniques</code> </p> </td> 
   <td colname="col2"> <p>Gesamtanzahl der Überlappung der individuellen Benutzer zwischen dem Grundliniensegment und den anderen für den Vergleich ausgewählten Segmenten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>Die % überlappende Benutzer zwischen dem Grundliniensegment und den anderen zum Vergleich ausgewählten Segmenten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Berichtsdatensätze für Segmente {#segment-trait-records}

Eine Datendatei für Ihren [Segmentzu-Trait-Überlappungs-Bericht](segment-trait-overlap-report.md) enthält die folgenden Datensätze.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beschriftung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ id</code> </p> </td> 
   <td colname="col2"> <p>Eigenschafts-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ name</code> </p> </td> 
   <td colname="col2"> <p>Eigenschaftsname. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>Die Datenanbieter-ID. Zu den IDs gehören: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1. Partei</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> Drittanbieter</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Name des Datenproviders. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Sie können Berichte für einen Zeitraum von 7 und 30 Tagen abrufen. Die <code> rangeid</code> entspricht den unten aufgeführten Zeitintervallen. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7-Tage </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Das Verarbeitungsdatum eines Berichts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ unique uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Unique Users im ausgewählten Segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ unique uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Unique Users in einer Eigenschaft. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ unique uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der eindeutigen Benutzer, die zwischen den ausgewählten Segmenten und Eigenschaften freigegeben wurden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ uniques_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>% der Unique Users, die zwischen der Eigenschaft und dem Segment überlappen. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ uniques_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>% der eindeutigen Benutzer, die zwischen Segment und Eigenschaft überlappen. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait-to-Trait-Berichtsdatensätze {#trait-trait-records}

Eine Datendatei für Ihren [Trait-to-Trait-Überlappungsbericht](trait-trait-overlap-report.md) enthält die folgenden Datensätze.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beschriftung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ trait_ id</code> </p> </td> 
   <td colname="col2"> <p>Die ID der Eigenschaft, die Sie mit der Grundlinieneigenschaft vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>Der Name der Eigenschaft, mit der Sie mit der Grundlinie vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ id</code> </p> </td> 
   <td colname="col2"> <p>Die ID Ihrer Grundlinieneigenschaft. Die Grundlinie ist die Eigenschaft, die Sie mit anderen Eigenschaften vergleichen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Ausgangsmerkmals, das Sie mit anderen Eigenschaften vergleichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>Die Datenanbieter-ID. Zu den IDs gehören: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1. Partei</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> Drittanbieter</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Name des Datenproviders. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Sie können Berichte für einen Zeitraum von 7 und 30 Tagen abrufen. Die <code> rangeid</code> entspricht den unten aufgeführten Zeitintervallen. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7-Tage </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Das Verarbeitungsdatum eines Berichts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ trait_ unique uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der eindeutigen Benutzer, die zwischen den ausgewählten Eigenschaften freigegeben wurden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ unique uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Unique Users in einer Basiseigenschaft. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ unique uniques</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der eindeutigen Benutzer, die zwischen den ausgewählten Eigenschaften freigegeben wurden. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_ trait_ uniques_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>% der Unique Users, die zwischen den ausgewählten Eigenschaften überlappen. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ uniques_ overlap_ perc</code> </p> </td> 
   <td colname="col2"> <p>% der eindeutigen Benutzer, die zwischen den ausgewählten Eigenschaften überlappen. Im UI-Bericht wird diese Zahl im Popup-Fenster angezeigt, wenn Sie den Mauszeiger über eine Eigenschaft in den Heatmap-Ergebnissen bewegen. </p> </td> 
  </tr> 
 </tbody> 
</table>

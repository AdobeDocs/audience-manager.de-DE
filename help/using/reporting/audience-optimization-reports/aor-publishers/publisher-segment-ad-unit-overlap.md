---
description: Der Bericht zu Anzeigeneinheitenüberlappung wird als ein Heat Chart angezeigt, das hohe und niedrige Überlappungen zwischen Ihren Anzeigeneinheiten und Audience Manager-Segmenten hervorhebt.
seo-description: Der Bericht zu Anzeigeneinheitenüberlappung wird als ein Heat Chart angezeigt, das hohe und niedrige Überlappungen zwischen Ihren Anzeigeneinheiten und Audience Manager-Segmenten hervorhebt.
seo-title: Segment auf Anzeigenüberlappung
solution: Audience Manager
title: Segment auf Anzeigenüberlappung
uuid: aaa 20163-58 aa -42 c 9-8 f 72-a 1 dfb 0 d 20 e 57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment to Ad Unit Overlap{#segment-to-ad-unit-overlap}

Der Bericht zu Anzeigeneinheitenüberlappung wird als ein Heat Chart angezeigt, das hohe und niedrige Überlappungen zwischen Ihren Anzeigeneinheiten und Audience Manager-Segmenten hervorhebt.

## Nutzungsszenario {#use-cases}

With the [!UICONTROL Segment to Ad Unit Overlap] report, you can understand which audiences visit your web properties. The report displays the overlap between members of your [!DNL Audience Manager] segments and the number of visitors to your web properties. Eine höhere Überschneidung bedeutet, dass viele Mitglieder eines Segments Ihre Webeigenschaft besuchen.

## Using the Segment to Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Ad Units]** and **[!UICONTROL Top N Segments]** controls to select your desired number of ad units and segments for the overlap. Sie können jeweils maximal 100 Elemente auswählen.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Beachten Sie, dass der 7-Tage- und 30-Tage-Suchzeitraum nur für Sonntag verfügbar sind.

Use the **[!UICONTROL Segment Name]** and the **[!UICONTROL Ad Unit]** boxes to filter any of segments and ad units.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Segment to Ad Unit Overlap] report could look similar to the one below. Bewegen Sie den Mauszeiger über eine Zelle, um weitere Informationen zu dieser Überlappung abzurufen. Weitere Informationen finden Sie unter Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzeigeneinheit </span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Bestandselements. Dies kann zum Beispiel einer der Websites oder einen Artikel auf Ihrer Website sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentechtzeit-Unique Time Anzahl</span> </p> </td> 
   <td colname="col2"> <p>The number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzeigeneinheit Individuelle Werte</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Ihrer Besucher für diese spezifische Anzeigeneinheit. Diese Informationen werden aus den DFP-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlappende Uniques-Anzahl</span> </p> </td> 
   <td colname="col2"> <p>Die Mitglieder Ihres Segments, die dem Anzeigeneinheitenelement offen gelegt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlappungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überlappung zwischen Anzeigeneinheiten und Segmentpopulationen. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Segment Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>


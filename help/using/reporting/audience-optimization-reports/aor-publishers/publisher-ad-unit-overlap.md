---
description: Der Bericht "Anzeigenüberlappung" wird als ein Heat Chart angezeigt, das hohe und niedrige Überlappungen zwischen Ihren Anzeigeneinheiten hervorhebt.
seo-description: Der Bericht "Anzeigenüberlappung" wird als ein Heat Chart angezeigt, das hohe und niedrige Überlappungen zwischen Ihren Anzeigeneinheiten hervorhebt.
seo-title: Anzeigenüberlappung
solution: Audience Manager
title: Anzeigenüberlappung
uuid: e 4467 e 81-acbf -474 e-b 501-89 d 57395651 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ad Unit Overlap{#ad-unit-overlap}

The **[!UICONTROL Ad Unit Overlap]** report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.

## Nutzungsszenario {#use-cases}

With the **[!UICONTROL Ad Unit Overlap]** report, you can gain insight into where your audience overlaps across your web properties. Der Bericht betrachtet Ihre 100 wichtigsten Eigenschaften und zeigt Ihnen die Überlappung.

## Using the Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Base Ad Units]** and **[!UICONTROL Top N Overlapping Ad Units]** controls to select your desired number of ad units for the overlap. Sie können jeweils maximal 100 Elemente auswählen.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Beachten Sie, dass der 7-Tage- und 30-Tage-Suchzeitraum nur für Sonntag verfügbar sind.

Use the **[!UICONTROL Base Ad Unit]** and the **[!UICONTROL Overlap Ad Unit]** controls to select which of your ad units you want to display in the overlap report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Ad Unit Overlap] report could look similar to the one below. Bewegen Sie den Mauszeiger über eine Zelle, um weitere Informationen zu dieser Überlappung abzurufen. Weitere Informationen finden Sie unter Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlappende Anzeigeneinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Bestandselements. Dies kann zum Beispiel einer der Websites oder einen Artikel auf Ihrer Website sein. Im obigen Bild sind die Basisanzeigeneinheiten Artikel 9 - 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basisanzeigeneinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Bestandselements. Dies kann zum Beispiel einer der Websites oder einen Artikel auf Ihrer Website sein. Im obigen Bild sind die Basisanzeigeneinheiten Artikel 1 - 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlappende Anzeigeneinheit - Anzahl</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die die Anzeigenartikelelemente 9 - 18 besucht haben. Diese Informationen werden aus den DFP-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basis-Anzeigeneinheit Individuelle Werte</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die die Anzeigeneinheitenelemente 1 - 8 besucht haben. Diese Informationen werden aus den DFP-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlappende Uniques-Anzahl</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlappungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Base Ad Unit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

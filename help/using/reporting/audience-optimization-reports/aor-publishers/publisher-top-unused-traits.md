---
description: Die nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch keine Mitglieder eines Segments sind, basierend auf Eigenschaften, Datenquelle und Leistung.
seo-description: Die nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch keine Mitglieder eines Segments sind, basierend auf Eigenschaften, Datenquelle und Leistung.
seo-title: Nicht verwendete Eigenschaften
solution: Audience Manager
title: Nicht verwendete Eigenschaften
uuid: 90 bcd 333-41 b 8-416 e-aa 4 e-a 6661891 df 50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Top Unused Traits{#top-unused-traits}

Die nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch keine Mitglieder eines Segments sind, basierend auf Eigenschaften, Datenquelle und Leistung.

## Nutzungsszenario {#use-cases}

With the [!UICONTROL Top Unused Traits] report, you can analyze and compare the performance of first and third party traits that are currently not mapped to a segment. Diese Ansicht kann auf die besten Eigenschaften hinweisen, die in einem Zielgruppensegment für die Kampagnenoptimierung oder für neue neue Gelegenheiten verwendet werden.

## Using the Top Unused Traits Report {#using-the-report}

Use the **[!UICONTROL Data Provider Type]** controls to toggle between first party and third party traits. Select **[!UICONTROL All]** to return first and third party traits in the report.

With the **[!UICONTROL Impressions]** slider, you can select a minimum and maximum value for returned impressions. Alle Eigenschaften, die für weniger oder mehr als die eingestellten Beschränkungen verantwortlich sind, werden nicht im Bericht angezeigt.

Use the **[!UICONTROL Day Range]** and **[!UICONTROL Date Through]** controls to adjust your look-back range. Beachten Sie, dass für diesen Bericht nur der 30-Tage-Blickzeitraum zur Verfügung steht.

Use the **[!UICONTROL Order]** drop-down box to select the web properties in your portfolio for which you want to return information.

In the **[!UICONTROL Data Provider]** drop-down box, select the data sources containing the traits you want to see in the report.

Use the **[!UICONTROL Traits]** drop-down box to select which traits you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Order IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Order] instead of the [!UICONTROL Order ID].

## Interpreting the Results {#interpreting-results}

**Beispielbericht**

Your [!UICONTROL Top Unused Traits] report could look similar to the one below. Klicken Sie in Ihrem Bericht auf ein Punktdiagramm, um die zugrunde liegenden Daten anzuzeigen.

Weitere Informationen finden Sie unter Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Datenprovider-Typ</span> </p> </td> 
   <td colname="col2"> <p>Gibt an, ob die ausgewählte Datenquelle Erstanbieter- oder Drittanbieter-Eigenschaften enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschafts-ID</span> </p> </td> 
   <td colname="col2"> <p>Die eindeutige ID dieser Eigenschaft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschaftsname</span> </p> </td> 
   <td colname="col2"> <p>Der alphanumerische Name, den Sie oder der Datenprovider dieser Eigenschaft zugewiesen haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Bestellung</span> </p> </td> 
   <td colname="col2"> <p>Die Webeigenschaft, für die dieser Bericht angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eindrücke</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihren Bestand speichern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait Uniques</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Eigenschaftsmitglieder innerhalb der letzten 30 Tage. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

Die Position Ihrer Eigenschaften in einem Bericht kann Ihnen sehr viel darüber informieren, welche Eigenschaften Sie zur Optimierung vorhandener Zielgruppensegmente verwenden könnten.

Die Eigenschaften, die sich oben auf der Impressions-Achse befinden, sind diejenigen, die Sie in Ihren Kampagnen verwenden möchten. Bei Eigenschaften mit einer geringen Anzahl von Impressionen ist es unwahrscheinlich, dass Sie diese Zielgruppe auf Ihrer Webeigenschaft basierend auf Ihren DFP-Daten erreichen.

Look to the left of the [!UICONTROL Unique Trait Realizations] axis for highly accurate traits and to the right for traits that can drive scale.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Platzierung zeigt an </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Oben links</b> </p> </td> 
   <td colname="col2"> <p>Eine hohe Anzahl von Impressionen, niedrige Anzahl von Eigenschaften. </p> <p>Dies ist eine sehr genaue Zielgruppe, die noch kein Mitglied eines Segments ist. Erwägen Sie das Targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten links</b> </p> </td> 
   <td colname="col2"> <p>Geringe Anzahl von Impressionen, niedrige Anzahl von Eigenschaften. </p> <p> Schließen Sie diese Eigenschaften ab, da die Mitglieder nicht zu Impressionen in Ihren Webeigenschaften beitragen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Oben rechts</b> </p> </td> 
   <td colname="col2"> <p>Eine hohe Anzahl von Impressionen, eine große Anzahl von Eigenschaften. </p> <p>Eine hohe Reichweite gegenüber einer Zielgruppe, die noch nicht in einem Segment angezeigt wird. Diese Zielgruppe ist ein primärer Kandidat für Targeting aufgrund der hohen Anzahl von Impressionen und der Skala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten rechts</b> </p> </td> 
   <td colname="col2"> <p>Geringe Anzahl von Impressionen, hohe Anzahl von Eigenschaften. </p> <p> Sie können diese Eigenschaften ausschließen, da die Mitglieder nicht zu Impressionen in Ihren Webeigenschaften beitragen. </p> </td> 
  </tr> 
 </tbody> 
</table>

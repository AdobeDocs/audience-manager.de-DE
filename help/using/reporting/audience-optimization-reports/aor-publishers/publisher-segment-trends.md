---
description: Der Segmenttrendbericht gibt Daten zu Impressionen und Durchklickraten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück. Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und an ein Ziel für das Targeting senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht an ein Ziel für das Targeting gesendet haben. Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild darüber zu erhalten, wie sich Ihre Zielgruppen im Laufe der Zeit verhalten.
seo-description: Der Segmenttrendbericht gibt Daten zu Impressionen und Durchklickraten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück. Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und an ein Ziel für das Targeting senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht an ein Ziel für das Targeting gesendet haben. Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild darüber zu erhalten, wie sich Ihre Zielgruppen im Laufe der Zeit verhalten.
seo-title: Segmenttrendbericht
solution: Audience Manager
title: Segmenttrendbericht
uuid: f 84 e 8 d 0 a -74 e 5-430 c-b 61 c-efb 696 faee 93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Trend Report{#segment-trend-report}

Der Segmenttrendbericht gibt Daten zu Impressionen und Durchklickraten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück.

Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und an ein Ziel für das Targeting senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht an ein Ziel für das Targeting gesendet haben.

Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild darüber zu erhalten, wie sich Ihre Zielgruppen im Laufe der Zeit verhalten.

## Nutzungsszenario {#use-cases}

Use the [!UICONTROL Segment Trend] report to validate a segment's performance over time and to pinpoint trends based on strong performance or scale.

Mit diesem Bericht können Sie erkennen, welche Ihrer Webeigenschaften eine falsche oder fehlerhafte Steigerung und Fehlerbehebung zeigen. This report is the next step after you identify your audience of interest in the [!UICONTROL Segment Performance] report, to ensure that the strong or poor performance you saw in the [!UICONTROL Segment Performance] tab is consistent over time.

## Using the Segment Trend Report {#using-the-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Adjust the look-back window with the **[!UICONTROL Date Through]** slider.

Click any of the segments under the **[!UICONTROL Date Through]** slider to bring up the option to keep only that segment in the report or exclude it.

Use the **[!UICONTROL Line Item]** drop-down box to select the properties in your portfolio for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item] IDs, as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item] ID.

## Interpreting the Results {#interpreting-results}

The [!UICONTROL Segment Trend] report returns data in a line graph for a 14-day interval only. In diesem Beispiel zeigt der Bericht Impressionen und Durchklicktrends für eine Gruppe zugeordneter und nicht zugeordneter Segmente.

Bewegen Sie den Mauszeiger über eine Zeile, um weitere Informationen zu diesem bestimmten Segmenttrend abzurufen. Weitere Informationen finden Sie unter Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment</span> </p> </td> 
   <td colname="col2"> <p>Der alphanumerische Name, den Sie diesem Segment zugewiesen haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment-ID</span> </p> </td> 
   <td colname="col2"> <p>Die eindeutige ID dieses Segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Zeileneintrag</span> </p> </td> 
   <td colname="col2"> <p>Die Webeigenschaft, für die dieser Bericht angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Klicks</span> </p> </td> 
   <td colname="col2"> <p>Die Frequenz, mit der Mitglieder dieser Eigenschaft auf Elemente in Ihrer Webeigenschaft geklickt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eindrücke</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihren Bestand speichern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Clickthrough-Rate. Diese Metrik legt den Prozentsatz der Impressionen, gefolgt von Klicks, fest. Dividieren Sie Klicks durch Impressionen, um diese Metrik zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentaufbau</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Segmentmitglieder innerhalb der letzten 30 Tage. </p> </td> 
  </tr> 
 </tbody> 
</table>

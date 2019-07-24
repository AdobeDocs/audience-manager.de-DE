---
description: Der Bericht "Segmentleistung" vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Real-Time Segment Uniques. Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und an ein Ziel für das Targeting senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht an ein Ziel für das Targeting gesendet haben. Beim Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und überflüssige Segmente suchen, die Sie möglicherweise an ein Ziel für Targeting senden möchten.
seo-description: Der Bericht "Segmentleistung" vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Real-Time Segment Uniques. Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und an ein Ziel für das Targeting senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht an ein Ziel für das Targeting gesendet haben. Beim Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und überflüssige Segmente suchen, die Sie möglicherweise an ein Ziel für Targeting senden möchten.
seo-title: Segmentleistungsbericht
solution: Audience Manager
title: Segmentleistungsbericht
uuid: c 9 a 1 e 9 ad -4 f 3 f -3334-a 3 ff -0 f 241 c 7303 c 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Performance Report{#segment-performance-report}

Der Bericht "Segmentleistung" vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Real-Time Segment Uniques.

Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und an ein Ziel für das Targeting senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht an ein Ziel für das Targeting gesendet haben.

Beim Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und überflüssige Segmente suchen, die Sie möglicherweise an ein Ziel für Targeting senden möchten.

## Nutzungsszenarios {#use-cases}

With the [!UICONTROL Segment Performance] report, you can:

* Identifizieren Sie zugeordnete Zielgruppensegmente, die eine Skalierung oder Leistung bringen.
* Identifizieren Sie nicht zugeordnete Segmente, die in zukünftigen Kampagnen eingeführt werden sollen, basierend auf dem Beitrag einer Zielgruppe zur bisherigen Leistung.

## Using the Segment Performance Report {#using-segment-performance-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Beachten Sie, dass der 7-Tage- und 30-Tage-Suchzeitraum nur für Sonntag verfügbar sind.

Use the **[!UICONTROL Line Item]** drop-down box to select the web properties for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Segment Performance] report could look similar to the one below. Klicken Sie in Ihrem Bericht auf ein Punktdiagramm, um die zugrunde liegenden Daten anzuzeigen. Weitere Informationen finden Sie unter Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Segment </p> </td> 
   <td colname="col2"> <p>Der alphanumerische Name, den Sie diesem Segment zugewiesen haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segment-ID </p> </td> 
   <td colname="col2"> <p>Die eindeutige ID dieses Segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zeileneintrag </p> </td> 
   <td colname="col2"> <p>Die Webeigenschaft, für die dieser Bericht angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Klicks </p> </td> 
   <td colname="col2"> <p>Die Frequenz, mit der Mitglieder dieser Eigenschaft auf Elemente in Ihrer Webeigenschaft geklickt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eindrücke </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihren Bestand speichern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Clickthrough-Rate. </p> <p>Diese Metrik legt den Prozentsatz der Impressionen, gefolgt von Klicks, fest. Dividieren Sie Klicks nach Impressionen, um diese Metrik zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Echtzeit-Segmentpopulation </p> </td> 
   <td colname="col2"> <p>The actual number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to Read Your Mapped Segment Results {#read-mapped-segment}

Die Position Ihrer zugeordneten Segmente in einem Bericht kann Ihnen sehr viel darüber informieren, welche Segmente gute Leistungen bringen und wo Sie möglicherweise einige Anpassungen vornehmen müssen.

Zum Lesen des Berichts ist es hilfreich, die Ergebnisse in vier Abschnitte mit imaginären Zeilen (Rot) und den im Beispielbericht unten stehenden Kategorien zu unterteilen. Die Beschriftungen im Beispiel können Ihnen dabei helfen, die Segmentleistung zu verstehen und auf diese Ergebnisse zu reagieren.

![](assets/publisher_segment_performance_mapped.png)

## How to Read Your Unmapped Segment Results {#read-unmapped-segment}

Looking at unmapped segments in a [!UICONTROL Segment Performance] report is a great way to find new segments you haven't considered for targeting. Einige dieser Segmente überschreiten möglicherweise Ihre zugeordneten Segmente.

Um diesen Bericht zu lesen, können Sie die Ergebnisse in vier Abschnitte mit imaginären Zeilen (Rot) und Kategorien unterteilen, die im Beispielbericht unten aufgeführt sind.

![](assets/publisher_segment_performance_unmapped.png)

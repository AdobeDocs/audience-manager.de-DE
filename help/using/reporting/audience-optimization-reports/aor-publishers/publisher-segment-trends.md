---
description: Der Bericht „Segmenttrends“ gibt Daten zu Impressionen und Clickthrough-Raten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück. Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber noch nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben. Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild vom Verhalten Ihrer Zielgruppen im Zeitverlauf zu erhalten.
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: Bericht zu Segmenttrends
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# Bericht zu Segmenttrends{#segment-trend-report}

Der Bericht „Segmenttrends“ gibt Daten zu Impressionen und Clickthrough-Raten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück.

Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber noch nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben.

Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild vom Verhalten Ihrer Zielgruppen im Zeitverlauf zu erhalten.

## Anwendungsfall {#use-cases}

Verwenden Sie den [!UICONTROL Segment Trend]-Bericht, um die Performance eines Segments im Zeitverlauf zu validieren und Trends basierend auf starker Performance oder Skalierung zu identifizieren.

Mit diesem Bericht können Sie nachvollziehen, welche Ihrer Web-Eigenschaften einen Rückgang oder eine fehlerhafte Zunahme aufweisen, und ggf. Fehler beheben. Dieser Bericht ist der nächste Schritt, nachdem Sie Ihre Zielgruppe im [!UICONTROL Segment Performance] Bericht identifiziert haben, um sicherzustellen, dass die starke oder schlechte Leistung, die Sie auf der Registerkarte [!UICONTROL Segment Performance] gesehen haben, im Laufe der Zeit konsistent ist.

## Verwenden des Berichts „Segmenttrends“ {#using-the-report}

Zwischen **[!UICONTROL Mapped]** und **[!UICONTROL Unmapped]** wechseln, um Segmente auszuwählen, die einem Ziel zugeordnet sind oder nicht. Wählen Sie **[!UICONTROL All]** aus, um alle Segmente in den Bericht aufzunehmen.

Passen Sie das Lookback-Fenster mit dem Schieberegler **[!UICONTROL Date Through]** an.

Klicken Sie auf eines der Segmente unter dem Regler **[!UICONTROL Date Through]**, um die Option aufzurufen, mit der Sie nur dieses Segment im Bericht behalten oder ausschließen können.

Verwenden Sie das Dropdown-Feld **[!UICONTROL Line Item]** , um die Eigenschaften in Ihrem Portfolio auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie in der Dropdown-Liste **[!UICONTROL Segment Data Source]** die Datenquellen aus, die die Segmente enthalten, die Sie im Bericht sehen möchten.

Verwenden Sie das Dropdown-Feld **[!UICONTROL Segment]** , um die Segmente auszuwählen, die im Bericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Bei der Aktivierung von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Line Item]-IDs hinzufügen, wie in Schritt 3 von [Importieren von Datendateien des Google Ad Managers (ehemals DFP) in den Audience Manager ](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md) beschrieben. Auf diese Weise können Sie sicherstellen, dass der Bericht die Web-Eigenschaft als [!UICONTROL Line Item] anstelle der [!UICONTROL Line Item]-ID angibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Der [!UICONTROL Segment Trend] gibt nur Daten in einem Liniendiagramm für ein 14-tägiges Intervall zurück. In diesem Beispiel zeigt der Bericht Impression- und Clickthrough-Trends für einen Satz von zugeordneten und nicht zugeordneten Segmenten.

Bewegen Sie den Mauszeiger über eine beliebige Zeile, um weitere Informationen zu diesem bestimmten Segmenttrend zu erhalten. Weitere Informationen finden Sie in den Beschreibungen in der Tabelle unten im Beispielbericht.

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
   <td colname="col1"> <p><span class="wintitle"> Posten</span> </p> </td> 
   <td colname="col2"> <p>Die Web-Eigenschaft, für die dieser Bericht angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Klicks</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft auf Elemente in Ihrer Web-Eigenschaft geklickt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihrem Inventar ausgesetzt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Clickthrough-Rate Diese Metrik gibt den Prozentsatz der Impressionen weiter, gefolgt von Klicks. Klicks durch Impressionen teilen, um diese Metrik zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment ist eindeutig</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Segmentmitglieder innerhalb der letzten 30 Tage. </p> </td> 
  </tr> 
 </tbody> 
</table>

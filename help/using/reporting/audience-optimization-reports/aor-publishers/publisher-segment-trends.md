---
description: Der Segmenttrend-Bericht gibt Daten zu Impressionen und Clickthrough-Raten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild davon zu erhalten, wie sich Ihre Audiencen im Laufe der Zeit verhalten.
seo-description: Der Segmenttrend-Bericht gibt Daten zu Impressionen und Clickthrough-Raten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild davon zu erhalten, wie sich Ihre Audiencen im Laufe der Zeit verhalten.
seo-title: Segment-Trend-Bericht
solution: Audience Manager
title: Segment-Trend-Bericht
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Berichte zur Zielgruppenoptimierung
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 3%

---

# Segment-Trend-Bericht{#segment-trend-report}

Der Segmenttrend-Bericht gibt Daten zu Impressionen und Clickthrough-Raten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück.

Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde.

Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild davon zu erhalten, wie sich Ihre Audiencen im Laufe der Zeit verhalten.

## Anwendungsfall {#use-cases}

Verwenden Sie den Bericht [!UICONTROL Segment Trend], um die Leistung eines Segments im Zeitverlauf zu überprüfen und Trends basierend auf einer starken Leistung oder Skalierung zu bestimmen.

Mit diesem Bericht können Sie erkennen, welche Ihrer Webeigenschaften eine Abweichung oder fehlerhafte Erhöhung aufweisen, und bei Bedarf eine Fehlerbehebung durchführen. Dieser Bericht ist der nächste Schritt, nachdem Sie Ihre für den [!UICONTROL Segment Performance]-Bericht interessante Audience identifiziert haben, um sicherzustellen, dass die starke oder schlechte Leistung, die Sie auf der Registerkarte [!UICONTROL Segment Performance] gesehen haben, im Laufe der Zeit konsistent ist.

## Verwenden des Segmenttrend-Berichts {#using-the-report}

Wechsel zwischen **[!UICONTROL Mapped]** und **[!UICONTROL Unmapped]**, um Segmente auszuwählen, die einem Ziel zugeordnet sind oder nicht. Wählen Sie **[!UICONTROL All]** aus, um alle Segmente in den Bericht einzubeziehen.

Passen Sie das Lookback-Fenster mit dem Schieberegler **[!UICONTROL Date Through]** an.

Klicken Sie auf eines der Segmente unter dem Schieberegler **[!UICONTROL Date Through]**, um die Option aufzurufen, um nur dieses Segment im Bericht zu belassen oder auszuschließen.

Verwenden Sie das Dropdownfeld **[!UICONTROL Line Item]**, um die Eigenschaften in Ihrem Portfolio auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie im Dropdownfeld **[!UICONTROL Segment Data Source]** die Datenquellen mit den Segmenten aus, die Sie im Bericht sehen möchten.

Verwenden Sie das Dropdownfeld **[!UICONTROL Segment]**, um auszuwählen, welche Segmente Sie im Bericht sehen möchten.

>[!IMPORTANT]
>
>Beim Aktivieren von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Line Item]-IDs einschließen, wie in Schritt 3 von [Google Ad Manager-(ehemals DFP-)Datendateien in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md) beschrieben. Auf diese Weise stellen Sie sicher, dass die Webeigenschaft im Bericht anstelle der [!UICONTROL Line Item]-ID als [!UICONTROL Line Item] gekennzeichnet wird.

## Interpretieren der Ergebnisse {#interpreting-results}

Der Bericht [!UICONTROL Segment Trend] gibt nur Daten in einem Liniendiagramm für einen Zeitraum von 14 Tagen zurück. In diesem Beispiel zeigt der Bericht Impressions- und Clickthrough-Trends für eine Reihe von zugeordneten und nicht zugeordneten Segmenten an.

Bewegen Sie den Mauszeiger über eine Zeile, um weitere Informationen zu diesem bestimmten Segmenttrend zu erhalten. Siehe Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col1"> <p><span class="wintitle"> Linienelement</span> </p> </td> 
   <td colname="col2"> <p>Die Webeigenschaft, für die Sie diesen Bericht sehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Klicks</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft auf Elemente in Ihrer Webeigenschaft geklickt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eindrücke</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihrem Bestand ausgesetzt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Clickthrough-Rate. Diese Metrik gibt den Prozentsatz der Impressionen, gefolgt von Klicks, wieder. Unterteilen Sie Klicks nach Impressionen, um diese Metrik zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentindividualisierung</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Segmentmitglieder innerhalb der letzten 30 Tage. </p> </td> 
  </tr> 
 </tbody> 
</table>

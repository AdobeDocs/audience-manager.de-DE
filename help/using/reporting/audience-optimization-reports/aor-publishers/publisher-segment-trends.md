---
description: Der Segmenttrend-Bericht gibt Daten zu Impressionen und Clickthrough-Raten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild davon zu erhalten, wie sich Ihre Zielgruppen im Laufe der Zeit verhalten.
seo-description: Der Segmenttrend-Bericht gibt Daten zu Impressionen und Clickthrough-Raten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild davon zu erhalten, wie sich Ihre Zielgruppen im Laufe der Zeit verhalten.
seo-title: Segmenttrend-Bericht
solution: Audience Manager
title: Segmenttrend-Bericht
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segmenttrend-Bericht{#segment-trend-report}

Der Segmenttrend-Bericht gibt Daten zu Impressionen und Clickthrough-Raten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück.

Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde.

Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild davon zu erhalten, wie sich Ihre Zielgruppen im Laufe der Zeit verhalten.

## Nutzungsszenario {#use-cases}

Verwenden Sie den [!UICONTROL Segment Trend] Bericht, um die Leistung eines Segments im Zeitverlauf zu validieren und Trends basierend auf leistungsstarker oder skalierbarer Leistung zu bestimmen.

Mit diesem Bericht können Sie erkennen, welche Ihrer Webeigenschaften eine Abweichung oder fehlerhafte Erhöhung aufweisen, und bei Bedarf eine Fehlerbehebung durchführen. Dieser Bericht ist der nächste Schritt, nachdem Sie Ihre Zielgruppe identifiziert haben, die für den [!UICONTROL Segment Performance] Bericht von Interesse ist, um sicherzustellen, dass die starke oder schlechte Leistung, die Sie auf der Registerkarte gesehen haben, im Laufe der Zeit konsistent ist [!UICONTROL Segment Performance] .

## Verwenden des Segmenttrend-Berichts {#using-the-report}

Wechsel zwischen Segmenten **[!UICONTROL Mapped]** und **[!UICONTROL Unmapped]** zur Auswahl, die einem Ziel zugeordnet sind oder nicht. Wählen Sie **[!UICONTROL All]** diese Option, um alle Segmente in den Bericht einzubeziehen.

Passen Sie das Lookback-Fenster mit dem **[!UICONTROL Date Through]** Schieberegler an.

Klicken Sie auf eines der Segmente unter dem **[!UICONTROL Date Through]** Schieberegler, um die Option aufzurufen, um nur dieses Segment im Bericht zu belassen oder auszuschließen.

Verwenden Sie das **[!UICONTROL Line Item]** Dropdownfeld, um die Eigenschaften in Ihrem Portfolio auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie im **[!UICONTROL Segment Data Source]** Dropdownfeld die Datenquellen mit den Segmenten aus, die Sie im Bericht sehen möchten.

Verwenden Sie das **[!UICONTROL Segment]** Dropdownfeld, um auszuwählen, welche Segmente Sie im Bericht sehen möchten.

>[!IMPORTANT]
>
>Bei Aktivierung [!UICONTROL Audience Optimization for Publishers]müssen Sie beschreibende Metadaten für [!UICONTROL Line Item] IDs einschließen, wie in Schritt 3 des [Imports von DFP-Datendateien in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)beschrieben. Auf diese Weise stellen Sie sicher, dass die Webeigenschaft im Bericht [!UICONTROL Line Item] anstelle der [!UICONTROL Line Item] ID detailliert beschrieben wird.

## Interpretieren der Ergebnisse {#interpreting-results}

Der [!UICONTROL Segment Trend] Bericht gibt Daten in einem Liniendiagramm nur für einen Zeitraum von 14 Tagen zurück. In diesem Beispiel zeigt der Bericht Impressions- und Clickthrough-Trends für eine Reihe von zugeordneten und nicht zugeordneten Segmenten an.

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
   <td colname="col1"> <p><span class="wintitle"> Segmentspezifische</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Segmentmitglieder innerhalb der letzten 30 Tage. </p> </td> 
  </tr> 
 </tbody> 
</table>

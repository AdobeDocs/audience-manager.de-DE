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


# Segmenttrendbericht{#segment-trend-report}

Der Segmenttrendbericht gibt Daten zu Impressionen und Durchklickraten von zugeordneten und nicht zugeordneten Segmenten im Zeitverlauf zurück.

Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und an ein Ziel für das Targeting senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht an ein Ziel für das Targeting gesendet haben.

Vergleichen Sie Trends und Volumen für Ihre ausgewählten Metriken, um ein besseres Bild darüber zu erhalten, wie sich Ihre Zielgruppen im Laufe der Zeit verhalten.

## Nutzungsszenario {#use-cases}

Verwenden Sie den [!UICONTROL Segment Trend] Bericht, um die Leistung eines Segments im Laufe der Zeit zu überprüfen und Trends anhand einer starken Leistung oder Skalierung zu bestimmen.

Mit diesem Bericht können Sie erkennen, welche Ihrer Webeigenschaften eine falsche oder fehlerhafte Steigerung und Fehlerbehebung zeigen. Dieser Bericht ist der nächste Schritt, nachdem Sie die Zielgruppe im [!UICONTROL Segment Performance] Bericht identifiziert haben, um sicherzustellen, dass die hohe oder schlechte Leistung in der [!UICONTROL Segment Performance] Registerkarte im Laufe der Zeit konsistent ist.

## Verwenden des Segmenttrendberichts {#using-the-report}

Wechsel zwischen **[!UICONTROL Mapped]** und **[!UICONTROL Unmapped]** zur Auswahl von Segmenten, die einem Ziel zugeordnet sind oder nicht. Wählen Sie diese Option, um **[!UICONTROL All]** alle Segmente in den Bericht aufzunehmen.

Passen Sie das Look-Back-Fenster mit **[!UICONTROL Date Through]** dem Schieberegler an.

Klicken Sie auf eines der Segmente unter dem **[!UICONTROL Date Through]** Schieberegler, um die Option aufzurufen, um nur dieses Segment im Bericht zu belassen oder auszuschließen.

Wählen **[!UICONTROL Line Item]** Sie die Eigenschaften in Ihrem Portfolio aus, für die Sie Informationen zurückgeben möchten.

Wählen Sie in der **[!UICONTROL Segment Data Source]** Dropdown-Liste die Datenquellen aus, die die Segmente enthalten, die im Bericht angezeigt werden sollen.

Verwenden Sie die **[!UICONTROL Segment]** Dropdownliste, um auszuwählen, welche Segmente im Bericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Bei Aktivierung [!UICONTROL Audience Optimization for Publishers]müssen Sie beschreibende Metadaten für [!UICONTROL Line Item] IDs einbeziehen, wie in Schritt 3 von [DFP-Datendateien in Audience Manager importieren](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)beschrieben. Dadurch stellen Sie sicher, dass der Bericht die Webeigenschaft anstelle [!UICONTROL Line Item] der [!UICONTROL Line Item] ID detailliert ausführt.

## Interpretieren der Ergebnisse {#interpreting-results}

Der [!UICONTROL Segment Trend] Bericht gibt Daten in einem Liniendiagramm nur für ein 14-Tage-Intervall zurück. In diesem Beispiel zeigt der Bericht Impressionen und Durchklicktrends für eine Gruppe zugeordneter und nicht zugeordneter Segmente.

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

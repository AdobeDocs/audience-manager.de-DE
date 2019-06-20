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


# Segmentleistungsbericht{#segment-performance-report}

Der Bericht &quot;Segmentleistung&quot; vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Real-Time Segment Uniques.

Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und an ein Ziel für das Targeting senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht an ein Ziel für das Targeting gesendet haben.

Beim Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und überflüssige Segmente suchen, die Sie möglicherweise an ein Ziel für Targeting senden möchten.

## Nutzungsszenarios {#use-cases}

Mit dem [!UICONTROL Segment Performance] Bericht können Sie:

* Identifizieren Sie zugeordnete Zielgruppensegmente, die eine Skalierung oder Leistung bringen.
* Identifizieren Sie nicht zugeordnete Segmente, die in zukünftigen Kampagnen eingeführt werden sollen, basierend auf dem Beitrag einer Zielgruppe zur bisherigen Leistung.

## Verwenden des Segmentleistungsberichts {#using-segment-performance-report}

Wechsel zwischen **[!UICONTROL Mapped]** und **[!UICONTROL Unmapped]** zur Auswahl von Segmenten, die einem Ziel zugeordnet sind oder nicht. Wählen Sie diese Option, um **[!UICONTROL All]** alle Segmente in den Bericht aufzunehmen.

Verwenden Sie den Steuerumfang **für Tagesbereich** und **Datum,** um den Look-Back-Bereich anzupassen. Beachten Sie, dass der 7-Tage- und 30-Tage-Suchzeitraum nur für Sonntag verfügbar sind.

Verwenden Sie die **[!UICONTROL Line Item]** Dropdownfeld, um die Webeigenschaften auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie in der **[!UICONTROL Segment Data Source]** Dropdown-Liste die Datenquellen aus, die die Segmente enthalten, die im Bericht angezeigt werden sollen.

Verwenden Sie die **[!UICONTROL Segment]** Dropdownliste, um auszuwählen, welche Segmente im Bericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Bei Aktivierung [!UICONTROL Audience Optimization for Publishers]müssen Sie beschreibende Metadaten hinzufügen, [!UICONTROL Line Item IDs]wie in Schritt 3 von [DFP-Datendateien in Audience Manager importieren](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)beschrieben. Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft anstelle [!UICONTROL Line Item] von &quot;und [!UICONTROL Line Item ID]«ausführt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Segment Performance] Bericht könnte wie folgt aussehen. Klicken Sie in Ihrem Bericht auf ein Punktdiagramm, um die zugrunde liegenden Daten anzuzeigen. Weitere Informationen finden Sie unter Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col2"> <p>Die tatsächliche Anzahl individueller Besucher, die in Echtzeit für den angegebenen Zeitraum angesehen wurden und für das Segment qualifiziert waren, wenn sie von <span class="keyword"> Audience Manager gesehen</span>wurden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## So lesen Sie die zugeordneten Segmentergebnisse {#read-mapped-segment}

Die Position Ihrer zugeordneten Segmente in einem Bericht kann Ihnen sehr viel darüber informieren, welche Segmente gute Leistungen bringen und wo Sie möglicherweise einige Anpassungen vornehmen müssen.

Zum Lesen des Berichts ist es hilfreich, die Ergebnisse in vier Abschnitte mit imaginären Zeilen (Rot) und den im Beispielbericht unten stehenden Kategorien zu unterteilen. Die Beschriftungen im Beispiel können Ihnen dabei helfen, die Segmentleistung zu verstehen und auf diese Ergebnisse zu reagieren.

![](assets/publisher_segment_performance_mapped.png)

## So lesen Sie Ihre nicht zugeordneten Segmentergebnisse {#read-unmapped-segment}

Die Betrachtung nicht zugeordneter Segmente in einem [!UICONTROL Segment Performance] Bericht ist eine großartige Möglichkeit, neue Segmente zu finden, die Sie nicht für Targeting angesehen haben. Einige dieser Segmente überschreiten möglicherweise Ihre zugeordneten Segmente.

Um diesen Bericht zu lesen, können Sie die Ergebnisse in vier Abschnitte mit imaginären Zeilen (Rot) und Kategorien unterteilen, die im Beispielbericht unten aufgeführt sind.

![](assets/publisher_segment_performance_unmapped.png)

---
description: Der Segmentleistungsbericht vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Echtzeit-Segmentindividualitäten. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Der Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten hilft Ihnen, vorhandene Kampagnen zu optimieren und übersehene Segmente zu finden, die Sie zum Targeting an ein Ziel senden möchten.
seo-description: Der Segmentleistungsbericht vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Echtzeit-Segmentindividualitäten. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Der Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten hilft Ihnen, vorhandene Kampagnen zu optimieren und übersehene Segmente zu finden, die Sie zum Targeting an ein Ziel senden möchten.
seo-title: Segmentleistungsbericht
solution: Audience Manager
title: Segmentleistungsbericht
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segmentleistungsbericht{#segment-performance-report}

Der Segmentleistungsbericht vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Echtzeit-Segmentindividualitäten.

Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde.

Der Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten hilft Ihnen, vorhandene Kampagnen zu optimieren und übersehene Segmente zu finden, die Sie zum Targeting an ein Ziel senden möchten.

## Nutzungsszenarios {#use-cases}

Mit dem [!UICONTROL Segment Performance] Bericht können Sie:

* Identifizieren Sie zugeordnete Zielgruppensegmente, die Skalierung oder Leistung fördern.
* Identifizieren Sie nicht zugeordnete Segmente, die Sie in zukünftige Kampagnen einführen möchten, basierend auf dem Beitrag einer Zielgruppe zur Performance in der Vergangenheit.

## Verwenden des Segmentleistungsberichts {#using-segment-performance-report}

Wechsel zwischen Segmenten **[!UICONTROL Mapped]** und **[!UICONTROL Unmapped]** zur Auswahl, die einem Ziel zugeordnet sind oder nicht. Wählen Sie **[!UICONTROL All]** diese Option, um alle Segmente in den Bericht einzubeziehen.

Passen Sie den **Rückblickbereich** mit den Steuerelementen **"Zeitraum bis** Ende"an. Beachten Sie, dass die 7- und 30-Tage-Rückblickzeit nur für Sonntagsdaten verfügbar ist.

Verwenden Sie das **[!UICONTROL Line Item]** Dropdownfeld, um die Webeigenschaften auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie im **[!UICONTROL Segment Data Source]** Dropdownfeld die Datenquellen mit den Segmenten aus, die Sie im Bericht sehen möchten.

Verwenden Sie das **[!UICONTROL Segment]** Dropdownfeld, um auszuwählen, welche Segmente Sie im Bericht sehen möchten.

>[!IMPORTANT]
>
>Bei Aktivierung [!UICONTROL Audience Optimization for Publishers]müssen Sie beschreibende Metadaten für [!UICONTROL Line Item IDs]angeben, wie in Schritt 3 des [Imports von DFP-Datendateien in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)beschrieben. Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft [!UICONTROL Line Item] anstelle der [!UICONTROL Line Item ID]Eigenschaft detailliert beschreibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Segment Performance] Bericht könnte dem unten stehenden ähneln. Klicken Sie in Ihrem Bericht auf eine Blase, um die zugrunde liegenden Daten anzuzeigen. Siehe Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col1"> <p>Linienelement </p> </td> 
   <td colname="col2"> <p>Die Webeigenschaft, für die Sie diesen Bericht sehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Klicks </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft auf Elemente in Ihrer Webeigenschaft geklickt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eindrücke </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihrem Bestand ausgesetzt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Clickthrough-Rate. </p> <p>Diese Metrik gibt den Prozentsatz der Impressionen, gefolgt von Klicks, wieder. Dividieren Sie Klicks durch Impressionen, um diese Metrik zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Population von Echtzeit-Segmenten </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl individueller Besucher, die in Echtzeit über den angegebenen Zeitraum hinweg gesehen wurden und die zum Zeitpunkt der Anzeige durch <span class="keyword"> Audience Manager</span>für das Segment qualifiziert waren. </p> </td> 
  </tr> 
 </tbody> 
</table>

## So lesen Sie die zugeordneten Segmentergebnisse {#read-mapped-segment}

Die Position der zugeordneten Segmente in einem Bericht kann Ihnen sehr gut erklären, welche Segmente gut abschneiden und wo Sie eventuell Anpassungen vornehmen müssen.

Zum Lesen des Berichts ist es hilfreich, die Ergebnisse in vier Abschnitte mit imaginären Zeilen (in rot) und den Kategorien zu unterteilen, die im Beispielbericht unten aufgeführt sind. Die Beschriftungen im Beispiel können Ihnen helfen, die Segmentleistung und die Reaktion auf diese Ergebnisse zu verstehen.

![](assets/publisher_segment_performance_mapped.png)

## Lesen der nicht zugeordneten Segmentergebnisse {#read-unmapped-segment}

Wenn Sie sich nicht zugeordnete Segmente in einem [!UICONTROL Segment Performance] Bericht ansehen, können Sie auf diese Weise neue Segmente finden, die Sie für das Targeting nicht berücksichtigt haben. Tatsächlich können einige dieser Segmente Ihre zugeordneten Segmente übertreffen.

Zum Lesen dieses Berichts hilft es, die Ergebnisse in vier Abschnitte mit imaginären Zeilen (in rot) und Kategorien zu unterteilen, die im folgenden Beispielbericht dargestellt werden.

![](assets/publisher_segment_performance_unmapped.png)

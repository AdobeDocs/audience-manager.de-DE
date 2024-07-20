---
description: Der Bericht zur Segmentleistung vergleicht zugeordnete und nicht zugeordnete Segmente anhand von Impressionen und Uniques des Echtzeit-Segments. Ein gemapptes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben. Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb von und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Segmentleistungsbericht für Herausgeber
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# Segmentleistungsbericht{#segment-performance-report}

Der Bericht zur Segmentleistung vergleicht zugeordnete und nicht zugeordnete Segmente anhand von Impressionen und Uniques des Echtzeit-Segments.

Ein gemapptes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben.

Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb von und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.

## Nutzungsszenarios {#use-cases}

Mit dem Bericht [!UICONTROL Segment Performance] können Sie:

* Ermitteln Sie zugeordnete Zielgruppensegmente, die die Skalierung oder Leistung steigern.
* Identifizieren Sie nicht zugeordnete Segmente, die in zukünftige Kampagnen eingeführt werden sollen, basierend auf dem Beitrag einer Zielgruppe zur früheren Performance.

## Verwenden des Segmentleistungsberichts {#using-segment-performance-report}

Zwischen **[!UICONTROL Mapped]** und **[!UICONTROL Unmapped]** wechseln, um Segmente auszuwählen, die einem Ziel zugeordnet sind oder nicht. Wählen Sie **[!UICONTROL All]** aus, um alle Ihre Segmente in den Bericht aufzunehmen.

Verwenden Sie die Steuerelemente **Tagesbereich** und **Datum bis** , um Ihren Rückblickbereich anzupassen. Beachten Sie, dass die 7- und 30-tägigen Rückblickperioden nur für Sonntagsdaten verfügbar sind.

Verwenden Sie das Dropdown-Feld **[!UICONTROL Line Item]** , um die Webeigenschaften auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie in der Dropdown-Liste **[!UICONTROL Segment Data Source]** die Datenquellen aus, die die Segmente enthalten, die Sie im Bericht sehen möchten.

Verwenden Sie das Dropdownfeld **[!UICONTROL Segment]** , um auszuwählen, welche Segmente im Bericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Beim Aktivieren von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Line Item IDs] einfügen, wie in Schritt 3 von [Importieren von Google Ad Manager-Datendateien (ehemals DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md) beschrieben. Dadurch stellen Sie sicher, dass der Bericht die Webeigenschaft als [!UICONTROL Line Item] anstelle von [!UICONTROL Line Item ID] detailliert beschreibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Segment Performance] -Bericht könnte dem unten stehenden ähneln. Klicken Sie in Ihrem Bericht auf eine Blase, um die zugrunde liegenden Daten anzuzeigen. Weitere Informationen finden Sie in der Tabelle unter dem Beispielbericht.

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
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft auf Elemente in Ihrer Webeigenschaft geklickt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eindrücke </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihrem Inventar ausgesetzt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Clickthrough-Rate. </p> <p>Diese Metrik überträgt den Prozentsatz der Impressionen, gefolgt von Klicks. Klicks durch Impressionen teilen , um diese Metrik zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segmentpopulation in Echtzeit </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl Unique Visitors, die in Echtzeit für den angegebenen Zeitraum gesehen wurden und die zum Zeitpunkt der Anzeige durch <span class="keyword"> Audience Manager</span> für das Segment qualifiziert waren. </p> </td> 
  </tr> 
 </tbody> 
</table>

## So lesen Sie die zugeordneten Segmentergebnisse {#read-mapped-segment}

Die Position Ihrer zugeordneten Segmente in einem Bericht kann Ihnen Aufschluss darüber geben, welche Segmente eine gute Leistung erbringen und wo Sie möglicherweise einige Anpassungen vornehmen müssen.

Zum Lesen des Berichts ist es hilfreich, die Ergebnisse in vier Abschnitte mit imaginären Zeilen (in Rot) und den im Beispielbericht unten angezeigten Kategorien zu unterteilen. Die Titel im Beispiel können Ihnen dabei helfen, die Segmentleistung und die Reaktion auf diese Ergebnisse zu verstehen.

![](assets/publisher_segment_performance_mapped.png)

## So lesen Sie die nicht zugeordneten Segmentergebnisse {#read-unmapped-segment}

Wenn Sie sich nicht zugeordnete Segmente in einem [!UICONTROL Segment Performance] -Bericht ansehen, können Sie neue Segmente finden, die Sie für das Targeting nicht berücksichtigt haben. Tatsächlich können einige dieser Segmente Ihre zugeordneten Segmente übertreffen.

Zum Lesen dieses Berichts ist es hilfreich, die Ergebnisse in vier Abschnitte mit imaginären Zeilen (in Rot) und Kategorien zu unterteilen, die im Beispielbericht unten angezeigt werden.

![](assets/publisher_segment_performance_unmapped.png)

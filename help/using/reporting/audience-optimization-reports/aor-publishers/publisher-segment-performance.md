---
description: Der Segmentleistungsbericht vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Echtzeit-Segmentindividualitäten. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.
seo-description: Der Segmentleistungsbericht vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Echtzeit-Segmentindividualitäten. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.
seo-title: Segmentleistungsbericht
solution: Audience Manager
title: Segmentleistungsbericht
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 1%

---


# Segmentleistungsbericht{#segment-performance-report}

Der Segmentleistungsbericht vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Echtzeit-Segmentindividualitäten.

Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde.

Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.

## Nutzungsszenarios {#use-cases}

Mit dem [!UICONTROL Segment Performance] Bericht haben Sie folgende Möglichkeiten:

* Identifizieren Sie zugeordnete Audiencen, die Skalierungs- oder Leistungssteigerungen bewirken.
* Identifizieren Sie nicht zugeordnete Segmente, die Sie in zukünftigen Kampagnen einführen möchten, basierend auf dem Beitrag einer Audience zur Performance in der Vergangenheit.

## Verwenden des Segmentleistungsberichts {#using-segment-performance-report}

Wechsel zwischen Segmenten **[!UICONTROL Mapped]** und **[!UICONTROL Unmapped]** zur Auswahl, die einem Ziel zugeordnet sind oder nicht. Wählen Sie **[!UICONTROL All]** diese Option, um alle Segmente in den Bericht einzubeziehen.

Passen Sie den **Rückblickbereich** mit den Steuerelementen **&quot;Zeitraum bis** Ende&quot;an. Beachten Sie, dass die 7- und 30-Tage-Rückblickzeit nur für Sonntagsdaten verfügbar ist.

Verwenden Sie das **[!UICONTROL Line Item]** Dropdownfeld, um die Webeigenschaften auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie im **[!UICONTROL Segment Data Source]** Dropdown-Feld die Datenquellen mit den Segmenten aus, die Sie im Bericht sehen möchten.

Verwenden Sie das **[!UICONTROL Segment]** Dropdownfeld, um auszuwählen, welche Segmente Sie im Bericht sehen möchten.

>[!IMPORTANT]
>
>Bei Aktivierung [!UICONTROL Audience Optimization for Publishers]müssen Sie beschreibende Metadaten für [!UICONTROL Line Item IDs]angeben, wie in Schritt 3 von &quot;DFP-Datendateien in Audience Manager [importieren&quot;beschrieben](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft [!UICONTROL Line Item] anstelle der [!UICONTROL Line Item ID]Eigenschaft detailliert beschreibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Segment Performance] Bericht könnte dem unten stehenden ähneln. Klicken Sie in Ihrem Bericht auf einen Punkt, um die zugrunde liegenden Daten Ansicht. Siehe Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col2"> <p>Die tatsächliche Anzahl individueller Besucher, die in Echtzeit für den angegebenen Zeitraum gesehen wurden und die zum Zeitpunkt, zu dem sie vom <span class="keyword"> Audience Manager</span>gesehen wurden, für das Segment qualifiziert waren. </p> </td> 
  </tr> 
 </tbody> 
</table>

## So lesen Sie die zugeordneten Segmentergebnisse {#read-mapped-segment}

Die Position der zugeordneten Segmente in einem Bericht kann Ihnen sehr gut erklären, welche Segmente gut abschneiden und wo Sie eventuell Anpassungen vornehmen müssen.

Zum Lesen des Berichts ist es hilfreich, die Ergebnisse in vier Abschnitte mit imaginären Zeilen (in Rot) und den Kategorien im Beispielbericht unten aufzuteilen. Die Beschriftungen im Beispiel können Ihnen dabei helfen, die Segmentleistung und die Reaktion auf diese Ergebnisse zu verstehen.

![](assets/publisher_segment_performance_mapped.png)

## Lesen der nicht zugeordneten Segmentergebnisse {#read-unmapped-segment}

Wenn Sie sich nicht zugeordnete Segmente in einem [!UICONTROL Segment Performance] Bericht ansehen, können Sie auf diese Weise neue Segmente finden, die Sie für das Targeting nicht berücksichtigt haben. Tatsächlich können einige dieser Segmente Ihre zugeordneten Segmente übertreffen.

Zum Lesen dieses Berichts ist es hilfreich, die Ergebnisse in vier Abschnitte mit imaginären Zeilen (in Rot) und Kategorien zu unterteilen, die im folgenden Beispielbericht dargestellt werden.

![](assets/publisher_segment_performance_unmapped.png)

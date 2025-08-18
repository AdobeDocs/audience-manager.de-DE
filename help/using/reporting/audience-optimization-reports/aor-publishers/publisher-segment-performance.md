---
description: Der Bericht zur Segmentleistung vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressions und eindeutige Segmentwerte in Echtzeit. Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber noch nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben. Der Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten hilft Ihnen, bestehende Kampagnen zu optimieren und übersehene Segmente zu finden, die Sie möglicherweise zur Zielgruppenbestimmung an ein Ziel senden möchten.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Bericht zur Segmentleistung für Herausgeber
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# Bericht zur Segmentleistung{#segment-performance-report}

Der Bericht zur Segmentleistung vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressions und eindeutige Segmentwerte in Echtzeit.

Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber noch nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben.

Der Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten hilft Ihnen, bestehende Kampagnen zu optimieren und übersehene Segmente zu finden, die Sie möglicherweise zur Zielgruppenbestimmung an ein Ziel senden möchten.

## Nutzungsszenarios {#use-cases}

Der [!UICONTROL Segment Performance] Bericht bietet folgende Möglichkeiten:

* Identifizieren Sie zugeordnete Zielgruppensegmente, die Skalierbarkeit oder Leistung fördern.
* Identifizieren Sie nicht zugeordnete Segmente, die in zukünftige Kampagnen eingeführt werden sollen, basierend auf dem Beitrag einer Audience zur bisherigen Leistung.

## Verwenden des Segmentleistungsberichts {#using-segment-performance-report}

Zwischen **[!UICONTROL Mapped]** und **[!UICONTROL Unmapped]** wechseln, um Segmente auszuwählen, die einem Ziel zugeordnet sind oder nicht. Wählen Sie **[!UICONTROL All]** aus, um alle Segmente in den Bericht aufzunehmen.

Verwenden Sie die Steuerelemente **Tagesbereich** und **Bis-Datum** um Ihren Lookback-Bereich anzupassen. Beachten Sie, dass die 7-tägigen und 30-tägigen Lookback-Zeiträume nur für Sonntagsdaten verfügbar sind.

Verwenden Sie das Dropdown-Feld **[!UICONTROL Line Item]** , um die Web-Eigenschaften auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie in der Dropdown-Liste **[!UICONTROL Segment Data Source]** die Datenquellen aus, die die Segmente enthalten, die Sie im Bericht sehen möchten.

Verwenden Sie das Dropdown-Feld **[!UICONTROL Segment]** , um die Segmente auszuwählen, die im Bericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Bei der Aktivierung von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Line Item IDs] einbeziehen, wie in Schritt 3 von [Importieren von Datendateien des Google Ad Manager (ehemals DFP) in Audience Manager beschrieben](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Auf diese Weise können Sie sicherstellen, dass der Bericht die Web-Eigenschaft als [!UICONTROL Line Item] anstelle des [!UICONTROL Line Item ID] angibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Segment Performance] könnte in etwa wie der unten stehende aussehen. Klicken Sie in Ihrem Bericht auf eine Blase, um die zugrunde liegenden Daten anzuzeigen. Weitere Informationen finden Sie in den Beschreibungen in der Tabelle unten im Beispielbericht.

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
   <td colname="col2"> <p>Die Web-Eigenschaft, für die dieser Bericht angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Klicks </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft auf Elemente in Ihrer Web-Eigenschaft geklickt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eindrücke </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihrem Inventar ausgesetzt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Clickthrough-Rate </p> <p>Diese Metrik gibt den Prozentsatz der Impressionen weiter, gefolgt von Klicks. Klicks durch Impressionen teilen, um diese Metrik zu erhalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Echtzeit-Segmentpopulation </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl der Unique Visitors, die für den angegebenen Zeitraum in Echtzeit angezeigt wurden und die für das Segment zu dem Zeitpunkt qualifiziert waren, als sie von <span class="keyword"> Audience Manager gesehen wurden</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lesen der Ergebnisse zugeordneter Segmente {#read-mapped-segment}

Die Position Ihrer zugeordneten Segmente in einem Bericht kann Ihnen Aufschluss darüber geben, welche Segmente eine gute Leistung erzielen und wo Sie möglicherweise Anpassungen vornehmen müssen.

Um den Bericht zu lesen, ist es hilfreich, die Ergebnisse in vier Abschnitte mit imaginären Linien (in rot) und die im folgenden Beispielbericht angezeigten Kategorien zu unterteilen. Die Beschriftungen im Beispiel können Ihnen dabei helfen, die Segmentleistung zu verstehen und zu verstehen, wie Sie auf diese Ergebnisse reagieren sollen.

![](assets/publisher_segment_performance_mapped.png)

## Lesen der nicht zugeordneten Segmentergebnisse {#read-unmapped-segment}

Das Anzeigen nicht zugeordneter Segmente in einem [!UICONTROL Segment Performance] Bericht ist eine hervorragende Möglichkeit, neue Segmente zu finden, die Sie für das Targeting nicht in Betracht gezogen haben. Tatsächlich können einige dieser Segmente Ihre zugeordneten Segmente übertreffen.

Um diesen Bericht zu lesen, hilft es, die Ergebnisse in vier Abschnitte mit imaginären Linien (in rot) und Kategorien zu unterteilen, die im folgenden Beispielbericht angezeigt werden.

![](assets/publisher_segment_performance_unmapped.png)

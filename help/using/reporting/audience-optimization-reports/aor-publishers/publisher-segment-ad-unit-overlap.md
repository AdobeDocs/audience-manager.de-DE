---
description: Der Bericht "Segmentüberschneidung zu Anzeigeneinheiten"wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten und Audience Manager-Segmenten hervorhebt.
seo-description: Der Bericht "Segmentüberschneidung zu Anzeigeneinheiten"wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten und Audience Manager-Segmenten hervorhebt.
seo-title: Segmentüberschneidung in Anzeigeneinheit
solution: Audience Manager
title: Überschneidung von Segment zu Anzeigeneinheit
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---


# Überschneidung von Segment zu Anzeigeneinheit{#segment-to-ad-unit-overlap}

Der Bericht &quot;Segmentüberschneidung zu Anzeigeneinheiten&quot;wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten und Audience Manager-Segmenten hervorhebt.

## Nutzungsszenario {#use-cases}

Mit dem [!UICONTROL Segment to Ad Unit Overlap] Bericht können Sie verstehen, welche Audiencen Ihre Webeigenschaften besuchen. Der Bericht zeigt die Überschneidung zwischen Segmentmitgliedern und die Anzahl der Besucher Ihrer Webeigenschaften an. [!DNL Audience Manager] Eine höhere Überschneidung bedeutet, dass viele Mitglieder eines Segments Ihre Webeigenschaft besuchen.

## Verwenden des Berichts &quot;Segmentüberschneidung zu Anzeigeneinheiten&quot; {#using-the-report}

Verwenden Sie die **[!UICONTROL Top N Ad Units]** und **[!UICONTROL Top N Segments]** -Steuerelemente, um die gewünschte Anzahl von Anzeigeneinheiten und Segmenten für die Überschneidung auszuwählen. Sie können jeweils maximal 100 Elemente auswählen.

Passen Sie den **Rückblickbereich** mit den Steuerelementen **&quot;Zeitraum bis** Ende&quot;an. Beachten Sie, dass die 7- und 30-Tage-Rückblickzeit nur für Sonntagsdaten verfügbar ist.

Verwenden Sie die **[!UICONTROL Segment Name]** und die **[!UICONTROL Ad Unit]** Kästchen, um beliebige Segmente und Anzeigeneinheiten zu filtern.

>[!IMPORTANT]
>
>Bei Aktivierung [!UICONTROL Audience Optimization for Publishers]müssen Sie beschreibende Metadaten für [!UICONTROL Ad Unit IDs]angeben, wie in Schritt 3 von &quot;DFP-Datendateien in Audience Manager [importieren&quot;beschrieben](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft [!UICONTROL Ad Unit] anstelle der [!UICONTROL Ad Unit ID]Eigenschaft detailliert beschreibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Segment to Ad Unit Overlap] Bericht könnte dem unten stehenden ähneln. Bewegen Sie den Mauszeiger über eine Zelle, um weitere Informationen zu dieser Überschneidung zu erhalten. Siehe Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzeigeneinheit </span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Bestandteils. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentanzahl individueller Echtzeit</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der individuellen Besucher, die in Echtzeit für den angegebenen Zeitraum gesehen wurden und die zum Zeitpunkt, zu dem sie vom <span class="keyword"> Audience Manager</span>gesehen wurden, für das Segment qualifiziert waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl individueller Anzeigeneinheiten</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Ihrer Besucher für diese bestimmte Anzeigeneinheit. Diese Informationen werden aus den DFP-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl individueller Überschneidungen</span> </p> </td> 
   <td colname="col2"> <p>Die Mitglieder Ihres Segments, die dem Anzeigenstückelement ausgesetzt waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überschneidungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen Anzeigen- und Segmentpopulationen. Dies ist die Anzahl <span class="wintitle"> individueller</span>Überschneidungen, ausgedrückt als Prozentsatz der <span class="wintitle"> Segment-Echtzeit-Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>


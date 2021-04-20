---
description: Der Bericht "Segmentüberschneidung zu Anzeigeneinheiten"wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten und Audience Manager-Segmenten hervorhebt.
seo-description: Der Bericht "Segmentüberschneidung zu Anzeigeneinheiten"wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten und Audience Manager-Segmenten hervorhebt.
seo-title: Überlagerung von Segmenten mit Anzeigeneinheiten
solution: Audience Manager
title: Überlagerung von Segmenten mit Anzeigeneinheiten
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# Überlagerung von Segmenten mit Anzeigeneinheiten{#segment-to-ad-unit-overlap}

Der Bericht &quot;Segmentüberschneidung zu Anzeigeneinheiten&quot;wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten und Audience Manager-Segmenten hervorhebt.

## Anwendungsfall {#use-cases}

Mit dem Bericht [!UICONTROL Segment to Ad Unit Overlap] können Sie verstehen, welche Audiencen Ihre Webeigenschaften besuchen. Der Bericht zeigt die Überschneidung zwischen Ihren [!DNL Audience Manager]-Segmenten und die Anzahl der Besucher Ihrer Webeigenschaften an. Eine höhere Überschneidung bedeutet, dass viele Mitglieder eines Segments Ihre Webeigenschaft besuchen.

## Verwenden des Berichts &quot;Segment zu Anzeigeneinheit - Überschneidung&quot; {#using-the-report}

Verwenden Sie die Steuerelemente **[!UICONTROL Top N Ad Units]** und **[!UICONTROL Top N Segments]**, um die gewünschte Anzahl von Anzeigeneinheiten und Segmenten für die Überschneidung auszuwählen. Sie können jeweils maximal 100 Elemente auswählen.

Mit den Steuerelementen **Zeitraum** und **Datum bis** können Sie Ihren Lookback-Bereich anpassen. Beachten Sie, dass die 7- und 30-Tage-Rückblickzeit nur für Sonntagsdaten verfügbar ist.

Verwenden Sie die Felder **[!UICONTROL Segment Name]** und **[!UICONTROL Ad Unit]**, um beliebige Segmente und Anzeigeneinheiten zu filtern.

>[!IMPORTANT]
>
>Wenn Sie [!UICONTROL Audience Optimization for Publishers] aktivieren, müssen Sie beschreibende Metadaten für [!UICONTROL Ad Unit IDs] einfügen, wie in Schritt 3 von [Google Ad Manager (ehemals DFP)-Datendateien in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md) beschrieben. Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft als [!UICONTROL Ad Unit] und nicht als [!UICONTROL Ad Unit ID] bezeichnet.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Segment to Ad Unit Overlap]-Bericht könnte ähnlich wie der unten stehende aussehen. Bewegen Sie den Mauszeiger über eine Zelle, um weitere Informationen zu dieser Überschneidung zu erhalten. Siehe Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col1"> <p><span class="wintitle"> Anzeigeneinheit  </span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Bestandteils. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segmentanzahl individueller Echtzeit</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der eindeutigen Besucher, die in Echtzeit für den angegebenen Zeitraum gesehen wurden und die zum Zeitpunkt, zu dem sie von <span class="keyword"> Audience Manager</span> gesehen wurden, für das Segment qualifiziert waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl individueller Anzeigeneinheiten</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Ihrer Besucher für diese bestimmte Anzeigeneinheit. Diese Informationen werden aus den Google Ad Manager-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl individueller Überschneidungen</span> </p> </td> 
   <td colname="col2"> <p>Die Mitglieder Ihres Segments, die dem Anzeigenstückelement ausgesetzt waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überschneidungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen Anzeigen- und Segmentpopulationen. Dies ist der Wert für die Anzahl individueller Überschneidungen <span class="wintitle">, ausgedrückt als Prozentsatz von <span class="wintitle"> Segment Real Time Uniques</span>.</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

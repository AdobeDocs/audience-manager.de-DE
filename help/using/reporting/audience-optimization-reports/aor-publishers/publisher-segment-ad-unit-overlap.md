---
description: Der Bericht zur Überschneidung von Segmenten in Anzeigenblöcken wird als Wärmediagramm angezeigt, das die hohen und niedrigen Überschneidungen zwischen Anzeigenblöcken und Audience Manager-Segmenten hervorhebt.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: Überschneidung von Segmenten zu Werbeeinheiten
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# Überschneidung von Segmenten zu Werbeeinheiten{#segment-to-ad-unit-overlap}

Der Bericht zur Überschneidung von Segmenten in Anzeigenblöcken wird als Wärmediagramm angezeigt, das die hohen und niedrigen Überschneidungen zwischen Anzeigenblöcken und Audience Manager-Segmenten hervorhebt.

## Anwendungsfall {#use-cases}

Mit dem [!UICONTROL Segment to Ad Unit Overlap] Bericht können Sie verstehen, welche Zielgruppen Ihre Web-Eigenschaften besuchen. Der Bericht zeigt die Überschneidung zwischen den Mitgliedern Ihrer [!DNL Audience Manager] Segmente und die Anzahl der Besucher Ihrer Web-Eigenschaften an. Eine höhere Überschneidung bedeutet, dass viele Mitglieder eines Segments Ihre Web-Eigenschaft besuchen.

## Verwenden des Berichts zur Segmentüberschneidung für das Hinzufügen von Einheiten {#using-the-report}

Verwenden Sie die Steuerelemente **[!UICONTROL Top N Ad Units]** und **[!UICONTROL Top N Segments]** , um die gewünschte Anzahl von Anzeigeneinheiten und Segmenten für die Überschneidung auszuwählen. Sie können maximal 100 Elemente für jeden auswählen.

Verwenden Sie die Steuerelemente **Tagesbereich** und **Bis-Datum** um Ihren Lookback-Bereich anzupassen. Beachten Sie, dass die 7-tägigen und 30-tägigen Lookback-Zeiträume nur für Sonntagsdaten verfügbar sind.

Verwenden Sie die **[!UICONTROL Segment Name]** und die **[!UICONTROL Ad Unit]**, um beliebige Segmente und Anzeigeneinheiten zu filtern.

>[!IMPORTANT]
>
>Bei der Aktivierung von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Ad Unit IDs] einbeziehen, wie in Schritt 3 von [Importieren von Datendateien des Google Ad Manager (ehemals DFP) in Audience Manager beschrieben](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Auf diese Weise können Sie sicherstellen, dass der Bericht die Web-Eigenschaft als [!UICONTROL Ad Unit] anstelle des [!UICONTROL Ad Unit ID] angibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Segment to Ad Unit Overlap] könnte in etwa wie der unten stehende aussehen. Bewegen Sie den Mauszeiger über eine beliebige Zelle, um weitere Informationen zu dieser Überschneidung zu erhalten. Weitere Informationen finden Sie in den Beschreibungen in der Tabelle unten im Beispielbericht.

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
   <td colname="col1"> <p><span class="wintitle"> Werbeeinheit </span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Inventarelements. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzahl der eindeutigen <span class="wintitle"> in Echtzeit</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Visitors, die für den angegebenen Zeitraum in Echtzeit gesehen und für das Segment zu dem Zeitpunkt qualifiziert wurden, als sie von <span class="keyword"> Audience Manager gesehen wurden</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzahl der eindeutigen <span class="wintitle"> Werbeeinheit</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Ihrer Besucher für diese spezifische Anzeigeneinheit. Diese Informationen werden aus den Google Ad Manager-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl eindeutige Überschneidungen</span> </p> </td> 
   <td colname="col2"> <p>Die Mitglieder Ihres Segments, die dem Element der Anzeigeneinheit ausgesetzt waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überschneidungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen Anzeigeneinheiten- und Segmentpopulationen. Dies ist die Anzahl der <span class="wintitle"> Überschneidungskennzeichen</span> ausgedrückt als Prozentsatz der <span class="wintitle"> Echtzeit-Kennzeichen des Segments</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

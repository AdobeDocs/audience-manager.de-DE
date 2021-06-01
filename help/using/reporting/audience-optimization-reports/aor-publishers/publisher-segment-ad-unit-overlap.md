---
description: Der Überlagerungsbericht Segment zu Anzeigeneinheit wird als Heatchart angezeigt, in dem die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten und den Segmenten der Audience Manager hervorgehoben werden.
seo-description: Der Überlagerungsbericht Segment zu Anzeigeneinheit wird als Heatchart angezeigt, in dem die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten und den Segmenten der Audience Manager hervorgehoben werden.
seo-title: Überlagerung von Segmenten mit Anzeigeneinheiten
solution: Audience Manager
title: Überlagerung von Segmenten mit Anzeigeneinheiten
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Berichte zur Zielgruppenoptimierung
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# Überlagerung von Segmenten mit Anzeigeneinheiten{#segment-to-ad-unit-overlap}

Der Überlagerungsbericht Segment zu Anzeigeneinheit wird als Heatchart angezeigt, in dem die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten und den Segmenten der Audience Manager hervorgehoben werden.

## Anwendungsfall {#use-cases}

Mit dem Bericht [!UICONTROL Segment to Ad Unit Overlap] können Sie erkennen, welche Zielgruppen Ihre Webeigenschaften besuchen. Der Bericht zeigt die Überschneidung zwischen den Mitgliedern Ihrer [!DNL Audience Manager]-Segmente und die Anzahl der Besucher Ihrer Webeigenschaften an. Eine höhere Überschneidung bedeutet, dass viele Mitglieder eines Segments Ihre Webeigenschaft besuchen.

## Überlagerungsbericht zwischen Segmenten und Anzeigeneinheiten verwenden {#using-the-report}

Verwenden Sie die Steuerelemente **[!UICONTROL Top N Ad Units]** und **[!UICONTROL Top N Segments]** , um die gewünschte Anzahl von Anzeigeneinheiten und Segmenten für die Überschneidung auszuwählen. Sie können für jedes Element eine maximale Anzahl von 100 Elementen auswählen.

Verwenden Sie die Steuerelemente **Day Range** und **Date Through** , um Ihren Lookback-Bereich anzupassen. Beachten Sie, dass die 7- und 30-tägigen Rückblickperioden nur für Sonntagsdaten verfügbar sind.

Verwenden Sie die Felder **[!UICONTROL Segment Name]** und **[!UICONTROL Ad Unit]** , um beliebige Segmente und Anzeigeneinheiten zu filtern.

>[!IMPORTANT]
>
>Beim Aktivieren von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Ad Unit IDs] einfügen, wie in Schritt 3 von [Importieren von Google Ad Manager-(ehemals DFP-)Datendateien in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md) beschrieben. Dadurch stellen Sie sicher, dass der Bericht die Webeigenschaft als [!UICONTROL Ad Unit] anstelle von [!UICONTROL Ad Unit ID] detailliert beschreibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Segment to Ad Unit Overlap] -Bericht könnte dem unten stehenden ähneln. Bewegen Sie den Mauszeiger über eine Zelle, um weitere Informationen zu dieser bestimmten Überschneidung zu erhalten. Weitere Informationen finden Sie in der Tabelle unter dem Beispielbericht.

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
   <td colname="col2"> <p>Der Name Ihres Inventarelements. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl der individuellen Segmentwerte in Echtzeit</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Unique Visitors, die in Echtzeit für den angegebenen Zeitraum angesehen wurden und die zum Zeitpunkt ihrer Anzeige durch den Audience Manager <span class="keyword"></span> für das Segment qualifiziert waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl eindeutiger Anzeigeneinheiten</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl Ihrer Besucher für diese spezifische Anzeigeneinheit. Diese Informationen werden aus den Google Ad Manager-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl der individuellen Überlagerungen</span> </p> </td> 
   <td colname="col2"> <p>Die Mitglieder Ihres Segments, die dem Anzeigeneinheiten-Element ausgesetzt waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlagerungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen Anzeigeneinheiten und Segmentpopulationen. Dies ist die <span class="wintitle"> Überlagerungsanzahl Individuelle Werte</span>, ausgedrückt als Prozentsatz der <span class="wintitle"> Echtzeit-Individuen des Segments</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

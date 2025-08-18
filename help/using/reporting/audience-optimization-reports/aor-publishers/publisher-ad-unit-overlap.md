---
description: Der Bericht zur Überschneidung von Werbeeinheiten wird als Diagramm angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Werbeeinheiten hervorhebt.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: Überschneidung der Werbeblöcke
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Überschneidung der Werbeblöcke{#ad-unit-overlap}

Der **[!UICONTROL Ad Unit Overlap]** Bericht wird als Wärmediagramm angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Werbeeinheiten hervorhebt.

## Anwendungsfall {#use-cases}

Mit dem **[!UICONTROL Ad Unit Overlap]** Bericht können Sie insight in einbinden, wo sich Ihre Zielgruppe über Ihre Web-Eigenschaften hinweg überschneidet. Der Bericht berücksichtigt Ihre 100 wichtigsten verwandten Eigenschaften und zeigt Ihnen die Überschneidung zwischen ihnen.

## Verwenden des Berichts zur Überschneidung von Werbeeinheiten {#using-the-report}

Verwenden Sie die Steuerelemente **[!UICONTROL Top N Base Ad Units]** und **[!UICONTROL Top N Overlapping Ad Units]** , um die gewünschte Anzahl von Anzeigeneinheiten für die Überschneidung auszuwählen. Sie können maximal 100 Elemente für jeden auswählen.

Verwenden Sie die Steuerelemente **Tagesbereich** und **Bis-Datum** um Ihren Lookback-Bereich anzupassen. Beachten Sie, dass die 7-tägigen und 30-tägigen Lookback-Zeiträume nur für Sonntagsdaten verfügbar sind.

Verwenden Sie die **[!UICONTROL Base Ad Unit]** und die **[!UICONTROL Overlap Ad Unit]**, um auszuwählen, welche der Anzeigeneinheiten im Überschneidungsbericht angezeigt werden soll.

>[!IMPORTANT]
>
>Bei der Aktivierung von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Ad Unit IDs] einbeziehen, wie in Schritt 3 von [Importieren von Datendateien des Google Ad Manager (ehemals DFP) in Audience Manager beschrieben](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Auf diese Weise können Sie sicherstellen, dass der Bericht die Web-Eigenschaft als [!UICONTROL Ad Unit] anstelle des [!UICONTROL Ad Unit ID] angibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Ad Unit Overlap] könnte in etwa wie der unten stehende aussehen. Bewegen Sie den Mauszeiger über eine beliebige Zelle, um weitere Informationen zu dieser Überschneidung zu erhalten. Weitere Informationen finden Sie in den Beschreibungen in der Tabelle unten im Beispielbericht.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überschneidungs-Werbeeinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Inventarelements. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. Im obigen Bild sind die Basis-Anzeigeneinheiten die Artikel 9 bis 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basis-Anzeigeneinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Inventarelements. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. Im obigen Bild sind die Basis-Anzeigeneinheiten die Artikel 1 bis 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl der eindeutigen Überschneidungen der Werbeeinheiten</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzerinnen und Benutzer, die die Elemente der Anzeigeneinheit besucht haben, 9 - 18. Diese Informationen werden aus den Google Ad Manager-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzahl <span class="wintitle"> eindeutigen Anzeigen-Basiseinheiten</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzerinnen und Benutzer, die die Elemente der Werbeeinheit besucht haben 1 - 8. Diese Informationen werden aus den Google Ad Manager-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl eindeutige Überschneidungen</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen den Benutzern, die eine <span class="wintitle"> Anzeigeneinheit für Basis-Anzeigen besucht haben</span> und <span class="wintitle"> Anzeigeneinheit für Überschneidungen</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überschneidungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen den Benutzern, die eine <span class="wintitle"> Anzeigeneinheit für Basis-Anzeigen besucht haben</span> und <span class="wintitle"> Anzeigeneinheit für Überschneidungen</span>. Dies ist die Anzahl der <span class="wintitle"> Überschneidungen</span> ausgedrückt als Prozentsatz der <span class="wintitle"> Basis-Anzeigeneinheit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

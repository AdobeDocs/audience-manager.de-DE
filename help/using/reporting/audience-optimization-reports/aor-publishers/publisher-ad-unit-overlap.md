---
description: Der Bericht "Anzeigeneinheit - Überschneidung"wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten hervorhebt.
seo-description: Der Bericht "Anzeigeneinheit - Überschneidung"wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten hervorhebt.
seo-title: Überlagerung von Anzeigeneinheiten
solution: Audience Manager
title: Überlagerung von Anzeigeneinheiten
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Berichte zur Zielgruppenoptimierung
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 3%

---

# Überlagerung von Anzeigeneinheiten{#ad-unit-overlap}

Der Bericht **[!UICONTROL Ad Unit Overlap]** wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten hervorhebt.

## Anwendungsfall {#use-cases}

Mit dem Bericht **[!UICONTROL Ad Unit Overlap]** können Sie Einblicke darin gewinnen, wo sich Ihre Audience über Ihre Webeigenschaften hinweg überschneidet. Der Bericht berücksichtigt Ihre 100 wichtigsten Eigenschaften und zeigt die Überschneidung zwischen ihnen.

## Verwenden des Überschneidungsberichts für die Anzeigeneinheit {#using-the-report}

Verwenden Sie die Steuerelemente **[!UICONTROL Top N Base Ad Units]** und **[!UICONTROL Top N Overlapping Ad Units]**, um die gewünschte Anzahl von Anzeigeneinheiten für die Überschneidung auszuwählen. Sie können jeweils maximal 100 Elemente auswählen.

Mit den Steuerelementen **Zeitraum** und **Datum bis** können Sie Ihren Lookback-Bereich anpassen. Beachten Sie, dass die 7- und 30-Tage-Rückblickzeit nur für Sonntagsdaten verfügbar ist.

Wählen Sie mit den Steuerelementen **[!UICONTROL Base Ad Unit]** und **[!UICONTROL Overlap Ad Unit]** aus, welche Ihrer Anzeigeneinheiten im Überschneidungsbericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Wenn Sie [!UICONTROL Audience Optimization for Publishers] aktivieren, müssen Sie beschreibende Metadaten für [!UICONTROL Ad Unit IDs] einfügen, wie in Schritt 3 von [Google Ad Manager (ehemals DFP)-Datendateien in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md) beschrieben. Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft als [!UICONTROL Ad Unit] und nicht als [!UICONTROL Ad Unit ID] bezeichnet.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Ad Unit Overlap]-Bericht könnte ähnlich wie der unten stehende aussehen. Bewegen Sie den Mauszeiger über eine Zelle, um weitere Informationen zu dieser Überschneidung zu erhalten. Siehe Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col1"> <p><span class="wintitle"> Überschneidungsanzeigeeinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Bestandteils. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. In der Abbildung oben sind die grundlegenden Anzeigeneinheiten Artikel 9 bis 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basisanzeigeneinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Bestandteils. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. In der Abbildung oben sind die grundlegenden Anzeigeneinheiten Artikel 1 bis 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl individueller Anzeigeneinheiten überlappen</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die die Artikel 9 bis 18 der Anzeigeneinheit besucht haben. Diese Informationen werden aus den Google Ad Manager-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl individueller Werbeanzeigen</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die die Elemente der Anzeigeneinheit 1 - 8 besucht haben. Diese Informationen werden aus den Google Ad Manager-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl individueller Überschneidungen</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen Ihren Benutzern, die eine <span class="wintitle"> Base Ad Unit</span> und <span class="wintitle"> Overlap Ad Unit</span> besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überschneidungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen Ihren Benutzern, die eine <span class="wintitle"> Base Ad Unit</span> und <span class="wintitle"> Overlap Ad Unit</span> besucht haben. Dies ist die Anzahl individueller Überschneidungen <span class="wintitle">, ausgedrückt als Prozentsatz der <span class="wintitle">-Basiswerbeeinheit</span>.</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

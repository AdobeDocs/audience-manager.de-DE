---
description: Der Bericht "Anzeigeneinheit - Überschneidung"wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten hervorhebt.
seo-description: Der Bericht "Anzeigeneinheit - Überschneidung"wird als Heatmap angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten hervorhebt.
seo-title: Überlagerung von Anzeigeneinheiten
solution: Audience Manager
title: Überlagerung von Anzeigeneinheiten
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 3%

---


# Überlagerung von Anzeigeneinheiten{#ad-unit-overlap}

Der **[!UICONTROL Ad Unit Overlap]** Bericht wird als Heat-Diagramm angezeigt, das die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten hervorhebt.

## Anwendungsfall {#use-cases}

Mit dem **[!UICONTROL Ad Unit Overlap]** Bericht erhalten Sie einen Einblick, wo sich Ihre Audience über Ihre Webeigenschaften hinweg überschneidet. Der Bericht berücksichtigt Ihre 100 wichtigsten Eigenschaften und zeigt die Überschneidung zwischen ihnen.

## Verwenden des Überschneidungsberichts für die Anzeigeneinheit {#using-the-report}

Verwenden Sie die **[!UICONTROL Top N Base Ad Units]** und **[!UICONTROL Top N Overlapping Ad Units]** -Steuerelemente, um die gewünschte Anzahl von Anzeigeneinheiten für die Überschneidung auszuwählen. Sie können jeweils maximal 100 Elemente auswählen.

Passen Sie den **Rückblickbereich** mit den Steuerelementen **&quot;Zeitraum bis** Ende&quot;an. Beachten Sie, dass die 7- und 30-Tage-Rückblickzeit nur für Sonntagsdaten verfügbar ist.

Verwenden Sie die Steuerelemente **[!UICONTROL Base Ad Unit]** und **[!UICONTROL Overlap Ad Unit]** wählen Sie aus, welche Ihrer Anzeigeneinheiten im Überschneidungsbericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Bei der Aktivierung [!UICONTROL Audience Optimization for Publishers]müssen Sie beschreibende Metadaten für [!UICONTROL Ad Unit IDs]angeben, wie in Schritt 3 von &quot;Google Ad Manager-Datendateien (ehemals DFP) in Audience Manager [](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)importieren&quot;beschrieben. Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft [!UICONTROL Ad Unit] anstelle der [!UICONTROL Ad Unit ID]Eigenschaft detailliert beschreibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Ad Unit Overlap] Bericht könnte dem unten stehenden ähneln. Bewegen Sie den Mauszeiger über eine Zelle, um weitere Informationen zu dieser Überschneidung zu erhalten. Siehe Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col2"> <p>Die Überschneidung zwischen Ihren Benutzern, die eine <span class="wintitle"> Basis-Anzeigeneinheit</span> und <span class="wintitle"> Überschneidungsanzeigeeinheit</span>besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überschneidungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen Ihren Benutzern, die eine <span class="wintitle"> Basis-Anzeigeneinheit</span> und <span class="wintitle"> Überschneidungsanzeigeeinheit</span>besucht haben. Dies ist die Anzahl <span class="wintitle"> der</span>individuellen Überschneidungen, ausgedrückt als Prozentsatz der <span class="wintitle"> Basis-Anzeigeneinheit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

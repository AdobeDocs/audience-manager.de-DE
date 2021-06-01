---
description: Der Überlagerungsbericht für Anzeigeneinheiten wird als Heatchart angezeigt, in dem die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten hervorgehoben werden.
seo-description: Der Überlagerungsbericht für Anzeigeneinheiten wird als Heatchart angezeigt, in dem die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten hervorgehoben werden.
seo-title: Überlagerung von Anzeigeneinheiten
solution: Audience Manager
title: Überlagerung von Anzeigeneinheiten
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Berichte zur Zielgruppenoptimierung
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 3%

---

# Überlagerung von Anzeigeneinheiten{#ad-unit-overlap}

Der Bericht **[!UICONTROL Ad Unit Overlap]** wird als Heatchart angezeigt, in dem die hohen und niedrigen Überschneidungen zwischen Ihren Anzeigeneinheiten hervorgehoben werden.

## Anwendungsfall {#use-cases}

Mit dem Bericht **[!UICONTROL Ad Unit Overlap]** können Sie Einblicke darin gewinnen, wo sich Ihre Zielgruppe über Ihre Web-Eigenschaften hinweg überschneidet. Der Bericht berücksichtigt Ihre 100 wichtigsten verwandten Eigenschaften und zeigt Ihnen die Überschneidung zwischen ihnen.

## Verwenden des Überlagerungsberichts für Anzeigeneinheiten {#using-the-report}

Verwenden Sie die Steuerelemente **[!UICONTROL Top N Base Ad Units]** und **[!UICONTROL Top N Overlapping Ad Units]** , um die gewünschte Anzahl von Anzeigeneinheiten für die Überschneidung auszuwählen. Sie können für jedes Element eine maximale Anzahl von 100 Elementen auswählen.

Verwenden Sie die Steuerelemente **Day Range** und **Date Through** , um Ihren Lookback-Bereich anzupassen. Beachten Sie, dass die 7- und 30-tägigen Rückblickperioden nur für Sonntagsdaten verfügbar sind.

Verwenden Sie die Steuerelemente **[!UICONTROL Base Ad Unit]** und **[!UICONTROL Overlap Ad Unit]** , um festzulegen, welche Ihrer Anzeigen-Einheiten im Überlagerungsbericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Beim Aktivieren von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Ad Unit IDs] einfügen, wie in Schritt 3 von [Importieren von Google Ad Manager-(ehemals DFP-)Datendateien in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md) beschrieben. Dadurch stellen Sie sicher, dass der Bericht die Webeigenschaft als [!UICONTROL Ad Unit] anstelle von [!UICONTROL Ad Unit ID] detailliert beschreibt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Ad Unit Overlap] -Bericht könnte dem unten stehenden ähneln. Bewegen Sie den Mauszeiger über eine Zelle, um weitere Informationen zu dieser bestimmten Überschneidung zu erhalten. Weitere Informationen finden Sie in der Tabelle unter dem Beispielbericht.

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
   <td colname="col1"> <p><span class="wintitle"> Überlagerungsanzeigeneinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Inventarelements. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. In der obigen Abbildung sind die grundlegenden Anzeigeneinheiten die Artikel 9 bis 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basisanzeigeneinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Inventarelements. Dies kann beispielsweise eine Ihrer Websites oder ein Artikel auf Ihrer Website sein. In der obigen Abbildung sind die grundlegenden Anzeigeneinheiten Artikel 1 bis 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl eindeutiger Überlagerungsanzeigen</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die die Artikel der Anzeigeneinheit 9 bis 18 besucht haben. Diese Informationen werden aus den Google Ad Manager-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl der individuellen Werbeeinheiten</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die die Elemente der Anzeigeneinheit 1 bis 8 besucht haben. Diese Informationen werden aus den Google Ad Manager-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Anzahl der individuellen Überlagerungen</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen Ihren Benutzern, die eine <span class="wintitle"> Base Ad Unit</span> und <span class="wintitle"> Overlap Ad Unit</span> besucht haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlagerungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überschneidung zwischen Ihren Benutzern, die eine <span class="wintitle"> Base Ad Unit</span> und <span class="wintitle"> Overlap Ad Unit</span> besucht haben. Dies ist die <span class="wintitle"> Überlagerungsanzahl Individuelle Werte</span>, ausgedrückt als Prozentsatz der <span class="wintitle"> -Basiswerbeeinheit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

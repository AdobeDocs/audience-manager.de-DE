---
description: Der Bericht "Anzeigenüberlappung" wird als ein Heat Chart angezeigt, das hohe und niedrige Überlappungen zwischen Ihren Anzeigeneinheiten hervorhebt.
seo-description: Der Bericht "Anzeigenüberlappung" wird als ein Heat Chart angezeigt, das hohe und niedrige Überlappungen zwischen Ihren Anzeigeneinheiten hervorhebt.
seo-title: Anzeigenüberlappung
solution: Audience Manager
title: Anzeigenüberlappung
uuid: e 4467 e 81-acbf -474 e-b 501-89 d 57395651 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Anzeigenüberlappung{#ad-unit-overlap}

Der **[!UICONTROL Ad Unit Overlap]** Bericht wird als ein Heat Chart angezeigt, das hohe und niedrige Überlappungen zwischen Ihren Anzeigeneinheiten hervorhebt.

## Nutzungsszenario {#use-cases}

Mit dem **[!UICONTROL Ad Unit Overlap]** Bericht können Sie Einblicke gewinnen, wo sich Ihre Zielgruppe über Ihre Webeigenschaften hinweg überlappen. Der Bericht betrachtet Ihre 100 wichtigsten Eigenschaften und zeigt Ihnen die Überlappung.

## Verwenden des Anzeigenüberlappungs-Berichts {#using-the-report}

Verwenden Sie die **[!UICONTROL Top N Base Ad Units]** Steuerelemente und **[!UICONTROL Top N Overlapping Ad Units]** Steuerelemente, um die gewünschte Anzahl von Anzeigeneinheiten für die Überschneidung auszuwählen. Sie können jeweils maximal 100 Elemente auswählen.

Verwenden Sie den Steuerumfang **für Tagesbereich** und **Datum,** um den Look-Back-Bereich anzupassen. Beachten Sie, dass der 7-Tage- und 30-Tage-Suchzeitraum nur für Sonntag verfügbar sind.

Verwenden Sie den **[!UICONTROL Base Ad Unit]** und **[!UICONTROL Overlap Ad Unit]** die Steuerelemente, um auszuwählen, welche Ihrer Anzeigeneinheiten im Überlappungsbericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Bei Aktivierung [!UICONTROL Audience Optimization for Publishers]müssen Sie beschreibende Metadaten hinzufügen, [!UICONTROL Ad Unit IDs]wie in Schritt 3 von [DFP-Datendateien in Audience Manager importieren](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)beschrieben. Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft anstelle [!UICONTROL Ad Unit] von &quot;und [!UICONTROL Ad Unit ID]«ausführt.

## Interpretieren der Ergebnisse {#interpreting-results}

Ihr [!UICONTROL Ad Unit Overlap] Bericht könnte wie folgt aussehen. Bewegen Sie den Mauszeiger über eine Zelle, um weitere Informationen zu dieser Überlappung abzurufen. Weitere Informationen finden Sie unter Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col1"> <p><span class="wintitle"> Überlappende Anzeigeneinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Bestandselements. Dies kann zum Beispiel einer der Websites oder einen Artikel auf Ihrer Website sein. Im obigen Bild sind die Basisanzeigeneinheiten Artikel 9 - 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basisanzeigeneinheit</span> </p> </td> 
   <td colname="col2"> <p>Der Name Ihres Bestandselements. Dies kann zum Beispiel einer der Websites oder einen Artikel auf Ihrer Website sein. Im obigen Bild sind die Basisanzeigeneinheiten Artikel 1 - 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlappende Anzeigeneinheit - Anzahl</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die die Anzeigenartikelelemente 9 - 18 besucht haben. Diese Informationen werden aus den DFP-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basis-Anzeigeneinheit Individuelle Werte</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Benutzer, die die Anzeigeneinheitenelemente 1 - 8 besucht haben. Diese Informationen werden aus den DFP-Protokollen extrahiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlappende Uniques-Anzahl</span> </p> </td> 
   <td colname="col2"> <p>Die Überlappung zwischen Ihren Benutzern, die eine <span class="wintitle"> Base Ad Unit</span> - und <span class="wintitle"> Überlappungsanzeigeneinheit besucht</span>haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Überlappungsprozentsatz</span> </p> </td> 
   <td colname="col2"> <p>Die Überlappung zwischen Ihren Benutzern, die eine <span class="wintitle"> Base Ad Unit</span> - und <span class="wintitle"> Überlappungsanzeigeneinheit besucht</span>haben. Hierbei handelt es sich um die <span class="wintitle"> Überlappende Uniques-Anzahl</span>, ausgedrückt als Prozentsatz der <span class="wintitle"> Basisanzeigeneinheit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

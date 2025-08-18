---
description: Fügen Sie in Segment Builder Eigenschaften hinzu und entfernen Sie sie, um die tatsächlichen Eigenschaftspopulationen zusammen mit den tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Mit den Daten zur geschätzten Populationsgröße können Sie das richtige Segment für Ihre Kampagne erstellen.
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: Daten zu Eigenschaften und Segmentpopulation in Segment Builder
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 1%

---

# [!UICONTROL Trait] und [!UICONTROL Segment] von Populationsdaten in [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Fügen Sie [!UICONTROL traits] hinzu und entfernen Sie sie in [!UICONTROL Segment Builder], um die tatsächlichen [!UICONTROL trait] Populationen zusammen mit den tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Mit den Daten zur geschätzten Populationsgröße können Sie das richtige Segment für Ihre Kampagne erstellen.

## [!UICONTROL Trait] Populationsdaten {#trait-population-data}

[!UICONTROL Segment Builder] zeigt die [!UICONTROL Total Trait Population] für den letzten Tag, an dem Sie einem Segment einen [!UICONTROL trait] hinzufügen. Diese Daten werden im blauen Feld um die ausgewählten [!UICONTROL trait] im Abschnitt [!UICONTROL Basic View] angezeigt.

![](assets/trait-size.png)

In der folgenden Tabelle werden die Metriken zur Eigenschaftenpopulation definiert:


| Metrik | Beschreibung |
|---------|----------|
| [!UICONTROL Total Trait Population] | Die Anzahl der eindeutigen IDs, die das ausgewählte Merkmal in ihrem Profil haben. |


## Berechnung der realen und geschätzten Segmentpopulationen {#calculating-real-estimated-populations}

Wenn Sie ein neues Segment erstellen oder ein vorhandenes Segment ändern, dauert es bis zu 24 Stunden, bis Audience Manager Ergebnisse für die tatsächlichen Echtzeit- und Gesamtsegmentpopulationen anzeigt.

Audience Manager kann jedoch sofort die Echtzeit- und Gesamtpopulation Ihres Segments schätzen. Diese Schätzungen basieren auf abgefragten historischen Daten und geben Ergebnisse im 95-%-Konfidenzintervall zurück.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder] zeigt ein blauer Balken in den Diagrammen mit der geschätzten Population die möglichen oberen und unteren Bereiche für die Segmentgröße an. Auch wenn die bisherige Leistung keine Garantie für zukünftige Ergebnisse bietet, können Ihnen die geschätzten Daten dabei helfen, die potenzielle Größe eines neuen oder bearbeiteten Segments zu verstehen.

## Übersicht über die Segmentpopulation {#segment-populations}

[!UICONTROL Segment Builder] zeigt Ihnen Daten zur Segmentpopulation beim Erstellen und Bearbeiten von Segmenten.

* Bei geschätzten Segmentpopulationsdaten (in Echtzeit und insgesamt) werden die Diagramme [!UICONTROL Segment Builder] nicht automatisch aktualisiert, wenn Sie Eigenschaften in einem Segment hinzufügen oder entfernen. Klicken Sie auf **[!UICONTROL Calculate Estimates]** , um die geschätzten Populationen anzuzeigen (oder zu aktualisieren).

* Für tatsächliche (reale) Segmentpopulationsdaten (Echtzeit und Gesamt) aktualisiert [!UICONTROL Segment Builder] das Segmentdiagramm automatisch, wenn Sie ein vorhandenes Segment laden. Bei neuen Segmenten oder wenn Sie einem vorhandenen Segment neue Eigenschaften hinzufügen, werden die tatsächlichen Populationsdaten erst 24 Stunden nach der Erstellung des Segments aktualisiert.

![](assets/segment-data.png)

Weitere Informationen zu den geschätzten und tatsächlichen Daten zur Segmentpopulation finden Sie in den nachstehenden Definitionen.

## Daten zur geschätzten Segmentpopulation definiert {#estimated-segment-population}

In der folgenden Tabelle werden die Metriken der geschätzten Population definiert.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> geschätzte Echtzeit-Population (potenzieller </span>) </p> </td> 
   <td colname="col2"> <p>Die geschätzte Anzahl der Unique Visitors, die im angegebenen Zeitraum in Echtzeit gesehen wurden und die zum Zeitpunkt ihrer Anzeige in Audience Manager für das Segment qualifiziert waren. </p> <p>In <span class="wintitle"> Segment Builder</span> können die Populationen der letzten 30 Tage für Eigenschaften (<span class="wintitle"> Gesamtzahl der </span>) für Eigenschaften und Segmente, die in Echtzeit ausgewertet werden, unterschiedlich sein. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Bei Eigenschaften zählt die Metrik der letzten 30 Tage die Anzahl der eindeutigen Benutzer, die sich in den letzten 30 Tagen für diese Eigenschaft qualifiziert haben. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Bei Segmenten, die in Echtzeit ausgewertet werden, zählt die Metrik der letzten 30 Tage die Anzahl der Benutzenden, die sich zu einem beliebigen Zeitpunkt in der Vergangenheit für ein Merkmal (in diesem Segment) qualifiziert haben und in den letzten 30 Tagen von Audience Manager erneut gesehen wurden. Angenommen, Sie haben einen Benutzer, der sich vor 60 Tagen für eine Eigenschaft qualifiziert hat und vor 10 Tagen erneut gesehen wurde. In den Daten wird dieser Benutzer nicht zur Anzahl der Eigenschaften hinzugefügt, da er sich zum ersten Mal für die Eigenschaft vor mehr als 30 Tagen qualifiziert hat. Sie werden jedoch in die letzte 30-Tage-Zählung für die Segmente einbezogen, die in Echtzeit ausgewertet werden. Dies liegt daran, dass sie sich innerhalb des 30-tägigen Zeitintervalls für das Segment qualifiziert haben. </li>
     </ul> </p> <p> <p>Hinweis: Die Metrik Geschätzte <span class="wintitle"> Echtzeit-</span> enthält keine Geräte, die sich für ein Segment qualifiziert haben, das auf Verbindungen basiert, die von einer <span class="wintitle">-Profilzusammenführungsregel bereitgestellt werden</span> die eine <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Gerätediagramm-Option verwendet</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> geschätzte Gesamtpopulation (potenziell)</span> </p> </td> 
   <td colname="col2"> <p>Die geschätzte Anzahl der Unique Visitors, die sich in Ihrem neuen oder geänderten Segment befinden könnten. Wie bei fast allen Schätzungen ist die Leistung in der Vergangenheit keine Garantie für zukünftige Ergebnisse, aber Sie können die geschätzte Gesamtsumme verwenden, um: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Ermitteln Sie, wie viele Personen ein neues oder überarbeitetes Segment erreichen könnte, wenn Sie ein Segment erstellen. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Passen Sie das Segment entsprechend Ihren Zielen an. Beispielsweise sind große Segmente für Kampagnen zur Markenwahrnehmung und kleinere Segmente für zielgerichtete Targeting- oder Retargeting-Kampagnen nützlich. </li> 
     </ul> </p> <p> <p>Hinweis: Die Metrik Geschätzte Gesamtpopulation <span class="wintitle"></span> enthält keine Geräte, die sich für ein Segment qualifiziert haben, basierend auf Verbindungen, die von einer <span class="wintitle">-Profilzusammenführungsregel bereitgestellt </span>, die eine <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Gerätediagrammoption verwendet</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorhandene (tatsächliche) Daten zur Segmentpopulation definiert {#existing-segment-population}

[!UICONTROL Profile Merge Rules] wirken sich auf die tatsächlichen Zahlen der Echtzeitpopulation und der Gesamtpopulation aus. Diese Gesamtwerte variieren je nachdem, ob die [!UICONTROL Profile Merge Rule], zu der ein Segment gehört, eine Gerätediagramm-Option verwendet oder nicht. Siehe auch [Optionen für Profilzusammenführungsregeln definiert](../../features/profile-merge-rules/merge-rule-definitions.md).

### Daten zur Segmentpopulation für [!UICONTROL Merge Rules] ohne [!UICONTROL Device Graph Option]

In der folgenden Tabelle werden die tatsächlichen Echtzeit- und Gesamtbevölkerungsmetriken definiert, wenn Ihre Segmente von einem ohne [!UICONTROL Profile Merge Rule] erstellten [!UICONTROL device graph] verwendet werden. Dies sind die Geräteoptionen Einstellungen **[!UICONTROL No Device Options]** und **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Echtzeit-Population (vorhanden)</span> </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl der Unique Visitors, die im angegebenen Zeitraum in Echtzeit gesehen und für das Segment qualifiziert wurden, als sie von Audience Manager gesehen wurden. </p> <p>In <span class="wintitle"> Segment Builder </span> die Populationen der letzten 30 Tage für Eigenschaften (<span class="wintitle"> Gesamtzahl der Eigenschaftspopulationen</span>) für Eigenschaften und Segmente, die in Echtzeit ausgewertet werden, unterschiedlich sein. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Bei Eigenschaften zählt die Metrik der letzten 30 Tage die Anzahl der eindeutigen Benutzer, die sich in den letzten 30 Tagen für diese Eigenschaft qualifiziert haben. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Bei Segmenten, die in Echtzeit ausgewertet werden, zählt die Metrik der letzten 30 Tage die Anzahl der Benutzenden, die sich zu einem beliebigen Zeitpunkt in der Vergangenheit für ein Merkmal (in diesem Segment) qualifiziert haben und in den letzten 30 Tagen von Audience Manager erneut gesehen wurden. Angenommen, Sie haben einen Benutzer, der sich vor 60 Tagen für eine Eigenschaft qualifiziert hat und vor 10 Tagen erneut gesehen wurde. In den Daten wird dieser Benutzer nicht zur Anzahl der Eigenschaften hinzugefügt, da er sich zum ersten Mal für die Eigenschaft vor mehr als 30 Tagen qualifiziert hat. Sie werden jedoch in die letzte 30-Tage-Zählung für die Segmente einbezogen, die in Echtzeit ausgewertet werden. Dies liegt daran, dass sie sich innerhalb des 30-tägigen Zeitintervalls für das Segment qualifiziert haben. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Gesamtbevölkerung (vorhanden)</span> </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl von Unique Visitors, die sich seit gestern für das Segment qualifiziert haben. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Daten zur Segmentpopulation für [!UICONTROL Merge Rules] mit einer [!UICONTROL Device Graph] Option

In der folgenden Tabelle werden die tatsächlichen Echtzeit- und Gesamtbevölkerungsmetriken definiert, wenn Ihre Segmente von einem mit einer [!UICONTROL Profile Merge Rule] erstellten [!DNL device graph] verwendet werden. Dies sind die Geräteoptionseinstellungen für die [!UICONTROL Profile Link Device Graph], die [!DNL Adobe] [!DNL device graph] und andere [!DNL device graph] von Drittanbietern, die Ihnen zur Verfügung stehen.


| Spalte A | Spalte B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing)] | Die tatsächliche Anzahl von Geräten, die in Echtzeit mit aktuellen Profilen angezeigt wird und die, wenn sie mit bis zu 100 anderen Geräteprofilen zusammengeführt werden, die durch das Gerätediagramm verbunden sind, die Eigenschaften enthalten, die für das Segment in dem Moment qualifiziert sind, in dem es von Audience Manager gesehen wurde. |
| [!UICONTROL Total Population (Existing)] | Die Gesamtzahl der Geräte mit Profilen, die bei der Zusammenführung mit bis zu 100 anderen Geräteprofilen, die durch das Gerätediagramm verbunden sind, alle für das Segment qualifiziert waren. |

### Einschränkungen aufgrund von Neuigkeit und Häufigkeitsausdrücken bei der Schätzung von Segmentpopulationen

[!UICONTROL Segment Builder] unterstützt Segmentgrößenschätzungen für Segmentregeln, die bis zu vier Neuigkeits- und Häufigkeitsausdrücke enthalten. Die Auswahl von mehr als vier Neuigkeit- und Häufigkeitsausdrücken beim Erstellen einer Segmentregel führt dazu, dass die Segmentschätzung beim Schätzen der Population einen Fehler anzeigt.

### Einschränkungen aufgrund von [!UICONTROL Merge Rules] bei der Schätzung von Segmentpopulationen

Derzeit gibt es eine bekannte Einschränkung, da unsere Segmentgrößenschätzung keine [!UICONTROL profile merge rules] berücksichtigt. Sehen Sie sich beispielsweise Segmente mit der **[!UICONTROL No Authenticated Profile + Current Device Profile]** &quot;[&quot; ](../../features/profile-merge-rules/merge-rule-definitions.md). Aufgrund der Art und Weise, wie wir derzeit die Segmentschätzungszahlen berechnen, enthalten die geschätzten Populationen authentifizierte Profile. Die vorhandenen Segmentpopulationen ignorieren jedoch korrekt authentifizierte Profile.

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm](../../faq/faq-profile-merge.md)
>* [Profil-Link](../profile-merge-rules/merge-rules-overview.md)

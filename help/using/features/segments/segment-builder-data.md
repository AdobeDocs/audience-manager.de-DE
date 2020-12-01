---
description: hinzufügen und entfernen Sie Eigenschaften im Segmentaufbau, um tatsächliche Eigenschaftspopulationen zusammen mit tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Anhand der Daten zur geschätzten Populationsgröße können Sie das richtige Segment für Ihre Kampagne erstellen.
seo-description: hinzufügen und entfernen Sie Eigenschaften im Segmentaufbau, um tatsächliche Eigenschaftspopulationen zusammen mit tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Anhand der Daten zur geschätzten Populationsgröße können Sie das richtige Segment für Ihre Kampagne erstellen.
seo-title: Eigenschafts- und Segmentpopulationsdaten in Segment Builder
solution: Audience Manager
title: Eigenschafts- und Segmentpopulationsdaten in Segment Builder
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 2%

---


# [!UICONTROL Trait] und  [!UICONTROL Segment] Populationsdaten in  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

hinzufügen und entfernen Sie [!UICONTROL traits] in [!UICONTROL Segment Builder], um tatsächliche [!UICONTROL trait]-Populationen zusammen mit tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Anhand der Daten zur geschätzten Populationsgröße können Sie das richtige Segment für Ihre Kampagne erstellen.

## [!UICONTROL Trait] Populationsdaten  {#trait-population-data}

[!UICONTROL Segment Builder] zeigt Ihnen  [!UICONTROL Total Trait Population] den letzten Tag, an dem Sie einem Segment eine  [!UICONTROL trait] hinzufügen. Diese Daten werden im blauen Feld um das ausgewählte [!UICONTROL trait] im Abschnitt [!UICONTROL Basic View] angezeigt.

![](assets/trait-size.png)

Die folgende Tabelle definiert die Populationsmetriken der Eigenschaften:


| Metrik | Beschreibung |
---------|----------|
| [!UICONTROL Total Trait Population] | Die Anzahl der eindeutigen IDs, deren Profil die ausgewählten Eigenschaften enthält. |


## Berechnen von tatsächlichen und geschätzten Segmentpopulationen {#calculating-real-estimated-populations}

Wenn Sie ein neues Segment erstellen oder ein vorhandenes Segment ändern, dauert es bis zu 24 Stunden, bis Audience Manager die Ergebnisse für tatsächliche Segmentpopulationen in Echtzeit und insgesamt anzeigen.

Audience Manager können jedoch sofort die Echtzeit- und Gesamtpopulation Ihres Segments schätzen. Diese Schätzungen basieren auf der Stichprobenauswahl von historischen Daten und den Rückgabeergebnissen im Konfidenzintervall von 95 %.

![](assets/confidence-interval.png)

Unter [!UICONTROL Segment Builder] zeigt ein blauer Balken auf den geschätzten Populationsdiagrammen die möglichen oberen und unteren Bereiche für die Segmentgröße an. Obwohl die bisherige Leistung keine Garantie für zukünftige Ergebnisse bietet, können Ihnen die geschätzten Daten dabei helfen, die potenzielle Größe eines neuen oder bearbeiteten Segments zu verstehen.

## Übersicht über Segmentpopulationsdaten {#segment-populations}

[!UICONTROL Segment Builder] zeigt Ihnen beim Erstellen und Bearbeiten von Segmenten die Segmentpopulationsdaten.

* Bei geschätzten Segmentpopulationsdaten (in Echtzeit und insgesamt) aktualisiert [!UICONTROL Segment Builder] die Diagramme nicht automatisch, wenn Sie Eigenschaften in einem Segment hinzufügen oder entfernen. Klicken Sie auf **[!UICONTROL Calculate Estimates]**, um die geschätzten Populationszahlen anzuzeigen (oder zu aktualisieren).

* Für tatsächliche (tatsächliche) Segmentpopulationsdaten (Echtzeit und Gesamtsumme) aktualisiert [!UICONTROL Segment Builder] das Segmentdiagramm automatisch, wenn Sie ein vorhandenes Segment laden. Bei neuen Segmenten oder beim Hinzufügen neuer Eigenschaften zu einem vorhandenen Segment werden die tatsächlichen Populationsdaten erst 24 Stunden nach der Erstellung des Segments aktualisiert.

![](assets/segment-data.png)

Weitere Informationen zu geschätzten und tatsächlichen Segmentpopulationsdaten finden Sie in den folgenden Definitionen.

## Geschätzte Segmentpopulationsdaten definiert {#estimated-segment-population}

Die folgende Tabelle definiert die geschätzten Populationsmetriken.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Geschätzte Echtzeit-Bevölkerung (Potenzial)  </span> </p> </td> 
   <td colname="col2"> <p>Die geschätzte Anzahl individueller Besucher, die in Echtzeit für den angegebenen Zeitraum gesehen wurden und die zum Zeitpunkt, zu dem sie vom Audience Manager gesehen wurden, für das Segment qualifiziert waren. </p> <p>In <span class="wintitle"> Segmentaufbau</span> können die letzten 30-Tage-Populationen für Eigenschaften (<span class="wintitle"> Gesamtanzahl der Eigenschaften</span>) für Eigenschaften und Segmente, die in Echtzeit ausgewertet werden, unterschiedlich sein. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Bei Eigenschaften zählt die letzte 30-Tage-Metrik die Anzahl der Unique Users, die sich in den letzten 30 Tagen für diese Eigenschaft qualifiziert haben. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Bei Segmenten, die in Echtzeit ausgewertet werden, zählt die letzte 30-Tage-Metrik die Anzahl der Benutzer, die sich zu einem bestimmten Zeitpunkt (in diesem Segment) für eine Eigenschaft qualifiziert haben und die innerhalb der letzten 30 Tage erneut vom Audience Manager gesehen wurden. Angenommen, Sie haben einen Benutzer, der sich vor 60 Tagen für eine Eigenschaft qualifiziert hat und vor 10 Tagen erneut gesehen wurde. In den Daten wird dieser Benutzer nicht zur Eigenschaftszählung hinzugefügt, da er sich vor mehr als 30 Tagen für die Eigenschaft qualifiziert hat. Sie werden jedoch in der letzten 30-Tage-Anzahl für die in Echtzeit ausgewerteten Segmente berücksichtigt. Dies liegt daran, dass sie sich innerhalb des 30-Tage-Zeitraums für das Segment qualifiziert haben. </li>
     </ul> </p> <p> <p>Hinweis: Die <span class="wintitle">-Metrik "Geschätzte Echtzeitpopulation</span>"enthält keine Geräte, die sich für ein Segment auf Grundlage von Verbindungen qualifiziert haben, die von einer <span class="wintitle"> Profil Merge Rule</span> bereitgestellt werden, die eine <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options">-Gerätediagrammoption</a> verwendet. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Geschätzte Gesamtbevölkerung (Potenzial)</span> </p> </td> 
   <td colname="col2"> <p>Die geschätzte Anzahl individueller Besucher, die sich in Ihrem neuen oder geänderten Segment befinden könnten. Wie bei fast jeder Schätzung garantiert die bisherige Performance keine zukünftigen Ergebnisse, aber Sie können die geschätzte Gesamtsumme wie folgt verwenden: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Erkennen Sie, wie viele Personen ein neues oder überarbeitetes Segment beim Erstellen eines Segments erreichen kann. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Passen Sie das Segment je nach Ihren Zielen an. Große Segmente eignen sich beispielsweise für Kampagnen, die das Markenbewusstsein berücksichtigen, kleinere Segmente eignen sich für gezielte Targeting- oder Targeting-Kampagnen. </li> 
     </ul> </p> <p> <p>Hinweis: Die Metrik <span class="wintitle"> "Geschätzte Gesamtpopulation</span>"enthält keine Geräte, die sich für ein Segment auf Grundlage von Verbindungen qualifiziert haben, die von einer <span class="wintitle"> Profil Merge Rule</span> bereitgestellt werden, die eine <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Gerätediagrammoption</a> verwendet. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorhandene (tatsächliche) Segmentpopulationsdaten definiert {#existing-segment-population}

[!UICONTROL Profile Merge Rules] Auswirkungen auf die tatsächlichen Echtzeit- und Gesamtbevölkerungszahlen. Diese Summen variieren je nachdem, ob das [!UICONTROL Profile Merge Rule]-Segment einer Gerätediagrammoption angehört oder nicht. Siehe auch [Profil Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

### Segmentpopulationsdaten für [!UICONTROL Merge Rules] ohne [!UICONTROL Device Graph Option]

Die folgende Tabelle definiert die tatsächlichen Echtzeit- und Gesamtpopulationsmetriken, wenn Ihre Segmente von einem [!UICONTROL Profile Merge Rule] verwendet werden, das ohne eine [!UICONTROL device graph]-Option erstellt wurde. Dies sind die Geräteoptionseinstellungen **[!UICONTROL No Device Options]** und **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population in Echtzeit (vorhanden)</span> </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl individueller Besucher, die in Echtzeit für den angegebenen Zeitraum gesehen wurden und die zum Zeitpunkt, zu dem sie vom Audience Manager gesehen wurden, für das Segment qualifiziert waren. </p> <p>In <span class="wintitle"> Segmentaufbau</span> können die letzten 30-Tage-Populationen für Eigenschaften (<span class="wintitle"> Gesamtanzahl der Eigenschaften</span>) für Eigenschaften und Segmente, die in Echtzeit ausgewertet werden, unterschiedlich sein. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Bei Eigenschaften zählt die letzte 30-Tage-Metrik die Anzahl der Unique Users, die sich in den letzten 30 Tagen für diese Eigenschaft qualifiziert haben. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Bei Segmenten, die in Echtzeit ausgewertet werden, zählt die letzte 30-Tage-Metrik die Anzahl der Benutzer, die sich zu einem bestimmten Zeitpunkt (in diesem Segment) für eine Eigenschaft qualifiziert haben und die innerhalb der letzten 30 Tage erneut vom Audience Manager gesehen wurden. Angenommen, Sie haben einen Benutzer, der sich vor 60 Tagen für eine Eigenschaft qualifiziert hat und vor 10 Tagen erneut gesehen wurde. In den Daten wird dieser Benutzer nicht zur Eigenschaftszählung hinzugefügt, da er sich vor mehr als 30 Tagen für die Eigenschaft qualifiziert hat. Sie werden jedoch in der letzten 30-Tage-Anzahl für die in Echtzeit ausgewerteten Segmente berücksichtigt. Dies liegt daran, dass sie sich innerhalb des 30-Tage-Zeitraums für das Segment qualifiziert haben. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Gesamtbevölkerung (vorhanden)</span> </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl der eindeutigen Besucher, die seit gestern für das Segment qualifiziert waren. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segmentpopulationsdaten für [!UICONTROL Merge Rules] mit einer [!UICONTROL Device Graph]-Option

Die folgende Tabelle definiert die tatsächlichen Echtzeit- und Gesamtbevölkerungsmetriken, wenn Ihre Segmente von einer mit der Option [!DNL device graph] erstellten [!UICONTROL Profile Merge Rule] verwendet werden. Dies sind die Geräteoptionseinstellungen für die Optionen [!UICONTROL Profile Link Device Graph], [!DNL Adobe] [!DNL device graph] und andere [!DNL device graph] von Drittanbietern, die Ihnen zur Verfügung stehen.


| Spalte A | Spalte B |
---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | Die tatsächliche Anzahl der Geräte, die in Echtzeit mit aktuellen Profilen gesehen werden, die bei der Zusammenführung mit bis zu 100 anderen Profilen, die mit dem Gerätediagramm verbunden sind, die Eigenschaften enthalten, die für das Segment zu dem Zeitpunkt gelten, zu dem es vom Audience Manager gesehen wurde. |
| [!UICONTROL Total Population (Existing)] | Die Gesamtzahl der Geräte mit Profilen, die bei der Zusammenführung mit bis zu 100 anderen Profilen, die über das Gerätediagramm angeschlossen sind, für das Segment qualifiziert waren. |

### Einschränkungen aufgrund von Ausdrücken zur Neuigkeit und Häufigkeit bei der Schätzung von Segmentpopulationen

[!UICONTROL Segment Builder] unterstützt Segmentgrößenschätzungen für Segmentregeln, die bis zu 4 Neuigkeiten und Frequenzen-Ausdruck enthalten. Wenn Sie beim Erstellen einer Segmentregel mehr als 4 Neuigkeits- und Häufigkeitsangaben wählen, zeigt die Segmentschätzung bei der Schätzung der Ausdruck einen Fehler an.

### Einschränkungen aufgrund von [!UICONTROL Merge Rules] bei der Schätzung von Segmentpopulationen

Zurzeit gibt es eine bekannte Einschränkung, da unser Segmentgrößenschätzer [!UICONTROL profile merge rules] nicht berücksichtigt. Betrachten Sie beispielsweise Segmente mit der **[!UICONTROL No Authenticated Profile + Current Device Profile]** [Mergeregel](../../features/profile-merge-rules/merge-rule-definitions.md). Aufgrund der Art, wie wir die Segmentschätzungszahlen derzeit berechnen, umfassen die geschätzten Populationen authentifizierte Profil. Die vorhandenen Segmentpopulationen ignorieren jedoch korrekt authentifizierte Profil.

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm](../../faq/faq-profile-merge.md)
>* [Profil-Link](../profile-merge-rules/merge-rules-overview.md)


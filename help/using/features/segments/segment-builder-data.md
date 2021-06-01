---
description: Fügen Sie Eigenschaften in Segment Builder hinzu und entfernen Sie diese, um die tatsächlichen Eigenschaftspopulationen zusammen mit den tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Die Daten zur geschätzten Populationsgröße helfen Ihnen beim Erstellen des richtigen Segments für Ihre Kampagne.
seo-description: Fügen Sie Eigenschaften in Segment Builder hinzu und entfernen Sie diese, um die tatsächlichen Eigenschaftspopulationen zusammen mit den tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Die Daten zur geschätzten Populationsgröße helfen Ihnen beim Erstellen des richtigen Segments für Ihre Kampagne.
seo-title: Eigenschafts- und Segmentpopulationsdaten in Segment Builder
solution: Audience Manager
title: Eigenschafts- und Segmentpopulationsdaten in Segment Builder
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: 'Segmente '
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 2%

---

# [!UICONTROL Trait] und  [!UICONTROL Segment] Populationsdaten in  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Fügen Sie [!UICONTROL traits] in [!UICONTROL Segment Builder] hinzu und entfernen Sie diese, um die tatsächlichen [!UICONTROL trait] Populationen sowie die tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Die Daten zur geschätzten Populationsgröße helfen Ihnen beim Erstellen des richtigen Segments für Ihre Kampagne.

## [!UICONTROL Trait] Populationsdaten  {#trait-population-data}

[!UICONTROL Segment Builder] zeigt Ihnen  [!UICONTROL Total Trait Population] den letzten Tag an, an dem Sie einem Segment einen  [!UICONTROL trait] hinzufügen. Diese Daten werden im blauen Feld um Ihr ausgewähltes [!UICONTROL trait] im Abschnitt [!UICONTROL Basic View] angezeigt.

![](assets/trait-size.png)

In der folgenden Tabelle werden die Eigenschaftspopulationsmetriken definiert:


| Metrik | Beschreibung |
---------|----------|
| [!UICONTROL Total Trait Population] | Die Anzahl der eindeutigen IDs, deren Profil die ausgewählte Eigenschaft enthält. |


## Berechnung der tatsächlichen und geschätzten Segmentpopulationen {#calculating-real-estimated-populations}

Wenn Sie ein neues Segment erstellen oder ein vorhandenes Segment ändern, dauert es bis zu 24 Stunden, bis der Audience Manager die Ergebnisse für die tatsächlichen Segmentpopulationen in Echtzeit und insgesamt anzeigt.

Audience Manager kann jedoch die Echtzeit- und Gesamtpopulationsgröße Ihres Segments sofort schätzen. Diese Schätzungen basieren auf der Stichprobe historischer Daten und geben Ergebnisse im Konfidenzintervall von 95 % zurück.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder] zeigt ein blauer Balken auf den geschätzten Populationsdiagrammen die möglichen oberen und unteren Bereiche für die Segmentgröße an. Auch wenn die bisherige Leistung keine Garantie für zukünftige Ergebnisse bietet, können Ihnen die geschätzten Daten dabei helfen, die potenzielle Größe eines neuen oder bearbeiteten Segments zu verstehen.

## Segmentpopulationsdaten - Überblick {#segment-populations}

[!UICONTROL Segment Builder] zeigt die Segmentpopulationsdaten bei der Erstellung und Bearbeitung von Segmenten an.

* Bei geschätzten Segmentpopulationsdaten (Echtzeit und Gesamtsumme) aktualisiert [!UICONTROL Segment Builder] die Diagramme nicht automatisch, wenn Sie Eigenschaften in einem Segment hinzufügen oder entfernen. Klicken Sie auf **[!UICONTROL Calculate Estimates]** , um die geschätzten Populationszahlen anzuzeigen (oder zu aktualisieren).

* Für tatsächliche (tatsächliche) Segmentpopulationsdaten (in Echtzeit und insgesamt) aktualisiert [!UICONTROL Segment Builder] das Segmentdiagramm automatisch, wenn Sie ein vorhandenes Segment laden. Für neue Segmente oder wenn Sie einem vorhandenen Segment neue Eigenschaften hinzufügen, werden die tatsächlichen Populationsdaten erst 24 Stunden nach der Erstellung des Segments aktualisiert.

![](assets/segment-data.png)

Weitere Informationen zu geschätzten und tatsächlichen Segmentpopulationsdaten finden Sie in den folgenden Definitionen.

## Geschätzte Segmentpopulationsdaten definiert {#estimated-segment-population}

In der folgenden Tabelle werden die geschätzten Populationsmetriken definiert.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Geschätzte Echtzeitpopulation (Potenzial)  </span> </p> </td> 
   <td colname="col2"> <p>Die geschätzte Anzahl Unique Visitors, die in Echtzeit über den angegebenen Zeitraum hinweg gesehen wurden und die zum Zeitpunkt ihrer Anzeige durch Audience Manager für das Segment qualifiziert waren. </p> <p>In <span class="wintitle"> Segment Builder</span> können sich die letzten 30 Tage für Eigenschaften (<span class="wintitle"> Gesamtzahl der Eigenschaftspopulationen</span>) für Eigenschaften und Segmente unterscheiden, die in Echtzeit ausgewertet werden. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Bei Eigenschaften zählt die Metrik der letzten 30 Tage die Anzahl der Unique Users, die sich in den letzten 30 Tagen für diese Eigenschaft qualifiziert haben. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Bei Segmenten, die in Echtzeit ausgewertet werden, zählt die Metrik der letzten 30 Tage die Anzahl der Benutzer, die sich zu einem bestimmten Zeitpunkt in der Vergangenheit für eine Eigenschaft (in diesem Segment) qualifiziert haben und innerhalb der letzten 30 Tage erneut vom Audience Manager gesehen wurden. Angenommen, Sie haben einen Benutzer, der sich vor 60 Tagen für eine Eigenschaft qualifiziert hat und vor 10 Tagen erneut gesehen wurde. In den Daten wird dieser Benutzer nicht zur Eigenschaftszählung hinzugefügt, da er sich vor mehr als 30 Tagen erstmals für die Eigenschaft qualifiziert hat. Sie werden jedoch in die letzten 30 Tage für die Segmente einbezogen, die in Echtzeit ausgewertet werden. Dies liegt daran, dass sie sich für das Segment innerhalb des 30-Tage-Zeitintervalls qualifiziert haben. </li>
     </ul> </p> <p> <p>Hinweis: Die Metrik <span class="wintitle"> Geschätzte Echtzeit-Population</span> umfasst keine Geräte, die sich für ein Segment qualifiziert haben, basierend auf Verbindungen, die von einer <span class="wintitle"> Profilzusammenführungsrichtlinie</span> bereitgestellt werden, die eine <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Gerätediagrammoption</a> verwendet. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Geschätzte Gesamtpopulation (Potenzial)</span> </p> </td> 
   <td colname="col2"> <p>Die geschätzte Anzahl Unique Visitors, die sich in Ihrem neuen oder geänderten Segment befinden könnten. Wie bei fast jeder Schätzung garantiert die bisherige Leistung keine zukünftigen Ergebnisse, aber Sie können die geschätzte Gesamtsumme wie folgt verwenden: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Ermitteln Sie, wie viele Personen ein neues oder überarbeitetes Segment erreichen kann, wenn Sie ein Segment erstellen. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Passen Sie das Segment entsprechend Ihren Zielen an. Große Segmente sind beispielsweise für Markenbewusstsein-Kampagnen nützlich, kleinere Segmente sind nützlich für zielgerichtete oder zielgerichtete Kampagnen. </li> 
     </ul> </p> <p> <p>Hinweis: Die Metrik <span class="wintitle"> Geschätzte Gesamtpopulation</span> umfasst keine Geräte, die sich für ein Segment qualifiziert haben, basierend auf Verbindungen, die von einer <span class="wintitle"> Profilzusammenführungsrichtlinie</span> bereitgestellt werden, die eine <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Gerätediagrammoption</a> verwendet. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vorhandene (tatsächliche) Segmentpopulationsdaten definiert {#existing-segment-population}

[!UICONTROL Profile Merge Rules] die tatsächlichen Echtzeit- und Gesamtpopulationszahlen beeinflussen. Diese Summen variieren je nachdem, ob das Segment [!UICONTROL Profile Merge Rule] zu einer Gerätediagrammoption gehört oder nicht. Siehe auch [Für Profilzusammenführungsrichtlinien definierte Optionen](../../features/profile-merge-rules/merge-rule-definitions.md).

### Segmentpopulationsdaten für [!UICONTROL Merge Rules] ohne [!UICONTROL Device Graph Option]

Die folgende Tabelle definiert die tatsächlichen Echtzeit- und Gesamtpopulationsmetriken, wenn Ihre Segmente von einer [!UICONTROL Profile Merge Rule] verwendet werden, die ohne [!UICONTROL device graph] -Option erstellt wurde. Dies sind die Geräteoptionen **[!UICONTROL No Device Options]** und **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Echtzeitpopulation (vorhanden)</span> </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl Unique Visitors, die in Echtzeit für den angegebenen Zeitraum gesehen wurden und die zum Zeitpunkt der Segmenterkennung durch den Audience Manager qualifiziert waren. </p> <p>In <span class="wintitle"> Segment Builder</span> können sich die letzten 30 Tage für Eigenschaften (<span class="wintitle"> Gesamtzahl der Eigenschaftspopulationen</span>) für Eigenschaften und Segmente unterscheiden, die in Echtzeit ausgewertet werden. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Bei Eigenschaften zählt die Metrik der letzten 30 Tage die Anzahl der Unique Users, die sich in den letzten 30 Tagen für diese Eigenschaft qualifiziert haben. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Bei Segmenten, die in Echtzeit ausgewertet werden, zählt die Metrik der letzten 30 Tage die Anzahl der Benutzer, die sich zu einem bestimmten Zeitpunkt in der Vergangenheit für eine Eigenschaft (in diesem Segment) qualifiziert haben und innerhalb der letzten 30 Tage erneut vom Audience Manager gesehen wurden. Angenommen, Sie haben einen Benutzer, der sich vor 60 Tagen für eine Eigenschaft qualifiziert hat und vor 10 Tagen erneut gesehen wurde. In den Daten wird dieser Benutzer nicht zur Eigenschaftszählung hinzugefügt, da er sich vor mehr als 30 Tagen erstmals für die Eigenschaft qualifiziert hat. Sie werden jedoch in die letzten 30 Tage für die Segmente einbezogen, die in Echtzeit ausgewertet werden. Dies liegt daran, dass sie sich für das Segment innerhalb des 30-Tage-Zeitintervalls qualifiziert haben. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Gesamtbevölkerung (bestehende)</span> </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl der Unique Visitors, die ab gestern für das Segment qualifiziert waren. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segmentpopulationsdaten für [!UICONTROL Merge Rules] mit einer [!UICONTROL Device Graph]-Option

In der folgenden Tabelle werden die tatsächlichen Echtzeit- und Gesamtpopulationsmetriken definiert, wenn Ihre Segmente von einer mit der Option [!DNL device graph] erstellten [!UICONTROL Profile Merge Rule] verwendet werden. Dies sind die Geräteoptionen-Einstellungen für [!UICONTROL Profile Link Device Graph], [!DNL Adobe] [!DNL device graph] und andere [!DNL device graph]-Auswahlmöglichkeiten von Drittanbietern, die Ihnen zur Verfügung stehen.


| Spalte A | Spalte B |
---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | Die tatsächliche Anzahl der Geräte, die in Echtzeit mit aktuellen Profilen angezeigt werden und die, wenn sie mit bis zu 100 anderen Geräteprofilen zusammengeführt werden, die mit dem Gerätediagramm verbunden sind, die Eigenschaften enthalten, die für das Segment qualifiziert sind, sobald es vom Audience Manager gesehen wurde. |
| [!UICONTROL Total Population (Existing)] | Die Gesamtzahl der Geräte mit Profilen, die bei der Zusammenführung mit bis zu 100 anderen Geräteprofilen, die durch das Gerätediagramm verbunden sind, alle für das Segment qualifiziert waren. |

### Einschränkungen aufgrund von Neuigkeits- und Frequenzausdrücken bei der Schätzung von Segmentpopulationen

[!UICONTROL Segment Builder] unterstützt Schätzungen der Segmentgröße für Segmentregeln, die bis zu 4 Neuigkeits- und Frequenzausdrücke enthalten. Wenn Sie beim Erstellen einer Segmentregel mehr als 4 Neuigkeits- und Häufigkeitsausdrücke auswählen, zeigt der Segmentschätzer bei der Schätzung der Population einen Fehler an.

### Einschränkungen aufgrund von [!UICONTROL Merge Rules] bei der Schätzung von Segmentpopulationen

Zurzeit gibt es eine bekannte Einschränkung, da unsere Schätzung der Segmentgröße [!UICONTROL profile merge rules] nicht berücksichtigt. Betrachten Sie beispielsweise Segmente mit der **[!UICONTROL No Authenticated Profile + Current Device Profile]** [Zusammenführungsregel](../../features/profile-merge-rules/merge-rule-definitions.md). Aufgrund der Art und Weise, wie wir die Segmentschätzungszahlen derzeit berechnen, umfassen die geschätzten Populationen authentifizierte Profile. Die vorhandenen Segmentpopulationen ignorieren jedoch korrekt authentifizierte Profile.

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm](../../faq/faq-profile-merge.md)
* [Profil-Link](../profile-merge-rules/merge-rules-overview.md)


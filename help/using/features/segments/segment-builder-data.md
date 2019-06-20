---
description: Fügen Sie Eigenschaften im Segmentaufbau hinzu und entfernen Sie diese, um Bestandspopulationen zusammen mit tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Die geschätzten Daten zur Bevölkerungsgröße helfen Ihnen, das richtige Segment für Ihre Kampagne zu erstellen.
seo-description: Fügen Sie Eigenschaften im Segmentaufbau hinzu und entfernen Sie diese, um Bestandspopulationen zusammen mit tatsächlichen und geschätzten Segmentpopulationsdaten anzuzeigen. Die geschätzten Daten zur Bevölkerungsgröße helfen Ihnen, das richtige Segment für Ihre Kampagne zu erstellen.
seo-title: Eigenschaften von Eigenschaften und Segmenten im Segmentaufbau
solution: Audience Manager
title: Eigenschaften von Eigenschaften und Segmenten im Segmentaufbau
uuid: e 1 e 59 c 0 a-b 4 c 7-4 cad -8485-3667 e 0 a 95 e 83
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

Add and remove traits in [!UICONTROL Segment Builder] to see actual trait populations along with actual and estimated segment population data. Die geschätzten Daten zur Bevölkerungsgröße helfen Ihnen, das richtige Segment für Ihre Kampagne zu erstellen.

## Trait Population Data {#trait-population-data}

[!UICONTROL Segment Builder] zeigt Ihnen [!UICONTROL Total Trait Population] den letzten Tag, wenn Sie einem Segment eine Eigenschaft hinzufügen. This data appears in the blue field around your selected trait in the [!UICONTROL Basic View] section.

![](assets/trait-size.png)

Die folgende Tabelle definiert die Eigenschaftenmetriken für Eigenschaften.

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Gesamtanzahl der Eigenschaften</span> </p> </td>
   <td colname="col2"> <p>Die Anzahl eindeutiger IDs, die die ausgewählte Eigenschaft in ihrem Profil enthalten. </p> </td>
  </tr> 
 </tbody> 
</table>

## Calculating Real and Estimated Segment Populations {#calculating-real-estimated-populations}

Wenn Sie ein neues Segment erstellen oder ein vorhandenes Segment ändern, dauert der Audience Manager 24 Stunden, bis die Ergebnisse für tatsächliche Echtzeit- und Gesamtsegmentpopulationen angezeigt werden.

Audience Manager kann jedoch sofort die Echtzeit- und Gesamtpopulationsgröße Ihres Segments schätzen. Diese Schätzungen basieren auf berechneten historischen Daten und geben Ergebnisse mit einem Konfidenzintervall von 95% zurück.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder], a blue bar on the estimated population graphs indicates the possible upper and lower ranges for segment size. Obwohl die vergangene Leistung zukünftige Ergebnisse nicht garantiert, können die geschätzten Daten Ihnen dabei helfen, die potenzielle Größe eines neuen oder bearbeiteten Segments zu verstehen.

## Segment Population Data Overview {#segment-populations}

[!UICONTROL Segment Builder] zeigt Ihnen die Segmentdaten während der Erstellung und Bearbeitung von Segmenten an.

* For estimated segment population data (real-time and total), [!UICONTROL Segment Builder] does not update the graphs automatically as you add or remove traits in a segment. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers.

* For actual (real) segment population data (real-time and total), [!UICONTROL Segment Builder] updates the segment graph automatically when you load an existing segment. Bei neuen Segmenten oder wenn Sie einem vorhandenen Segment neue Eigenschaften hinzufügen, werden die tatsächlichen Populationsdaten erst nach 24 Stunden nach dem Erstellen des Segments aktualisiert.

![](assets/segment-data.png)

Weitere Informationen zu den geschätzten und tatsächlichen Segmentpopulationsdaten finden Sie in den unten stehenden Definitionen.

## Estimated Segment Population Data Defined {#estimated-segment-population}

In der folgenden Tabelle sind die geschätzten Bevölkerungsmetriken definiert.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Geschätzte Echtzeitpopulation (Potenzielles Potenzial) </span> </p> </td> 
   <td colname="col2"> <p>Die geschätzte Anzahl individueller Besucher, die in Echtzeit für den angegebenen Zeitraum angesehen wurden und für das Segment qualifiziert waren, wenn sie von Audience Manager gesehen wurden. </p> <p>In <span class="wintitle"> Segment Builder</span>, the last 30-day populations for traits (<span class="wintitle"> Total Trait Populations</span>), can be different for traits and segments evaluated in real-times. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Bei Eigenschaften zählt die letzte 30-Tage-Metrik die Anzahl der Unique Users, die in den letzten 30 Tagen für diese Eigenschaft qualifiziert waren. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Bei Segmenten, die in Echtzeit ausgewertet werden, zählt die letzte 30-Tage-Metrik die Anzahl der Benutzer, die zu einem bestimmten Zeitpunkt für eine Eigenschaft (in diesem Segment) qualifiziert haben und von Audience Manager innerhalb der letzten 30 Tage erneut gesehen wurden. Angenommen, Sie haben einen Benutzer, der sich vor 60 Tagen für eine Eigenschaft qualifiziert hat und vor 10 Tagen erneut angezeigt wurde. In den Daten wird dieser Benutzer nicht der Anzahl der Eigenschaften hinzugefügt, da er vor mehr als 30 Tagen für die Eigenschaft qualifiziert wurde. Sie werden jedoch in der letzten 30-Tage-Anzahl für die in Echtzeit ausgewerteten Segmente einbezogen. Dies liegt daran, dass sie innerhalb des 30-Tage-Zeitintervalls für das Segment qualifiziert sind. </li>
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Real-Time Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Geschätzte Gesamtpopulation (Potenzielles Potenzial)</span> </p> </td> 
   <td colname="col2"> <p>Die geschätzte Anzahl individueller Besucher, die sich in Ihrem neuen oder geänderten Segment befinden können. Wie bei fast jeder Schätzung garantiert auch die vergangene Performance keine zukünftigen Ergebnisse, Sie können jedoch die geschätzte Summe für Folgendes verwenden: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Erkennen Sie, wie viele Personen ein neues oder überarbeitetes Segment erreichen können, wenn Sie ein Segment erstellen. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Passen Sie das Segment je nach Ihren Zielen an. Große Segmente eignen sich beispielsweise für Markenbewusstsein-Kampagnen und kleinere Segmente sind nützlich für fokussierte Targeting- oder Neutargeting-Kampagnen. </li> 
     </ul> </p> <p> <p>Note: The <span class="wintitle"> Estimated Total Population</span> metric does not include devices that have qualified for a segment based on connections provided by a <span class="wintitle"> Profile Merge Rule</span> that uses a <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> device graph option</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Existing (Actual) Segment Population Data Defined {#existing-segment-population}

[!UICONTROL Profile Merge Rules] hat die tatsächliche Echtzeit- und Gesamtanzahl der Populationszahlen. These totals vary depending on if the [!UICONTROL Profile Merge Rule] a segment belongs to uses a device graph option or not. See also, [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

### Segmentpopulationsdaten für Zusammenführungsregeln ohne Gerätediagrammoption

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created without a device graph option. These are the device options settings **[!UICONTROL No Device Options]** and **[!UICONTROL Current Device Proflie]**.

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
   <td colname="col2"> <p>Die tatsächliche Anzahl individueller Besucher, die in Echtzeit für den angegebenen Zeitraum angesehen wurden und für das Segment qualifiziert waren, wenn sie von Audience Manager gesehen wurden. </p> <p>In <span class="wintitle"> Segment Builder</span>, the last 30-day populations for traits (<span class="wintitle"> Total Trait Populations</span>), can be different for traits and segments evaluated in real-time. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Bei Eigenschaften zählt die letzte 30-Tage-Metrik die Anzahl der Unique Users, die in den letzten 30 Tagen für diese Eigenschaft qualifiziert waren. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Bei Segmenten, die in Echtzeit ausgewertet werden, zählt die letzte 30-Tage-Metrik die Anzahl der Benutzer, die zu einem bestimmten Zeitpunkt für eine Eigenschaft (in diesem Segment) qualifiziert haben und von Audience Manager innerhalb der letzten 30 Tage erneut gesehen wurden. Angenommen, Sie haben einen Benutzer, der sich vor 60 Tagen für eine Eigenschaft qualifiziert hat und vor 10 Tagen erneut angezeigt wurde. In den Daten wird dieser Benutzer nicht der Anzahl der Eigenschaften hinzugefügt, da er vor mehr als 30 Tagen für die Eigenschaft qualifiziert wurde. Sie werden jedoch in der letzten 30-Tage-Anzahl für die in Echtzeit ausgewerteten Segmente einbezogen. Dies liegt daran, dass sie innerhalb des 30-Tage-Zeitintervalls für das Segment qualifiziert sind. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Gesamtpopulation (vorhanden)</span> </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Anzahl individueller Besucher, die seit gestern für das Segment qualifiziert waren. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segmentpopulationsdaten für Zusammenführungsregeln mit einer Gerätediagrammoption

The following table defines the actual real-time and total population metrics when your segments are used by a [!UICONTROL Profile Merge Rule] created with a device graph option. These are the device options settings for the [!UICONTROL Profile Link Device Graph], the [!DNL Adobe] device graph, and other third-party device graph choices that are available to you.

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Population in Echtzeit (vorhanden)</span> </p> </td> 
   <td colname="col2"> <p>The actual number of devices seen in real-time with current profiles that, when merged with up to 3-other device profiles connected by the device graph, contains the traits to qualify for the segment the moment it was seen by <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Gesamtpopulation (vorhanden)</span> </p> </td> 
   <td colname="col2"> <p>Die Gesamtzahl der Geräte mit Profilen, die bei der Zusammenführung mit bis zu 3 anderen Geräteprofilen, die durch das Gerätediagramm verbunden sind, für das Segment qualifiziert waren. </p> </td>
  </tr>
 </tbody>
</table>

### Einschränkungen aufgrund von Neuigkeit- und Frequenzausdrücken beim Schätzen von Segmentpopulationen

[!UICONTROL Segment Builder] unterstützt Segmentgrößenschätzungen für Segmentregeln mit bis zu vier Neuigkeit- und Frequenzausdrücken. Wenn Sie beim Erstellen einer Segmentregel mehr als 4 Neuigkeit- und Häufigkeitsausdrücke auswählen, zeigt die Segmentschätzung einen Fehler bei der Schätzung der Population an.

### Einschränkungen aufgrund von Zusammenführungsregeln beim Schätzen von Segmentpopulationen

Derzeit gibt es eine bekannte Einschränkung, da unsere Schätzung für die Segmentgröße keine Profilzusammenführungsregeln berücksichtigt. For example, look at segments with the **No Authenticated Profile + Current Device Profile** [merge rule](../../features/profile-merge-rules/merge-rule-definitions.md). Aufgrund der Art und Weise, wie wir die Segmentschätzung-Zahlen derzeit berechnen, enthalten die geschätzten Populationen authentifizierte Profile. Die vorhandenen Segmentpopulationen ignorieren authentifizierte Profile jedoch korrekt.

>[!MORE_ LIKE_ THIS]
>
>* [Regeln für die Profilzusammenführung und häufig gestellte Fragen zum Gerätediagramm](../../faq/faq-profile-merge.md)
>* [Profillink](../../features/profile-merge-rules/merge-rules-overview.md)


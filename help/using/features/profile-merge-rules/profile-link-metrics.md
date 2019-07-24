---
description: Profillinkmetriken liefern Daten zu Personen und Geräten, die sich bei Ihrer Site authentifizieren. Die Daten und Diagramme in Profillink-Updates werden dynamisch aktualisiert, wenn Sie eine Regel zusammenführen oder auf eine vorhandene Regel im Dashboard "Profile Merge Rules" klicken. Diese Metriken können Gerätediagramme aus den Adobe Experience Cloud Device Co-op oder anderen Gerätediagrammquellen von Drittanbietern enthalten.
seo-description: Profillinkmetriken liefern Daten zu Personen und Geräten, die sich bei Ihrer Site authentifizieren. Die Daten und Diagramme in Profillink-Updates werden dynamisch aktualisiert, wenn Sie eine Regel zusammenführen oder auf eine vorhandene Regel im Dashboard "Profile Merge Rules" klicken. Diese Metriken können Gerätediagramme aus den Adobe Experience Cloud Device Co-op oder anderen Gerätediagrammquellen von Drittanbietern enthalten.
seo-title: Berichtsmetriken für Regeln zur Profilzusammenführung
solution: Audience Manager
title: Berichtsmetriken für Regeln zur Profilzusammenführung
uuid: 76 a 86 ff 0-4 c 64-4734-aec 0-0 a 8828942096
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Report Metrics for Profile Merge Rules {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Link] Metriken liefern Daten zu Personen und Geräten, die sich auf Ihrer Site authentifizieren. The data and graphs in [!UICONTROL Profile Link] update dynamically as you create a merge rules or when you click an existing rule from the [!UICONTROL Profile Merge Rules] dashboard. These metrics can include device graph from the [!DNL Adobe Experience Cloud Device Co-op] or other third-party device graph sources.

## Merge Rule Metrics {#merge-rule-metrics}

Reports return data in side-by-side bar graphs when your merge rules use data from the [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) or other, third-party device graphs you may have access to in [!DNL Audience Manager]. This lets you compare your authenticated, first-party data with cross-device data provided by the [!UICONTROL Experience Cloud Device Co-op] or another, third-party device graph. For information about data returned by the [!UICONTROL Device Co-op], see [The Device Graph: Internal Processes and Output](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Diese Daten werden täglich aktualisiert.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrik </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Authentifizierte Aktivität</span></b> </p> </td> 
   <td colname="col2"> <p>Zeigt Folgendes: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Aktive Personen</span>: Die Anzahl der Personen, die in den letzten 60 Tagen für Ihre Site authentifiziert haben. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Geräteübergreifend: Die Gesamtanzahl </span> der in der<a href="../../features/profile-merge-rules/merge-rules-start.md#create-data-source"> </a> Datenquelle<a href="../../features/manage-datasources.md#create-data-source"> des ausgewählten </a> Authentifizierungsprofils gespeicherten Geräte-IDs<a href="../../features/profile-merge-rules/merge-rule-definitions.md"> für die Lebensdauer, die die Datenquelle bereits vorhanden ist.</a> </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % Aktive Personen</span>: Zeigt <span class="wintitle"> aktive Personen</span> als % an. </li> 
    </ul> <p> <span class="wintitle"> Mit authentifizierten Aktivitäten</span> können Sie Datenquellen nach Aktivität, Volumen und Prozent vergleichen. Sie kann Ihnen dabei helfen, eine Datenquelle zu finden, die viele Personen und einen hohen Prozentsatz aktiver Benutzer aufweist. Sie können auch Werte beim Vergleich von Datenquellen mit hohem Anteil aktiver Benutzer im Vergleich zur Gesamtgröße der Zielgruppe finden. Manchmal ist eine Datenquelle mit niedriger Gesamtanzahl der Lebensdauer und einer hohen Aktivität wertvoller als die mit hohen Lebensdauerergebnissen und niedrigen Aktivitätszahlen. </p> <p> <p>Note: The <span class="wintitle"> Authenticated Activity</span> metrics contain <span class="wintitle"> Profile Link</span> data only. This report does not include <span class="wintitle"> Device Graph</span> data. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Durchschnittliche Geräte pro Person</span></b> </p> </td> 
   <td colname="col2"> <p> Zeigt die durchschnittliche Anzahl von Geräten an, die von Besuchern verwendet werden, die sich für die ausgewählte Datenquelle auf Ihrer Site authentifiziert haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Geräte insgesamt</span></b> </p> </td> 
   <td colname="col2"> <p>Zeigt die Gesamtzahl der Geräte an, die Personen für die Authentifizierung Ihrer Site für die ausgewählte Datenquelle verwendet haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Personen insgesamt</span></b> </p> </td> 
   <td colname="col2"> <p>Zeigt die Gesamtanzahl der Personen an, die für die ausgewählte Datenquelle als spezifisch identifiziert wurden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Device Graph Metrics {#device-graph-metrics}

The [!UICONTROL Merge Rules] reports also show data on the total number of people and devices who have visited your site for the selected data source and device graph. Diese Metriken geben Daten basierend auf voreingestellten Zeitintervallen (der Rückblickzeitraum) zurück, die je nach Gerät, das Sie beim Erstellen einer Regel auswählen, variieren. In der folgenden Tabelle sind die Berichtsintervalle für die einzelnen Gerätediagrammoptionen aufgeführt.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gerätediagrammoption </th> 
   <th colname="col2" class="entry"> Berichtssuchintervall </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profillink</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Personen insgesamt: 60 Tage </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Geräte insgesamt: 120 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Co-op Device Graph</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Personen insgesamt: 180 Tage </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Geräte insgesamt: 180 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Liveramp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Personen insgesamt: 180 Tage </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Geräte insgesamt: 180 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Personen insgesamt: 60 Tage </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Geräte insgesamt 60 Tage </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Reports {#sample-reports}

### Standard-Profillink-Bericht

A standard [!UICONTROL Profile Link] report looks like the following example. Zusammenführungsregeln, die mehrere Datenquellen (bis zu 3, maximal) verwenden, zeigen Diagramme in separaten Registern für jede Datenquelle an. This merge rule does not include [!UICONTROL Device Co-op] data.

![](assets/coop-metrics1.png)

### Profillink-Bericht mit Gerätediagrammdaten

A [!UICONTROL Profile Link] report that includes device graph data from the [!UICONTROL Adobe Experience Cloud Device Co-op] or a third-party device graph shows [!UICONTROL Profile Link] and device graph data with side-by-side bar graphs. Placing these graphs adjacent to each other lets you evaluate the benefits of using the [!UICONTROL Experience Cloud Device Co-op] compared to [!UICONTROL Profile Link] by itself. Zusammenführungsregeln, die mehrere Datenquellen (bis zu 3, maximal) verwenden, zeigen Diagramme in separaten Registern für jede Datenquelle an. As a reminder, the [!UICONTROL Authenticated Activity] graph and metrics do not return data from the [!DNL Adobe] device graph or other, third-party device graphs you may have access to in [!DNL Audience Manager].

![](assets/coop-metrics2.png)

## Profile Link Trend Graphs {#profile-link-trend}

In addition to the other data visualizations, [!UICONTROL Profile Link] reports include a line graph. Mit dem Liniendiagramm zeigen Sie Trends im Laufe der Zeit für Ihre Profilregeln an. Trend graphs (and the other reports) are available when you click a rule from the [!UICONTROL Profile Merge Rules] landing page ( **[!UICONTROL Audience Data > Profile Merge Rules]**). These graphs include device graph data if you're a member of the [!UICONTROL Device Co-op] or other, third-party device graphs you may have access to in [!DNL Audience Manager]. Klicken Sie auf eine Trendlinie, um die zugrunde liegenden Daten zu sehen.

![](assets/authenticated_trends.png)

>[!MORE_ LIKE_ THIS]
>
>* [Häufig gestellte Fragen zur Profilzusammenführung](../../faq/faq-profile-merge.md)


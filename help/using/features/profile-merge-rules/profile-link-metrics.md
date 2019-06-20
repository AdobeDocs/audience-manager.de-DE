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


# Berichtsmetriken für Regeln zur Profilzusammenführung {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Link] Metriken liefern Daten zu Personen und Geräten, die sich auf Ihrer Site authentifizieren. Die Daten und Diagramme werden [!UICONTROL Profile Link] dynamisch beim Erstellen einer Zusammenführungsregeln oder beim Klicken auf eine vorhandene Regel im [!UICONTROL Profile Merge Rules] Dashboard aktualisiert. Diese Metriken können Gerätediagramme aus den Gerätediagrammen des [!DNL Adobe Experience Cloud Device Co-op] oder anderer Drittanbieter enthalten.

## Zusammenführungsregelmetriken {#merge-rule-metrics}

Berichte geben Daten in nebeneinander liegenden Balkendiagrammen zurück, wenn Ihre Zusammenführungsregeln Daten aus den [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) oder anderen Gerätediagrammen von Drittanbietern verwenden [!DNL Audience Manager]. Dadurch können Sie Ihre authentifizierten, Erstanbieterdaten mit geräteübergreifenden Daten vergleichen, die vom [!UICONTROL Experience Cloud Device Co-op] oder einem anderen Gerätediagramm bereitgestellt werden. Informationen zu den von der Seite zurückgegebenen Daten [!UICONTROL Device Co-op]finden Sie [unter Gerätediagramm: Interne Prozesse und Ausgabe](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Diese Daten werden täglich aktualisiert.

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
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Cross Device</span>: The total number of <a href="../../features/profile-merge-rules/merge-rules-start.md#create-data-source"> Cross Device IDs</a> stored in the <a href="../../features/manage-datasources.md#create-data-source"> Data Source</a> of the selected <a href="../../features/profile-merge-rules/merge-rule-definitions.md"> Authenticated Profile</a> for the lifetime that the data source has existed. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % Aktive Personen</span>: Zeigt <span class="wintitle"> aktive Personen</span> als % an. </li> 
    </ul> <p> <span class="wintitle"> Mit authentifizierten Aktivitäten</span> können Sie Datenquellen nach Aktivität, Volumen und Prozent vergleichen. Sie kann Ihnen dabei helfen, eine Datenquelle zu finden, die viele Personen und einen hohen Prozentsatz aktiver Benutzer aufweist. Sie können auch Werte beim Vergleich von Datenquellen mit hohem Anteil aktiver Benutzer im Vergleich zur Gesamtgröße der Zielgruppe finden. Manchmal ist eine Datenquelle mit niedriger Gesamtanzahl der Lebensdauer und einer hohen Aktivität wertvoller als die mit hohen Lebensdauerergebnissen und niedrigen Aktivitätszahlen. </p> <p> <p>Hinweis: Die Metriken <span class="wintitle"> für Authentifizierungsaktivitäten</span> enthalten <span class="wintitle"> nur</span> Profillinkdaten. Der Bericht enthält <span class="wintitle"> keine Gerätediagrammdaten</span> . </p> </p> </td> 
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

## Gerätediagrammmetriken {#device-graph-metrics}

Die [!UICONTROL Merge Rules] Berichte zeigen auch Daten über die Gesamtanzahl der Personen und Geräte an, die Ihre Site für die ausgewählte Datenquelle und das ausgewählte Gerätediagramm besucht haben. Diese Metriken geben Daten basierend auf voreingestellten Zeitintervallen (der Rückblickzeitraum) zurück, die je nach Gerät, das Sie beim Erstellen einer Regel auswählen, variieren. In der folgenden Tabelle sind die Berichtsintervalle für die einzelnen Gerätediagrammoptionen aufgeführt.

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

## Beispielberichte {#sample-reports}

### Standard-Profillink-Bericht

Ein [!UICONTROL Profile Link] Standardbericht sieht wie folgt aus. Zusammenführungsregeln, die mehrere Datenquellen (bis zu 3, maximal) verwenden, zeigen Diagramme in separaten Registern für jede Datenquelle an. Diese Zusammenführungsregel enthält [!UICONTROL Device Co-op] keine Daten.

![](assets/coop-metrics1.png)

### Profillink-Bericht mit Gerätediagrammdaten

Ein [!UICONTROL Profile Link] Bericht, der Gerätediagrammdaten aus dem Gerätediagramm [!UICONTROL Adobe Experience Cloud Device Co-op] oder einem Drittanbieter-Gerätediagramm enthält, zeigt [!UICONTROL Profile Link] Daten zu Gerätediagrammen mit nebeneinander dargestellten Balkendiagrammen an. Wenn Sie diese Diagramme nebeneinander platzieren, können Sie die Vorteile der Verwendung [!UICONTROL Experience Cloud Device Co-op][!UICONTROL Profile Link] des Vergleichs vergleichen. Zusammenführungsregeln, die mehrere Datenquellen (bis zu 3, maximal) verwenden, zeigen Diagramme in separaten Registern für jede Datenquelle an. Die [!UICONTROL Authenticated Activity] Grafik und die Metriken geben keine Daten aus dem [!DNL Adobe] Gerätediagramm oder anderen Gerätediagrammen von Drittanbietern zurück, auf die Sie Zugriff [!DNL Audience Manager]haben.

![](assets/coop-metrics2.png)

## Profillink-Trenddiagramme {#profile-link-trend}

Zusätzlich zu den anderen Datenvisualisierungen enthalten [!UICONTROL Profile Link] Berichte ein Liniendiagramm. Mit dem Liniendiagramm zeigen Sie Trends im Laufe der Zeit für Ihre Profilregeln an. Trenddiagramme (und andere Berichte) sind verfügbar, wenn Sie auf eine Regel von der [!UICONTROL Profile Merge Rules] Landingpage ( **[!UICONTROL Audience Data > Profile Merge Rules]**) klicken. Zu diesen Diagrammen zählen Gerätediagrammdaten, wenn Sie Mitglied der [!UICONTROL Device Co-op] oder anderer Gerätediagramme sind, auf die Sie Zugriff [!DNL Audience Manager]haben. Klicken Sie auf eine Trendlinie, um die zugrunde liegenden Daten zu sehen.

![](assets/authenticated_trends.png)

>[!MORE_ LIKE_ THIS]
>
>* [Häufig gestellte Fragen zur Profilzusammenführung](../../faq/faq-profile-merge.md)


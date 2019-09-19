---
description: Profillink-Metriken liefern Daten zu Personen und Geräten, die sich für Ihre Site authentifizieren. Die Daten und Diagramme in Profillink werden dynamisch aktualisiert, wenn Sie eine Zusammenführungsregel erstellen oder wenn Sie im Dashboard Regeln zur Profilzusammenführung auf eine vorhandene Regel klicken. Diese Metriken können Gerätediagramme aus der Adobe Experience Cloud-Gerätekooperation oder anderen Gerätediagrammen von Drittanbietern enthalten.
seo-description: Profillink-Metriken liefern Daten zu Personen und Geräten, die sich für Ihre Site authentifizieren. Die Daten und Diagramme in Profillink werden dynamisch aktualisiert, wenn Sie eine Zusammenführungsregel erstellen oder wenn Sie im Dashboard Regeln zur Profilzusammenführung auf eine vorhandene Regel klicken. Diese Metriken können Gerätediagramme aus der Adobe Experience Cloud-Gerätekooperation oder anderen Gerätediagrammen von Drittanbietern enthalten.
seo-title: Berichtsmetriken für Regeln zur Profilzusammenführung
solution: Audience Manager
title: Berichtsmetriken für Regeln zur Profilzusammenführung
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


#  Berichtsmetriken für Regeln zur Profilzusammenführung {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Link] Metriken liefern Daten zu Personen und Geräten, die sich für Ihre Site authentifizieren. Die Daten und Diagramme in [!UICONTROL Profile Link] werden beim Erstellen einer Zusammenführungsregel oder beim Klicken auf eine vorhandene Regel im [!UICONTROL Profile Merge Rules] Dashboard dynamisch aktualisiert. Diese Metriken können Gerätediagramme aus den [!DNL Adobe Experience Cloud Device Co-op] oder anderen Gerätediagrammen von Drittanbietern enthalten.

## Regelmetriken zusammenführen {#merge-rule-metrics}

Berichte geben Daten in nebeneinander liegenden Balkendiagrammen zurück, wenn Ihre Zusammenführungsregeln Daten aus der [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) oder anderen Gerätediagrammen von Drittanbietern verwenden, auf die Sie möglicherweise Zugriff haben [!DNL Audience Manager]. Auf diese Weise können Sie Ihre authentifizierten Erstanbieter-Daten mit geräteübergreifenden Daten vergleichen, die vom [!UICONTROL Experience Cloud Device Co-op] oder einem anderen Gerätediagramm eines Drittanbieters bereitgestellt werden. Informationen zu den vom [!UICONTROL Device Co-op]Gerät zurückgegebenen Daten finden Sie [im Gerätediagramm: Interne Prozesse und Ausgabe](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Diese Daten werden täglich aktualisiert.

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
   <td colname="col2"> <p>Zeigt: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Aktive Personen</span>: Die Anzahl der Personen, die sich in den letzten 60 Tagen bei Ihrer Site authentifiziert haben. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Geräteübergreifend</span>: Die Gesamtzahl der <a href="../../features/profile-merge-rules/merge-rules-start.md#create-data-source"> geräteübergreifenden IDs</a> , die während der Lebensdauer, die die Datenquelle<a href="../../features/manage-datasources.md#create-data-source"> hat, in der </a> Datenquelledes ausgewählten <a href="../../features/profile-merge-rules/merge-rule-definitions.md"> authentifizierten Profils</a> gespeichert wurden. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % Aktive Personen</span>: Zeigt <span class="wintitle"> Aktive Personen</span> als % an. </li> 
    </ul> <p> <span class="wintitle"> Mit authentifizierter Aktivität</span> können Sie Datenquellen nach Aktivität, Volumen und Prozent vergleichen. Es kann Ihnen helfen, eine Datenquelle zu finden, die viele Personen und einen hohen Prozentsatz aktiver Benutzer hat. Oder Sie können einen Wert beim Vergleich von Datenquellen mit einem hohen Anteil aktiver Benutzer im Vergleich zur Gesamtgröße der Zielgruppe finden. Manchmal ist beispielsweise eine Datenquelle mit einer niedrigen Gesamtlebensdauer und einer hohen Aktivität wertvoller als eine Datenquelle mit einer hohen Lebensdauer und einer niedrigen Aktivitätszahl. </p> <p> <p>Hinweis: Die <span class="wintitle"> Metriken für authentifizierte Aktivitäten</span> enthalten nur <span class="wintitle"> Profillinkdaten</span> . Dieser Bericht enthält keine <span class="wintitle"> Gerätediagrammdaten</span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Durchschnittliche Geräte pro Person</span></b> </p> </td> 
   <td colname="col2"> <p> Zeigt die durchschnittliche Anzahl der Geräte an, die von Besuchern verwendet werden, die sich für die ausgewählte Datenquelle bei Ihrer Site authentifiziert haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Geräte insgesamt</span></b> </p> </td> 
   <td colname="col2"> <p>Zeigt die Gesamtanzahl der Geräte an, auf denen die Authentifizierung für die ausgewählte Datenquelle auf Ihrer Site erfolgte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Personen insgesamt</span></b> </p> </td> 
   <td colname="col2"> <p>Zeigt die Gesamtanzahl der Personen an, die für die ausgewählte Datenquelle deterministisch identifiziert wurden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Gerätediagrammmetriken {#device-graph-metrics}

Die [!UICONTROL Merge Rules] Berichte zeigen auch Daten zur Gesamtzahl der Personen und Geräte an, die Ihre Site für die ausgewählte Datenquellen- und Gerätegrafik besucht haben. Diese Metriken geben Daten basierend auf voreingestellten Zeitintervallen (der Rückblickzeit) zurück, die je nach der Geräteoption, die Sie beim Erstellen einer Regel auswählen, variieren. In der folgenden Tabelle sind diese Berichtintervalle für die einzelnen Gerätediagrammoptionen aufgeführt.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gerätediagrammoption </th> 
   <th colname="col2" class="entry"> Rückblickintervall für Berichte </th> 
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
   <td colname="col1"> <p><span class="wintitle"> Co-op-Gerätediagramm</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Personen insgesamt: 180 Tage </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Geräte insgesamt: 180 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Personen insgesamt: 180 Tage </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Geräte insgesamt: 180 Tage </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Band</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Personen insgesamt: 60 Tage </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Geräte insgesamt 60 Tage </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielberichte {#sample-reports}

### Standardprofilverknüpfungsbericht

Ein Standardbericht [!UICONTROL Profile Link] sieht wie im folgenden Beispiel aus. Regeln zusammenführen, die mehrere Datenquellen (bis zu 3) verwenden, zeigen Diagramme auf separaten Registerkarten für jede Datenquelle an. Diese Zusammenführungsregel enthält keine [!UICONTROL Device Co-op] Daten.

![](assets/coop-metrics1.png)

### Profillinkbericht mit Gerätediagrammdaten

Ein [!UICONTROL Profile Link] Bericht, der Gerätediagrammdaten aus dem [!UICONTROL Adobe Experience Cloud Device Co-op] oder einem Gerätediagramm eines Drittanbieters enthält, zeigt [!UICONTROL Profile Link] und zeigt Gerätediagramme mit nebeneinander liegenden Balkendiagrammen an. Wenn Sie diese Diagramme nebeneinander anordnen, können Sie die Vorteile der Verwendung der Diagramme [!UICONTROL Experience Cloud Device Co-op] im Vergleich zu [!UICONTROL Profile Link] selbst bewerten. Regeln zusammenführen, die mehrere Datenquellen (bis zu 3) verwenden, zeigen Diagramme auf separaten Registerkarten für jede Datenquelle an. Zur Erinnerung: Das [!UICONTROL Authenticated Activity] Diagramm und die Metriken geben keine Daten aus dem [!DNL Adobe] Gerätediagramm oder anderen Gerätediagrammen von Drittanbietern zurück, auf die Sie möglicherweise Zugriff haben [!DNL Audience Manager].

![](assets/coop-metrics2.png)

## Trenddiagramme für Profillinks {#profile-link-trend}

Zusätzlich zu den anderen Datenvisualisierungen enthalten [!UICONTROL Profile Link] Berichte ein Liniendiagramm. Das Liniendiagramm zeigt Ihnen Trends im Zeitverlauf für Ihre Profilregeln. Trenddiagramme (und andere Berichte) stehen zur Verfügung, wenn Sie auf eine Regel auf der [!UICONTROL Profile Merge Rules] Einstiegsseite ( **[!UICONTROL Audience Data > Profile Merge Rules]**) klicken. Diese Diagramme enthalten Gerätediagrammdaten, wenn Sie Mitglied der [!UICONTROL Device Co-op] oder anderer Gerätediagramme von Drittanbietern sind, auf die Sie möglicherweise Zugriff haben [!DNL Audience Manager]. Klicken Sie auf eine Trendlinie, um die zugrunde liegenden Daten anzuzeigen.

![](assets/authenticated_trends.png)

>[!MORE_LIKE_THIS]
>
>* [Häufig gestellte Fragen zu Regeln zur Profilzusammenführung](../../faq/faq-profile-merge.md)


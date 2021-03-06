---
description: Profillinkmetriken bieten Daten zu Personen und Geräten, die sich für Ihre Site authentifizieren. Die Daten und Diagramme im Profillink werden beim Erstellen von Zusammenführungsregeln oder beim Klicken auf eine vorhandene Regel im Dashboard Profilzusammenführungsregeln dynamisch aktualisiert. Diese Metriken können Gerätediagramme aus der Adobe Experience Cloud-Gerätekooperation oder anderen Gerätediagrammquellen von Drittanbietern enthalten.
seo-description: Profillinkmetriken bieten Daten zu Personen und Geräten, die sich für Ihre Site authentifizieren. Die Daten und Diagramme im Profillink werden beim Erstellen von Zusammenführungsregeln oder beim Klicken auf eine vorhandene Regel im Dashboard Profilzusammenführungsregeln dynamisch aktualisiert. Diese Metriken können Gerätediagramme aus der Adobe Experience Cloud-Gerätekooperation oder anderen Gerätediagrammquellen von Drittanbietern enthalten.
seo-title: Berichtsmetriken für Profilzusammenführungsrichtlinien
solution: Audience Manager
title: Berichtsmetriken für Profilzusammenführungsrichtlinien
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profilzusammenführung
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 2%

---

# Berichtsmetriken für Profilzusammenführungsrichtlinien {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] Metriken liefern Daten zu Personen und Geräten, die sich bei Ihrer Site authentifizieren. Die Daten und Diagramme in [!UICONTROL Profile Merge Rule Reports] werden beim Erstellen einer Zusammenführungsregel oder beim Klicken auf eine vorhandene Regel im [!UICONTROL Profile Merge Rules]-Dashboard dynamisch aktualisiert. Diese Metriken können Gerätediagramme aus den Quellen [!DNL Adobe Experience Cloud Device Co-op] oder anderen Gerätediagrammen von Drittanbietern enthalten.

## Metriken zu Zusammenführungsregeln {#merge-rule-metrics}

Berichte geben Daten in parallelen Balkendiagrammen zurück, wenn Ihre Zusammenführungsregeln Daten aus der [Adobe Experience Cloud Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/about/overview.html) oder anderen Gerätediagrammen von Drittanbietern verwenden, auf die Sie möglicherweise in [!DNL Audience Manager] zugreifen können. Auf diese Weise können Sie Ihre authentifizierten Erstanbieterdaten mit geräteübergreifenden Daten vergleichen, die vom [!UICONTROL Experience Cloud Device Co-op] oder einem anderen Gerätediagramm von Drittanbietern bereitgestellt werden. Informationen zu den von [!UICONTROL Device Co-op] zurückgegebenen Daten finden Sie unter [Das Gerätediagramm: Interne Prozesse und Ausgabe](https://experienceleague.adobe.com/docs/device-co-op/using/device-graph/device-graph-overview.html). Diese Daten werden täglich aktualisiert.

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
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Geräteübergreifend</span>: Die Gesamtanzahl der  <a href="merge-rules-start.md#create-data-source"> geräteübergreifenden </a> IDs, die in der  <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html"> Data </a> Sources-Ressource des ausgewählten  <a href="merge-rule-definitions.md"> authentifizierten </a> Profils während der Lebensdauer gespeichert sind, in der die Datenquelle existiert. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % Aktive Personen</span>: Zeigt  <span class="wintitle"> aktive </span> Menschen in % an. </li> 
    </ul> <p> <span class="wintitle"> Authentifizierte </span> Aktivitätstypen: Sie vergleichen Datenquellen nach Aktivität, Volumen und Prozent. Es kann Ihnen dabei helfen, eine Datenquelle zu finden, die viele Personen und einen hohen Prozentsatz aktiver Benutzer aufweist. Oder Sie können beim Vergleich von Datenquellen mit einem hohen Anteil aktiver Benutzer im Vergleich zur Gesamtzielgruppengröße einen Wert finden. Manchmal sind Datenquellen mit niedrigen Gesamtlebenszeitzahlen und hoher Aktivität nützlicher als solche mit hohen Lebenszyklusergebnissen und niedrigen Aktivitätszahlen. </p> <p> <p>Hinweis: Die Metriken <span class="wintitle"> Authentifizierte Aktivität</span> enthalten nur <span class="wintitle"> Profillink</span> -Daten. Dieser Bericht enthält keine <span class="wintitle">-Gerätediagrammdaten</span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Durchschnittliche Geräte pro Person</span></b> </p> </td> 
   <td colname="col2"> <p> Zeigt die durchschnittliche Anzahl der Geräte an, die von Besuchern verwendet werden, die sich bei Ihrer Site für die ausgewählte Datenquelle authentifiziert haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Geräte insgesamt</span></b> </p> </td> 
   <td colname="col2"> <p>Zeigt die Gesamtzahl der Geräte an, die zum Authentifizieren bei Ihrer Site für die ausgewählte Datenquelle verwendet wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Personen insgesamt</span></b> </p> </td> 
   <td colname="col2"> <p>Zeigt die Gesamtzahl der Personen an, die für die ausgewählte Datenquelle deterministisch identifiziert wurden. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Gerätediagrammmetriken {#device-graph-metrics}

Die [!UICONTROL Merge Rules] -Berichte zeigen auch Daten zur Gesamtzahl der Personen und Geräte an, die Ihre Site für die ausgewählte Datenquelle und das ausgewählte Gerätediagramm besucht haben. Diese Metriken geben Daten basierend auf voreingestellten Zeitintervallen (dem Rückblickzeitraum) zurück, die je nach der Geräteoption variieren, die Sie beim Erstellen einer Regel auswählen. In der folgenden Tabelle sind diese Berichtsintervalle für die einzelnen Gerätediagrammoptionen aufgeführt.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gerätediagrammoption </th> 
   <th colname="col2" class="entry"> Berichtsrückblickintervall </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profil-Link</span> </p> </td> 
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
   <td colname="col1"> <p><span class="wintitle"> Tapet</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Personen insgesamt: 60 Tage </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Geräte insgesamt 60 Tage </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielberichte {#sample-reports}

### Standardbericht zu Profillinks

Ein standardmäßiger [!UICONTROL Profile Link] -Bericht sieht wie im folgenden Beispiel aus. Zusammenführungsregeln, die mehrere Datenquellen verwenden (bis zu 3, max.), zeigen Diagramme auf separaten Registerkarten für jede Datenquelle an. Diese Zusammenführungsregel enthält keine [!UICONTROL Device Co-op] -Daten.

![](assets/profile-link-metrics.png)

### Profillinkbericht mit Gerätediagrammdaten

Ein [!UICONTROL Profile Link Device Graph] -Bericht, der Gerätediagrammdaten aus dem [!UICONTROL Adobe Experience Cloud Device Co-op] oder einem Gerätediagramm von Drittanbietern enthält, zeigt [!UICONTROL Profile Link] und Gerätediagrammdaten mit nebeneinander liegenden Balkendiagrammen an. Wenn Sie diese Diagramme nebeneinander platzieren, können Sie die Vorteile der Verwendung von [!UICONTROL Experience Cloud Device Co-op] im Vergleich zu [!UICONTROL Profile Link] selbst bewerten. Zusammenführungsregeln, die mehrere Datenquellen verwenden (bis zu 3, max.), zeigen Diagramme auf separaten Registerkarten für jede Datenquelle an. Zur Erinnerung: Das [!UICONTROL Authenticated Activity]-Diagramm und die Metriken geben keine Daten aus dem [!DNL Adobe]-Gerätediagramm oder anderen Gerätediagrammen von Drittanbietern zurück, auf die Sie möglicherweise in [!DNL Audience Manager] zugreifen können.

![](assets/profile-link-graph.png)

## Trenddiagramme für Profillinks {#profile-link-trend}

Zusätzlich zu den anderen Datenvisualisierungen enthalten [!UICONTROL Profile Link] -Berichte ein Liniendiagramm. Das Liniendiagramm soll Ihnen Trends im Zeitverlauf für Ihre Profilregeln zeigen. Trenddiagramme (und die anderen Berichte) sind verfügbar, wenn Sie auf eine Regel auf der Landingpage [!UICONTROL Profile Merge Rules] ( **[!UICONTROL Audience Data > Profile Merge Rules]**) klicken. Diese Diagramme enthalten Gerätediagrammdaten, wenn Sie Mitglied der [!UICONTROL Device Co-op] oder anderer Gerätediagramme von Drittanbietern sind, auf die Sie möglicherweise in [!DNL Audience Manager] zugreifen können. Klicken Sie auf eine Trendlinie, um die zugrunde liegenden Daten anzuzeigen.

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)


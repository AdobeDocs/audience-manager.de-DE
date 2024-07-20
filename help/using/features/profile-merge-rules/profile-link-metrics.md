---
description: Profillinkmetriken bieten Daten zu Personen und Geräten, die sich für Ihre Site authentifizieren. Die Daten und Diagramme im Profillink werden beim Erstellen von Zusammenführungsregeln oder beim Klicken auf eine vorhandene Regel im Dashboard Profilzusammenführungsregeln dynamisch aktualisiert. Diese Metriken können Gerätediagramme aus anderen Gerätediagrammquellen von Drittanbietern enthalten.
seo-description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from other third-party device graph sources.
seo-title: Report Metrics for Profile Merge Rules
solution: Audience Manager
title: Berichtsmetriken für Profilzusammenführungsrichtlinien
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 0%

---

# Berichtsmetriken für Profilzusammenführungsrichtlinien {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] -Metriken liefern Daten zu Personen und Geräten, die sich für Ihre Site authentifizieren. Die Daten und Grafiken in [!UICONTROL Profile Merge Rule Reports] werden beim Erstellen einer Zusammenführungsregel oder beim Klicken auf eine vorhandene Regel im Dashboard [!UICONTROL Profile Merge Rules] dynamisch aktualisiert. Diese Metriken können Gerätediagramme aus anderen Gerätediagrammquellen von Drittanbietern enthalten.

## Metriken zu Zusammenführungsregeln {#merge-rule-metrics}

Berichte geben Daten in parallelen Balkendiagrammen zurück, wenn Ihre Zusammenführungsregeln Daten aus Gerätediagrammen von Drittanbietern verwenden, auf die Sie in [!DNL Audience Manager] Zugriff haben. Auf diese Weise können Sie Ihre authentifizierten Erstanbieterdaten mit geräteübergreifenden Daten vergleichen, die von Gerätediagrammen von Drittanbietern bereitgestellt werden. Diese Daten werden täglich aktualisiert.

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
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Geräteübergreifend</span>: Die Gesamtzahl der <a href="merge-rules-start.md#create-data-source"> geräteübergreifenden IDs</a>, die im <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html"> Data Source</a> des ausgewählten <a href="merge-rule-definitions.md"> authentifizierten Profils</a> während der Lebensdauer gespeichert sind, für die die Datenquelle existiert hat. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % aktive Personen</span>: Zeigt <span class="wintitle"> aktive Personen</span> als Prozentsatz an. </li> 
    </ul> <p> <span class="wintitle"> Authentifizierte Aktivität</span>: ermöglicht den Vergleich von Datenquellen nach Aktivität, Volumen und Prozent. Es kann Ihnen dabei helfen, eine Datenquelle zu finden, die viele Personen und einen hohen Prozentsatz aktiver Benutzer aufweist. Oder Sie können beim Vergleich von Datenquellen mit einem hohen Anteil aktiver Benutzer im Vergleich zur Gesamtzielgruppengröße einen Wert finden. Manchmal sind Datenquellen mit niedrigen Gesamtlebenszeitzahlen und hoher Aktivität nützlicher als solche mit hohen Lebenszyklusergebnissen und niedrigen Aktivitätszahlen. </p> <p> <p>Hinweis: Die Metriken <span class="wintitle"> Authentifizierte Aktivität</span> enthalten nur Daten vom Typ <span class="wintitle"> Profillink</span> . Dieser Bericht enthält keine <span class="wintitle"> Gerätediagramm</span> -Daten. </p> </p> </td> 
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
   <td colname="col1"> <p><span class="wintitle"> Profillink</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Personen insgesamt: 60 Tage </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Geräte insgesamt: 120 Tage </li> 
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

### Standardbericht zu Profillinks

Ein standardmäßiger [!UICONTROL Profile Link] -Bericht sieht wie im folgenden Beispiel aus. Zusammenführungsregeln, die mehrere Datenquellen verwenden (bis zu 3, max.), zeigen Diagramme auf separaten Registerkarten für jede Datenquelle an. Diese Zusammenführungsregel enthält keine [!UICONTROL external device graph] -Daten.

![](assets/profile-link-metrics.png)

### Profil-Link-Bericht mit Gerätediagrammdaten

Ein [!UICONTROL Profile Link Device Graph] -Bericht mit Gerätediagrammdaten aus Gerätediagrammen von Drittanbietern zeigt [!UICONTROL Profile Link] und Gerätediagrammdaten mit nebeneinander liegenden Balkendiagrammen an. Wenn Sie diese Diagramme nebeneinander platzieren, können Sie die Vorteile der Verwendung externer Gerätediagramme im Vergleich zu [!UICONTROL Profile Link] selbst bewerten. Zusammenführungsregeln, die mehrere Datenquellen verwenden (bis zu 3, max.), zeigen Diagramme auf separaten Registerkarten für jede Datenquelle an. Zur Erinnerung: Das [!UICONTROL Authenticated Activity] -Diagramm und die Metriken geben keine Daten aus dem [!DNL Adobe] -Gerätediagramm oder anderen Gerätediagrammen von Drittanbietern zurück, auf die Sie in [!DNL Audience Manager] Zugriff haben.

![](assets/profile-link-graph.png)

## Trenddiagramme für Profillinks {#profile-link-trend}

Zusätzlich zu den anderen Datenvisualisierungen enthalten [!UICONTROL Profile Link] Berichte ein Liniendiagramm. Das Liniendiagramm wurde entwickelt, um Ihnen Trends im Zeitverlauf für Ihre Profilregeln anzuzeigen. Trenddiagramme (und die anderen Berichte) sind verfügbar, wenn Sie auf eine Regel auf der Einstiegsseite [!UICONTROL Profile Merge Rules] ( **[!UICONTROL Audience Data > Profile Merge Rules]**) klicken. Diese Diagramme enthalten Gerätediagrammdaten, wenn Sie Mitglied von Gerätediagrammen von Drittanbietern sind, auf die Sie möglicherweise in [!DNL Audience Manager] zugreifen können. Klicken Sie auf eine Trendlinie, um die zugrunde liegenden Daten anzuzeigen.

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)

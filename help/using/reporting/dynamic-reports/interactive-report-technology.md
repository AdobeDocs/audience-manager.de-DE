---
description: Beschreibt die zugrunde liegende Software, die die interaktiven Berichte steuert, und den Zeitplan für die Datenaktualisierung.
seo-description: Beschreibt die zugrunde liegende Software, die die interaktiven Berichte steuert, und den Zeitplan für die Datenaktualisierung.
seo-title: Berichtstechnologie
solution: Audience Manager
title: Berichtstechnologie
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Überlagerungsberichte
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 3%

---

# Berichtstechnologie{#report-technology}

Beschreibt die zugrunde liegende Software, die die interaktiven Berichte steuert, und den Zeitplan für die Datenaktualisierung.

<!-- 

c_report_technology.xml

 -->

## Interaktive Berichte Tableau-Technologie verwenden

[!DNL Audience Manager] verwendet  [](https://www.tableausoftware.com/) Tableausoftware, um Daten in den interaktiven Berichten anzuzeigen. Bei [!DNL Tableau] verwenden die [!UICONTROL Delivery and Overlap]-Berichte visuelle Hinweise und Symbole, die Ihnen helfen:

* Suchen Sie nach Eigenschaften mit hoher und niedriger Leistung.
* Eigenschaften und Segmente mit geringer und hoher Unique Visitor-Überschneidung ausfindig machen.
* Verwenden Sie Überlagerungsdaten, um zielgerichtete Segmente zu erstellen.
* Erweitern Sie die Reichweite, indem Sie verwandte Eigenschaften mit geringer Überschneidung identifizieren.

## Zeitplan für die Datenaktualisierung

Die Berichtsdaten werden jeden Sonntag wöchentlich aktualisiert. Die Aktualisierung verarbeitet Daten vom Samstag (dem Vortag) zurück zum vorherigen Sonntag.

## In interaktiven Berichten verwendete Formen, Farben und Größen {#shapes-colors-sizes}

Die meisten interaktiven Berichte zeigen Ergebnisse mit Formen unterschiedlicher Größe und Farben an. Dieses Anzeigeformat soll Ihnen dabei helfen, die Daten visuell darzustellen, ohne durch Zeilen und Spalten mit Zahlen navigieren zu müssen.

<!-- 

r_legend.xml

 -->

### Berichtslegende

In der folgenden Tabelle werden die in dynamischen Berichten verwendeten Formen, Größen und Farben definiert.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Formen</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Kreise zeigen Ihre eigenen Erstanbietereigenschaften an. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Quadrate geben Eigenschaften von Drittanbietern an. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Farben</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Rote Farbtöne zeigen die <i>niedrige</i> Überschneidung an. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Grüne Farbtöne zeigen eine <i>hohe</i> Überschneidung an. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Größe</b> </td> 
   <td colname="col2"> Die Größe erhöht oder verringert sich im direkten Verhältnis zur Reichweite (die Anzahl oder % der Klicks oder Unique Users in einer Eigenschaft oder einem Segment). </td> 
  </tr> 
 </tbody> 
</table>

## Tableau-Dokumentation {#tableau-documentation}

Weitere Informationen zu Tableau-Steuerelementen, die Sie in unseren interaktiven Berichten sehen können, finden Sie in der offiziellen Dokumentation für [Tableau-Server unter Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)

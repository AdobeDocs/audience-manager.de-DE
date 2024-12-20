---
description: Beschreibt die zugrunde liegende Software, die die interaktiven Berichte und den Zeitplan für die Datenaktualisierung unterstützt.
seo-description: Describes the underlying software that powers the interactive reports and the data update schedule.
seo-title: Report Technology
solution: Audience Manager
title: Berichtstechnologie
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Berichtstechnologie{#report-technology}

Beschreibt die zugrunde liegende Software, die die interaktiven Berichte und den Zeitplan für die Datenaktualisierung unterstützt.

<!-- 

c_report_technology.xml

 -->

## Interaktive Berichte verwenden die Tableau-Technologie

[!DNL Audience Manager] verwendet [Tableau](https://www.tableausoftware.com/)-Software, um Daten in interaktiven Berichten anzuzeigen. Bei [!DNL Tableau] verwenden die [!UICONTROL Delivery and Overlap]-Berichte visuelle Hinweise und Symbole, die Ihnen helfen:

* Finden Sie Leistungsmerkmale mit hoher und niedriger Leistung.
* Erkennen Sie Eigenschaften und Segmente mit geringer und hoher Unique Visitor-Überschneidung.
* Verwenden Sie Überschneidungsdaten, um Zielsegmente zu erstellen.
* Erweitern Sie die Reichweite, indem Sie verwandte Eigenschaften mit geringer Überschneidung identifizieren.

## Zeitplan für die Datenaktualisierung

Die Berichtsdaten werden wöchentlich jeden Sonntag aktualisiert. Die Aktualisierung verarbeitet Daten vom Samstag (am Vortag) zurück zum vorherigen Sonntag.

## In interaktiven Berichten verwendete Formen, Farben und Größen {#shapes-colors-sizes}

Die meisten interaktiven Berichte zeigen Ergebnisse mit Formen in verschiedenen Größen und Farben an. Dieses Anzeigeformat soll Ihnen dabei helfen, die Daten visuell zu verstehen, ohne durch Zeilen und Spalten von Zahlen navigieren zu müssen.

<!-- 

r_legend.xml

 -->

### Berichtslegende

In der folgenden Tabelle werden die Formen, Größen und Farben definiert, die in dynamischen Berichten verwendet werden.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datenelement </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Shapes</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Kreise zeigen Ihre eigenen First-Party-Eigenschaften an. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Quadrate zeigen Eigenschaften von Drittanbietern an. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Farben</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Rote Schattierungen weisen auf <i>niedrige</i> Überlappung hin. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Grüne Schattierungen weisen auf <i>hohe</i> Überschneidung hin. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Größe</b> </td> 
   <td colname="col2"> Die Größe erhöht oder verringert sich direkt proportional zum Erreichen (die Anzahl oder der Prozentsatz der Klicks oder Unique Users in einem Trait oder Segment). </td> 
  </tr> 
 </tbody> 
</table>

## Tableau-Dokumentation {#tableau-documentation}

Weitere Informationen zu den Tableau-Steuerelementen, die Sie in unseren interaktiven Berichten finden, finden Sie in der offiziellen Dokumentation zu [Tableau Server unter Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)

---
description: Beschreibt die zugrunde liegende Software, die interaktive Berichte und den Zeitplan für die Datenaktualisierung nutzt.
seo-description: Beschreibt die zugrunde liegende Software, die interaktive Berichte und den Zeitplan für die Datenaktualisierung nutzt.
seo-title: Berichttechnologie
solution: Audience Manager
title: Berichttechnologie
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Berichttechnologie{#report-technology}

Beschreibt die zugrunde liegende Software, die interaktive Berichte und den Zeitplan für die Datenaktualisierung nutzt.

<!-- 

c_report_technology.xml

 -->

## Interaktive Berichte - Tableau-Technologie

[!DNL Audience Manager] verwendet [Tableau](https://www.tableausoftware.com/) -Software, um Daten in den interaktiven Berichten anzuzeigen. Darüber [!DNL Tableau]hinaus verwenden die [!UICONTROL Delivery and Overlap] Berichte visuelle Hinweise und Symbole, die Ihnen helfen,

* Finden Sie Leistungsmerkmale mit hoher und niedriger Leistung.
* Spotmerkmale und Segmente mit einer niedrigen und hohen Überschneidung bei Unique Visitor.
* Verwenden Sie überlappende Daten, um zielgerichtete Segmente zu erstellen.
* Erweitern Sie die Reichweite, indem Sie zugehörige Eigenschaften mit geringer Überschneidung identifizieren.

## Zeitplan für Datenaktualisierung

Die Berichtsdaten werden jeden Sonntag wöchentlich aktualisiert. Die Aktualisierung verarbeitet Daten vom Samstag (dem Vortag) bis zum vorherigen Sonntag.

## In interaktiven Berichten verwendete Formen, Farben und Größen {#shapes-colors-sizes}

Die meisten interaktiven Berichte zeigen Ergebnisse mit Formen unterschiedlicher Größe und Farben an. Dieses Anzeigeformat hilft Ihnen, die Daten visuell zu verstehen, ohne durch Zeilen und Spalten von Zahlen blättern zu müssen.

<!-- 

r_legend.xml

 -->

### Report Legende

Die folgende Tabelle definiert die in den dynamischen Berichten verwendeten Formen, Größen und Farben.

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Kreise zeigen Ihre eigenen Eigenschaften von Erstanbietern an. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Quadrate geben Eigenschaften von Drittanbietern an. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Farben</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Rote Farbtöne weisen auf eine <i>geringe</i> Überschneidung hin. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Grüne Schattierungen weisen auf eine <i>hohe</i> Überschneidung hin. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Größe</b> </td> 
   <td colname="col2"> Die Größe erhöht oder verringert sich in direktem Verhältnis zur Reichweite (die Anzahl oder % der Klicks oder Unique Users in einer Eigenschaft oder einem Segment). </td> 
  </tr> 
 </tbody> 
</table>

## Berichtssymbole und -werkzeuge erläutert {#icons-tools-explained}

Beschreibt das Suchen und Verwenden der verschiedenen Symbole, die in den dynamischen Berichten verwendet werden.

<!-- 

r_icons.xml

 -->

### Datensymbole und Werkzeuge

Die folgenden Symbole und Tools stehen am unteren Rand jedes dynamischen Berichtsfensters zur Verfügung. Die folgende Abbildung enthält weitere Informationen zu diesen Werkzeugen.

![](assets/tools_icons90.png)

### Daten exportieren

Mit diesen Tools können Sie Daten aus dem Bericht in vier verschiedene Formate exportieren.

| Exportoption | Exportieren von Daten |
|---|---|
| **[!UICONTROL Image]** | Als Bild-Datei (.png). Nützlich, wenn Sie Berichtsdaten in ihrem ursprünglichen, grafischen Format herunterladen und freigeben möchten. |
| **[!UICONTROL PDF]** | Als PDF-Datei. |
| **[!UICONTROL Data]** | In einem neuen Browserfenster als numerische Daten in Spalten und Zeilen. |
| **[!UICONTROL Crosstab]** | Als .csv-Datei. |

### Änderungen wiederherstellen

Wählen Sie dieses Tool, um alle interaktiven Klickänderungen rückgängig zu machen, die Sie möglicherweise für den Bericht vorgenommen haben.

### Automatische Updates

Bei den Berichten [!UICONTROL Delivery-Performance] und [!UICONTROL Trait-to-Trait Overlap] Berichten handelt es sich um dynamische Berichte, die je nach Benutzerklick-Aktionen reagieren und sich ändern.

Angenommen, Sie möchten im [!UICONTROL Overlap] Bericht mehrere Advertiser auswählen. Wenn diese Option aktiviert ist, werden die Daten bei automatischen Aktualisierungen zurückgegeben, sobald Sie ein Kontrollkästchen aktivieren. Dieses dynamische Verhalten kann Ihren Workflow unterbrechen, da Sie warten müssen, bis der Bericht fertig verarbeitet ist, bevor Sie einen anderen Anbieter auswählen. Verwenden Sie dieses Tool, um diese Funktion nach Bedarf zu deaktivieren (und wieder einzuschalten).

### Daten aktualisieren

Klicken Sie auf das Aktualisierungssymbol, um einen Bericht auszuführen oder den Datensatz neu zu laden. Wenn die automatischen Aktualisierungen deaktiviert sind, klicken Sie auf Aktualisieren, um den Bericht auszuführen oder zu aktualisieren.

### Suchwerkzeug

Die Suche wird durch ein generisches Lupensymbol dargestellt (nicht angezeigt). Das Suchfeld wird ausgeblendet, bis Sie auf die Auswahlbeschriftungen links im Bildschirm klicken. Die nachstehende Tabelle beschreibt die Position des Suchwerkzeugs für jeden Bericht.

| Bericht | Um die Suche zu finden, halten Sie den Mauszeiger über |
|---|---|
| [!UICONTROL Delivery and Performance] anzeigen | Die Beschriftung "Name des Advertisers". |
| [!UICONTROL Overlap] Berichte | Die Beschriftung "SID-Name". |

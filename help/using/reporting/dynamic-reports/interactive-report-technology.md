---
description: Beschreibt die zugrunde liegende Software, die die interaktiven Berichte und den Zeitplan für die Datenaktualisierung ausweist.
seo-description: Beschreibt die zugrunde liegende Software, die die interaktiven Berichte und den Zeitplan für die Datenaktualisierung ausweist.
seo-title: Berichtstechnologie
solution: Audience Manager
title: Berichtstechnologie
uuid: 5 f 3 d 815 b-e 1 e 6-42 f 2-b 848-ac 035 a 5 aa 77 d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Berichtstechnologie{#report-technology}

Beschreibt die zugrunde liegende Software, die die interaktiven Berichte und den Zeitplan für die Datenaktualisierung ausweist.

<!-- 

c_report_technology.xml

 -->

## Interaktive Berichte verwenden Tableau-Technologie

[!DNL Audience Manager] verwendet [Tableau](https://www.tableausoftware.com/) -Software, um Daten in den interaktiven Berichten anzuzeigen. Mit [!DNL Tableau]den [!UICONTROL Delivery and Overlap] Berichten werden visuelle Hinweise und Symbole verwendet, die Folgendes unterstützen:

* Finden Sie hohe und niedrige Leistungseigenschaften.
* Volltoneigenschaften und Segmente mit niedrigem und hoher individueller Besucher.
* Verwenden Sie Überlappungsdaten, um zielgerichtete Segmente zu erstellen.
* Erweitern Sie die Reichweite, indem Sie verwandte Eigenschaften mit geringer Überlappung identifizieren.

## Zeitplan für Datenaktualisierung

Die Berichtsdaten werden pro Sonntag wöchentlich aktualisiert. Das Update verarbeitet Daten von Samstag (am Tag vor) zurück zum vorherigen Sonntag.

## In interaktiven Berichten verwendete Formen, Farben und Größen {#shapes-colors-sizes}

Die meisten interaktiven Berichte zeigen Ergebnisse mit unterschiedlichen Größen und Farben an. Dieses Anzeigeformat hilft Ihnen, die Daten visuell zu machen, ohne die Zeilen und Spalten von Zahlen durchblättern zu müssen.

<!-- 

r_legend.xml

 -->

### Berichtslegende

In der folgenden Tabelle sind die Formen, Größen und Farben definiert, die in den dynamischen Berichten verwendet werden.

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
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Kreise weisen auf Ihre eigenen Erstanbietereigenschaften hin. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Quadrate weisen auf Eigenschaften von Drittanbietern hin. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Farben</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Rote Schattierungen weisen <i>auf niedrige</i> Überlappung hin. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Grüne Schattierungen weisen <i>auf hohe</i> Überlappung hin. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Größe</b> </td> 
   <td colname="col2"> Die Größe erhöht oder verringert sich in direktem Verhältnis zu Reichweite (die Anzahl oder % der Klicks oder Unique Users in einer Eigenschaft oder einem Segment). </td> 
  </tr> 
 </tbody> 
</table>

## Erklärung der Berichtsymbole und Tools {#icons-tools-explained}

Beschreibt, wie Sie die verschiedenen Symbolwerkzeuge in den dynamischen Berichten suchen und verwenden.

<!-- 

r_icons.xml

 -->

### Datensymbole und Werkzeuge

Unten in jedem dynamischen Berichtsfenster stehen die folgenden Symbole zur Verfügung. Die folgende Abbildung zeigt weitere Informationen zu diesen Werkzeugen.

![](assets/tools_icons90.png)

### Daten exportieren

Mit diesen Tools können Sie Daten aus dem Bericht in vier verschiedene Formate exportieren.

| Exportoption | Exportiert Daten |
|---|---|
| **[!UICONTROL Image]** | Als Bild-Datei (. png). Nützlich, wenn Sie Berichtsdaten im ursprünglichen, grafischen Format herunterladen und freigeben möchten. |
| **[!UICONTROL PDF]** | Als PDF-Datei. |
| **[!UICONTROL Data]** | In einem neuen Browserfenster als numerische Daten in Spalten und Zeilen. |
| **[!UICONTROL Crosstab]** | Als. csv-Datei. |

### Änderungen zurücksetzen

Wählen Sie dieses Tool aus, um interaktive Klicks rückgängig zu machen, die Sie möglicherweise im Bericht vorgenommen haben.

### Automatische Updates

Die [!UICONTROL Delivery-Performance] Berichte und [!UICONTROL Trait-to-Trait Overlap] Berichte sind dynamische Berichte, die je nach Benutzerklickaktionen reagieren und sich ändern.

Angenommen, Sie möchten mehrere Werbetreibende im [!UICONTROL Overlap] Bericht auswählen. Wenn diese Option aktiviert ist, werden die automatischen Updates gestartet, sobald Sie ein Kontrollkästchen aktivieren. Dieses dynamische Verhalten kann Ihren Arbeitsablauf stören, da Sie warten müssen, bis der Bericht die Verarbeitung abgeschlossen hat, bevor Sie einen anderen Advertiser auswählen. Verwenden Sie dieses Werkzeug, um die Funktion (und wieder) nach Bedarf zu deaktivieren.

### Daten aktualisieren

Klicken Sie auf das Aktualisierungssymbol, um einen Bericht auszuführen oder Ihren Datensatz neu zu laden. Wenn automatische Updates deaktiviert sind, klicken Sie auf Aktualisieren, um den Bericht auszuführen oder zu aktualisieren.

### Suchtool

Die Suche wird durch ein generisches Lupensymbol dargestellt (nicht angezeigt). Das Suchfeld wird ausgeblendet, bis Sie auf der linken Seite des Bildschirms auf die Auswahlbeschriftungen klicken. Die folgende Tabelle beschreibt den Ort des Suchtools für jeden Bericht.

| Bericht | Um Suche zu suchen, bewegen Sie den Mauszeiger über den |
|---|---|
| [!UICONTROL Delivery and Performance] anzeigen | Die Bezeichnung &quot;Advertisername&quot; . |
| [!UICONTROL Overlap] Berichte | Die Bezeichnung &quot;SID-Name&quot; . |

---
description: Der Berichtsabschnitt für Testgruppenberichte gibt Informationen zu Testgruppenkonversionen zurück, was einen einfachen Vergleich der Effektivität von Testsegmenten ermöglicht. Für die Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.
seo-description: Der Berichtsabschnitt für Testgruppenberichte gibt Informationen zu Testgruppenkonversionen zurück, was einen einfachen Vergleich der Effektivität von Testsegmenten ermöglicht. Für die Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.
seo-title: Testgruppenberichte
solution: Audience Manager
title: Testgruppenberichte
topic: DIL-API
uuid: 21303 c 3 e -4 c 5-4728-a 759-96 c 2 a 1 d 99 b 69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Testgruppenberichte {#test-group-reporting}

Der Berichtsabschnitt für Testgruppenberichte gibt Informationen zu Testgruppenkonversionen zurück, was einen einfachen Vergleich der Effektivität von Testsegmenten ermöglicht. Für die Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.

[!UICONTROL Audience Lab] gibt detaillierte Berichtsinformationen für die erstellten Testsegmente zurück und ermöglicht es Ihnen, die Berichtsdaten als [!DNL CSV] Dateien zu speichern. Sie können zwischen **[!UICONTROL Aggregate Reporting]** und **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** gibt die absoluten Zahlen für Ihre Testsegmente zurück. **[!UICONTROL Trend Reporting]** gibt ein Diagramm des Trends *über einen bestimmten Zeitraum zurück*. Mit vier Registern können Sie die Berichte anpassen:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Populationskonversionsrate</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt den Prozentsatz der Geräte zurück, die zu einem bestimmten Testsegment gehören, das konvertiert wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Konverter</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Geräte zurück, die die in den Testgruppen ausgewählten Konversionseigenschaften ausfüllen. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Sehen Sie sich dieses Video</a> an, um zu erfahren, wie Konversionseigenschaften erstellt werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Summenkonversionen</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der von den Testsegmenten generierten Konversionen zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Testsegmente testen</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Geräte zurück, die zu den Testsegmenten gehören. Wechsel zwischen <b><span class="uicontrol"> Gesamtpopulation</span></b> oder <b><span class="uicontrol"> Echtzeitpopulation</span></b>. Der Unterschied wird in den häufig gestellten Fragen zur <a href="../../faq/faq-reporting.md"> Berichterstellung</a> erläutert. </p> </td>
  </tr>
 </tbody>
</table>

Sie können eine bestimmte Konversionseigenschaft auswählen, für die der Bericht erstellt werden soll, oder Sie können alle kombinierten Eigenschaften auswählen. Sie können einen Datumsbereich definieren, für den die Informationen zurückgegeben werden sollen, und den Bericht als [!DNL CSV] Datei exportieren.

>[!NOTE]
>
>* Die Berichterstellung für eine Testgruppe füllt den Tag nach dem Startdatum.
>* Eine Konversion wird nur für ein Gerät nach dem Startdatum eines Tests gezählt und nach dem Hinzufügen des Geräts zu einem Testsegment. Wenn eine Konvertierung für dieses Gerät vor dem zugewiesenen Test erfolgt, wird die Konvertierung nicht gezählt.


Ein zurückgegebenes **[!UICONTROL Aggregate Reporting]** Diagramm könnte wie folgt aussehen:

![](assets/aggregate-reporting.PNG)

Ein zurückgegebenes **[!UICONTROL Trend Reporting]** Diagramm könnte wie folgt aussehen. Wählen **[!UICONTROL Normalized]** Sie im Kontrollkästchen, wenn Sie die absoluten Zahlen ignorieren möchten, und konzentrieren Sie sich einfach auf die Trends der Testsegmente.

![](assets/trend-reporting.PNG)
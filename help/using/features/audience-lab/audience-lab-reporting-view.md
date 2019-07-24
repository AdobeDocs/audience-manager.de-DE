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


# Test Group Reporting {#test-group-reporting}

Der Berichtsabschnitt für Testgruppenberichte gibt Informationen zu Testgruppenkonversionen zurück, was einen einfachen Vergleich der Effektivität von Testsegmenten ermöglicht. Für die Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.

[!UICONTROL Audience Lab] gibt detaillierte Berichtsinformationen für die erstellten Testsegmente zurück und ermöglicht es Ihnen, die Berichtsdaten als [!DNL CSV] Dateien zu speichern. You can select between **[!UICONTROL Aggregate Reporting]** and **[!UICONTROL Trend Reporting]**.

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
   <td colname="col2"> <p>Gibt die Anzahl der Geräte zurück, die zu den Testsegmenten gehören. Toggle between <b><span class="uicontrol"> Total Population</span></b> or <b><span class="uicontrol"> Real-time Population</span></b>. The difference is explained in the <a href="../../faq/faq-reporting.md"> Reporting FAQ</a> . </p> </td>
  </tr>
 </tbody>
</table>

Sie können eine bestimmte Konversionseigenschaft auswählen, für die der Bericht erstellt werden soll, oder Sie können alle kombinierten Eigenschaften auswählen. You can define a date range for which the information should be returned and export the report as a [!DNL CSV] file.

>[!NOTE]
>
>* Die Berichterstellung für eine Testgruppe füllt den Tag nach dem Startdatum.
>* Eine Konversion wird nur für ein Gerät nach dem Startdatum eines Tests gezählt und nach dem Hinzufügen des Geräts zu einem Testsegment. Wenn eine Konvertierung für dieses Gerät vor dem zugewiesenen Test erfolgt, wird die Konvertierung nicht gezählt.


A returned **[!UICONTROL Aggregate Reporting]** chart could look like this:

![](assets/aggregate-reporting.PNG)

A returned **[!UICONTROL Trend Reporting]** chart could look like the one below. Select **[!UICONTROL Normalized]** in the check box if you want to ignore the absolute numbers and simply focus on the test segments trends.

![](assets/trend-reporting.PNG)
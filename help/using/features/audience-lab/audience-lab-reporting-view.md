---
description: Der Abschnitt zur Testgruppenberichterstattung gibt Informationen zu Testgruppenkonversionen zurück, sodass die Testsegmentwirksamkeit einfach verglichen werden kann. Zur Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: Testgruppenberichte
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Testgruppenberichte {#test-group-reporting}

Der Abschnitt zur Testgruppenberichterstattung gibt Informationen zu Testgruppenkonversionen zurück, sodass die Testsegmentwirksamkeit einfach verglichen werden kann. Zur Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.

[!UICONTROL Audience Lab] gibt detaillierte Berichtsinformationen für die von Ihnen erstellten Testsegmente zurück und ermöglicht es Ihnen, die Berichtsdaten als [!DNL CSV] -Dateien zu speichern. Sie können zwischen **[!UICONTROL Aggregate Reporting]** und **[!UICONTROL Trend Reporting]** wählen.

**[!UICONTROL Aggregate Reporting]** gibt die absoluten Zahlen für Ihre Testsegmente zurück. **[!UICONTROL Trend Reporting]** gibt ein Diagramm des Trends *über einen bestimmten Zeitraum zurück*. Mit vier Registerkarten können Sie die Berichte anpassen:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bevölkerungskonversionsrate</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt den Prozentsatz der Geräte zurück, die zu einem bestimmten Testsegment gehören und konvertiert wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Konverter</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Geräte zurück, die die in den Testgruppen ausgewählten Konversionseigenschaften gezeigt haben. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Sehen Sie sich dieses Video</a> an, um zu erfahren, wie Sie Konversionseigenschaften erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gesamtkonversionen</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Konversionen zurück, die von den Testsegmenten generiert wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Testsegmentpopulationen</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Geräte zurück, die zu den Testsegmenten gehören. Zwischen <b><span class="uicontrol"> Gesamtpopulation</span></b> oder <b><span class="uicontrol"> Echtzeitpopulation</span></b> wechseln. Der Unterschied wird in den <a href="../../faq/faq-reporting.md"> FAQ zu Berichten</a> erläutert. </p> </td>
  </tr>
 </tbody>
</table>

Sie können eine bestimmte Konversionseigenschaft auswählen, für die der Bericht generiert werden soll, oder Sie können alle kombinierten Eigenschaften auswählen. Sie können einen Datumsbereich definieren, für den die Informationen zurückgegeben werden sollen, und den Bericht als [!DNL CSV] -Datei exportieren.

>[!NOTE]
>
>* Die Berichterstellung für eine Testgruppe wird am Tag nach dem Startdatum ausgefüllt.
>* Eine Konversion wird für ein Gerät erst nach dem Startdatum eines Tests und nach dem Hinzufügen des Geräts zu einem Testsegment gezählt. Wenn eine Konversion für dieses Gerät stattfindet, bevor ihm eine Testgruppe zugewiesen wird, wird die Konversion nicht gezählt.

Ein zurückgegebenes **[!UICONTROL Aggregate Reporting]** Diagramm könnte wie folgt aussehen:

![](assets/aggregate-reporting.PNG)

Ein zurückgegebenes **[!UICONTROL Trend Reporting]** -Diagramm könnte wie das unten stehende aussehen. Wählen Sie im Kontrollkästchen **[!UICONTROL Normalized]** aus, wenn Sie die absoluten Zahlen ignorieren und sich einfach auf die Trends der Testsegmente konzentrieren möchten.

![](assets/trend-reporting.PNG)

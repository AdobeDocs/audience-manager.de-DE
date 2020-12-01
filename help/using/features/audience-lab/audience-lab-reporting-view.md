---
description: Der Abschnitt zum Berichte der Testgruppe gibt Informationen zu Testgruppenkonversionen zurück, was einen einfachen Vergleich der Wirksamkeit des Testsegments ermöglicht. Zur Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.
seo-description: Der Abschnitt zum Berichte der Testgruppe gibt Informationen zu Testgruppenkonversionen zurück, was einen einfachen Vergleich der Wirksamkeit des Testsegments ermöglicht. Zur Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.
seo-title: Testgruppenberichte
solution: Audience Manager
title: Testgruppenberichte
topic: DIL API
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---


# Testgruppenberichte {#test-group-reporting}

Der Abschnitt zum Berichte der Testgruppe gibt Informationen zu Testgruppenkonversionen zurück, was einen einfachen Vergleich der Wirksamkeit des Testsegments ermöglicht. Zur Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.

[!UICONTROL Audience Lab] gibt detaillierte Berichte-Informationen für die von Ihnen erstellten Testsegmente zurück und ermöglicht Ihnen, die Berichte-Daten als  [!DNL CSV] Dateien zu speichern. Sie können zwischen **[!UICONTROL Aggregate Reporting]** und **[!UICONTROL Trend Reporting]** wählen.

**[!UICONTROL Aggregate Reporting]** gibt die absoluten Zahlen für Ihre Testsegmente zurück. **[!UICONTROL Trend Reporting]** gibt ein Diagramm des Trends  *über einen bestimmten Zeitraum* zurück. Mit vier Registerkarten können Sie die Berichte anpassen:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bevölkerung Konversionsrat</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt den Prozentsatz der Geräte zurück, die zu einem bestimmten Testsegment gehören und konvertiert wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Konverter</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Geräte zurück, die die in den Testgruppen ausgewählten Konvertierungseigenschaften gezeigt haben. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Sehen Sie sich dieses </a> Video an, um zu erfahren, wie Sie Konversionseigenschaften erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gesamtumrechnungen</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Konversionen zurück, die von den Testsegmenten generiert wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Segmentpopulationen testen</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Geräte zurück, die zu den Testsegmenten gehören. Wechsel zwischen <b><span class="uicontrol"> Gesamtpopulation</span></b> oder <b><span class="uicontrol"> Echtzeitpopulation</span></b>. Der Unterschied wird in den <a href="../../faq/faq-reporting.md"> Berichte FAQ</a> erklärt. </p> </td>
  </tr>
 </tbody>
</table>

Sie können eine bestimmte Konversionseigenschaft auswählen, für die der Bericht generiert werden soll, oder Sie können alle kombinierten Eigenschaften auswählen. Sie können einen Datumsbereich definieren, für den die Informationen zurückgegeben werden sollen, und den Bericht als [!DNL CSV]-Datei exportieren.

>[!NOTE]
>
>* Berichte für eine Testgruppe füllt den Tag nach dem Beginn.
>* Eine Konversion wird für ein Beginn erst nach dem Testdatum und nach dem Hinzufügen des Geräts zu einem Testsegment gezählt. Wenn für dieses Gerät eine Konversion erfolgt, bevor eine Testgruppe zugewiesen wird, wird die Konversion nicht gezählt.


Ein zurückgegebenes **[!UICONTROL Aggregate Reporting]**-Diagramm könnte wie folgt aussehen:

![](assets/aggregate-reporting.PNG)

Ein zurückgegebenes **[!UICONTROL Trend Reporting]**-Diagramm könnte wie das unten dargestellte aussehen. Wählen Sie **[!UICONTROL Normalized]** im Kontrollkästchen aus, wenn Sie die absoluten Zahlen ignorieren und sich einfach auf die Trends der Testsegmente konzentrieren möchten.

![](assets/trend-reporting.PNG)
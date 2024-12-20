---
description: Der Abschnitt „Testgruppenberichte“ gibt Informationen zu Testgruppenkonversionen zurück, die einen einfachen Vergleich der Testsegmenteffizienz ermöglichen. Für die Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.
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

Der Abschnitt „Testgruppenberichte“ gibt Informationen zu Testgruppenkonversionen zurück, die einen einfachen Vergleich der Testsegmenteffizienz ermöglichen. Für die Datenvisualisierung stehen zahlreiche Filter und Dimensionen zur Verfügung.

[!UICONTROL Audience Lab] gibt detaillierte Reporting-Informationen zu den von Ihnen erstellten Testsegmenten zurück und ermöglicht Ihnen das Speichern der Reporting-Daten als [!DNL CSV]. Sie können zwischen **[!UICONTROL Aggregate Reporting]** und **[!UICONTROL Trend Reporting]** wählen.

**[!UICONTROL Aggregate Reporting]** gibt die absoluten Zahlen für Ihre Testsegmente zurück. **[!UICONTROL Trend Reporting]** gibt ein Diagramm des Trends (*einen bestimmten Zeitraum)*. Vier Registerkarten ermöglichen die Anpassung der Berichte:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Konversionsrate <b><span class="uicontrol"> Population</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt den Prozentsatz der Geräte zurück, die zu einem bestimmten Testsegment gehören und konvertiert wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Konverter</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Geräte zurück, die das/die ausgewählte(n) Konversionsmerkmal(e) in den Testgruppen gezeigt haben. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> In diesem Video </a> Sie, wie Sie Konversionseigenschaften erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Konversionen insgesamt</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der von den Testsegmenten generierten Konversionen zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Testsegmentpopulationen</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die Anzahl der Geräte zurück, die zu den Testsegmenten gehören Schalten Sie zwischen <b><span class="uicontrol"> Gesamtpopulation </span></b> Echtzeit-<b><span class="uicontrol"> um</span></b>. Der Unterschied wird in den häufig gestellten Fragen zur <a href="../../faq/faq-reporting.md">-Berichterstellung </a>. </p> </td>
  </tr>
 </tbody>
</table>

Sie können ein spezifisches Konversionseigenschaft auswählen, für das der Bericht generiert werden soll, oder Sie können alle Eigenschaften kombiniert auswählen. Sie können einen Datumsbereich definieren, für den die Informationen zurückgegeben werden sollen, und den Bericht als [!DNL CSV] exportieren.

>[!NOTE]
>
>* Berichte für eine Testgruppe werden am Tag nach dem Startdatum ausgefüllt.
>* Eine Konversion wird für ein Gerät erst nach dem Startdatum eines Tests und nach dem Hinzufügen des Geräts zu einem Testsegment gezählt. Wenn für dieses Gerät eine Konversion durchgeführt wird, bevor es einer Testgruppe zugewiesen wird, wird die Konversion nicht gezählt.

Ein zurückgegebenes **[!UICONTROL Aggregate Reporting]** könnte wie folgt aussehen:

![](assets/aggregate-reporting.PNG)

Ein zurückgegebenes **[!UICONTROL Trend Reporting]** könnte wie das folgende aussehen. Aktivieren Sie das Kontrollkästchen **[!UICONTROL Normalized]** , wenn Sie die absoluten Zahlen ignorieren und sich einfach auf die Trends der Testsegmente konzentrieren möchten.

![](assets/trend-reporting.PNG)

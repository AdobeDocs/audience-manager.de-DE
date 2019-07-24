---
description: Beschreibt die für den Aktualisierungsprozess des Überlappungs-Berichts erforderlichen Segmentgrößen und Erstellungszeiten.
seo-description: Beschreibt die für den Aktualisierungsprozess des Überlappungs-Berichts erforderlichen Segmentgrößen und Erstellungszeiten.
seo-title: Zeitplan für Überlappungsberichte und Mindestsegmentgröße
solution: Audience Manager
title: Zeitplan für Überlappungsberichte und Mindestsegmentgröße
uuid: 35 c 1 cb 39-e 28 d -4 d 20-88 c 9-5 ff 4 fe 154 e 9 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overlap Reports: Update Schedule and Minimum Segment Size{#overlap-reports-update-schedule-and-minimum-segment-size}

Beschreibt die für den Aktualisierungsprozess des Überlappungs-Berichts erforderlichen Segmentgrößen und Erstellungszeiten.

## Update Schedule and Requirements {#update-schedule}

[!UICONTROL Overlap] Berichte wöchentlich am Sonntag aktualisiert. Die Vorverarbeitung von Berichten beginnt am Samstag. Dies hat Auswirkungen darauf, wie neue oder vorhandene Segmente am Montag in einem Überlappungsbericht angezeigt werden. So werden Sie in einen Überlappungsbericht aufgenommen:

* Ein Segment muss in den letzten 14 Tagen mindestens 70.000 Echtzeit-Echtzeit-Benutzer enthalten. Read more about [Minimum Unique Visitor Requirements for Traits and Segments](../../reporting/report-sampling.md#data-sampling-ratio).
* Ein Segment muss vor 12 Uhr am Donnerstag erstellt worden sein (2 volle Tage vor dem Beginn des Aktualisierungsprozesses des Berichts zur Aktualisierung des Wochenzeitberichts).
* Your company must be a Full [!DNL Audience Manager] customer. Please contact your [!DNL Audience Manager] consultant or Customer Care to find out more.

## Segment Size and/or Creation Time Affects Reporting {#segment-size}

If you do not see a segment in one of the [!UICONTROL Overlap] reports, it may be because the segment does not meet these minimum requirements.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nutzungsszenario </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentgröße zu klein</b> </p> </td> 
   <td colname="col2"> <p>Nehmen wir an, Sie erstellen ein Segment vor 12 Uhr am Donnerstag, aber es enthält weniger als 70.000 Echtzeit-Benutzer. This segment won't appear in an <span class="wintitle"> Overlap Report</span> until it meets the user threshold requirements. Beachten Sie auch, dass das Segment dem erforderlichen Benutzerzähler am Donnerstag oder vor der Schwellenzeitmetoff entsprechen muss. If it does not meet the weekly deadline, the segment will appear in the <span class="wintitle"> Overlap Reports</span> for the week after the upcoming Sunday data run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Zu spät erstelltes Segment</b> </p> </td> 
   <td colname="col2"> <p>Nehmen wir an, Sie erstellen am Freitag ein Segment und es enthält mehr als 70.000 Echtzeit-Benutzer. This segment won't appear in the <span class="wintitle"> Overlap Reports</span> for the next week because it was created less than 2 days prior to the report update period. However, the segment will appear in an <span class="wintitle"> Overlap Report</span> after the next weekly update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Überschneidungsbericht zwischen Eigenschaften](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Überschneidungsbericht zwischen Segmenten und Eigenschaften](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Überschneidungsbericht zwischen Segmenten](../../reporting/dynamic-reports/segment-segment-overlap-report.md)


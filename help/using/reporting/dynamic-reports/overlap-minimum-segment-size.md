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


# Überlappungsberichte: Zeitplan und Mindestgröße des Segments aktualisieren{#overlap-reports-update-schedule-and-minimum-segment-size}

Beschreibt die für den Aktualisierungsprozess des Überlappungs-Berichts erforderlichen Segmentgrößen und Erstellungszeiten.

## Zeitplan und Anforderungen aktualisieren {#update-schedule}

[!UICONTROL Overlap] Berichte wöchentlich am Sonntag aktualisiert. Die Vorverarbeitung von Berichten beginnt am Samstag. Dies hat Auswirkungen darauf, wie neue oder vorhandene Segmente am Montag in einem Überlappungsbericht angezeigt werden. So werden Sie in einen Überlappungsbericht aufgenommen:

* Ein Segment muss in den letzten 14 Tagen mindestens 70.000 Echtzeit-Echtzeit-Benutzer enthalten. Erfahren Sie mehr über [die Mindestanforderungen an individuelle Besucher für Eigenschaften und Segmente](../../reporting/report-sampling.md#data-sampling-ratio).
* Ein Segment muss vor 12 Uhr am Donnerstag erstellt worden sein (2 volle Tage vor dem Beginn des Aktualisierungsprozesses des Berichts zur Aktualisierung des Wochenzeitberichts).
* Ihr Unternehmen muss ein vollständiger [!DNL Audience Manager] Kunde sein. Wenden Sie sich an Ihren [!DNL Audience Manager] Berater oder an den Kundendienst, um weitere Informationen zu erhalten.

## Segmentgröße und/oder Erstellungszeit beeinflussen die Berichterstellung {#segment-size}

Wenn in einem der [!UICONTROL Overlap] Berichte kein Segment angezeigt wird, kann es vorkommen, dass das Segment diese Mindestanforderungen nicht erfüllt.

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
   <td colname="col2"> <p>Nehmen wir an, Sie erstellen ein Segment vor 12 Uhr am Donnerstag, aber es enthält weniger als 70.000 Echtzeit-Benutzer. Dieses Segment wird erst dann in <span class="wintitle"> einem Überlappungsbericht</span> angezeigt, wenn die Benutzerschwellenwerte erfüllt sind. Beachten Sie auch, dass das Segment dem erforderlichen Benutzerzähler am Donnerstag oder vor der Schwellenzeitmetoff entsprechen muss. Wenn der wöchentliche Termin nicht erreicht wird, wird das Segment in den <span class="wintitle"> Überlappungsberichten</span> für die Woche nach den bevorstehenden Daten zum Sonntag angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Zu spät erstelltes Segment</b> </p> </td> 
   <td colname="col2"> <p>Nehmen wir an, Sie erstellen am Freitag ein Segment und es enthält mehr als 70.000 Echtzeit-Benutzer. Dieses Segment wird in den <span class="wintitle"> Überlappungsberichten</span> für die nächste Woche nicht angezeigt, da es weniger als 2 Tage vor dem Berichtzeitraum erstellt wurde. Das Segment wird jedoch nach dem nächsten wöchentlichen Update in einem <span class="wintitle"> Überlappungsbericht</span> angezeigt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Überschneidungsbericht zwischen Eigenschaften](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Überschneidungsbericht zwischen Segmenten und Eigenschaften](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Überschneidungsbericht zwischen Segmenten](../../reporting/dynamic-reports/segment-segment-overlap-report.md)


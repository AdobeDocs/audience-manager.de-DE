---
description: Beschreibt die für den Aktualisierungsprozess des Überschneidungsberichts erforderlichen Anforderungen an die Segmentgröße und die Erstellungszeit.
seo-description: Beschreibt die für den Aktualisierungsprozess des Überschneidungsberichts erforderlichen Anforderungen an die Segmentgröße und die Erstellungszeit.
seo-title: Überlagerungsberichte - Zeitplan und Mindestsegmentgröße aktualisieren
solution: Audience Manager
title: Überlagerungsberichte - Zeitplan und Mindestsegmentgröße aktualisieren
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Überschneidungsberichte: Zeitplan und Mindestsegmentgröße aktualisieren{#overlap-reports-update-schedule-and-minimum-segment-size}

Beschreibt die für den Aktualisierungsprozess des Überschneidungsberichts erforderlichen Anforderungen an die Segmentgröße und die Erstellungszeit.

## Zeitplan und Anforderungen aktualisieren {#update-schedule}

[!UICONTROL Overlap] Berichte werden am Sonntag wöchentlich aktualisiert. Die Berichtvorverarbeitung beginnt am Samstag. Dies wirkt sich darauf aus, wie neue oder vorhandene Segmente am Montag in einem Überschneidungsbericht angezeigt werden. In einen Überschneidungsbericht aufzunehmen:

* Ein Segment muss mindestens 70.000 Benutzer in Echtzeit während der letzten 14 Tage enthalten. Erfahren Sie mehr über die [Mindestanforderungen an individuelle Besucher für Eigenschaften und Segmente](../../reporting/report-sampling.md#data-sampling-ratio).
* Ein Segment muss vor Donnerstag UTC um 12 Uhr erstellt worden sein (2 volle Tage vor Beginn des Aktualisierungsprozesses des wöchentlichen Überschneidungsberichts).
* Ihr Unternehmen muss ein Full- [!DNL Audience Manager] Kunde sein. Wenden Sie sich an Ihren [!DNL Audience Manager] Berater oder an den Kundendienst, um weitere Informationen zu erhalten.

## Segmentgröße und/oder Erstellungszeit beeinflussen die Berichterstellung {#segment-size}

Wenn in einem der [!UICONTROL Overlap] Berichte kein Segment angezeigt wird, kann dies daran liegen, dass das Segment diese Mindestanforderungen nicht erfüllt.

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
   <td colname="col2"> <p>Nehmen wir an, Sie erstellen ein Segment vor 12 Uhr UTC am Donnerstag, es enthält jedoch weniger als 70.000 Benutzer in Echtzeit. Dieses Segment wird erst dann in einem <span class="wintitle"> Overlap-Bericht</span> angezeigt, wenn die Schwellenwerte für Benutzer erfüllt sind. Beachten Sie auch, dass das Segment die erforderliche Benutzeranzahl für den Donnerstag oder vor dem Ende des Zeitraums erfüllen muss. Wenn der Wochenende-Termin nicht eingehalten wird, wird das Segment in den <span class="wintitle"> Überschneidungsberichten</span> für die Woche nach der Ausführung der kommenden Sonntagsdaten angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Zu spät erstelltes Segment</b> </p> </td> 
   <td colname="col2"> <p>Nehmen wir an, Sie erstellen am Freitag ein Segment, das mehr als 70.000 Benutzer in Echtzeit enthält. Dieses Segment wird für die nächste Woche nicht in den <span class="wintitle"> Überschneidungsberichten</span> angezeigt, da es weniger als 2 Tage vor dem Aktualisierungszeitraum erstellt wurde. Das Segment wird jedoch nach der nächsten wöchentlichen Aktualisierung in einem <span class="wintitle"> Überschneidungsbericht</span> angezeigt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Überschneidungsbericht zwischen Eigenschaften](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Überschneidungsbericht zwischen Segmenten und Eigenschaften](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Überschneidungsbericht zwischen Segmenten](../../reporting/dynamic-reports/segment-segment-overlap-report.md)


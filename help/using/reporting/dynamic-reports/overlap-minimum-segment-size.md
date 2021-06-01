---
description: Beschreibt die Anforderungen an die Segmentgröße und die Erstellungszeit, die für den Aktualisierungsprozess des Overlap Report erforderlich sind.
seo-description: Beschreibt die Anforderungen an die Segmentgröße und die Erstellungszeit, die für den Aktualisierungsprozess des Overlap Report erforderlich sind.
seo-title: Aktualisierungszeitplan für Überlagerungsberichte und Mindestsegmentgröße
solution: Audience Manager
title: Aktualisierungszeitplan für Überlagerungsberichte und Mindestsegmentgröße
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Überlagerungsberichte
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---

# Überlagerungsberichte: Aktualisierungszeitplan und Mindestsegmentgröße{#overlap-reports-update-schedule-and-minimum-segment-size}

Beschreibt die Anforderungen an Eigenschaften und Segmentgröße sowie die Erstellungszeit, die für den Aktualisierungsprozess von Overlap Report erforderlich sind.

## Zeitplan und Anforderungen aktualisieren {#update-schedule}

[!UICONTROL Overlap] Berichte werden am Sonntag wöchentlich aktualisiert. Die Berichtsvorverarbeitung beginnt am Samstag. Dies wirkt sich darauf aus, wie neue oder vorhandene Segmente am Montag in einem Überschneidungsbericht angezeigt werden. In einen Überschneidungsbericht aufzunehmen:

* Ein Segment muss mindestens 70.000 Benutzer in den letzten 14 Tagen in Echtzeit enthalten.
* Eine Eigenschaft muss in den letzten 14 Tagen 28.000 [Unique Trait-Realisierungen](/help/using/features/traits/trait-and-segment-qualification-reference.md) enthalten.
* Ein Segment muss vor 12:00 Uhr (Donnerstag, UTC) erstellt worden sein (2 volle Tage vor Beginn des wöchentlichen Aktualisierungsprozesses des Überschneidungsberichts).
* Ihr Unternehmen muss ein Full [!DNL Audience Manager]-Kunde sein. Wenden Sie sich an Ihren [!DNL Audience Manager]-Berater oder an die Kundenunterstützung, um mehr zu erfahren.

## Segmentgröße und/oder Erstellungszeit wirkt sich auf die Berichterstellung aus {#segment-size}

Wenn in einem der [!UICONTROL Overlap] -Berichte kein Segment angezeigt wird, liegt dies möglicherweise daran, dass das Segment diese Mindestanforderungen nicht erfüllt.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Anwendungsfall </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentgröße zu klein</b> </p> </td> 
   <td colname="col2"> <p>Nehmen wir an, Sie erstellen ein Segment vor 12 Uhr UTC am Donnerstag, es enthält jedoch weniger als 70.000 Benutzer in Echtzeit. Dieses Segment wird erst dann in einem <span class="wintitle"> Overlap Report</span> angezeigt, wenn es die Anforderungen an den Benutzerschwellenwert erfüllt. Beachten Sie außerdem, dass das Segment die erforderliche Benutzeranzahl für den Donnerstag oder vor dem Donnerstag-Cutoff-Zeitraum erfüllen muss. Wenn das Segment die wöchentliche Frist nicht erfüllt, wird es in den <span class="wintitle"> Überlagerungsberichten</span> für die Woche nach der nächsten Ausführung der Sonntagsdaten angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment, das zu spät erstellt wurde</b> </p> </td> 
   <td colname="col2"> <p>Angenommen, Sie erstellen am Freitag ein Segment, das mehr als 70.000 Benutzer in Echtzeit enthält. Dieses Segment wird für die nächste Woche nicht in den <span class="wintitle"> Überlagerungsberichten</span> angezeigt, da es weniger als 2 Tage vor dem Aktualisierungszeitraum des Berichts erstellt wurde. Das Segment wird jedoch nach der nächsten wöchentlichen Aktualisierung in einem <span class="wintitle"> Overlap Report</span> angezeigt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Überlagerungsbericht zwischen Eigenschaften](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
* [Überlagerungsbericht zwischen Segmenten und Eigenschaften](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
* [Überlagerungsbericht zwischen Segmenten](../../reporting/dynamic-reports/segment-segment-overlap-report.md)


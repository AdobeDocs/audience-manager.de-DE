---
description: Beschreibt die Segmentgröße und die Erstellungszeitanforderungen, die für den Aktualisierungsprozess des Überschneidungsberichts erforderlich sind.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Aktualisierungszeitplan für Überschneidungsberichte und minimale Segmentgröße
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 3%

---

# Überschneidungsberichte: Zeitplan und Mindestsegmentgröße aktualisieren{#overlap-reports-update-schedule-and-minimum-segment-size}

Beschreibt die Eigenschaften- und Segmentgröße sowie die Anforderungen an die Erstellungszeit, die für den Aktualisierungsprozess des Überschneidungsberichts erforderlich sind.

## Zeitplan und Anforderungen aktualisieren {#update-schedule}

[!UICONTROL Overlap] Berichte werden wöchentlich am Sonntag aktualisiert. Die Berichtsvorverarbeitung beginnt am Samstag. Dies wirkt sich darauf aus, wie neue oder vorhandene Segmente in einem Überschneidungsbericht am Montag angezeigt werden. In einen Überschneidungsbericht aufzunehmen:

* Ein Segment muss in den letzten 14 Tagen mindestens 70.000 Echtzeit-Benutzer enthalten.
* Ein Merkmal muss in den [&#x200B; 14 Tagen 28.000 &#x200B;](/help/using/features/traits/trait-and-segment-qualification-reference.md)Eindeutige Merkmale“ enthalten.
* Ein Segment muss vor Donnerstag, 12 Uhr UTC (2 volle Tage vor Beginn des Aktualisierungsprozesses des wöchentlichen Überschneidungsberichts) erstellt worden sein.
* Ihr Unternehmen muss ein Full-[!DNL Audience Manager]-Kunde sein. Wenden Sie sich an Ihren [!DNL Audience Manager] oder die Kundenunterstützung, um mehr zu erfahren.

## Die Segmentgröße und/oder die Erstellungszeit wirken sich auf das Reporting aus {#segment-size}

Wenn ein Segment nicht in einem der [!UICONTROL Overlap] Berichte angezeigt wird, kann dies daran liegen, dass das Segment diese Mindestanforderungen nicht erfüllt.

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
   <td colname="col2"> <p>Angenommen, Sie erstellen ein Segment vor Donnerstag, 12 Uhr UTC, es enthält jedoch insgesamt weniger als 70.000 Echtzeit-Benutzer. Dieses Segment wird erst dann in einem <span class="wintitle">-Überschneidungsbericht angezeigt, </span> es die Anforderungen an den Benutzerschwellenwert erfüllt. Beachten Sie außerdem, dass das Segment die erforderliche Benutzeranzahl ab dem Donnerstag-Abschaltzeitraum oder davor erfüllen muss. Wenn die wöchentliche Frist nicht eingehalten wird, wird das Segment in den <span class="wintitle"> Überschneidungsberichten für </span> Woche nach der bevorstehenden Sonntagsdatenausführung angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment zu spät erstellt</b> </p> </td> 
   <td colname="col2"> <p>Angenommen, Sie erstellen am Freitag ein Segment mit mehr als 70.000 Echtzeit-Benutzern. Dieses Segment wird in den <span class="wintitle"> Überschneidungsberichten der nächsten </span> nicht angezeigt, da es weniger als 2 Tage vor dem Berichtsaktualisierungszeitraum erstellt wurde. Das Segment wird jedoch nach der nächsten wöchentlichen Aktualisierung in <span class="wintitle"> Bericht "</span> Überschneidung“ angezeigt. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Überlagerungsbericht zwischen Eigenschaften](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Überlagerungsbericht zwischen Segmenten und Eigenschaften](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Überlagerungsbericht zwischen Segmenten](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

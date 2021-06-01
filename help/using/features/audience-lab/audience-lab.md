---
description: Erstellen sich gegenseitig ausschließende Testsegmente in Segmenttestgruppen, um die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe beilegen und Ihr Segment in Prozentsätze eines Ganzen unterteilen, um die Wirksamkeit zu testen.
seo-description: Erstellen sich gegenseitig ausschließende Testsegmente in Segmenttestgruppen, um die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe beilegen und Ihr Segment in Prozentsätze eines Ganzen unterteilen, um die Wirksamkeit zu testen.
seo-title: 'Audience Lab '
solution: Audience Manager
title: 'Audience Lab '
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: 'Audience Lab '
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 4%

---

# [!UICONTROL Audience Lab] {#audience-lab}

Erstellen sich gegenseitig ausschließender Testsegmente in [!UICONTROL Segment Test Groups] , um die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe beilegen und Ihr Segment in Prozentsätze eines Ganzen unterteilen, um die Wirksamkeit zu testen.

## Überblick {#audience-lab-overview}

[!UICONTROL Audience Lab] verwendet  [Profil-](../../features/profile-merge-rules/merge-rules-overview.md) Link für geräteübergreifende Tests. Dadurch wird sichergestellt, dass sich ein Benutzer für dasselbe Testsegment qualifiziert und geräteübergreifend gleich behandelt. Die Testsegmente in Testgruppen übernehmen die [Profilzusammenführungsrichtlinie](../../features/profile-merge-rules/merge-rules-dashboard.md), die das Basissegment ihr zugewiesen hat.

Die Standardansicht [!UICONTROL Audience Lab] zeigt eine Karte für jede der Testgruppen an. Klicken Sie auf eine Karte, um auf die Ansicht **[!UICONTROL Test Group]** zuzugreifen. Diese Ansicht enthält die folgenden Informationen:

* **[Informationen zu Testgruppen](../../features/audience-lab/audience-lab-information-view.md)**
* **[Testgruppenberichte](../../features/audience-lab/audience-lab-reporting-view.md)**

Sie können **bis zu 10 Testgruppen** erstellen, von denen jede **bis zu 15 Testsegmente** enthält.

![](assets/test-groups-view.PNG)

## Suchen und Filtern von Testgruppen {#search-and-filter}

Sobald Sie mit der Erstellung mehrerer Testgruppen mit mehreren Testsegmenten beginnen, kann es einfacher sein, das Suchfeld zu verwenden, um eine bestimmte Testgruppe zu finden. Sie können nach einer Testgruppe suchen, indem Sie:

* Name der Testgruppe;
* Der Name eines der Testsegmente in Ihrer Testgruppe;
* Die Beschreibung der Testgruppe.

![](assets/search_and_filter_audience_lab.png)

Sie können Ihre Testgruppen auch nach Status filtern. Alle verfügbaren Status werden im Abschnitt [Status](../../features/audience-lab/audience-lab.md#status) weiter unten beschrieben.

## [!UICONTROL Status] {#status}

Der Status einer Testgruppe kann aktiv, geplant, ausgesetzt, Entwurf oder abgeschlossen sein. Weitere Informationen zu den einzelnen Punkten finden Sie in der unten stehenden Tabelle:

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Status </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktiv </span></b> </p> </td> 
   <td colname="col2"> <p>Eine Testgruppe <i>active</i> bedeutet, dass derzeit Daten an Ziele gesendet werden. Drücken Sie <b><span class="uicontrol"> Pause Test </span></b> auf der Karte <b><span class="uicontrol"> Testgruppe </span></b> , um das Senden von Daten an Ziele auszusetzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Eingeplant </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>geplante</i> Testgruppe ist noch nicht aktiv, kann aber nicht mehr bearbeitet werden. Sie wird am Startdatum aktiv, das Sie im Assistenten <b>Erstellen von Testgruppen</b> ausgewählt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> angehalten </span></b> </p> </td> 
   <td colname="col2"> <p>Eine Testgruppe <i>paused</i> sendet derzeit keine Daten an Ziele. Drücken Sie <b><span class="uicontrol"> Aktiv </span></b> auf der Karte <b><span class="uicontrol"> Testgruppe </span></b> , um das Senden von Eigenschaften fortzusetzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Entwurf </span></b> </p> </td> 
   <td colname="col2"> <p>Eine Testgruppe <i>draft</i> ist noch nicht aktiv und kann noch bearbeitet werden. Es werden noch keine Daten an die zugeordneten Ziele gesendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Abgeschlossen </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>fertige</i> Testgruppe hat das Enddatum erreicht, das Sie im Assistenten <b><span class="uicontrol"> Testgruppen erstellen </span></b> ausgewählt haben, und hat das Senden von Berichtsdaten beendet. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Aktionen </th> 
   <th colname="col2" class="entry"> Beschreibung </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bearbeiten </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar <b>nur</b> für Entwurfstestgruppen. Ermöglicht die Wiederaufnahme des Assistenten <b><span class="uicontrol"> Neue Testgruppe erstellen </span></b> . </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pause </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für aktive Testgruppen. Ermöglicht das Anhalten des Sendens der Testsegmente an Ziele. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktiv machen  </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für angehaltene Testgruppen. Ermöglicht Ihnen, das Senden der Testsegmente an Ziele fortzusetzen. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ansicht </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für abgeschlossene Testgruppen. Ermöglicht die Anzeige der Berichtsinformationen, die der Test generiert hat. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplizieren </span></b> </p> </td>
   <td colname="col2"> <p>Ermöglicht die Erstellung einer neuen Testgruppe mit der Konfiguration, die Sie duplizieren. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Löschen </span></b> </p> </td>
   <td colname="col2"> <p>Ermöglicht das Löschen einer Testgruppe. Die Zuordnung der Testsegmente zu den Zielen wird aufgehoben, das Grundliniensegment und die mit der Testgruppe verknüpften Konversionseigenschaften sind vollständig bearbeitbar. Wenn Sie eine Testgruppe löschen, werden Sie in einem Warnhinweis aufgefordert, die CSV-Datei herunterzuladen, damit die Berichterstellung gespeichert werden kann. </p> </td>
  </tr>
 </tbody>
</table>

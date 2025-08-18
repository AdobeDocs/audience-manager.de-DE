---
description: Erstellen Sie sich gegenseitig ausschließende Testsegmente in Segmenttestgruppen, um die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe zur Seite legen und Ihr Segment in Prozentsätze eines Ganzen aufteilen, um die Wirksamkeit zu testen.
seo-description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 2%

---

# [!UICONTROL Audience Lab] {#audience-lab}

Erstellen Sie sich gegenseitig ausschließende Testsegmente, [!UICONTROL Segment Test Groups] die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe zur Seite legen und Ihr Segment in Prozentsätze eines Ganzen aufteilen, um die Wirksamkeit zu testen.

## Überblick {#audience-lab-overview}

[!UICONTROL Audience Lab] verwendet [Profil-Link](../../features/profile-merge-rules/merge-rules-overview.md) für geräteübergreifende Tests. Dadurch wird sichergestellt, dass Benutzende für dasselbe Testsegment qualifiziert sind und geräteübergreifend dieselbe Behandlung erhalten. Die Testsegmente in Testgruppen übernehmen die [Profilzusammenführungsregel](../../features/profile-merge-rules/merge-rules-dashboard.md) die dem Basissegment zugewiesen wurde.

In der [!UICONTROL Audience Lab] Standardansicht wird für jede Testgruppe eine Karte angezeigt. Klicken Sie auf eine Karte, um auf die **[!UICONTROL Test Group]** zuzugreifen. Diese Ansicht enthält die folgenden Informationen:

* **[Informationen zu Testgruppen](../../features/audience-lab/audience-lab-information-view.md)**
* **[Testgruppenberichte](../../features/audience-lab/audience-lab-reporting-view.md)**

Sie können (**zu 10 Testgruppen** jeweils mit (**zu 15 Testsegmenten** erstellen.

![](assets/test-groups-view.PNG)

## Testgruppen suchen und filtern {#search-and-filter}

Sobald Sie mit der Erstellung mehrerer Testgruppen mit mehreren Testsegmenten beginnen, kann es einfacher sein, das Suchfeld zu verwenden, um eine bestimmte Testgruppe zu finden. Sie können nach einer Testgruppe suchen, indem Sie:

* Name der Prüfgruppe;
* Der Name eines der Testsegmente in Ihrer Testgruppe;
* Die Beschreibung der Testgruppe.

![](assets/search_and_filter_audience_lab.png)

Sie können Ihre Testgruppen auch nach Status filtern. Alle verfügbaren Status werden im Abschnitt [Status](../../features/audience-lab/audience-lab.md#status) unten beschrieben.

## [!UICONTROL Status] {#status}

Der Status einer Testgruppe kann aktiv, geplant, angehalten, Entwurf oder abgeschlossen sein. Weitere Informationen zu den einzelnen Kriterien finden Sie in der folgenden Tabelle:

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Status </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Aktive <b><span class="uicontrol"> </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>aktive</i> Testgruppe bedeutet, dass derzeit Daten an Ziele gesendet werden. Drücken Sie <b><span class="uicontrol"> Pause Test </span></b> auf der Karte <b><span class="uicontrol"> Test Group </span></b> , um das Senden von Daten an Ziele auszusetzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> geplanter </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>geplante</i> Testgruppe ist noch nicht aktiv, kann jedoch nicht mehr bearbeitet werden. Sie wird zu dem Startdatum aktiv, das Sie im Assistenten <b>Testgruppen erstellen</b> ausgewählt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> angehalten </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>angehaltene</i> Testgruppe sendet derzeit keine Daten an Ziele. Drücken Sie <b><span class="uicontrol"> Auf der Karte </span></b> Testgruppe <b><span class="uicontrol"> die Option Aktive </span></b> festlegen , um den Versand der Eigenschaften fortzusetzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>Entwurf</i> Testgruppe ist noch nicht aktiv und kann noch bearbeitet werden. Es sendet noch keine Daten an die zugeordneten Ziele. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> abgeschlossen </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>abgeschlossene</i> Testgruppe hat das Enddatum erreicht, das Sie im <b><span class="uicontrol"> "</span></b> Testgruppen erstellen“ ausgewählt haben, und hat den Versand von Berichtsdaten beendet. </p> </td>
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
   <td colname="col1"> <p> <b><span class="uicontrol"> bearbeiten </span></b> </p> </td>
   <td colname="col2"> <p>Nur <b> für </b>-Testgruppen verfügbar. Ermöglicht es Ihnen, den Assistenten <b><span class="uicontrol"> Erstellen einer neuen Testgruppe </span></b> fortsetzen. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pause </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für aktive Testgruppen. Ermöglicht das Pausieren des Versands der Testsegmente an Ziele. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Make Active </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für pausierte Testgruppen. Ermöglicht es Ihnen, das Senden der Testsegmente an Ziele fortzusetzen. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> View </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für abgeschlossene Testgruppen. Ermöglicht die Anzeige der Reporting-Informationen, die der Test generiert hat. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> doppelter </span></b> </p> </td>
   <td colname="col2"> <p>Ermöglicht die Erstellung einer neuen Testgruppe mit derselben Konfiguration wie die zu duplizierende. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> </span></b> </p> </td>
   <td colname="col2"> <p>Ermöglicht das Löschen einer Testgruppe. Die Zuordnung der Testsegmente zu den Zielen wird aufgehoben, und das Baseline-Segment sowie die mit der Testgruppe verknüpften Konversionseigenschaften sind vollständig bearbeitbar. Ein Warnhinweis fordert Sie dazu auf, die CSV-Datei herunterzuladen, wenn Sie eine Testgruppe löschen, um die Berichte bei Bedarf zu speichern. </p> </td>
  </tr>
 </tbody>
</table>

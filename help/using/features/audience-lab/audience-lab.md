---
description: Erstellen Sie sich gegenseitig ausschließende Testsegmente in Segmenttestgruppen, um die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe beilegen und Ihr Segment in Prozentsätze eines Ganzen unterteilen, um die Wirksamkeit zu testen.
seo-description: Erstellen Sie sich gegenseitig ausschließende Testsegmente in Segmenttestgruppen, um die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe beilegen und Ihr Segment in Prozentsätze eines Ganzen unterteilen, um die Wirksamkeit zu testen.
seo-title: 'Audience Lab '
solution: Audience Manager
title: 'Audience Lab '
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---


# [!UICONTROL Audience Lab] {#audience-lab}

Erstellen Sie sich gegenseitig ausschließende Testsegmente in [!UICONTROL Segment Test Groups], um die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe beilegen und Ihr Segment in Prozentsätze eines Ganzen unterteilen, um die Wirksamkeit zu testen.

## Überblick {#audience-lab-overview}

[!UICONTROL Audience Lab] verwendet  [Profil ](../../features/profile-merge-rules/merge-rules-overview.md) Linkto-Power-geräteübergreifende Tests. Dadurch wird sichergestellt, dass sich ein Benutzer für dasselbe Testsegment qualifiziert und geräteübergreifend gleich behandelt wird. Die Testsegmente in Testgruppen übernehmen die [Profil Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md), die das Basissegment ihr zugewiesen hat.

Die Standardkarte [!UICONTROL Audience Lab] zeigt eine Ansicht für jede der Testgruppen an. Klicken Sie auf eine Karte, um auf die Ansicht **[!UICONTROL Test Group]** zuzugreifen. Diese Ansicht enthält die folgenden Informationen:

* **[Informationen zu Testgruppen](../../features/audience-lab/audience-lab-information-view.md)**
* **[Testgruppenberichte](../../features/audience-lab/audience-lab-reporting-view.md)**

Sie können bis zu 10 Testgruppen **mit jeweils** bis zu 15 Testsegmenten **erstellen.**

![](assets/test-groups-view.PNG)

## Testgruppen suchen und filtern {#search-and-filter}

Wenn Sie mit der Erstellung mehrerer Testgruppen mit mehreren Testsegmenten Beginn haben, ist es möglicherweise einfacher, das Suchfeld zu verwenden, um eine bestimmte Testgruppe zu finden. Sie können nach einer Testgruppe suchen, indem Sie:

* Name der Prüfgruppe;
* Der Name eines der Testsegmente in Ihrer Testgruppe;
* Die Beschreibung der Testgruppe.

![](assets/search_and_filter_audience_lab.png)

Sie können Ihre Testgruppen auch nach Status filtern. Alle verfügbaren Status werden im Abschnitt [Status](../../features/audience-lab/audience-lab.md#status) beschrieben.

## [!UICONTROL Status] {#status}

Der Status einer Testgruppe kann aktiv, geplant, angehalten, Entwurf oder abgeschlossen sein. Weitere Informationen zu den einzelnen in der nachstehenden Tabelle:

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
   <td colname="col2"> <p>Eine <i>aktive</i>-Testgruppe bedeutet, dass derzeit Daten an Ziele gesendet werden. Drücken Sie auf <b><span class="uicontrol"> Test anhalten </span></b> in der Karte <b><span class="uicontrol"> Testgruppe </span></b>, um das Senden von Daten an Ziele auszusetzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Eingeplant </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>geplante</i> Testgruppe ist noch nicht aktiv, kann aber nicht mehr bearbeitet werden. Es wird am Beginn aktiv, den Sie im Assistenten <b>Testgruppen erstellen</b> ausgewählt haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> angehalten </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>angehaltene</i>-Testgruppe sendet derzeit keine Daten an Ziele. Drücken Sie auf <b><span class="uicontrol"> Aktiv </span></b> auf der Karte <b><span class="uicontrol"> Testgruppe </span></b>, um das Senden von Eigenschaften fortzusetzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Entwurf </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>draft</i>-Testgruppe ist noch nicht aktiv und kann trotzdem bearbeitet werden. Es werden noch keine Daten an die zugeordneten Ziele gesendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Abgeschlossen </span></b> </p> </td> 
   <td colname="col2"> <p>Eine <i>abgeschlossene</i>-Testgruppe hat das Enddatum erreicht, das Sie im Assistenten <b><span class="uicontrol"> Testgruppen erstellen </span></b> ausgewählt haben, und das Senden von Berichte-Daten wurde beendet. </p> </td>
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
   <td colname="col2"> <p>Verfügbar <b>nur</b> für Entwurfstestgruppen. Damit können Sie den Assistenten <b><span class="uicontrol"> Neue Testgruppe </span></b> erstellen fortsetzen. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pause </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für aktive Testgruppen. Ermöglicht es Ihnen, das Senden der Testsegmente an Ziele anzuhalten. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktiv  </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für angehaltene Testgruppen. Ermöglicht es Ihnen, mit dem Senden der Testsegmente an Ziele fortzufahren. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ansicht </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für abgeschlossene Testgruppen. Ermöglicht die Ansicht der Testinformationen zum Berichte. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplizieren </span></b> </p> </td>
   <td colname="col2"> <p>Ermöglicht Ihnen das Erstellen einer neuen Testgruppe mit derselben Konfiguration wie die, die Sie duplizieren. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Löschen </span></b> </p> </td>
   <td colname="col2"> <p>Ermöglicht das Löschen einer Testgruppe. Die Zuordnung der Testsegmente zu den Zielen wird aufgehoben, das Grundliniensegment und die Konversionseigenschaften, die der Testgruppe zugeordnet sind, können vollständig bearbeitet werden. Wenn Sie eine Testgruppe löschen, werden Sie aufgefordert, die CSV-Datei herunterzuladen, um den Berichte zu speichern. </p> </td>
  </tr>
 </tbody>
</table>
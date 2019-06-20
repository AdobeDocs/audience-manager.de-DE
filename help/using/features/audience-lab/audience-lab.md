---
description: Erstellen Sie sich gegenseitig ausschließende Testsegmente in Segmenttestgruppen, um die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe festlegen und Ihr Segment in Prozentsätze teilen, um die Effektivität zu testen.
seo-description: Erstellen Sie sich gegenseitig ausschließende Testsegmente in Segmenttestgruppen, um die Effektivität verschiedener Ziele zu vergleichen und zu messen. Sie können eine Kontrollgruppe festlegen und Ihr Segment in Prozentsätze teilen, um die Effektivität zu testen.
seo-title: Zielgruppe Lab
solution: Audience Manager
title: Zielgruppe Lab
topic: DIL-API
uuid: aaee 820 c -1 e 78-4 fd 4-bd 8 f -2629085 d 78 e 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

Create mutually exclusive test segments in [!UICONTROL Segment Test Groups] to compare and measure effectiveness of different destinations. Sie können eine Kontrollgruppe festlegen und Ihr Segment in Prozentsätze teilen, um die Effektivität zu testen.

## Überblick {#audience-lab-overview}

[!UICONTROL Audience Lab] verwendet [Profillink](../../features/profile-merge-rules/merge-rules-overview.md) , um geräteübergreifende Tests zu testen. Dadurch wird sichergestellt, dass sich ein Benutzer für dasselbe Testsegment qualifiziert und die gleiche Behandlung geräteübergreifend erhält. The test segments in test groups will inherit the [Profile Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md) the base segment has assigned to it.

The [!UICONTROL Audience Lab] default view displays a card for each of the test groups. Click a card to access the **[!UICONTROL Test Group]** view. Diese Ansicht enthält die folgenden Informationen:

* **[Testgruppeninformationen](../../features/audience-lab/audience-lab-information-view.md)**
* **[Testgruppenberichte](../../features/audience-lab/audience-lab-reporting-view.md)**

You are able to create **up to 10 test groups**, each one with **up to 15 test segments**.

![](assets/test-groups-view.PNG)

## Search and Filter Test Groups {#search-and-filter}

Sobald Sie mit der Erstellung mehrerer Testgruppen mit mehreren Testsegmenten begonnen haben, kann es einfacher sein, das Suchfeld zu verwenden, um eine bestimmte Testgruppe zu finden. Sie können nach einer Testgruppe suchen nach:

* Der Name der Testgruppe;
* Der Name eines der Testsegmente in Ihrer Testgruppe;
* Die Beschreibung der Testgruppe.

![](assets/search_and_filter_audience_lab.png)

Sie können Ihre Testgruppen auch nach Status filtern. All available statuses are described in the [Status](../../features/audience-lab/audience-lab.md#status) section below.

## Status {#status}

Der Status einer Testgruppe kann aktiv, geplant, angehalten, Entwurf oder abgeschlossen sein. Weitere Informationen zu jedem der beiden Elemente in der folgenden Tabelle:

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
   <td colname="col2"> <p>An <i>active</i> test group means that data is currently being sent to destinations. Press <b><span class="uicontrol"> Pause Test </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to suspend sending data to destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geplant </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>scheduled</i> test group is not yet active but cannot be edited anymore. It will become active at the start date you selected in the <b>Create Test Groups</b> wizard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Angehalten </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>paused</i> test group does not currently send data to destinations. Press <b><span class="uicontrol"> Make Active </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to resume sending traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Entwurf </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>draft</i> test group is not yet active and can still be edited. Daten werden noch nicht an die zugeordneten Ziele gesendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Abgeschlossen </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>completed</i> test group has reached the end date you selected in the <b><span class="uicontrol"> Create Test Groups </span></b> wizard and has stopped sending reporting data. </p> </td>
  </tr>
 </tbody>
</table>

## Aktionen {#actions}

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
   <td colname="col2"> <p>Available <b>only</b> for draft test groups. Allows you to resume the <b><span class="uicontrol"> Create New Test Group </span></b> wizard. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pause </span></b> </p> </td>
   <td colname="col2"> <p>Für aktive Testgruppen verfügbar. Damit können Sie die Übermittlung der Testsegmente an Ziele anhalten. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktiv machen </span></b> </p> </td>
   <td colname="col2"> <p>Für angehaltene Testgruppen verfügbar. Ermöglicht das Fortsetzen der Testsegmente an Ziele. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ansicht </span></b> </p> </td>
   <td colname="col2"> <p>Verfügbar für abgeschlossene Testgruppen. Ermöglicht es Ihnen, die Berichtsinformationen anzuzeigen, die der Test generiert hat. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplizieren </span></b> </p> </td>
   <td colname="col2"> <p>Hiermit können Sie eine neue Testgruppe mit derselben Konfiguration erstellen wie die, die Sie duplizieren. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Löschen </span></b> </p> </td>
   <td colname="col2"> <p>Hiermit können Sie eine Testgruppe löschen. Die Testsegmente werden nicht von den Zielen zugeordnet, das Grundliniensegment und die Konversionseigenschaften, die mit der Testgruppe verknüpft sind, sind vollständig bearbeitbar. Eine Warnung fordert Sie auf, die CSV-Datei herunterzuladen, wenn Sie eine Testgruppe löschen, um die Berichterstellung zu speichern, falls gewünscht. </p> </td>
  </tr>
 </tbody>
</table>
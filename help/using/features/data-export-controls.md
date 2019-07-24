---
description: Datenexportkontrollen verhindern, dass Sie Daten an Ziele senden, wenn diese Aktion Datenschutz- oder Datennutzungsvereinbarungen verletzt.
seo-description: Datenexportkontrollen verhindern, dass Sie Daten an Ziele senden, wenn diese Aktion Datenschutz- oder Datennutzungsvereinbarungen verletzt.
seo-title: Datenexportkontrolle
solution: Audience Manager
title: Datenexportkontrolle
uuid: de 7 f 3608-c 0 cb -4049-973 a -8 be 54525 c 600
translation-type: tm+mt
source-git-commit: 302670f294574c3b56ccd16aeca8ebab8f4e8ce9

---


# Datenexportkontrolle {#data-export-controls}

[!UICONTROL Data Export Controls] verhindern, dass Daten an Ziele gesendet werden, wenn diese Aktion Datenschutz- oder Datennutzungsvereinbarungen verletzt.

## Überblick {#overview}

[!UICONTROL Data Export Controls] ermöglicht die Klassifizierung [von Datenquellen](../features/datasources-list-and-settings.md#data-sources-list-and-settings) und [Zielen](../features/destinations/destinations.md). Die von Ihnen angewandten Klassifizierungen bestimmen, wann Daten in ein Ziel exportiert werden können oder nicht. Diese Funktion besteht aus:

* **[!UICONTROL Data Export Controls]**: Sie können Datenexportsteuerelemente für *Datenquellen festlegen*. Wenn diese Einstellung in einer Datenquelle festgelegt ist, schränken diese Steuerelemente die Verwendung der Datenquelle und deren Eigenschaften ein.
* **[!UICONTROL Data Export Labels]**: Sie können Datenexportbeschriftungen auf *Zielen festlegen*. Bei Festlegung auf einem Ziel identifizieren diese Beschriftungen, wie das Ziel Daten verwendet. See [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) to learn how to add export labels to a destination.

Auf der Grundlage der auf eine Datenquelle und ein Ziel angewendeten Classifications werden Sie durch die Exportsteuerelemente vom folgenden abgebrochen:

* Hinzufügen einer Eigenschaft zu einem Segment, wenn die Eigenschaft zu einer Datenquelle gehört, die über eine Datenexportsteuerung verfügt, die mit einer oder mehreren der Ziele, denen das Segment zugeordnet ist, nicht kompatibel ist.
For example, say a segment is mapped to a destination with the export label **[UICONTROL! This destination may enable a combination with personally identifiable information (PII)]**. Export controls stop you from adding a trait to that segment if the data source that the trait belongs to has a data export control that says **[UICONTROL! Cannot be tied to personally identifiable information (PII)]**.
* Wenn Sie Daten an ein Zielziel senden, wird eine Datenexportbeschriftung, die von einem Datenexportsteuerelement gesperrt wird, auf einer der folgenden Weisen gesperrt:
   * Die Datenquelle einer einbezogenen Eigenschaft;
   * Die Datenquelle einer Eigenschaft, die in einem eingeschlossenen Segment verwendet wird;
   * Die Regel zum Profilzusammenführen, die von einem einbezogenen Segment genutzt wird;
   * Eine der Datenquellen, die die Profilregel für die Profilzusammenführung enthält.

[!UICONTROL Data Export Controls] sind für alle Audience Manager-Kunden automatisch verfügbar. Sie benötigen jedoch Administratorrechte, um einer Datenquelle Exportsteuerelemente hinzuzufügen. Adding export labels to a destination requires administrator permissions *or* sufficient privileges to create or edit a destination.

## Controls and labels defined {#controls-labels}

[!UICONTROL Data Export Controls] Bereitstellen der folgenden Steuerelemente, um Datenquellen und Ziele zu klassifizieren.

Um die Datenauslieferung zu blockieren, müssen Sie eine Datenquelle mit einem Exportsteuerelement klassifizieren und eine Exportbeschriftung zu einem Ziel hinzufügen. Wenn Sie nur die Exportsteuerelemente auf eine Datenquelle oder ein Ziel anwenden, wird die Datenauslieferung nicht eingeschränkt. When set on both the data source *and* destination, the export controls will limit the traits you can add to a segment and prevent sending the segment members to a destination.

Außerdem muss mindestens eine Exportbeschriftung mit einem Exportsteuerelement übereinstimmen, bevor die Datenauslieferungsbeschränkungen wirksam werden. For example, say you add the [!UICONTROL PII] export control to a data source. Als Nächstes fügen Sie die Onsite-Targeting-Bezeichnung zu einem Ziel hinzu. In diesem Fall schränken Exportsteuerelemente die Datenauslieferung kein, da die Einstellungen nicht übereinstimmen. However, if you add the [!UICONTROL PII] export label to the destination, the export controls will block the export.

>[!IMPORTANT]
>
>[Sie können den Export eines Segments nicht blockieren, indem Sie ein Datenexportsteuerelement in die Datenquelle des Segments platzieren. Sie müssen das Steuerelement auf einer der folgenden Weisen festlegen:
> * Die Datenquellen der im Segment verwendeten Eigenschaften;
> * Die Regel zum Profilzusammenführen, die vom Segment genutzt wird;
> * Eine der Datenquellen, die die Profilregel des Segments enthält, verwendet.


<br> 

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datenexportsteuerelemente für eine Datenquelle </th> 
   <th colname="col2" class="entry"> Datenexportbeschriftungen für ein Ziel </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Keine Einschränkung</span></b> </td> 
   <td colname="col2"> Keine </td> 
   <td colname="col3"> Standardmäßig werden Exportbeschränkungen für neue Datenquellen und Ziele nicht festgelegt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht an personenbezogene Informationen</span></b> (PII) gebunden werden </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann eine Kombination mit personenbezogenen Informationen (PII) aktivieren.</span></b> </td> 
   <td colname="col3">Wenn diese Option aktiviert ist, können Sie: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Fügen Sie Segmente zu Segmenten hinzu, die den Zielen zugeordnet sind, die PII verwenden. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Ordnen Sie mit einer Eigenschaft erstellte Segmente von der Datenquelle an Ziele zu, die PII verwenden. </li> 
    </ul> <p>Dies ist oft für Drittanbieter von Daten und bei der Verwendung von Datenquellen, die Anzeige-/Medienverfolgungsinformationen enthalten, erforderlich. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für das Targeting auf der Site verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für das Targeting auf dem Site-Targeting verwendet werden.</span></b> </td> 
   <td colname="col3">Wenn diese Option aktiviert ist, können Sie: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Fügen Sie Segmente zu Segmenten hinzu, die Ziele zugeordnet sind, die die Anzeigenauslieferung basierend auf dem Webbrowserverlauf eines Besuchers anpassen. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Ordnen Sie mit einer Eigenschaft erstellte Segmente von der Datenquelle zu Zielen zu, die die Anzeigenauslieferung basierend auf dem Webbrowserverlauf eines Besuchers anpassen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für Targeting außerhalb der Site verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für das Offsite-Targeting von Werbung verwendet werden.</span></b> </td> 
   <td colname="col3">Diese Einschränkungen werden im Allgemeinen bei Auswahl verwendet: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Fügen Sie Segmente zu Segmenten hinzu, die Ziele zugeordnet sind, die Benutzer auf anderen Sites erneut ansprechen. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Ordnen Sie mit einer Eigenschaft erstellte Segmente von der Datenquelle zu Zielen zu, die Benutzer auf anderen Sites erneut ansprechen. </li> 
    </ul> <p>Oft erforderlich, wenn Sie mit Daten aus sozialen Plattformen arbeiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für Personalisierung auf der Site verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für Personalisierung auf der Site verwendet werden.</span></b> </td> 
   <td colname="col3">Wenn diese Option aktiviert ist, können Sie: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Fügen Sie Segmente zu Segmenten hinzu, die Ziele zugeordnet sind, die Inhalte basierend auf Benutzerinteressen oder dem Webbrowserverlauf anpassen. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Ordnen Sie mit einer Eigenschaft erstellte Segmente von der Datenquelle zu Zielen zu, die Inhalte basierend auf Benutzerinteressen oder dem Webbrowserverlauf anpassen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Arbeitsablauf{#workflow}

Überprüfen Sie zunächst die Datenquelle und die Zieldokumentation. Diese Artikel enthalten Anweisungen zum Hinzufügen von Exportsteuerelementen und Bezeichnungen zu Ihren Datenquellen und Zielen.

* [Datenquelle erstellen](../features/manage-datasources.md#create-data-source)
* [Datenexport-Beschriftungen zu einem Ziel hinzufügen](../features/destinations/manage-destinations.md#add-data-export-labels)
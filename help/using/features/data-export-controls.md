---
description: Mit den Datenexportkontrollen können Sie verhindern, dass Daten an Ziele gesendet werden, wenn diese Aktion Datenschutzvereinbarungen oder Datenverwendungsvereinbarungen verletzt.
seo-description: Mit den Datenexportkontrollen können Sie verhindern, dass Daten an Ziele gesendet werden, wenn diese Aktion Datenschutzvereinbarungen oder Datenverwendungsvereinbarungen verletzt.
seo-title: Datenexportkontrollen
solution: Audience Manager
title: Datenexportkontrollen
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 1%

---


# Datenexportkontrollen {#data-export-controls}

[!UICONTROL Data Export Controls] verhindern, dass Sie Daten an Ziele senden, wenn diese Aktion gegen Datenschutzvereinbarungen oder Datennutzungsvereinbarungen verstößt.

## Überblick {#overview}

[!UICONTROL Data Export Controls] können Sie  [Datenquellen ](../features/datasources-list-and-settings.md#data-sources-list-and-settings) und  [Ziele](../features/destinations/destinations.md) klassifizieren. Die angewendeten Klassifizierungen bestimmen, wann Daten an ein Ziel exportiert werden können oder nicht. Diese Funktion umfasst:

* **[!UICONTROL Data Export Controls]**: Sie können Datenexportsteuerelemente für  *Datenquellen* festlegen. Wenn diese Steuerelemente in einer Datenquelle festgelegt sind, beschränken sie die Verwendung dieser Datenquelle und ihrer Eigenschaften.
* **[!UICONTROL Data Export Labels]**: Sie können Datenexportbeschriftungen für  *Ziele* festlegen. Wenn diese Beschriftungen auf einem Ziel festgelegt werden, wird angegeben, wie das Ziel Daten verwendet. Informationen zum Hinzufügen von Exportbeschriftungen zu einem Ziel finden Sie unter [Hinzufügen Datenexportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md).

Basierend auf den Classifications, die auf eine Datenquelle und ein Ziel angewendet werden, verhindern die Exportsteuerelemente Folgendes:

* Hinzufügen einer Eigenschaft zu einem Segment, wenn die Eigenschaft zu einer Datenquelle mit einer Datenexportsteuerung gehört, die mit einer Datenexportbeschriftung für eines oder mehrere Ziele, denen das Segment zugeordnet ist, nicht kompatibel ist.
Beispiel: Ein Segment wird einem Ziel mit der Exportbezeichnung **[!DNL This destination may enable a combination with personally identifiable information (PII)]** zugeordnet. Exportsteuerelemente verhindern, dass Sie diesem Segment eine Eigenschaft hinzufügen, wenn die Datenquelle, zu der die Eigenschaft gehört, über eine Datenexportsteuerung mit der Bezeichnung **[!DNL Cannot be tied to personally identifiable information (PII)]** verfügt.
* Das Senden von Daten an ein Ziel hat eine Datenexportbeschriftung, die von einem Datenexportsteuerelement blockiert wird für eines der folgenden Elemente:
   * die Datenquelle einer eingeschlossenen Eigenschaft;
   * Die Datenquelle einer Eigenschaft, die in einem eingeschlossenen Segment verwendet wird;
   * Die Profil Merge-Regel, die von einem eingeschlossenen Segment genutzt wird;
   * Eine der Datenquellen, die von der Profil-Zusammenführungsregel eines Segments verwendet werden.

[!UICONTROL Data Export Controls] automatisch für alle Audience Manager verfügbar sind. Sie benötigen jedoch Administratorberechtigungen, um einer Datenquelle Exportsteuerelemente hinzuzufügen. Das Hinzufügen von Exportbeschriftungen zu einem Ziel erfordert Administratorberechtigungen *oder*, die ausreichen, um ein Ziel zu erstellen oder zu bearbeiten.

## Steuerelemente und Beschriftungen definiert {#controls-labels}

[!UICONTROL Data Export Controls] stellen Sie die folgenden Steuerelemente bereit, mit denen Sie Datenquellen und Ziele klassifizieren können.

Um den Versand zu blockieren, müssen Sie eine Datenquelle mit einer Exportsteuerung klassifizieren und eine Exportbeschriftung zu einem Ziel hinzufügen. Wenn Sie Exportsteuerelemente nur auf eine Datenquelle oder ein Ziel anwenden, schränkt diese Funktion den Versand von Daten nicht ein. Wenn dies für das Ziel *und* festgelegt ist, beschränken die Exportsteuerelemente die Eigenschaften, die Sie einem Segment hinzufügen können, und verhindern, dass die Segmentmitglieder an ein Ziel gesendet werden.

Darüber hinaus muss mindestens eine Exportbeschriftung mit einer Exportkontrolle übereinstimmen, bevor Versand-Einschränkungen wirksam werden. Angenommen, Sie fügen einer Datenquelle das Exportsteuerelement [!UICONTROL PII] hinzu. Als Nächstes fügen Sie die Targeting-Bezeichnung auf der Site zu einem Ziel hinzu. In diesem Fall schränken Exportsteuerelemente den Versand von Daten nicht ein, da die Einstellungen nicht übereinstimmen. Wenn Sie jedoch die Exportbezeichnung [!UICONTROL PII] zum Ziel hinzufügen, blockieren die Exportsteuerelemente den Export.

>[!IMPORTANT]
>
>Sie können den Export eines Segments nicht blockieren, indem Sie eine Datenexportkontrolle in der Datenquelle des Segments platzieren. Sie müssen das Steuerelement auf einen der folgenden Schritte festlegen:
> * die Datenquellen der im Segment verwendeten Eigenschaften;
> * Die vom Profil verwendete Segmentzusammenführungsregel;
> * Eine der Datenquellen, die von der Segmentregel zum Zusammenführen von Profilen verwendet wird.


<br>

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datenexportsteuerelemente für eine Datenquelle </th> 
   <th colname="col2" class="entry"> Datenexport-Bezeichnungen für ein Ziel </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Keine Einschränkung</span></b> </td> 
   <td colname="col2"> Keine </td> 
   <td colname="col3"> Standardmäßig werden für neue Datenquellen und Ziele keine Exportbeschränkungen festgelegt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht mit persönlich identifizierbaren Informationen</span></b>  (PII) verknüpft werden </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann eine Kombination mit personenbezogenen Daten (PII) ermöglichen</span></b> </td> 
   <td colname="col3">Bei Auswahl dieser Option ist Folgendes nicht möglich: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">hinzufügen Eigenschaften zu Segmenten, die Zielen zugeordnet sind, die PII verwenden. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Ordnen Sie mit einer Eigenschaft aus der Datenquelle erstellte Segmente Zielen zu, die PII verwenden. </li> 
    </ul> <p>Dies wird häufig von Drittanbietern von Daten und bei der Verwendung von Datenquellen, die Anzeigen-/Medienverfolgungsinformationen enthalten, benötigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für das Targeting von Onsite-Anzeigen verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für Onsite-Anzeigen-Targeting verwendet werden</span></b> </td> 
   <td colname="col3">Bei Auswahl dieser Option ist Folgendes nicht möglich: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">hinzufügen Eigenschaften zu Segmenten, die Zielen zugeordnet sind, die den Versand der Anzeige auf Grundlage des Webbrowserverlaufs eines Besuchers anpassen. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Ordnen Sie mit einer Eigenschaft aus der Datenquelle erstellte Segmente Zielen zu, die den Versand der Anzeige auf Grundlage des Webbrowserverlaufs eines Besuchers anpassen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für Targeting von Offsite-Anzeigen verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für Offsite-Anzeigen-Targeting verwendet werden</span></b> </td> 
   <td colname="col3">Diese Einschränkungen werden im Allgemeinen mit Wenn ausgewählt verwendet. Sie können nicht: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">hinzufügen Eigenschaften zu Segmenten, die Zielen zugeordnet sind, die die Zielgruppe von Benutzern auf anderen Sites wiederherstellen. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die Benutzer auf anderen Sites erneut Zielgruppe. </li> 
    </ul> <p>Wird häufig benötigt, wenn Daten von Social Media-Plattformen verarbeitet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für die Personalisierung vor Ort verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für die Personalisierung von Onsite-Anzeigen verwendet werden</span></b> </td> 
   <td colname="col3">Bei Auswahl dieser Option ist Folgendes nicht möglich: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">hinzufügen Eigenschaften zu Segmenten, die Zielen zugeordnet sind, die Inhalte auf Grundlage der Benutzerinteressen oder des Webbrowserverlaufs anpassen. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die Inhalte basierend auf Benutzerinteressen oder dem Web-Browsing-Verlauf anpassen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Arbeitsablauf{#workflow}

Lesen Sie zunächst die Dokumentation zu Datenquelle und Ziel. Diese Artikel enthalten Anweisungen zum Hinzufügen von Exportsteuerelementen und Beschriftungen zu Ihren Datenquellen und Zielen.

* [Erstellen einer Datenquelle](../features/manage-datasources.md#create-data-source)
* [hinzufügen Datenexportbeschriftungen an ein Ziel](../features/destinations/add-data-export-labels.md)
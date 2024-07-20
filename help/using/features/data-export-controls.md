---
description: Mit der Datenexportkontrolle können Sie verhindern, dass Daten an Ziele gesendet werden, wenn diese Aktion Datenschutz- oder Datennutzungsvereinbarungen verletzt.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Datenexportkontrolle
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: 26aa0a210a045b40b2329844324315a092947188
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Datenexportkontrolle {#data-export-controls}

[!UICONTROL Data Export Controls] verhindert, dass Sie Daten an Ziele senden, wenn diese Aktion Datenschutz- oder Datennutzungsvereinbarungen verletzt.

## Überblick {#overview}

Mit [!UICONTROL Data Export Controls] können Sie [Datenquellen](../features/datasources-list-and-settings.md#data-sources-list-and-settings) und [Ziele](../features/destinations/destinations.md) klassifizieren. Die angewendeten Klassifizierungen bestimmen, wann Daten an ein Ziel exportiert werden können oder nicht. Diese Funktion besteht aus:

* **[!UICONTROL Data Export Controls]**: Sie können Datenexportkontrollen für *Datenquellen* festlegen. Wenn diese Steuerelemente in einer Datenquelle festgelegt sind, beschränken sie die Verwendung dieser Datenquelle und ihrer Eigenschaften.
* **[!UICONTROL Data Export Labels]**: Sie können Datenexportbeschriftungen für *Ziele* festlegen. Wenn diese Beschriftungen für ein Ziel festgelegt werden, erkennen Sie, wie das Ziel Daten verwendet. Informationen zum Hinzufügen von Exportbeschriftungen zu einem Ziel finden Sie unter [Hinzufügen von Datenexportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) .

Basierend auf den Classifications, die auf eine Datenquelle und ein Ziel angewendet werden, verhindern die Exportkontrollen Folgendes:

* Hinzufügen einer Eigenschaft zu einem Segment, wenn die Eigenschaft zu einer Datenquelle gehört, die über eine Datenexportsteuerung verfügt, die mit einer Datenexportbezeichnung für eines oder mehrere der Ziele, denen das Segment zugeordnet ist, nicht kompatibel ist.
Beispiel: Ein Segment ist einem Ziel mit der Exportbezeichnung **[!DNL This destination may enable a combination with personally identifiable information (PII)]** zugeordnet. Exportsteuerelemente hindern Sie daran, diesem Segment eine Eigenschaft hinzuzufügen, wenn die Datenquelle, zu der die Eigenschaft gehört, über ein Datenexportsteuerelement mit dem Wert **[!DNL Cannot be tied to personally identifiable information (PII)]** verfügt.
* Senden von Daten an ein Ziel mit einer Datenexportbeschriftung, die von einer Datenexportkontrolle für Folgendes blockiert wird:
   * Die Datenquelle einer eingeschlossenen Eigenschaft;
   * Die Datenquelle einer Eigenschaft, die in einem eingeschlossenen Segment verwendet wird;
   * Die Profilzusammenführungsrichtlinie, die von einem eingeschlossenen Segment genutzt wird;
   * Jede der Datenquellen, die von der Profilzusammenführungsrichtlinie eines enthaltenen Segments verwendet werden.

[!UICONTROL Data Export Controls] ist automatisch für alle Audience Manager verfügbar. Sie benötigen jedoch Administratorberechtigungen, um einer Datenquelle Exportkontrollen hinzuzufügen. Das Hinzufügen von Exportbeschriftungen zu einem Ziel erfordert Administratorberechtigungen *oder*, die ausreichen, um ein Ziel zu erstellen oder zu bearbeiten.

## Definierte Steuerelemente und Beschriftungen {#controls-labels}

[!UICONTROL Data Export Controls] stellt die folgenden Steuerelemente bereit, mit denen Sie Datenquellen und Ziele klassifizieren können.

Um die Datenbereitstellung zu blockieren, müssen Sie eine Datenquelle mit einer Exportsteuerung klassifizieren und einem Ziel eine Exportbezeichnung hinzufügen. Wenn Sie Exportkontrollen nur auf eine Datenquelle oder ein Ziel anwenden, wird die Datenbereitstellung durch diese Funktion nicht eingeschränkt. Wenn sowohl für das Ziel der Datenquelle *als auch für das Ziel* festgelegt, beschränken die Exportkontrollen die Eigenschaften, die Sie zu einem Segment hinzufügen können, und verhindern das Senden der Segmentmitglieder an ein Ziel.

Darüber hinaus muss mindestens eine Exportbeschriftung mit einer Exportkontrolle übereinstimmen, bevor die Datenbereitstellungsbeschränkungen wirksam werden. Angenommen, Sie fügen einer Datenquelle das Exportsteuerelement [!UICONTROL PII] hinzu. Als Nächstes fügen Sie einem Ziel die Targeting-Bezeichnung auf der Site hinzu. In diesem Fall beschränkt die Exportsteuerung die Datenbereitstellung nicht, da die Einstellungen nicht übereinstimmen. Wenn Sie jedoch die Exportbezeichnung [!UICONTROL PII] zum Ziel hinzufügen, blockieren die Exportkontrollen den Export.

>[!IMPORTANT]
>
>Sie können den Export eines Segments nicht blockieren, indem Sie eine Datenexport-Kontrolle auf die Datenquelle des Segments platzieren. Sie müssen das Steuerelement auf einen der folgenden Schritte festlegen:
> * Die Datenquellen der im Segment verwendeten Eigenschaften;
> * Die vom Segment verwendete Profilzusammenführungsrichtlinie;
> * Jede der Datenquellen, die von der Profilzusammenführungsrichtlinie des Segments verwendet werden.

<br>

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datenexportkontrollen für eine Daten-Source </th> 
   <th colname="col2" class="entry"> Datenexportbeschriftungen für ein Ziel </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Keine Einschränkung</span></b> </td> 
   <td colname="col2"> Keine </td> 
   <td colname="col3"> Standardmäßig sind für neue Datenquellen und Ziele keine Exportbeschränkungen festgelegt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Darf nicht an persönlich identifizierbare Informationen gebunden werden</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann eine Kombination mit persönlich identifizierbaren Informationen (PII) ermöglichen</span></b> </td> 
   <td colname="col3">Bei Aktivierung dieser Option ist Folgendes nicht möglich: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Fügen Sie Eigenschaften zu Segmenten hinzu, die Zielen zugeordnet sind, die PII verwenden. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die PII verwenden. </li> 
    </ul> <p>Dies wird häufig von Datenanbietern von Drittanbietern und bei der Verwendung von Datenquellen benötigt, die Anzeigen-/Medien-Tracking-Informationen enthalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für On-site-Anzeigen-Targeting verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für das Targeting von Onsite-Anzeigen verwendet werden</span></b> </td> 
   <td colname="col3">Bei Aktivierung dieser Option ist Folgendes nicht möglich: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Fügen Sie Eigenschaften zu Segmenten hinzu, die Zielen zugeordnet sind, die die Anzeigenbereitstellung basierend auf dem Webbrowserverlauf eines Besuchers anpassen. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die die Anzeigenbereitstellung basierend auf dem Webbrowserverlauf eines Besuchers anpassen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für Offsite-Anzeigen-Targeting verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für das Targeting von Offsite-Anzeigen verwendet werden</span></b> </td> 
   <td colname="col3">Bei Aktivierung dieser Option ist Folgendes nicht möglich: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Fügen Sie Eigenschaften zu Segmenten hinzu, die Zielen zugeordnet sind, die Benutzer auf anderen Sites erneut ansprechen. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die Benutzer auf anderen Sites erneut ansprechen. </li> 
    </ul> <p>Häufig erforderlich bei der Arbeit mit Daten aus Social-Media-Plattformen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für die Personalisierung auf der Site verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für die Personalisierung von Onsite-Werbeanzeigen verwendet werden</span></b> </td> 
   <td colname="col3">Bei Aktivierung dieser Option ist Folgendes nicht möglich: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Fügen Sie Eigenschaften zu Segmenten hinzu, die Zielen zugeordnet sind, die Inhalt basierend auf Benutzerinteressen oder Webbrowserverlauf anpassen. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die Inhalte basierend auf Benutzerinteressen oder dem Webbrowsing-Verlauf anpassen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Workflow {#workflow}

Lesen Sie zunächst die Dokumentation zur Datenquelle und zum Ziel . Diese Artikel enthalten Anweisungen zum Hinzufügen von Exportsteuerelementen und Beschriftungen zu Ihren Datenquellen und Zielen.

* [Erstellen einer Datenquelle](../features/manage-datasources.md#create-data-source)
* [Hinzufügen von Datenexportbeschriftungen zu einem Ziel](../features/destinations/add-data-export-labels.md)

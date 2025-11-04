---
description: Datenexportsteuerelemente verhindern, dass Sie Daten an Ziele senden, wenn diese Aktion gegen Datenschutz- oder Datennutzungsvereinbarungen verstößt.
seo-description: Data Export Controls prevent you from sending data to destinations when this action violates data privacy or data use agreements.
seo-title: Data Export Controls
solution: Audience Manager
title: Datenexportkontrolle
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
exl-id: 4369c210-bcf1-48cc-a9bb-0d122f6c03d4
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 1%

---

# Datenexportkontrolle {#data-export-controls}

[!UICONTROL Data Export Controls] verhindern, dass Sie Daten an Ziele senden, wenn diese Aktion gegen Datenschutz- oder Datennutzungsvereinbarungen verstößt.

## Überblick {#overview}

[!UICONTROL Data Export Controls] können Sie [Datenquellen“ &#x200B;](../features/datasources-list-and-settings.md#data-sources-list-and-settings) &quot;[&quot; &#x200B;](../features/destinations/destinations.md). Die Klassifizierungen, die Sie anwenden, bestimmen, wann Daten an ein Ziel exportiert werden können oder nicht. Diese Funktion besteht aus:

* **[!UICONTROL Data Export Controls]**: Sie können Datenexportsteuerelemente für (*)*. Wenn diese Steuerelemente für eine Datenquelle festgelegt sind, wird die Verwendung dieser Datenquelle und ihrer Eigenschaften eingeschränkt.
* **[!UICONTROL Data Export Labels]**: Sie können Datenexportbeschriftungen für (*)*. Wenn sie für ein Ziel festgelegt werden, identifizieren diese Kennzeichnungen, wie das Ziel Daten verwendet. Unter [Hinzufügen von Datenexportkennzeichnungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) erfahren Sie, wie Sie einem Ziel Exportkennzeichnungen hinzufügen.

Auf Grundlage der auf eine Datenquelle und ein Ziel angewendeten Klassifizierungen verhindern die Exportsteuerelemente Folgendes:

* Hinzufügen einer Eigenschaft zu einem Segment, wenn die Eigenschaft zu einer Datenquelle gehört, die über ein Datenexportsteuerelement verfügt, das mit einer Datenexportbezeichnung für eines oder mehrere der Ziele, denen das Segment zugeordnet ist, nicht kompatibel ist.
Angenommen, ein Segment wird einem Ziel mit der Exportbezeichnung **[!DNL This destination may enable a combination with personally identifiable information (PII)]** zugeordnet. Exportsteuerelemente verhindern das Hinzufügen einer Eigenschaft zu diesem Segment, wenn die Datenquelle, zu der die Eigenschaft gehört, über ein Datenexportsteuerelement verfügt, das **[!DNL Cannot be tied to personally identifiable information (PII)]** lautet.
* Senden von Daten an ein Ziel mit einer Datenexportkennzeichnung, die durch ein Datenexportsteuerelement in einem der folgenden Elemente blockiert wird:
   * Datenquelle eines eingeschlossenen Merkmals;
   * Die Datenquelle eines Merkmals, das in einem eingeschlossenen Segment verwendet wird;
   * Die Profilzusammenführungsregel, die von einem eingeschlossenen Segment genutzt wird;
   * Jede der Datenquellen, die die Profilzusammenführungsregel eines Segments verwendet.

[!UICONTROL Data Export Controls] sind automatisch für alle Audience Manager-Kunden verfügbar. Sie benötigen jedoch Administratorberechtigungen, um Exportsteuerelemente zu einer Datenquelle hinzuzufügen. Das Hinzufügen von Exportkennzeichnungen zu einem Ziel erfordert Administratorberechtigungen *oder* um ein Ziel zu erstellen oder zu bearbeiten.

## Steuerelemente und Beschriftungen definiert {#controls-labels}

[!UICONTROL Data Export Controls] bieten die folgenden Steuerelemente, mit denen Sie Datenquellen und Ziele klassifizieren können.

Um die Datenbereitstellung zu blockieren, müssen Sie eine Datenquelle mit einer Exportsteuerung klassifizieren und einem Ziel eine Exportkennzeichnung hinzufügen. Wenn Sie Exportsteuerelemente nur auf eine Datenquelle oder ein Ziel anwenden, schränkt diese Funktion die Datenbereitstellung nicht ein. Wenn die Exportsteuerelemente sowohl für die Datenquelle *als auch für* Ziel festgelegt sind, begrenzen sie die Eigenschaften, die Sie einem Segment hinzufügen können, und verhindern das Senden der Segmentmitglieder an ein Ziel.

Darüber hinaus muss mindestens eine Exportkennzeichnung mit einer Exportsteuerung übereinstimmen, damit Datenbereitstellungsbeschränkungen wirksam werden. Angenommen, Sie fügen das [!UICONTROL PII]-Exportsteuerelement einer Datenquelle hinzu. Als Nächstes fügen Sie einem Ziel die Kennzeichnung Targeting auf der Site hinzu. In diesem Fall schränken die Exportsteuerelemente die Datenbereitstellung nicht ein, da die Einstellungen nicht übereinstimmen. Wenn Sie dem Ziel jedoch die [!UICONTROL PII] Exportbeschriftung hinzufügen, blockieren die Exportsteuerelemente den Export.

>[!IMPORTANT]
>
>Sie können den Export eines Segments nicht blockieren, indem Sie ein Datenexportsteuerelement auf der Datenquelle des Segments platzieren. Sie müssen das Steuerelement auf eine der folgenden Optionen festlegen:
>
> * die Datenquellen der im Segment verwendeten Eigenschaften;
> * Die vom Segment verwendete Profilzusammenführungsregel;
> * Jede der Datenquellen, die die Profilzusammenführungsregel des Segments verwendet.

<br>

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Steuerelemente für den Datenexport für eine Data Source </th> 
   <th colname="col2" class="entry"> Datenexport-Kennzeichnungen für ein Ziel </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> keine Einschränkung</span></b> </td> 
   <td colname="col2"> Keine </td> 
   <td colname="col3"> Standardmäßig sind für neue Datenquellen und Ziele keine Exportbeschränkungen festgelegt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> kann nicht mit persönlich identifizierbaren Informationen verknüpft werden</span></b> (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann eine Kombination mit persönlich identifizierbaren Informationen (PII) ermöglichen</span></b> </td> 
   <td colname="col3">Wenn diese Option aktiviert ist, können Sie nicht: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Hinzufügen von Eigenschaften zu Segmenten, die Zielen zugeordnet sind, die personenbezogene Daten verwenden. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die personenbezogene Daten verwenden. </li> 
    </ul> <p>Dies wird häufig von Drittanbietern von Daten und bei der Verwendung von Datenquellen benötigt, die Anzeigen-/Medien-Tracking-Informationen enthalten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für das Targeting von Anzeigen auf der Site verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für das Targeting von Anzeigen auf der Site verwendet werden</span></b> </td> 
   <td colname="col3">Wenn diese Option aktiviert ist, können Sie nicht: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Hinzufügen von Eigenschaften zu Segmenten, die Zielen zugeordnet sind, welche die Anzeigenbereitstellung basierend auf dem Webbrowserverlauf eines Besuchers anpassen. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die die Bereitstellung von Anzeigen basierend auf dem Navigationsverlauf eines Besuchers anpassen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kann nicht für das Targeting von Offsite-Anzeigen verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für das Targeting von Offsite-Anzeigen verwendet werden</span></b> </td> 
   <td colname="col3">Wenn diese Option aktiviert ist, können Sie nicht: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Fügen Sie Segmente, die Zielen zugeordnet sind, Eigenschaften hinzu, um Benutzer auf anderen Sites erneut anzusprechen. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die Benutzer auf anderen Sites erneut ansprechen. </li> 
    </ul> <p>Häufig erforderlich beim Arbeiten mit Daten von Social-Media-Plattformen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> kann nicht für die Personalisierung vor Ort verwendet werden</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Dieses Ziel kann für die Personalisierung von Anzeigen auf der Site verwendet werden</span></b> </td> 
   <td colname="col3">Wenn diese Option aktiviert ist, können Sie nicht: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Fügen Sie Segmenten, die Zielen zugeordnet sind, Eigenschaften hinzu, um Inhalte basierend auf Benutzerinteressen oder dem Verlauf des Webbrowsens anzupassen. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">Ordnen Sie Segmente, die mit einer Eigenschaft aus der Datenquelle erstellt wurden, Zielen zu, die Inhalte basierend auf Benutzerinteressen oder dem Verlauf des Webbrowsens anpassen. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Workflow {#workflow}

Lesen Sie zunächst die Dokumentation zu Datenquelle und Ziel. Diese Artikel enthalten Anweisungen zum Hinzufügen von Exportsteuerelementen und Beschriftungen zu Ihren Datenquellen und Zielen.

* [Erstellen einer Datenquelle](../features/manage-datasources.md#create-data-source)
* [Hinzufügen von Datenexportbeschriftungen zu einem Ziel](../features/destinations/add-data-export-labels.md)

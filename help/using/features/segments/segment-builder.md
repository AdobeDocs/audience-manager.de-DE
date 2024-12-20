---
description: Beschreibt das Erstellen von Segmenten mit Segment Builder.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Segmentaufbau
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Beschreibt die erforderlichen und optionalen Schritte zum Erstellen eines Segments in [!UICONTROL Segment Builder].

## Videodemonstration

Sehen Sie sich zunächst das Video [Erstellen von Segmenten in Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4) an. Das Video führt Sie durch den Prozess der Segmenterstellung. Weitere Informationen finden Sie in den folgenden Abschnitten.

## Erstellen eines [!UICONTROL Segment] {#create-segment}

### Segment Builder-Abschnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] besteht aus drei separaten Abschnitten: [!UICONTROL Basic Information], [!UICONTROL Traits] und [!UICONTROL Destinations Mapping]. Um einen [!UICONTROL segment] zu erstellen, füllen Sie die erforderlichen Felder in den Abschnitten [!UICONTROL Basic Information] und [!UICONTROL Traits] aus. [!UICONTROL Destinations Mapping] sind optional. Weitere Informationen finden Sie in der nachstehenden Anweisung.

1. Im Abschnitt [Grundlegende Informationen](../../features/segments/segment-builder.md#segment-builder-controls-basics):

   ![create-segment](assets/create-segment.png)

   * Benennen Sie die [!UICONTROL segment]. Ein [!UICONTROL segment] darf maximal 255 Zeichen lang sein.
   * Legen Sie den [!UICONTROL segment] fest (aktiv ist der Standard).
   * Wählen Sie eine [!UICONTROL data source]. Verwenden Sie das erste Dropdown-Menü, um zwischen Audience Manager [!UICONTROL data sources], Adobe Analytics Report Suites oder beiden zu filtern. Wählen Sie dann im zweiten Dropdown-Menü Ihre [!UICONTROL data source] aus. Wenn Sie keine Adobe Analytics Report Suites verwenden, ist die [!UICONTROL data source] deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen festgelegt.
   * Wählen Sie ein [!UICONTROL profile merge rule] für die [!UICONTROL segment] aus.
   * Weisen Sie die [!UICONTROL segment] einem Speicherordner zu.

1. Im Abschnitt [Eigenschaften](../../features/segments/segment-builder.md#segment-builder-controls-traits):
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Suchen Sie nach der [!UICONTROL trait], die Sie einem Segment hinzufügen möchten, und klicken Sie auf **[!UICONTROL Add Trait]**. Fügen Sie eine weitere [!UICONTROL trait] hinzu, um eine [!UICONTROL trait] zu erstellen.
   * Rufen Sie das [!UICONTROL Advanced Search] Modal durch Klicken auf **[!UICONTROL Browse All Traits]** auf. Nach [!UICONTROL traits] nach Name, ID, Beschreibung oder [!UICONTROL data source] suchen. Klicken Sie auf einen Ordner, während Sie suchen, um die Ergebnisse auf diesen Ordner und dessen Unterordner zu beschränken. Sie können [!UICONTROL traits] auch nach [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] und [!UICONTROL Algorithmic]) oder Populationstyp ([Geräte-ID](../../reference/ids-in-aam.md) und [Geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern.
     ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Erhalten Sie [ beim ](trait-recommendations.md) Ihrer [!UICONTROL segment] Live-Eigenschaftsempfehlungen.
   * Klicken und ziehen Sie [!UICONTROL traits], um separate Gruppen zu erstellen.
   * Bewegen Sie den Mauszeiger zwischen Gruppen, um Beziehungen mit booleschen [!UICONTROL AND]-, [!UICONTROL OR]- [!UICONTROL AND NOT] festzulegen.
   * Bewegen Sie den Mauszeiger über das Uhrensymbol, um dem [!UICONTROL trait] Regeln [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md) hinzuzufügen.
   * Zeigen Sie Segmentpopulationsdaten an, während Sie [!UICONTROL traits] hinzufügen oder entfernen. Klicken Sie auf **[!UICONTROL Calculate Estimates]** , um die geschätzten Populationen anzuzeigen (oder zu aktualisieren). Weitere Informationen zu [Segmentpopulationsdaten](../../features/segments/segment-builder-data.md#segment-populations) finden Sie in der [!UICONTROL Segment Builder].
   * Klicken Sie abschließend auf **[!UICONTROL Save]** .

1. *(Optional)* Ordnen Sie eine [!UICONTROL segment] einem [!UICONTROL destination] im Abschnitt [Zielzuordnung](../../features/segments/segment-builder.md#segment-builder-controls-destinations) zu:
   * Suchen Sie nach dem [!UICONTROL destination] und klicken Sie auf **[!UICONTROL Add Destination]**. Beachten Sie, dass die [!UICONTROL destination] bereits vorhanden sein muss, bevor Sie sie einem [!UICONTROL segment] hinzufügen können.
   * Klicken Sie abschließend auf **[!UICONTROL Save]** .

Sehen Sie sich das folgende Video an, um einen detaillierten Überblick über die Funktionsweise geräteübergreifender Metriken zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder]: Abschnitt [!UICONTROL Basic Information] {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder] können Sie mit [!UICONTROL the Basic Information] Einstellungen neue Eigenschaften erstellen oder vorhandene bearbeiten. Um einen neuen [!UICONTROL segment] zu erstellen, geben Sie einen Namen und einen [!UICONTROL data source] an und wählen Sie einen Speicherordner aus. Alle anderen Felder sind optional. Fahren Sie abschließend mit dem Abschnitt [!UICONTROL Traits] fort.

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| Feld | Beschreibung |
---------|----------
| **[!UICONTROL Name]** | Geben Sie dem Segment einen kurzen, logischen Namen, der seine Funktion oder seinen Zweck beschreibt. Vermeiden Sie Abkürzungen und Sonderzeichen. Die maximale Länge eines Segmentnamens beträgt 255 Zeichen. |
| **[!UICONTROL Description]** | Ein Feld für zusätzliche beschreibende Informationen zum Segment. |
| **[!UICONTROL Integration Code]** | Ein Feld für eine benutzerdefinierte ID oder andere unternehmensspezifische Informationen. |
| **[!UICONTROL Data Source]** | Ordnet das Segment einem bestimmten Datenanbieter zu. <br> Verwenden Sie das erste Dropdown-Menü, um zwischen Audience Manager-Datenquellen, Adobe Analytics Report Suites oder beidem zu filtern. Wählen Sie dann im zweiten Dropdown-Menü Ihre Datenquelle aus. <br> Wenn Sie Adobe Analytics Report Suites nicht verwenden, ist die Datenquellentyp-Auswahl deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen festgelegt. |
| **[!UICONTROL Profile Merge Rule]** | Wählt die für die Segmentqualifikation zu verwendende Profilzusammenführungsregel aus. |
| **[!UICONTROL Status]** | Aktiviert oder deaktiviert das Segment (standardmäßig aktiv). |
| **Ordnerspeicher** | Bestimmt, zu welchem Speicherordner das Segment gehört. |

## [!UICONTROL Segment Builder]: Abschnitt [!UICONTROL Traits] {#segment-builder-controls-traits}

Im [!UICONTROL Segment Builder] Abschnitt [!UICONTROL Traits] können Sie [!UICONTROL traits] in einer [!UICONTROL segment] verwalten, [!UICONTROL trait] Gruppen erstellen und Qualifizierungskriterien festlegen. Um einen [!UICONTROL trait] zu einem [!UICONTROL segment] hinzuzufügen, geben Sie den [!UICONTROL trait] in das Suchfeld ein und klicken Sie auf [!UICONTROL Add Trait]. Speichern Sie die [!UICONTROL trait] (falls fertig) oder gehen Sie zu [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Voraussetzungen:** Füllen Sie die erforderlichen Felder im Abschnitt [!UICONTROL Basic Information] aus.

| Feld | Beschreibung |
|--- |--- |
| **[!UICONTROL Basic View]** | Dieser Abschnitt enthält visuelle Steuerelemente, mit denen Sie: <ul><li>Erstellen Sie neue und verwalten Sie vorhandene [!UICONTROL segments].</li><li>Entfernen von [!UICONTROL traits] aus einer [!UICONTROL segment].</li><li>Bis zu 50 (maximal) [!UICONTROL traits] zu einer [!UICONTROL segment] hinzufügen.</li><li>Drag-and-Drop [!UICONTROL traits], um neue Gruppen zu erstellen.</li><li>Anzeigen von [!UICONTROL traits]- und [!UICONTROL trait] in einer [!UICONTROL segment].</li><li>Legen Sie Qualifizierungskriterien mit booleschen Ausdrücken, Vergleichsoperatoren und Einstellungen für Neuigkeit/Häufigkeit fest.</li></ul> |
| **[!UICONTROL Code View]** | Öffnet eine Entwicklungsumgebung, in der Sie [!UICONTROL traits], Gruppen und Qualifizierungsanforderungen mit Code anstelle der visuellen Benutzeroberfläche erstellen und verwalten können. Die Code-Ansicht ist nützlich, wenn Ihre [!UICONTROL segments]: <ul><li>Enthält mehr als 50 [!UICONTROL traits] in einem einzelnen [!UICONTROL segment]. Hinweis: [!UICONTROL Segments] sind auf maximal 5.000 [!UICONTROL traits] begrenzt.</li><li>enthalten viele [!UICONTROL trait].</li><li>Komplexe Qualifikationsanforderungen haben.</li></ul> |
| Durchsuchen | Hilft Ihnen bei der Suche nach [!UICONTROL traits] zum Hinzufügen zu einer [!UICONTROL segment]. |
| Empfehlungen | Erhalten Sie Live-Empfehlungen für ähnliche [!UICONTROL traits] von Ihren Erstanbieter-[!UICONTROL traits] und [!UICONTROL Audience Marketplace] Daten-Feeds, die Sie abonniert haben. Fügen Sie diese Empfehlungen zur [!UICONTROL segment] hinzu, um Ihre Audience zu erweitern. Weitere Informationen finden Sie unter [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Erhalten Sie Live-Empfehlungen für ähnliche [!UICONTROL traits] aus [!UICONTROL Audience Marketplace] Daten-Feeds, die Sie nicht abonniert haben. Weitere Informationen finden Sie unter [Trait Recommendations](trait-recommendations.md). |
| Tatsächliche und geschätzte [!UICONTROL Segment] | Siehe [Eigenschafts- und Segmentpopulationsdaten in Segment Builder](segment-builder-data.md). |

## Entfernen von [!UICONTROL Traits] aus einer [!UICONTROL Segment] {#remove-traits}

Die Verwaltung der [!UICONTROL traits] in Ihrer [!UICONTROL segments] ist ein wichtiger Bestandteil für die Aufrechterhaltung der [!UICONTROL segments]. Führen Sie die folgenden Schritte aus, wenn Sie [!UICONTROL traits] aus einer [!UICONTROL segment] entfernen müssen.

So entfernen Sie [!UICONTROL traits] aus einer [!UICONTROL segment]:

1. Gehe zu **[!UICONTROL Audience Data > Segments]**. Scrollen Sie durch die Liste oder verwenden Sie die Suchfunktion, um die [!UICONTROL segment] zu finden, mit der Sie arbeiten möchten.
2. Klicken Sie auf den [!UICONTROL segment], um den Bildschirm [!UICONTROL segment] zu öffnen.
3. Klicken Sie **Bearbeiten**, um [!UICONTROL Segment Builder] zu öffnen, und klicken Sie dann auf **Eigenschaften**, um das [!UICONTROL traits] zu öffnen.
4. Bewegen Sie den Mauszeiger über die [!UICONTROL trait], die Sie löschen möchten, und klicken Sie dann auf das X. Durch diese Aktion wird die [!UICONTROL trait] sofort aus Ihrer [!UICONTROL segment] entfernt.

## [!UICONTROL Segment Builder]: Abschnitt [!UICONTROL Destinations Mappings] {#segment-builder-controls-destinations}

[!UICONTROL Segment Builder] können Sie im optionalen [!UICONTROL Destinations Mapping]-Abschnitt [!UICONTROL segment] Daten an [!DNL cookie], [!DNL URL] oder [!UICONTROL server-to-server destination] von Drittanbietern senden. Um einen [!UICONTROL destination] hinzuzufügen, suchen (oder durchsuchen) Sie nach einem [!UICONTROL destination], geben Sie [!UICONTROL destination] Informationen ein und klicken Sie auf **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Voraussetzungen

Füllen Sie die erforderlichen Felder in den Abschnitten [!UICONTROL Basic Information] und [!UICONTROL Traits] aus. Außerdem muss das Ziel bereits vorhanden sein.

### [!UICONTROL Destination Mappings] Suchtools

Das **[!UICONTROL Destination Mappings]** enthält Suchwerkzeuge, wie in der folgenden Tabelle beschrieben.

| Suchtyp | Beschreibung |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Ermöglicht die Suche nach einem bestimmten [!UICONTROL destination] anhand des Namens. Zum Suchen beginnen Sie zu tippen. Das Feld wird basierend auf Ihren Suchbegriffen automatisch ausgefüllt. Klicken Sie abschließend auf **[!UICONTROL Add Destination]** . |
| **[!UICONTROL Browse All Destinations]** | Durchsuchen Sie eine Liste *alle* für Sie verfügbaren [!UICONTROL destinations]. Wählen Sie [!UICONTROL destinations] aus der Popup-Liste aus und fügen Sie sie zu Ihrer [!UICONTROL segment] hinzu. |

## Felder in den [!UICONTROL Destination Mappings] Popup-Fenstern {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder] wird das Dialogfeld [!UICONTROL Add Destination] angezeigt, nachdem Sie eine [!UICONTROL destination] ausgewählt haben. In diesem Fenster werden statische Informationen zu den [!UICONTROL destination] und Feldern angezeigt, die je nach [!UICONTROL destination] variieren. Geben Sie die erforderlichen Informationen in die leeren Felder ein, um ein [!UICONTROL destination mapping] einzurichten.

>[!NOTE]
>
>Veröffentlichungstermine sind optional. Wenn dies leer ist, wird das Ziel aktiv und läuft nie ab.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Felder

Geben Sie in den [!UICONTROL Destination Mapping] die Schlüssel-Wert-Paare an, die zum Senden von Daten an die [!UICONTROL destination] verwendet werden sollen. Geben Sie den Schlüssel im ersten Feld und die Werte im zweiten Feld ein. Ihr [!UICONTROL cookie destination] könnte in etwa wie folgt aussehen:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Felder

Geben Sie in den Feldern [!UICONTROL URL] und [!UICONTROL Secure URL] die vollständige standardmäßige oder sichere Adresse an, die zum Senden von Daten an den [!UICONTROL destination] verwendet wird.

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Felder

Geben Sie im Feld [!UICONTROL Destination Value] den Wert (Teil eines Schlüssel-Wert-Paares) an, der zum Senden von Daten an die [!UICONTROL destination] verwendet werden soll.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Erstellen eines Cookie-Ziels](../../features/destinations/create-cookie-destination.md)
>* [Erstellen eines URL-Ziels](../../features/destinations/create-url-destination.md)

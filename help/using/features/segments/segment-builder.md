---
description: Beschreibt das Erstellen von Segmenten mit Segment Builder.
seo-description: Beschreibt das Erstellen von Segmenten mit Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Segment Builder
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: 'Segmente '
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Beschreibt die erforderlichen und optionalen Schritte zum Erstellen eines Segments in [!UICONTROL Segment Builder].

## Videodemonstration

Sehen Sie sich zunächst das Video [Segmente im Audience Manager erstellen](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4) an. Das Video führt Sie durch den Prozess der Segmenterstellung. Weitere Informationen finden Sie in den folgenden Abschnitten.

## Erstellen Sie eine [!UICONTROL Segment] {#create-segment}

### Segment Builder-Abschnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] besteht aus 3 getrennten Abschnitten:  [!UICONTROL Basic Information],  [!UICONTROL Traits]und  [!UICONTROL Destinations Mapping]. Um [!UICONTROL segment] zu erstellen, füllen Sie die erforderlichen Felder in den Abschnitten [!UICONTROL Basic Information] und [!UICONTROL Traits] aus. [!UICONTROL Destinations Mapping] -Einstellungen sind optional. Weitere Hilfe finden Sie in den unten stehenden Anweisungen.

1. Im Abschnitt [Grundlegende Informationen](../../features/segments/segment-builder.md#segment-builder-controls-basics) :

   ![create-segment](assets/create-segment.png)

   * Benennen Sie [!UICONTROL segment]. Die maximale Länge eines Namens [!UICONTROL segment] beträgt 255 Zeichen.
   * Den Status [!UICONTROL segment] festlegen (standardmäßig aktiv).
   * Wählen Sie eine [!UICONTROL data source]. Verwenden Sie das erste Dropdown-Menü, um zwischen Audience Manager [!UICONTROL data sources], Adobe Analytics Report Suites oder beidem zu filtern. Wählen Sie dann im zweiten Dropdown-Menü [!UICONTROL data source] aus. Wenn Sie keine Adobe Analytics Report Suites verwenden, ist die Typauswahl vom Typ [!UICONTROL data source] deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen festgelegt.
   * Wählen Sie eine [!UICONTROL profile merge rule] für die [!UICONTROL segment]-Qualifizierung aus.
   * Weisen Sie [!UICONTROL segment] einem Speicherordner zu.

1. Im Abschnitt [Eigenschaften](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Suchen Sie nach dem [!UICONTROL trait], den Sie einem Segment hinzufügen möchten, und klicken Sie auf **[!UICONTROL Add Trait]**. Fügen Sie ein weiteres [!UICONTROL trait] hinzu, um eine [!UICONTROL trait] -Gruppe zu erstellen.
   * Rufen Sie das Modal [!UICONTROL Advanced Search] auf, indem Sie auf **[!UICONTROL Browse All Traits]** klicken. Suchen Sie nach [!UICONTROL traits] nach Name, ID, Beschreibung oder [!UICONTROL data source]. Klicken Sie auf einen Ordner, während Sie suchen, um die Ergebnisse auf diesen Ordner und dessen Unterordner zu beschränken. Sie können [!UICONTROL traits] auch nach [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] und [!UICONTROL Algorithmic]) oder Populationstyp ([Geräte-ID](../../reference/ids-in-aam.md) und [Geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern.
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Rufen Sie [Eigenschaftsempfehlungen](trait-recommendations.md) auf, während Sie [!UICONTROL segment] erstellen.
   * Klicken und ziehen Sie [!UICONTROL traits] , um separate Gruppen zu erstellen.
   * Bewegen Sie den Mauszeiger zwischen Gruppen, um Beziehungen mit booleschen [!UICONTROL AND]-, [!UICONTROL OR]-, [!UICONTROL AND NOT]-Werten festzulegen.
   * Bewegen Sie den Mauszeiger über das Uhrensymbol, um [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md) der [!UICONTROL trait]-Regel hinzuzufügen.
   * Zeigen Sie die Populationsdaten des Segments beim Hinzufügen oder Entfernen von [!UICONTROL traits] an. Klicken Sie auf **[!UICONTROL Calculate Estimates]** , um die geschätzten Populationszahlen anzuzeigen (oder zu aktualisieren). Weitere Informationen zu [Segmentpopulationsdaten](../../features/segments/segment-builder-data.md#segment-populations) finden Sie in der [!UICONTROL Segment Builder].
   * Klicken Sie abschließend auf **[!UICONTROL Save]** .

1. *(Optional)* Ordnen Sie eine  [!UICONTROL segment] zu einer  [!UICONTROL destination] im Abschnitt  [Zielzuordnung ](../../features/segments/segment-builder.md#segment-builder-controls-destinations) zu:
   * Suchen Sie nach [!UICONTROL destination] und klicken Sie auf **[!UICONTROL Add Destination]**. Beachten Sie, dass [!UICONTROL destination] bereits vorhanden sein muss, bevor Sie sie zu einem [!UICONTROL segment] hinzufügen können.
   * Klicken Sie abschließend auf **[!UICONTROL Save]** .

Sehen Sie sich das Video unten an, um sich ausführlich anzusehen, wie geräteübergreifende Metriken funktionieren.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Steuerelemente:  [!UICONTROL Basic Information] Abschnitt  {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder] können Sie mit den Einstellungen [!UICONTROL the Basic Information] neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. Um einen neuen [!UICONTROL segment] zu erstellen, geben Sie einen Namen ein, einen [!UICONTROL data source] und wählen Sie einen Speicherordner aus. Alle anderen Felder sind optional. Wechseln Sie nach Abschluss zum Abschnitt [!UICONTROL Traits] .

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
| **[!UICONTROL Name]** | Geben Sie dem Segment einen kurzen logischen Namen, der seine Funktion oder seinen Zweck beschreibt. Vermeiden Sie Abkürzungen und Sonderzeichen. Die maximale Länge eines Segmentnamens beträgt 255 Zeichen. |
| **[!UICONTROL Description]** | Ein Feld für zusätzliche beschreibende Informationen zum Segment. |
| **[!UICONTROL Integration Code]** | Ein Feld für eine benutzerdefinierte ID oder andere unternehmensspezifische Informationen. |
| **[!UICONTROL Data Source]** | Verbindet das Segment mit einem bestimmten Datenanbieter. <br> Verwenden Sie das erste Dropdown-Menü, um zwischen Audience Manager-Datenquellen, Adobe Analytics-Report Suites oder beidem zu filtern. Wählen Sie dann im zweiten Dropdown-Menü Ihre Datenquelle aus. <br> Wenn Sie keine Adobe Analytics Report Suites verwenden, ist die Datenquellenauswahl deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen festgelegt. |
| **[!UICONTROL Profile Merge Rule]** | Wählt die Profilzusammenführungsrichtlinie aus, die für die Segmentqualifizierung verwendet werden soll. |
| **[!UICONTROL Status]** | Aktiviert oder deaktiviert das Segment (standardmäßig aktiv). |
| **Ordnerspeicher** | Bestimmt, zu welchem Speicherordner das Segment gehört. |

## [!UICONTROL Segment Builder] Steuerelemente:  [!UICONTROL Traits] Abschnitt  {#segment-builder-controls-traits}

Im Abschnitt [!UICONTROL Segment Builder] können Sie [!UICONTROL Traits] im Bereich [!UICONTROL traits] verwalten, [!UICONTROL segment] Gruppen erstellen und Qualifizierungskriterien festlegen. [!UICONTROL trait] Um [!UICONTROL trait] zu einem [!UICONTROL segment] hinzuzufügen, geben Sie den Namen [!UICONTROL trait] in das Suchfeld ein und klicken Sie auf [!UICONTROL Add Trait]. Speichern Sie [!UICONTROL trait] (falls fertig) oder wechseln Sie zu [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Voraussetzungen:** Füllen Sie die erforderlichen Felder im  [!UICONTROL Basic Information] Abschnitt aus.

| Feld | Beschreibung |
|--- |--- |
| **[!UICONTROL Basic View]** | Dieser Abschnitt enthält visuelle Steuerelemente, mit denen Sie: <ul><li>Erstellen Sie neue und verwalten Sie vorhandene [!UICONTROL segments].</li><li>Entfernen Sie [!UICONTROL traits] aus einem [!UICONTROL segment].</li><li>Fügen Sie bis zu 50 (maximal) [!UICONTROL traits] zu einem [!UICONTROL segment] hinzu.</li><li>Ziehen Sie [!UICONTROL traits] in den Arbeitsbereich, um neue Gruppen zu erstellen.</li><li>Zeigen Sie [!UICONTROL traits] und [!UICONTROL trait] Gruppen in einer [!UICONTROL segment] an.</li><li>Legen Sie Qualifizierungskriterien mit booleschen Ausdrücken, Vergleichsoperatoren und Einstellungen für Neuigkeit/Häufigkeit fest.</li></ul> |
| **[!UICONTROL Code View]** | Öffnet eine Entwicklungsumgebung, in der Sie [!UICONTROL traits], Gruppen und Qualifizierungsanforderungen mit Code anstelle der visuellen Benutzeroberfläche erstellen und verwalten können. Die Codeansicht ist nützlich, wenn Sie [!UICONTROL segments]: <ul><li>Sie enthalten mehr als 50 [!UICONTROL traits] in einer Person [!UICONTROL segment]. Hinweis: [!UICONTROL Segments] sind auf 5000 [!UICONTROL traits] (maximal) begrenzt.</li><li>Enthält viele [!UICONTROL trait] Gruppen.</li><li>komplexe Qualifizierungsanforderungen erfüllen.</li></ul> |
| Durchsuchen | Hilft Ihnen, [!UICONTROL traits] zu finden, um sie einem [!UICONTROL segment] hinzuzufügen. |
| Empfehlungen | Rufen Sie Live-Empfehlungen für ähnliche [!UICONTROL traits] von Ihren Erstanbieter-Datenfeeds [!UICONTROL traits] und [!UICONTROL Audience Marketplace] ab, die Sie abonniert haben. Fügen Sie diese Empfehlungen zur Regel [!UICONTROL segment] hinzu, um Ihre Zielgruppe zu erweitern. Weitere Informationen finden Sie unter [Eigenschaft Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Rufen Sie Live-Empfehlungen für ähnliche [!UICONTROL traits] von [!UICONTROL Audience Marketplace]-Daten-Feeds ab, für die Sie kein Abonnement haben. Weitere Informationen finden Sie unter [Eigenschaft Recommendations](trait-recommendations.md). |
| Reale und geschätzte [!UICONTROL Segment] Größendaten | Siehe [Eigenschafts- und Segmentpopulationsdaten in Segment Builder](segment-builder-data.md). |

## Entfernen Sie [!UICONTROL Traits] aus einem [!UICONTROL Segment] {#remove-traits}

Die Verwaltung von [!UICONTROL traits] in [!UICONTROL segments] ist ein wichtiger Teil der Funktionsfähigkeit von [!UICONTROL segments]. Führen Sie diese Schritte aus, wenn Sie [!UICONTROL traits] aus einem [!UICONTROL segment] entfernen müssen.

So entfernen Sie [!UICONTROL traits] aus einem [!UICONTROL segment]:

1. Gehen Sie zu **[!UICONTROL Audience Data > Segments]**. Scrollen Sie durch die Liste oder verwenden Sie die Suchfunktion, um die [!UICONTROL segment] zu finden, mit der Sie arbeiten möchten.
2. Klicken Sie auf den Namen [!UICONTROL segment] , um den Detailbildschirm [!UICONTROL segment] zu öffnen.
3. Klicken Sie auf **Bearbeiten**, um [!UICONTROL Segment Builder] zu öffnen, und klicken Sie dann auf **Eigenschaften**, um das Bedienfeld [!UICONTROL traits] zu öffnen.
4. Bewegen Sie den Mauszeiger über das zu löschende [!UICONTROL trait] und klicken Sie auf das X. Dadurch wird das [!UICONTROL trait] sofort aus Ihrem [!UICONTROL segment] entfernt.

## [!UICONTROL Segment Builder] Steuerelemente:  [!UICONTROL Destinations Mappings] Abschnitt  {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder] können Sie im optionalen Abschnitt [!UICONTROL Destinations Mapping] [!UICONTROL segment] Daten an einen Drittanbieter [!DNL cookie], [!DNL URL] oder [!UICONTROL server-to-server destination] senden. Um [!UICONTROL destination] hinzuzufügen, suchen (oder durchsuchen) Sie nach einem [!UICONTROL destination], geben Sie [!UICONTROL destination] spezifische Informationen ein und klicken Sie auf **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Voraussetzungen

Füllen Sie die erforderlichen Felder in den Abschnitten [!UICONTROL Basic Information] und [!UICONTROL Traits] aus. Außerdem muss das Ziel bereits vorhanden sein.

### [!UICONTROL Destination Mappings] Suchwerkzeuge

Der Bereich **[!UICONTROL Destination Mappings]** enthält Suchwerkzeuge, wie in der folgenden Tabelle beschrieben.

| Suchtyp | Beschreibung |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Ermöglicht die Suche nach einem bestimmten [!UICONTROL destination] nach Namen. Beginnen Sie mit der Eingabe, um zu suchen. Das Feld wird basierend auf Ihren Suchbegriffen automatisch ausgefüllt. Klicken Sie abschließend auf **[!UICONTROL Add Destination]** . |
| **[!UICONTROL Browse All Destinations]** | Durchsuchen Sie eine Liste von *all* [!UICONTROL destinations], die Ihnen zur Verfügung stehen. Wählen Sie [!UICONTROL destinations] aus und fügen Sie [!UICONTROL segment] aus der Popup-Liste zu Ihrem  hinzu. |

## Felder im Popup-Fenster {#fields-in-dest-mappings}[!UICONTROL Destination Mappings]

In [!UICONTROL Segment Builder] wird das Dialogfeld [!UICONTROL Add Destination] angezeigt, nachdem Sie ein [!UICONTROL destination] ausgewählt haben. In diesem Fenster werden statische Informationen zu den Feldern [!UICONTROL destination] und angezeigt, die je nach Typ [!UICONTROL destination] variieren. Geben Sie die erforderlichen Informationen in die leeren Felder ein, um [!UICONTROL destination mapping] einzurichten.

>[!NOTE]
>
>Veröffentlichungsdaten sind optional. Wenn das Feld leer ist, wird das Ziel aktiv und läuft nie ab.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Felder

Geben Sie in den Feldern [!UICONTROL Destination Mapping] die Schlüssel-Wert-Paare an, die zum Senden von Daten an [!UICONTROL destination] verwendet werden. Geben Sie im ersten Feld den Schlüssel und im zweiten den Wert ein. Ihr [!UICONTROL cookie destination]-Pop könnte in etwa wie folgt aussehen:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Felder

Geben Sie in den Feldern [!UICONTROL URL] und [!UICONTROL Secure URL] die vollständige Standard- oder sichere Adresse an, die zum Senden von Daten an [!UICONTROL destination] verwendet wird.

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Felder

Geben Sie im Feld [!UICONTROL Destination Value] den Wert (Teil eines Schlüssel-Wert-Paares) an, der zum Senden von Daten an [!UICONTROL destination] verwendet wird.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Erstellen eines Cookie-Ziels](../../features/destinations/create-cookie-destination.md)
* [Erstellen eines URL-Ziels](../../features/destinations/create-url-destination.md)


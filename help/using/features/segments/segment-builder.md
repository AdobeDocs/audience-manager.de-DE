---
description: Beschreibt das Erstellen von Segmenten mit dem Segmentaufbau.
seo-description: Beschreibt das Erstellen von Segmenten mit dem Segmentaufbau.
seo-title: Segment Builder
solution: Audience Manager
title: Segmentaufbau
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: 'Segmente '
translation-type: tm+mt
source-git-commit: 9e0c936ba514e517bcbd7572420118293f9a791f
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 2%

---


# [!UICONTROL Segment Builder] {#segment-builder}

Beschreibt die erforderlichen und optionalen Schritte zum Erstellen eines Segments in [!UICONTROL Segment Builder].

## Videodemonstration

Beginn durch Anzeigen des Videos [Segmente in Audience Manager erstellen](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). Das Video führt Sie durch den Prozess der Segmenterstellung. Lesen Sie die folgenden Abschnitte für weitere Informationen.

## Erstellen Sie eine [!UICONTROL Segment] {#create-segment}

### Segmentaufbauabschnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] besteht aus 3 getrennten Abschnitten:  [!UICONTROL Basic Information],  [!UICONTROL Traits]und  [!UICONTROL Destinations Mapping]. Um ein [!UICONTROL segment] zu erstellen, füllen Sie die erforderlichen Felder in den Abschnitten [!UICONTROL Basic Information] und [!UICONTROL Traits] aus. [!UICONTROL Destinations Mapping] sind optional. Weitere Hilfe finden Sie in den unten stehenden Anweisungen.

1. Im Abschnitt [Grundlegende Informationen](../../features/segments/segment-builder.md#segment-builder-controls-basics):

   ![create-segment](assets/create-segment.png)

   * Benennen Sie [!UICONTROL segment]. Die maximale Länge eines [!UICONTROL segment]-Namens beträgt 255 Zeichen.
   * Legen Sie den Status [!UICONTROL segment] fest (aktiv ist der Standard).
   * Wählen Sie ein [!UICONTROL data source]. Verwenden Sie das erste Dropdown-Menü, um zwischen Audience Manager [!UICONTROL data sources], Adobe Analytics Report Suites oder beiden zu filtern. Wählen Sie dann im zweiten Dropdown-Menü Ihr [!UICONTROL data source] aus. Wenn Sie keine Adobe Analytics Report Suites verwenden, ist die Typauswahl [!UICONTROL data source] deaktiviert und standardmäßig nur Audience Manager-Datenquellen.
   * Wählen Sie ein [!UICONTROL profile merge rule] aus, das für die [!UICONTROL segment]-Qualifizierung verwendet werden soll.
   * Weisen Sie das [!UICONTROL segment] einem Ordner &quot;Datenspeicherung&quot;zu.

1. Im Abschnitt [Eigenschaften](../../features/segments/segment-builder.md#segment-builder-controls-traits):
   ![segment-builder-properties](assets/segment-builder-traits.png)
   * Suchen Sie nach dem [!UICONTROL trait], das Sie einem Segment hinzufügen möchten, und klicken Sie auf **[!UICONTROL Add Trait]**. hinzufügen Sie eine weitere [!UICONTROL trait]-Gruppe, um eine [!UICONTROL trait]-Gruppe zu erstellen.
   * Rufen Sie das Modal [!UICONTROL Advanced Search] auf, indem Sie auf **[!UICONTROL Browse All Traits]** klicken. Suchen Sie nach [!UICONTROL traits] nach Name, ID, Beschreibung oder [!UICONTROL data source]. Klicken Sie auf einen Ordner, während Sie suchen, um die Ergebnisse auf diesen Ordner und dessen Unterordner zu beschränken. Sie können [!UICONTROL traits] auch nach [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] und [!UICONTROL Algorithmic]) oder Populationstyp ([Geräte-ID](../../reference/ids-in-aam.md) und [Geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern.
      ![segment-builder-browser-properties](assets/segment-builder-browse-traits.png)
   * Holen Sie sich live [Empfehlungen für Eigenschaften](trait-recommendations.md), während Sie [!UICONTROL segment] erstellen.
   * Klicken und ziehen Sie [!UICONTROL traits], um separate Gruppen zu erstellen.
   * Bewegen Sie den Mauszeiger über Gruppen, um Beziehungen mit booleschen [!UICONTROL AND]-, [!UICONTROL OR]-, [!UICONTROL AND NOT]-Werten festzulegen.
   * Bewegen Sie den Mauszeiger über das Uhrensymbol, um [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md)-Regeln zu [!UICONTROL trait] hinzuzufügen.
   * Populationsdaten für Segmentgruppen beim Hinzufügen oder Entfernen von [!UICONTROL traits]. Klicken Sie auf **[!UICONTROL Calculate Estimates]**, um die geschätzten Populationszahlen anzuzeigen (oder zu aktualisieren). Lesen Sie mehr über [Segmentpopulationsdaten](../../features/segments/segment-builder-data.md#segment-populations) in der [!UICONTROL Segment Builder].
   * Klicken Sie abschließend auf **[!UICONTROL Save]**.

1. *(Optional)* Ordnen Sie  [!UICONTROL segment] einem Element  [!UICONTROL destination] im Abschnitt  [Zielzuordnung einen ](../../features/segments/segment-builder.md#segment-builder-controls-destinations) zu:
   * Suchen Sie nach dem [!UICONTROL destination] und klicken Sie auf **[!UICONTROL Add Destination]**. Beachten Sie, dass das [!UICONTROL destination] bereits vorhanden sein muss, bevor Sie es zu einem [!UICONTROL segment] hinzufügen können.
   * Klicken Sie abschließend auf **[!UICONTROL Save]**.

Sehen Sie sich das unten stehende Video an, um einen detaillierten Überblick über die Funktionsweise geräteübergreifender Metriken zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Steuerelemente:  [!UICONTROL Basic Information] Abschnitt  {#segment-builder-controls-basics}

Mit den [!UICONTROL Segment Builder]-Einstellungen können Sie neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. [!UICONTROL the Basic Information] Um ein neues [!UICONTROL segment] zu erstellen, geben Sie einen Namen, ein [!UICONTROL data source] ein und wählen Sie einen Datenspeicherung-Ordner aus. Alle anderen Felder sind optional. Wechseln Sie nach Abschluss zum Abschnitt [!UICONTROL Traits].

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
| **[!UICONTROL Description]** | Ein Feld für weitere beschreibende Informationen zum Segment. |
| **[!UICONTROL Integration Code]** | Ein Feld für eine benutzerdefinierte ID oder andere Firma-spezifische Informationen. |
| **[!UICONTROL Data Source]** | Verbindet das Segment mit einem bestimmten Datenanbieter. <br> Verwenden Sie das erste Dropdownmenü, um zwischen Audience Manager-Datenquellen, Adobe Analytics-Report Suites oder beiden zu filtern. Wählen Sie dann im zweiten Dropdownmenü die Datenquelle aus. <br> Wenn Sie keine Adobe Analytics Report Suites verwenden, ist die Datenquellenauswahl deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen eingestellt. |
| **[!UICONTROL Profile Merge Rule]** | Wählt die Profil Merge Rule aus, die für die Segmentqualifizierung verwendet werden soll. |
| **[!UICONTROL Status]** | Aktiviert oder deaktiviert das Segment (standardmäßig aktiv). |
| **Datenspeicherung von Ordnern** | Legt fest, zu welcher Datenspeicherung das Segment gehört. |

## [!UICONTROL Segment Builder] Steuerelemente:  [!UICONTROL Traits] Abschnitt  {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder] können Sie im Abschnitt [!UICONTROL Traits] [!UICONTROL traits] in einem [!UICONTROL segment] verwalten, [!UICONTROL trait]-Gruppen erstellen und Qualifizierungskriterien festlegen. Um einem [!UICONTROL segment] einen [!UICONTROL trait] hinzuzufügen, geben Sie den [!UICONTROL trait]-Namen in das Suchfeld ein und klicken Sie auf [!UICONTROL Add Trait]. Speichern Sie [!UICONTROL trait] (falls fertig) oder gehen Sie zu [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Voraussetzungen:** Füllen Sie die erforderlichen Felder im  [!UICONTROL Basic Information] Abschnitt aus.

| Feld | Beschreibung |
|--- |--- |
| **[!UICONTROL Basic View]** | Dieser Abschnitt enthält visuelle Steuerelemente, mit denen Sie: <ul><li>Erstellen Sie neue und verwalten Sie vorhandene [!UICONTROL segments].</li><li>Entfernen Sie [!UICONTROL traits] von einem [!UICONTROL segment].</li><li>hinzufügen bis zu 50 (maximal) [!UICONTROL traits] bis zu einem [!UICONTROL segment].</li><li>Ziehen Sie [!UICONTROL traits] per Drag &amp; Drop, um neue Gruppen zu erstellen.</li><li>Gruppen der Ansichten [!UICONTROL traits] und [!UICONTROL trait] in [!UICONTROL segment].</li><li>Legen Sie Qualifizierungskriterien mit booleschen Ausdrücken, Vergleichsoperatoren und Neuigkeits-/Häufigkeitseinstellungen fest.</li></ul> |
| **[!UICONTROL Code View]** | Öffnet eine Entwicklungs-Umgebung, mit der Sie [!UICONTROL traits]-, Gruppen- und Qualifizierungsanforderungen mit Code anstelle der visuellen Schnittstelle erstellen und verwalten können. Die Code-Ansicht ist nützlich, wenn Sie [!UICONTROL segments]: <ul><li>Enthält mehr als 50 [!UICONTROL traits] in einer einzelnen [!UICONTROL segment]. Hinweis: [!UICONTROL Segments] sind auf 5000 [!UICONTROL traits] (maximal) begrenzt.</li><li>Enthält viele [!UICONTROL trait]-Gruppen.</li><li>Halten Sie komplexe Qualifikationsanforderungen ein.</li></ul> |
| Durchsuchen | Hilft Ihnen, [!UICONTROL traits] zu einer [!UICONTROL segment] hinzuzufügen. |
| Empfehlungen | Rufen Sie Live-Empfehlungen für ähnliche [!UICONTROL traits]-Datenfeeds von Ihren Erstanbietern [!UICONTROL traits] und [!UICONTROL Audience Marketplace] ab, die Sie abonniert haben. hinzufügen Sie diese Empfehlungen an die [!UICONTROL segment]-Regel, um Ihre Audience zu erweitern. Lesen Sie mehr unter [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Rufen Sie Live-Empfehlungen für ähnliche [!UICONTROL traits]-Datenfeeds ab, die Sie nicht abonniert haben. [!UICONTROL Audience Marketplace] Lesen Sie mehr unter [Trait Recommendations](trait-recommendations.md). |
| Richtige und geschätzte [!UICONTROL Segment]-Größendaten | Siehe [Eigenschafts- und Segmentpopulationsdaten in Segment Builder](segment-builder-data.md). |

## [!UICONTROL Traits] von einem [!UICONTROL Segment] {#remove-traits} entfernen

Die Verwaltung von [!UICONTROL traits] in Ihrer [!UICONTROL segments] ist ein wichtiger Aspekt, um [!UICONTROL segments] funktionsfähig zu halten. Führen Sie diese Schritte aus, wenn Sie [!UICONTROL traits] aus einem [!UICONTROL segment] entfernen müssen.

So entfernen Sie [!UICONTROL traits] aus einem [!UICONTROL segment]:

1. Gehen Sie zu **[!UICONTROL Audience Data > Segments]**. Blättern Sie durch die Liste oder verwenden Sie die Suchfunktion, um das [!UICONTROL segment] zu finden, mit dem Sie arbeiten möchten.
2. Klicken Sie auf den Namen [!UICONTROL segment], um den Detailbildschirm [!UICONTROL segment] zu öffnen.
3. Klicken Sie auf **Bearbeiten**, um [!UICONTROL Segment Builder] zu öffnen, und klicken Sie dann auf **Eigenschaften**, um das Bedienfeld [!UICONTROL traits] zu öffnen.
4. Bewegen Sie den Mauszeiger über das [!UICONTROL trait], das Sie löschen möchten, und klicken Sie dann auf das X. Durch diese Aktion wird das [!UICONTROL trait] sofort aus dem [!UICONTROL segment] entfernt.

## [!UICONTROL Segment Builder] Steuerelemente:  [!UICONTROL Destinations Mappings] Abschnitt  {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder] können Sie im optionalen Abschnitt [!UICONTROL Destinations Mapping] [!UICONTROL segment] Daten an einen Drittanbieter [!DNL cookie], [!DNL URL] oder [!UICONTROL server-to-server destination] senden. Um ein [!UICONTROL destination] hinzuzufügen, suchen (oder suchen) Sie nach einem [!UICONTROL destination], geben Sie [!UICONTROL destination] spezifische Informationen ein und klicken Sie auf **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Voraussetzungen

Füllen Sie die erforderlichen Felder in den Abschnitten [!UICONTROL Basic Information] und [!UICONTROL Traits] aus. Außerdem muss das Ziel bereits vorhanden sein.

### [!UICONTROL Destination Mappings] Suchwerkzeuge

Das Bedienfeld **[!UICONTROL Destination Mappings]** enthält Suchwerkzeuge, wie in der unten stehenden Tabelle beschrieben.

| Suchtyp | Beschreibung |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Ermöglicht die Suche nach einem bestimmten [!UICONTROL destination]-Namen. Zur Suche geben Sie Beginn ein. Das Feld wird basierend auf Ihren Suchbegriffen automatisch ausgefüllt. Klicken Sie abschließend auf **[!UICONTROL Add Destination]**. |
| **[!UICONTROL Browse All Destinations]** | Durchsuchen Sie eine Liste von *all* [!UICONTROL destinations], die Ihnen zur Verfügung steht. Wählen Sie [!UICONTROL destinations] aus und fügen Sie [!UICONTROL segment] aus der Popup-Liste hinzu. |

## Felder im Popup-Fenster {#fields-in-dest-mappings}[!UICONTROL Destination Mappings]

In [!UICONTROL Segment Builder] wird das [!UICONTROL Add Destination]-Dialogfeld angezeigt, nachdem Sie ein [!UICONTROL destination] ausgewählt haben. In diesem Fenster werden statische Informationen zum Typ [!UICONTROL destination] und zu Feldern angezeigt, die je nach Typ [!UICONTROL destination] variieren. Geben Sie die erforderlichen Informationen in den leeren Feldern ein, um ein [!UICONTROL destination mapping] einzurichten.

>[!NOTE]
>
>Veröffentlichungsdaten sind optional. Wenn das Feld leer ist, wird das Ziel aktiv und läuft nie ab.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Felder

Geben Sie in den Feldern [!UICONTROL Destination Mapping] die Schlüssel-Wert-Paare an, die zum Senden von Daten an das [!UICONTROL destination] verwendet werden. Geben Sie den Schlüssel im ersten Feld und die Werte im zweiten ein. Ihr [!UICONTROL cookie destination]-Pop könnte wie folgt aussehen:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Felder

Geben Sie in den Feldern [!UICONTROL URL] und [!UICONTROL Secure URL] die vollständige Standard- oder sichere Adresse ein, die zum Senden von Daten an das [!UICONTROL destination] verwendet wird.

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Felder

Geben Sie im Feld [!UICONTROL Destination Value] den Wert (Teil eines Schlüssel-Wert-Paars) an, mit dem Daten an das [!UICONTROL destination] gesendet werden.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Cookie-Ziel erstellen](../../features/destinations/create-cookie-destination.md)
>* [URL-Ziel erstellen](../../features/destinations/create-url-destination.md)


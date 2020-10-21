---
description: Beschreibt das Erstellen von Segmenten mit dem Segmentaufbau.
seo-description: Beschreibt das Erstellen von Segmenten mit dem Segmentaufbau.
seo-title: Segment Builder
solution: Audience Manager
title: Segment Builder
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 2%

---


# [!UICONTROL Segment Builder] {#segment-builder}

Beschreibt die erforderlichen und optionalen Schritte zum Erstellen eines Segments in [!UICONTROL Segment Builder].

## Videodemonstration

Beginn durch Anzeigen des Videos zum [Erstellen von Segmenten in Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). Das Video führt Sie durch den Prozess der Segmenterstellung. Lesen Sie die folgenden Abschnitte für weitere Informationen.

## Erstellen Sie eine [!UICONTROL Segment] {#create-segment}

### Segmentaufbauabschnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] besteht aus 3 getrennten Abschnitten: [!UICONTROL Basic Information], [!UICONTROL Traits]und [!UICONTROL Destinations Mapping]. Füllen Sie zum Erstellen eines [!UICONTROL segment]Felds die erforderlichen Felder in den Abschnitten [!UICONTROL Basic Information] und [!UICONTROL Traits] aus. [!UICONTROL Destinations Mapping] sind optional. Weitere Hilfe finden Sie in den unten stehenden Anweisungen.

1. Im Abschnitt [Grundlegende Informationen](../../features/segments/segment-builder.md#segment-builder-controls-basics) :

   ![create-segment](assets/create-segment.png)

   * Benennen Sie die [!UICONTROL segment]. Die maximale Länge eines [!UICONTROL segment] Namens beträgt 255 Zeichen.
   * Legen Sie den [!UICONTROL segment] Status fest (aktiv ist der Standard).
   * Wählen Sie eine [!UICONTROL data source]. Verwenden Sie das erste Dropdownmenü, um zwischen Audience Manager [!UICONTROL data sources], Adobe Analytics Report Suites oder beiden zu filtern. Wählen Sie dann im zweiten Dropdown-Menü Ihre [!UICONTROL data source]Auswahl aus. Wenn Sie keine Adobe Analytics Report Suites verwenden, ist die [!UICONTROL data source] Typauswahl deaktiviert und standardmäßig nur Audience Manager-Datenquellen.
   * Wählen Sie eine [!UICONTROL profile merge rule] zu verwendende [!UICONTROL segment] Qualifikation aus.
   * Weisen Sie den Ordner [!UICONTROL segment] einem Datenspeicherung zu.

1. Im Abschnitt [Eigenschaften](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-properties](assets/segment-builder-traits.png)
   * Suchen Sie nach dem Segment, das [!UICONTROL trait] Sie einem Segment hinzufügen möchten, und klicken Sie auf **[!UICONTROL Add Trait]**. hinzufügen einer anderen [!UICONTROL trait] zum Erstellen einer [!UICONTROL trait] Gruppe.
   * Rufen Sie das [!UICONTROL Advanced Search] Modal auf, indem Sie auf **[!UICONTROL Browse All Traits]**. Suchen Sie nach [!UICONTROL traits] Name, ID, Beschreibung oder [!UICONTROL data source]. Klicken Sie auf einen Ordner, während Sie suchen, um die Ergebnisse auf diesen Ordner und dessen Unterordner zu beschränken. Sie können auch nach [!UICONTROL traits] Typ [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]und [!UICONTROL Algorithmic]) oder Population ([Geräte-ID](../../reference/ids-in-aam.md) und [geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern.
      ![segment-builder-browser-properties](assets/segment-builder-browse-traits.png)
   * Hier erhalten Sie Empfehlungen [zu den Eigenschaften](trait-recommendations.md) , die Sie beim Erstellen Ihrer [!UICONTROL segment]Website verwenden.
   * Klicken und ziehen Sie, [!UICONTROL traits] um separate Gruppen zu erstellen.
   * Bewegen Sie den Mauszeiger über Gruppen, um Beziehungen zu booleschen [!UICONTROL AND], [!UICONTROL OR]und [!UICONTROL AND NOT] Werten festzulegen.
   * Bewegen Sie den Mauszeiger über das Uhrensymbol, um [Neuigkeits- und Häufigkeitsregeln](../../features/segments/recency-and-frequency.md) zum [!UICONTROL trait]Symbol hinzuzufügen.
   * Populationsdaten für Segmentgruppen beim Hinzufügen oder Entfernen [!UICONTROL traits]. Klicken Sie auf **[!UICONTROL Calculate Estimates]** , um die geschätzten Populationszahlen anzuzeigen (oder zu aktualisieren). Mehr über [Segmentpopulationsdaten](../../features/segments/segment-builder-data.md#segment-populations) im [!UICONTROL Segment Builder].
   * Klicken Sie **[!UICONTROL Save]** nach Abschluss des Vorgangs auf .

1. *(Optional)* Ordnen Sie einem [!UICONTROL segment] im Abschnitt &quot; [!UICONTROL destination] Zielzuordnung [](../../features/segments/segment-builder.md#segment-builder-controls-destinations) &quot;eine Zuordnung zu:
   * Suchen Sie nach dem [!UICONTROL destination] und klicken Sie auf **[!UICONTROL Add Destination]**. Beachten Sie, dass die [!UICONTROL destination] muss bereits vorhanden sein, bevor Sie sie zu einer [!UICONTROL segment]hinzufügen können.
   * Klicken Sie **[!UICONTROL Save]** nach Abschluss des Vorgangs auf .

Sehen Sie sich das unten stehende Video an, um einen detaillierten Überblick über die Funktionsweise geräteübergreifender Metriken zu erhalten.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## [!UICONTROL Segment Builder] Steuerelemente: [!UICONTROL Basic Information] Abschnitt {#segment-builder-controls-basics}

Mit [!UICONTROL Segment Builder]den [!UICONTROL the Basic Information] Einstellungen können Sie neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. Um eine neue Datenspeicherung zu erstellen, geben Sie einen Namen, einen [!UICONTROL segment][!UICONTROL data source]und einen Ordner ein. Alle anderen Felder sind optional. Gehen Sie nach Abschluss zum [!UICONTROL Traits] Abschnitt.

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

## [!UICONTROL Segment Builder] Steuerelemente: [!UICONTROL Traits] Abschnitt {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder]diesem Abschnitt können Sie [!UICONTROL Traits] in einem [!UICONTROL traits] Abschnitt verwalten, [!UICONTROL segment][!UICONTROL trait] Gruppen erstellen und Qualifizierungskriterien festlegen. Um einer [!UICONTROL trait] zu einer Suchmaschine hinzuzufügen, geben Sie [!UICONTROL segment]den [!UICONTROL trait] Namen in das Suchfeld ein und klicken Sie auf [!UICONTROL Add Trait]. Speichern Sie die Datei [!UICONTROL trait] (falls fertig) oder wechseln Sie zu [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Voraussetzungen:** Füllen Sie die erforderlichen Felder im [!UICONTROL Basic Information] Abschnitt aus.

| Feld | Beschreibung |
|--- |--- |
| **[!UICONTROL Basic View]** | Dieser Abschnitt enthält visuelle Steuerelemente, mit denen Sie: <ul><li>Erstellen Sie neue und verwalten Sie bestehende [!UICONTROL segments].</li><li>Entfernen Sie [!UICONTROL traits] eine [!UICONTROL segment].</li><li>hinzufügen bis zu 50 (maximal) [!UICONTROL traits] bis zu einer [!UICONTROL segment].</li><li>Ziehen Sie per Drag &amp; Drop [!UICONTROL traits] neue Gruppen.</li><li>Ansicht [!UICONTROL traits] und [!UICONTROL trait] Gruppen in einem [!UICONTROL segment].</li><li>Legen Sie Qualifizierungskriterien mit booleschen Ausdrücken, Vergleichsoperatoren und Neuigkeits-/Häufigkeitseinstellungen fest.</li></ul> |
| **[!UICONTROL Code View]** | Öffnet eine Entwicklungs-Umgebung, mit der Sie mit Code anstelle der visuellen Benutzeroberfläche [!UICONTROL traits]Gruppen- und Qualifikationsanforderungen erstellen und verwalten können. Die Code-Ansicht ist hilfreich, wenn Sie [!UICONTROL segments]: <ul><li>Enthält mehr als 50 [!UICONTROL traits] in einer Person [!UICONTROL segment]. Hinweis: [!UICONTROL Segments] maximal 5000 [!UICONTROL traits] (maximal).</li><li>Enthält viele [!UICONTROL trait] Gruppen.</li><li>Halten Sie komplexe Qualifikationsanforderungen ein.</li></ul> |
| Durchsuchen | Hilft Ihnen [!UICONTROL traits] zu einer [!UICONTROL segment]hinzuzufügen. |
| Empfehlungen | Hier erhalten Sie Live-Empfehlungen für ähnliche Dienste [!UICONTROL traits]von Ihren Erstanbieter- [!UICONTROL traits] und [!UICONTROL Audience Marketplace] Datenfeeds, die Sie abonniert haben. hinzufügen Sie diese Empfehlungen an die [!UICONTROL segment] Regel, um Ihre Audience zu erweitern. Mehr darüber in [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Rufen Sie Live-Empfehlungen für ähnliche Dienste [!UICONTROL traits]aus [!UICONTROL Audience Marketplace] Datenfeeds ab, die Sie nicht abonniert haben. Mehr darüber in [Trait Recommendations](trait-recommendations.md). |
| Daten zur tatsächlichen und geschätzten [!UICONTROL Segment] Größe | Siehe [Eigenschafts- und Segmentpopulationsdaten in Segment Builder](segment-builder-data.md). |

## Entfernen [!UICONTROL Traits] von [!UICONTROL Segment] {#remove-traits}

Die Verwaltung der [!UICONTROL traits] in Ihrer [!UICONTROL segments] ist ein wichtiger Teil der [!UICONTROL segments] Lebensfähigkeit. Führen Sie die folgenden Schritte aus, wenn Sie [!UICONTROL traits] aus einem [!UICONTROL segment]Element entfernen müssen.

So entfernen Sie [!UICONTROL traits] aus einem [!UICONTROL segment]:

1. Geh zu **[!UICONTROL Audience Data > Segments]**. Blättern Sie durch die Liste oder verwenden Sie die Suchfunktion, um die zu [!UICONTROL segment] finden, mit der Sie arbeiten möchten.
2. Klicken Sie auf den [!UICONTROL segment] Namen, um den [!UICONTROL segment] Detailbildschirm zu öffnen.
3. Klicken Sie auf **Bearbeiten** , um das Fenster zu öffnen, [!UICONTROL Segment Builder] und klicken Sie dann auf **Eigenschaften** , um das [!UICONTROL traits] Fenster zu öffnen.
4. Bewegen Sie den Mauszeiger über den zu [!UICONTROL trait] löschenden Inhalt und klicken Sie dann auf das X. Durch diese Aktion wird die [!UICONTROL trait] Datei sofort aus Ihrem System entfernt [!UICONTROL segment].

## [!UICONTROL Segment Builder] Steuerelemente: [!UICONTROL Destinations Mappings] Abschnitt {#segment-builder-controls-destinations}

Im [!UICONTROL Segment Builder]optionalen [!UICONTROL Destinations Mapping] Abschnitt können Sie [!UICONTROL segment] Daten an einen Drittanbieter [!DNL cookie], [!DNL URL]oder [!UICONTROL server-to-server destination]an einen Drittanbieter senden. Um eine [!UICONTROL destination]Datei hinzuzufügen, suchen (oder suchen) Sie nach einer [!UICONTROL destination]Datei, geben Sie [!UICONTROL destination] spezifische Informationen ein und klicken Sie auf **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Voraussetzungen

Füllen Sie die erforderlichen Felder in den [!UICONTROL Basic Information] Abschnitten und [!UICONTROL Traits] Abschnitten aus. Außerdem muss das Ziel bereits vorhanden sein.

### [!UICONTROL Destination Mappings] Suchwerkzeuge

Das **[!UICONTROL Destination Mappings]** Bedienfeld enthält Suchwerkzeuge, wie in der unten stehenden Tabelle beschrieben.

| Suchtyp | Beschreibung |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Ermöglicht die Suche nach einem bestimmten [!UICONTROL destination] Namen. Zur Suche geben Sie Beginn ein. Das Feld wird basierend auf Ihren Suchbegriffen automatisch ausgefüllt. Klicken Sie **[!UICONTROL Add Destination]** nach Abschluss des Vorgangs auf . |
| **[!UICONTROL Browse All Destinations]** | Durchsuchen Sie eine Liste *aller* verfügbaren Elemente [!UICONTROL destinations] . Wählen Sie [!UICONTROL destinations] aus der Popup-Liste aus und fügen Sie sie [!UICONTROL segment] hinzu. |

## Felder im [!UICONTROL Destination Mappings] Popup-Fenster {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder]wird das [!UICONTROL Add Destination] Dialogfeld angezeigt, nachdem Sie eine [!UICONTROL destination]Auswahl getroffen haben. In diesem Fenster werden statische Informationen zu den Feldern [!UICONTROL destination] und Feldern angezeigt, die je nach [!UICONTROL destination] Typ variieren. Geben Sie die erforderlichen Informationen in den leeren Feldern ein, um eine [!UICONTROL destination mapping]zu erstellen.

>[!NOTE]
>
>Veröffentlichungsdaten sind optional. Wenn das Feld leer ist, wird das Ziel aktiv und läuft nie ab.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Felder

Geben Sie in den [!UICONTROL Destination Mapping] Feldern die Schlüssel-Wert-Paare an, die zum Senden von Daten an die [!UICONTROL destination]Variable verwendet werden. Geben Sie den Schlüssel im ersten Feld und die Werte im zweiten ein. Ihr [!UICONTROL cookie destination] Pop könnte wie folgt aussehen:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Felder

Geben Sie in den Feldern [!UICONTROL URL] und [!UICONTROL Secure URL] die vollständige Standard- oder sichere Adresse ein, die zum Senden der Daten an die [!UICONTROL destination]Adresse verwendet wird.

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Felder

Geben Sie im [!UICONTROL Destination Value] Feld den Wert (Teil eines Schlüssel-Wert-Paars) an, mit dem Daten an den [!UICONTROL destination]Benutzer gesendet werden.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Cookie-Ziel erstellen](../../features/destinations/create-cookie-destination.md)
>* [URL-Ziel erstellen](../../features/destinations/create-url-destination.md)


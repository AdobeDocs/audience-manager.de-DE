---
description: Beschreibt, wie Segmente mit Segmentaufbau erstellt werden.
seo-description: Beschreibt, wie Segmente mit Segmentaufbau erstellt werden.
seo-title: Segmentaufbau
solution: Audience Manager
title: Segmentaufbau
uuid: 5 ca 924 a 5-2 b 29-4802-ab 02-e 292 d 77 a 0 aae
translation-type: tm+mt
source-git-commit: b346dbe500f1e662c7b121a18c6cc0704ef3cfac

---


# Segmentaufbau {#segment-builder}

Describes the required and optional steps that create a segment in [!UICONTROL Segment Builder].

## Segment erstellen {#create-segment}

### Segment Builder-Abschnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] besteht aus drei separaten Abschnitten: [!UICONTROL Basic Information][!UICONTROL Traits], und [!UICONTROL Destinations Mapping]. To create a segment, complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. [!UICONTROL Destinations Mapping] Einstellungen optional sind. Weitere Hilfe finden Sie in den unten stehenden Anweisungen.

1. In the [Basic Information](../../features/segments/segment-builder.md#segment-builder-controls-basics) section:
   * Benennen Sie das Segment. Die maximale Länge eines Segmentnamens beträgt 255 Zeichen.
   * Legen Sie den Segmentstatus fest (aktiv ist die Standardeinstellung).
   * Wählen Sie eine Datenquelle aus.
   * Wählen Sie eine Regel zur Profilzusammenführung, die für die Segmentqualifizierung verwendet werden soll.
   * Weisen Sie das Segment einem Speicherordner zu.
1. In the [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) section:
   * Search for the trait you want to add to a segment and click **[!UICONTROL Add Trait]**. Fügen Sie eine weitere Eigenschaft hinzu, um eine Eigenschaftsgruppe zu erstellen.
   * Bring up the Advanced Search modal by clicking **[!UICONTROL Browse All Traits]**. Suchen Sie nach Eigenschaften nach Name, ID, Beschreibung oder Datenquelle. Klicken Sie bei der Suche auf einen Ordner, um die Ergebnisse auf diesen Ordner und dessen Unterordner einzuschränken. Sie können Eigenschaften auch nach Eigenschaften filtern.
   * Get live [trait recommendations](trait-recommendations.md) as you build your segment.
   * Klicken Sie auf Eigenschaften und ziehen Sie sie, um separate Gruppen zu erstellen.
   * Hover between groups to set relationships with Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] values.
   * Hover over the clock icon to add [recency and frequency](../../features/segments/recency-and-frequency.md) rules to the trait.
   * Zeigen Sie Segmentpopulationsdaten an, wenn Sie Eigenschaften hinzufügen oder entfernen. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers. Read more about [segment population data](../../features/segments/segment-builder-data.md#segment-populations) in the Segment Builder.
   * Click **[!UICONTROL Save]** when done.
1. *(Optional)* Ordnen Sie einem Ziel im Abschnitt [Zielzuordnung](../../features/segments/segment-builder.md#segment-builder-controls-destinations) ein Segment zu:
   * Search for the destination and click **[!UICONTROL Add Destination]**. Beachten Sie, dass das Ziel bereits vorhanden ist, bevor Sie es einem Segment hinzufügen können.
   * Click **[!UICONTROL Save]** when done.

## Segment Builder Controls: Basic Information Section {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] settings let you create new, or edit existing traits. Um ein neues Segment zu erstellen, geben Sie einen Namen, eine Datenquelle und einen Speicherordner an. Alle anderen Felder sind optional. Move on to the [!UICONTROL Traits] section when done.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Geben Sie dem Segment einen kurzen, logischen Namen, der seine Funktion oder Ihren Zweck beschreibt. Vermeiden Sie Abkürzungen und Sonderzeichen. Die maximale Länge eines Segmentnamens beträgt 255 Zeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Beschreibung</b> </td> 
   <td colname="col2"> <p>Ein Feld für weitere beschreibende Informationen über das Segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integrationscode</b> </td> 
   <td colname="col2"> <p>Ein Feld für eine benutzerdefinierte ID oder andere unternehmensspezifische Informationen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Datenquelle</b> </td> 
   <td colname="col2"> <p>Verknüpft das Segment mit einem bestimmten Datenanbieter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Regel zum Profilzusammenführen</b> </td> 
   <td colname="col2"> <p>Wählt die Regel zum Profilzusammenführen für die Segmentqualifizierung aus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Aktiviert bzw. deaktiviert das Segment (standardmäßig aktiv). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ordnerspeicher</b> </td> 
   <td colname="col2"> <p>Legt fest, zu welchem Speicherordner das Segment gehört. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment Builder Controls: Traits Section {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], the [!UICONTROL Traits] section lets you manage traits in a segment, create trait groups, and set qualification criteria. To add a trait to a segment, type the trait name in the search field and click [!UICONTROL Add Trait]. Save the trait (if finished) or move on to [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**Voraussetzungen:** Füllen Sie die erforderlichen Felder im [!UICONTROL Basic Information] Abschnitt aus.

| Feld | Beschreibung |
|--- |--- |
| Einfache Ansicht | Dieser Abschnitt enthält visuelle Steuerelemente, mit denen Sie: <ul><li>Erstellen Sie neue Segmente und verwalten Sie vorhandene Segmente.</li><li>Entfernen Sie Eigenschaften aus einem Segment.</li><li>Fügen Sie einem Segment bis zu 50 (maximal) Eigenschaften hinzu.</li><li>Ziehen Sie Eigenschaften, um neue Gruppen zu erstellen.</li><li>Eigenschaften und Trait-Gruppen in einem Segment anzeigen.</li><li>Legen Sie Qualifizierungskriterien mit booleschen Ausdrücken, Vergleichsoperatoren und Neuigkeits-/Häufigkeitseinstellungen fest.</li></ul> |
| Codeansicht | Öffnet eine Entwicklungsumgebung, mit der Sie Eigenschaften, Gruppen und Qualifikationsanforderungen mit Code anstelle der visuellen Benutzeroberfläche erstellen und verwalten können. Die Codeansicht ist hilfreich, wenn Ihre Segmente: <ul><li>Enthält mehr als 50 Eigenschaften in einem einzelnen Segment. Hinweis: Segmente sind auf 5000 Eigenschaften begrenzt (Maximum).</li><li>Enthält viele Trait-Gruppen.</li><li>Über komplexe Qualifikationsanforderungen verfügen.</li></ul> |
| Durchsuchen | Hilft Ihnen bei der Suche nach Eigenschaften, die einem Segment hinzugefügt werden sollen. |
| Empfehlungen | Rufen Sie Live-Empfehlungen für ähnliche Eigenschaften auf, um sie zur Segmentregel hinzuzufügen. Read more in [Trait Recommendations](trait-recommendations.md). |
| Daten zu tatsächlichen und geschätzten Segmentgrößen | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Remove Traits from a Segment {#remove-traits}

Die Verwaltung der Eigenschaften in Ihren Segmenten ist ein wichtiger Aspekt bei der Aktivierung von Segmenten. Führen Sie die folgenden Schritte aus, wenn Sie Eigenschaften aus einem Segment entfernen müssen.

Entfernen von Eigenschaften aus einem Segment

1. Go to **Audience Data &gt; Segments**. Blättern Sie durch die Liste oder verwenden Sie die Suchfunktion, um das Segment zu finden, mit dem Sie arbeiten möchten.
2. Klicken Sie auf den Segmentnamen, um den Bilddetails-Bildschirm zu öffnen.
3. Click **Edit** to open Segment Builder and then click **Traits** to open the traits panel.
4. Bewegen Sie den Mauszeiger über die Eigenschaft, die Sie löschen möchten, und klicken Sie auf das X. Durch diese Aktion wird sofort die Eigenschaft aus Ihrem Segment entfernt.

## Segment Builder Controls: Destinations Mappings Section {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], the optional [!UICONTROL Destinations Mapping] section lets you send segment data to a third-party [!DNL cookie], [!DNL URL], or server-to-server destination. To add a destination, search (or browse) for a destination, provide destination specific information, and click **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Voraussetzungen

Complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. Außerdem muss das Ziel bereits vorhanden sein.

### Suchzuordnungssuchtools

The **[!UICONTROL Destination Mappings]** panel contains search tools as described in the table below.

| Suchtyp | Beschreibung |
|---|---|
| **Suche nach Zielname** | Ermöglicht die Suche nach einem bestimmten Ziel nach Name. Um zu suchen, beginnen Sie mit der Eingabe. Das Feld wird basierend auf Ihren Suchbegriffen automatisch vervollständigt. Click **[!UICONTROL Add Destination]** when done. |
| **Alle Ziele durchsuchen** | Browse a list of *all* destinations available to you. Wählen Sie Ziele aus der Popup-Liste aus und fügen Sie ihr Ziele hinzu. |

## Fields in the Destination Mappings Pop-up Windows {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], the [!UICONTROL Add Destination] dialog appears after you select a destination. Dieses Fenster zeigt statische Informationen über das Ziel und die Felder an, die je nach Zieltyp variieren. Geben Sie die erforderlichen Informationen in den leeren Feldern ein, um eine Zielzuordnung einzurichten.

>[!NOTE]
>
>Veröffentlichungsdaten sind optional. Wenn das Ziel leer ist, wird es aktiv und nie ablaufen.

<!-- r_add_mappings_pop.xml -->

### Cookie-Zielfelder

In the [!UICONTROL Destination Mapping] fields, specify the key-value pairs used to send data to the destination. Geben Sie den Schlüssel im ersten Feld und die Werte in der zweiten ein. Ihr Cookie-Ziel sollte wie folgt aussehen:

![](assets/cookie_modal.PNG)

### URL-Zielfelder

In the [!UICONTROL URL] and [!UICONTROL Secure URL] fields, specify the complete standard or secure address used to send data to the destination.

![](assets/url_modal.PNG)

### Server-zu-Server-Zielfelder

In the [!UICONTROL Destination Value] field specify the value (part of a key-value pair) used to send data to the destination.

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen eines Cookie-Ziels](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [URL-Ziel erstellen](../../features/destinations/manage-destinations.md#configure-url-destination)


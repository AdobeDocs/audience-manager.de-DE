---
description: Beschreibt, wie Segmente mit Segmentaufbau erstellt werden.
seo-description: Beschreibt, wie Segmente mit Segmentaufbau erstellt werden.
seo-title: Segmentaufbau
solution: Audience Manager
title: Segmentaufbau
uuid: 5 ca 924 a 5-2 b 29-4802-ab 02-e 292 d 77 a 0 aae
translation-type: tm+mt
source-git-commit: 2733080505760bbcf39737f0ad0d2d7605d1f477

---


# Segmentaufbau {#segment-builder}

Beschreibt die erforderlichen und optionalen Schritte, die ein Segment erstellen.[!UICONTROL Segment Builder]

## Videodemonstration

Das folgende Video führt Sie durch den Segmenterstellungsprozess. Lesen Sie die folgenden Abschnitte, um weitere Informationen zu erhalten.

>[!VIDEO](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)

## Segment erstellen {#create-segment}

### Segment Builder-Abschnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] besteht aus drei separaten Abschnitten: [!UICONTROL Basic Information][!UICONTROL Traits], und [!UICONTROL Destinations Mapping]. Zum Erstellen eines Segments füllen Sie die erforderlichen Felder in den [!UICONTROL Basic Information] Abschnitten und [!UICONTROL Traits] Abschnitten aus. [!UICONTROL Destinations Mapping] Einstellungen optional sind. Weitere Hilfe finden Sie in den unten stehenden Anweisungen.

1. Im Abschnitt [Grundlegende Informationen](../../features/segments/segment-builder.md#segment-builder-controls-basics) :
   * Benennen Sie das Segment. Die maximale Länge eines Segmentnamens beträgt 255 Zeichen.
   * Legen Sie den Segmentstatus fest (aktiv ist die Standardeinstellung).
   * Wählen Sie eine Datenquelle aus.
   * Wählen Sie eine Regel zur Profilzusammenführung, die für die Segmentqualifizierung verwendet werden soll.
   * Weisen Sie das Segment einem Speicherordner zu.
1. Im Abschnitt [Eigenschaften](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Suchen Sie nach der Eigenschaft, die Sie einem Segment hinzufügen möchten, und klicken **[!UICONTROL Add Trait]** Sie auf. Fügen Sie eine weitere Eigenschaft hinzu, um eine Eigenschaftsgruppe zu erstellen.
   * Rufen Sie die modale Suche auf, indem **[!UICONTROL Browse All Traits]** Sie auf klicken. Suchen Sie nach Eigenschaften nach Name, ID, Beschreibung oder Datenquelle. Klicken Sie bei der Suche auf einen Ordner, um die Ergebnisse auf diesen Ordner und dessen Unterordner einzuschränken. Sie können Eigenschaften auch nach Eigenschaften filtern.
   * Erhalten Sie Empfehlungen für Live [-Eigenschaften, wenn Sie](trait-recommendations.md) Ihr Segment erstellen.
   * Klicken Sie auf Eigenschaften und ziehen Sie sie, um separate Gruppen zu erstellen.
   * Bewegen Sie den Mauszeiger zwischen Gruppen, um Beziehungen mit Boolescher Sprache [!UICONTROL AND]festzulegen, [!UICONTROL OR]Werte [!UICONTROL AND NOT] .
   * Bewegen Sie den Mauszeiger über das Uhrsymbol, um der Eigenschaft [Neuigkeit- und](../../features/segments/recency-and-frequency.md) Häufigkeitsregeln hinzuzufügen.
   * Zeigen Sie Segmentpopulationsdaten an, wenn Sie Eigenschaften hinzufügen oder entfernen. Klicken **[!UICONTROL Calculate Estimates]** Sie auf, um die geschätzten Populationszahlen anzuzeigen (oder zu aktualisieren). Weitere Informationen zu [Segmentpopulationsdaten](../../features/segments/segment-builder-data.md#segment-populations) finden Sie im Segmentaufbau.
   * Click **[!UICONTROL Save]** when done.
1. *(Optional)* Ordnen Sie einem Ziel im Abschnitt [Zielzuordnung](../../features/segments/segment-builder.md#segment-builder-controls-destinations) ein Segment zu:
   * Suchen Sie nach dem Ziel und klicken **[!UICONTROL Add Destination]** Sie auf. Beachten Sie, dass das Ziel bereits vorhanden ist, bevor Sie es einem Segment hinzufügen können.
   * Click **[!UICONTROL Save]** when done.

## Steuerelemente für Segmentaufbau: Abschnitt "Grundinformationen « {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder]können [!UICONTROL the Basic Information] Sie mit Einstellungen neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. Um ein neues Segment zu erstellen, geben Sie einen Namen, eine Datenquelle und einen Speicherordner an. Alle anderen Felder sind optional. Wechseln Sie zum [!UICONTROL Traits] Abschnitt, wenn Sie fertig sind.

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

## Steuerelemente für Segmentaufbau: Abschnitt "Eigenschaften « {#segment-builder-controls-traits}

Im [!UICONTROL Segment Builder][!UICONTROL Traits] Abschnitt können Sie Eigenschaften in einem Segment verwalten, Eigenschaftsgruppen erstellen und Qualifizierungskriterien festlegen. Um einem Segment eine Eigenschaft hinzuzufügen, geben Sie den Eigenschaftsnamen in das Suchfeld ein und klicken [!UICONTROL Add Trait]Sie auf. Speichern Sie die Eigenschaft (falls beendet) oder wechseln Sie zu [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**Voraussetzungen:** Füllen Sie die erforderlichen Felder im [!UICONTROL Basic Information] Abschnitt aus.

| Feld | Beschreibung |
|--- |--- |
| Einfache Ansicht | Dieser Abschnitt enthält visuelle Steuerelemente, mit denen Sie: <ul><li>Erstellen Sie neue Segmente und verwalten Sie vorhandene Segmente.</li><li>Entfernen Sie Eigenschaften aus einem Segment.</li><li>Fügen Sie einem Segment bis zu 50 (maximal) Eigenschaften hinzu.</li><li>Ziehen Sie Eigenschaften, um neue Gruppen zu erstellen.</li><li>Eigenschaften und Trait-Gruppen in einem Segment anzeigen.</li><li>Legen Sie Qualifizierungskriterien mit booleschen Ausdrücken, Vergleichsoperatoren und Neuigkeits-/Häufigkeitseinstellungen fest.</li></ul> |
| Codeansicht | Öffnet eine Entwicklungsumgebung, mit der Sie Eigenschaften, Gruppen und Qualifikationsanforderungen mit Code anstelle der visuellen Benutzeroberfläche erstellen und verwalten können. Die Codeansicht ist hilfreich, wenn Ihre Segmente: <ul><li>Enthält mehr als 50 Eigenschaften in einem einzelnen Segment. Hinweis: Segmente sind auf 5000 Eigenschaften begrenzt (Maximum).</li><li>Enthält viele Trait-Gruppen.</li><li>Über komplexe Qualifikationsanforderungen verfügen.</li></ul> |
| Durchsuchen | Hilft Ihnen bei der Suche nach Eigenschaften, die einem Segment hinzugefügt werden sollen. |
| Empfehlungen | Rufen Sie Live-Empfehlungen für ähnliche Eigenschaften auf, um sie zur Segmentregel hinzuzufügen. Weitere Informationen finden Sie in [Trait Recommendations](trait-recommendations.md). |
| Daten zu tatsächlichen und geschätzten Segmentgrößen | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Eigenschaften aus einem Segment entfernen {#remove-traits}

Die Verwaltung der Eigenschaften in Ihren Segmenten ist ein wichtiger Aspekt bei der Aktivierung von Segmenten. Führen Sie die folgenden Schritte aus, wenn Sie Eigenschaften aus einem Segment entfernen müssen.

Entfernen von Eigenschaften aus einem Segment

1. Gehen Sie zu **Zielgruppendaten &gt; Segmente**. Blättern Sie durch die Liste oder verwenden Sie die Suchfunktion, um das Segment zu finden, mit dem Sie arbeiten möchten.
2. Klicken Sie auf den Segmentnamen, um den Bilddetails-Bildschirm zu öffnen.
3. Klicken Sie auf **Bearbeiten** , um Segmentaufbau zu öffnen, und klicken Sie dann **auf Eigenschaften** , um das Eigenschaftenbedienfeld zu öffnen.
4. Bewegen Sie den Mauszeiger über die Eigenschaft, die Sie löschen möchten, und klicken Sie auf das X. Durch diese Aktion wird sofort die Eigenschaft aus Ihrem Segment entfernt.

## Steuerelemente für Segmentaufbau: Abschnitt "Ziele zuordnungen « {#segment-builder-controls-destinations}

Im [!UICONTROL Segment Builder]optionalen [!UICONTROL Destinations Mapping] Abschnitt können Sie Segmentdaten an einen Drittanbieter [!DNL cookie]oder [!DNL URL]Server-zu-Server-Ziel senden. Um ein Ziel hinzuzufügen, suchen (oder durchsuchen) Sie ein Ziel, geben Sie zielspezifische Informationen an und klicken **[!UICONTROL Add Destination]** Sie auf.

<!-- r_segment_destinations_map.xml -->

### Voraussetzungen

Füllen Sie die erforderlichen Felder in den [!UICONTROL Basic Information] Abschnitten aus [!UICONTROL Traits] . Außerdem muss das Ziel bereits vorhanden sein.

### Suchzuordnungssuchtools

Das **[!UICONTROL Destination Mappings]** Bedienfeld enthält Suchwerkzeuge, wie in der folgenden Tabelle beschrieben.

| Suchtyp | Beschreibung |
|---|---|
| **Suche nach Zielname** | Ermöglicht die Suche nach einem bestimmten Ziel nach Name. Um zu suchen, beginnen Sie mit der Eingabe. Das Feld wird basierend auf Ihren Suchbegriffen automatisch vervollständigt. Click **[!UICONTROL Add Destination]** when done. |
| **Alle Ziele durchsuchen** | Durchsuchen Sie eine Liste aller *für Sie verfügbaren* Ziele. Wählen Sie Ziele aus der Popup-Liste aus und fügen Sie ihr Ziele hinzu. |

## Felder im Popup-Fenster "Zielzuordnungen « {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder]wird das [!UICONTROL Add Destination] Dialogfeld angezeigt, nachdem Sie ein Ziel ausgewählt haben. Dieses Fenster zeigt statische Informationen über das Ziel und die Felder an, die je nach Zieltyp variieren. Geben Sie die erforderlichen Informationen in den leeren Feldern ein, um eine Zielzuordnung einzurichten.

>[!NOTE]
>
>Veröffentlichungsdaten sind optional. Wenn das Ziel leer ist, wird es aktiv und nie ablaufen.

<!-- r_add_mappings_pop.xml -->

### Cookie-Zielfelder

Geben Sie in den [!UICONTROL Destination Mapping] Feldern die Schlüssel/Wert-Paare an, die zum Senden von Daten an das Ziel verwendet werden. Geben Sie den Schlüssel im ersten Feld und die Werte in der zweiten ein. Ihr Cookie-Ziel sollte wie folgt aussehen:

![](assets/cookie_modal.PNG)

### URL-Zielfelder

Geben Sie in [!UICONTROL URL] den Feldern und [!UICONTROL Secure URL] Feldern die vollständige Standardadresse oder sichere Adresse an, mit der Daten an das Ziel gesendet werden.

![](assets/url_modal.PNG)

### Server-zu-Server-Zielfelder

Geben Sie im [!UICONTROL Destination Value] Feld den Wert (Teil eines Schlüssel-Wert-Paars) an, der verwendet wird, um Daten an das Ziel zu senden.

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen eines Cookie-Ziels](../../features/destinations/create-cookie-destination.md)
>* [URL-Ziel erstellen](../../features/destinations/create-url-destination.md)


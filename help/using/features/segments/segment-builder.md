---
description: Beschreibt das Erstellen von Segmenten mit dem Segmentaufbau.
seo-description: Beschreibt das Erstellen von Segmenten mit dem Segmentaufbau.
seo-title: Segmentaufbau
solution: Audience Manager
title: Segmentaufbau
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 0d0806ef2c84b4770adc29d668351ac3f2d8cc5f

---


# Segmentaufbau {#segment-builder}

Beschreibt die erforderlichen und optionalen Schritte zum Erstellen eines Segments in [!UICONTROL Segment Builder].

## Videodemonstration

Beginnen Sie mit dem Anzeigen des Videos["Segmente ](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)erstellen"in Audience Manager. Das Video führt Sie durch den Prozess der Segmenterstellung. Lesen Sie die folgenden Abschnitte für weitere Informationen.

## Segment erstellen {#create-segment}

### Segmentaufbauabschnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] besteht aus 3 getrennten Abschnitten: [!UICONTROL Basic Information], [!UICONTROL Traits]und [!UICONTROL Destinations Mapping]. Um ein Segment zu erstellen, füllen Sie die erforderlichen Felder in den [!UICONTROL Basic Information] und in den [!UICONTROL Traits] Abschnitten aus. [!UICONTROL Destinations Mapping] sind optional. Weitere Hilfe finden Sie in den unten stehenden Anweisungen.

1. Im Abschnitt [Grundlegende Informationen](../../features/segments/segment-builder.md#segment-builder-controls-basics) :
   * Benennen Sie das Segment. Die maximale Länge eines Segmentnamens beträgt 255 Zeichen.
   * Legen Sie den Segmentstatus fest (standardmäßig aktiv).
   * Wählen Sie eine Datenquelle.
   * Wählen Sie eine Regel zur Profilzusammenführung, die für die Segmentqualifizierung verwendet werden soll.
   * Weisen Sie das Segment einem Speicherordner zu.
1. Im Abschnitt [Eigenschaften](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Suchen Sie nach der Eigenschaft, die Sie einem Segment hinzufügen möchten, und klicken Sie auf **[!UICONTROL Add Trait]**. Fügen Sie eine weitere Eigenschaft hinzu, um eine Eigenschaftsgruppe zu erstellen.
   * Rufen Sie das Modal Erweiterte Suche auf, indem Sie auf **[!UICONTROL Browse All Traits]**. Suchen Sie nach Eigenschaften nach Name, ID, Beschreibung oder Datenquelle. Klicken Sie auf einen Ordner, während Sie suchen, um die Ergebnisse auf diesen Ordner und dessen Unterordner zu beschränken. Sie können Eigenschaften auch nach Eigenschaftstyp filtern.
   * Beim Erstellen Ihres Segments erhalten Sie Empfehlungen [zu](trait-recommendations.md) den Live-Eigenschaften.
   * Durch Klicken und Ziehen können Sie verschiedene Gruppen erstellen.
   * Bewegen Sie den Mauszeiger über Gruppen, um Beziehungen zu booleschen [!UICONTROL AND], [!UICONTROL OR]und [!UICONTROL AND NOT] Werten festzulegen.
   * Bewegen Sie den Mauszeiger über das Uhrensymbol, um der Eigenschaft [Neuigkeits- und Häufigkeitsregeln](../../features/segments/recency-and-frequency.md) hinzuzufügen.
   * Zeigen Sie Daten zur Segmentpopulation an, während Sie Eigenschaften hinzufügen oder entfernen. Klicken Sie auf **[!UICONTROL Calculate Estimates]** , um die geschätzten Populationszahlen anzuzeigen (oder zu aktualisieren). Weitere Informationen zu [Segmentpopulationsdaten](../../features/segments/segment-builder-data.md#segment-populations) finden Sie im Segmentaufbau.
   * Click **[!UICONTROL Save]** when done.
1. *(Optional)* Ordnen Sie ein Segment einem Ziel im Abschnitt [Zielzuordnung](../../features/segments/segment-builder.md#segment-builder-controls-destinations) zu:
   * Suchen Sie nach dem Ziel und klicken Sie auf **[!UICONTROL Add Destination]**. Beachten Sie, dass das Ziel bereits vorhanden sein muss, bevor Sie es zu einem Segment hinzufügen können.
   * Click **[!UICONTROL Save]** when done.

## Segmentaufbau-Steuerelemente: Abschnitt "Grundlegende Informationen" {#segment-builder-controls-basics}

Mit [!UICONTROL Segment Builder]den [!UICONTROL the Basic Information] Einstellungen können Sie neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. Um ein neues Segment zu erstellen, geben Sie einen Namen, eine Datenquelle und einen Speicherordner an. Alle anderen Felder sind optional. Gehen Sie nach Abschluss zum [!UICONTROL Traits] Abschnitt.

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
   <td colname="col2"> <p>Geben Sie dem Segment einen kurzen logischen Namen, der seine Funktion oder seinen Zweck beschreibt. Vermeiden Sie Abkürzungen und Sonderzeichen. Die maximale Länge eines Segmentnamens beträgt 255 Zeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Beschreibung</b> </td> 
   <td colname="col2"> <p>Ein Feld für weitere beschreibende Informationen zum Segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integrationscode</b> </td> 
   <td colname="col2"> <p>Ein Feld für eine benutzerdefinierte ID oder andere unternehmensspezifische Informationen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Datenquelle</b> </td> 
   <td colname="col2"> <p>Verbindet das Segment mit einem bestimmten Datenanbieter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Regel zur Profilzusammenführung</b> </td> 
   <td colname="col2"> <p>Wählt die Regel zur Profilzusammenführung aus, die für die Segmentqualifizierung verwendet werden soll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Aktiviert oder deaktiviert das Segment (standardmäßig aktiv). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ordnerspeicher</b> </td> 
   <td colname="col2"> <p>Legt fest, zu welchem Speicherordner das Segment gehört. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentaufbau-Steuerelemente: Eigenschaftenabschnitt {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder][!UICONTROL Traits] diesem Abschnitt können Sie Eigenschaften in einem Segment verwalten, Eigenschaftsgruppen erstellen und Qualifizierungskriterien festlegen. Um einem Segment eine Eigenschaft hinzuzufügen, geben Sie den Eigenschaftsnamen in das Suchfeld ein und klicken Sie auf [!UICONTROL Add Trait]. Speichern Sie die Eigenschaft (sofern fertig) oder wechseln Sie zu [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**** Voraussetzungen: Füllen Sie die erforderlichen Felder im [!UICONTROL Basic Information] Abschnitt aus.

| Feld | Beschreibung |
|--- |--- |
| Grundansicht | Dieser Abschnitt enthält visuelle Steuerelemente, mit denen Sie: <ul><li>Erstellen Sie neue und verwalten Sie vorhandene Segmente.</li><li>Entfernen Sie Eigenschaften aus einem Segment.</li><li>Fügen Sie einem Segment bis zu 50 (maximal) Eigenschaften hinzu.</li><li>Ziehen Sie Eigenschaften per Drag &amp; Drop, um neue Gruppen zu erstellen.</li><li>Zeigen Sie Eigenschaften und Eigenschaftsgruppen in einem Segment an.</li><li>Legen Sie Qualifizierungskriterien mit booleschen Ausdrücken, Vergleichsoperatoren und Einstellungen für Neuigkeit/Häufigkeit fest.</li></ul> |
| Codeansicht | Öffnet eine Entwicklungsumgebung, in der Sie Eigenschaften, Gruppen und Qualifikationsanforderungen mit Code anstelle der visuellen Schnittstelle erstellen und verwalten können. Die Codeansicht ist nützlich, wenn Ihre Segmente: <ul><li>Enthält mehr als 50 Eigenschaften in einem einzelnen Segment. Hinweis: Segmente sind auf maximal 5000 Eigenschaften beschränkt.</li><li>Enthält viele Eigenschaftsgruppen.</li><li>Komplexe Qualifikationsanforderungen</li></ul> |
| Durchsuchen | Hilft Ihnen, Eigenschaften zu finden, die einem Segment hinzugefügt werden sollen. |
| Empfehlungen | Hier finden Sie Live-Empfehlungen für ähnliche Eigenschaften, die Sie der Segmentregel hinzufügen können. Mehr darüber finden Sie unter [Eigenschaftsempfehlungen](trait-recommendations.md). |
| Daten zur tatsächlichen und geschätzten Segmentgröße | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Eigenschaften aus einem Segment entfernen {#remove-traits}

Die Verwaltung der Eigenschaften in Ihren Segmenten ist ein wichtiger Bestandteil der Segmentfunktionalität. Gehen Sie wie folgt vor, wenn Sie Eigenschaften aus einem Segment entfernen müssen.

So entfernen Sie Eigenschaften aus einem Segment:

1. Gehen Sie zu **Zielgruppendaten &gt; Segmente**. Blättern Sie durch die Liste oder verwenden Sie die Suchfunktion, um das Segment zu finden, mit dem Sie arbeiten möchten.
2. Klicken Sie auf den Segmentnamen, um den Bildschirm mit den Segmentdetails zu öffnen.
3. Klicken Sie auf **Bearbeiten** , um den Segmentaufbau zu öffnen, und klicken Sie dann auf **Eigenschaften** , um das Eigenschaftenbedienfeld zu öffnen.
4. Bewegen Sie den Mauszeiger über die Eigenschaft, die Sie löschen möchten, und klicken Sie dann auf das X. Durch diese Aktion wird die Eigenschaft sofort aus Ihrem Segment entfernt.

## Segmentaufbau-Steuerelemente: Zuordnungsabschnitt für Ziele {#segment-builder-controls-destinations}

Im [!UICONTROL Segment Builder]Abschnitt "Optional"können Sie [!UICONTROL Destinations Mapping] Segmentdaten an ein Drittanbieter-, [!DNL cookie]Server- [!DNL URL]oder Server-zu-Server-Ziel senden. Um ein Ziel hinzuzufügen, suchen (oder suchen) Sie nach einem Ziel, geben Sie zielspezifische Informationen ein und klicken Sie auf **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Voraussetzungen

Füllen Sie die erforderlichen Felder in den [!UICONTROL Basic Information] Abschnitten und [!UICONTROL Traits] Abschnitten aus. Außerdem muss das Ziel bereits vorhanden sein.

### Suchwerkzeuge für Zielzuordnungen

Das **[!UICONTROL Destination Mappings]** Bedienfeld enthält Suchwerkzeuge, wie in der unten stehenden Tabelle beschrieben.

| Suchtyp | Beschreibung |
|---|---|
| **Suche nach Zielnamen** | Ermöglicht die Suche nach einem bestimmten Ziel anhand des Namens. Um zu suchen, beginnen Sie mit der Eingabe. Das Feld wird basierend auf Ihren Suchbegriffen automatisch ausgefüllt. Click **[!UICONTROL Add Destination]** when done. |
| **Alle Ziele durchsuchen** | Durchsuchen Sie eine Liste *aller* verfügbaren Ziele. Wählen Sie Ziele aus und fügen Sie Ihr Segment aus der Popup-Liste hinzu. |

## Felder im Popup-Fenster "Zielzuordnungen" {#fields-in-dest-mappings}

Das Dialogfeld wird angezeigt, [!UICONTROL Segment Builder]nachdem Sie ein Ziel ausgewählt [!UICONTROL Add Destination] haben. In diesem Fenster werden statische Informationen über das Ziel und die Felder angezeigt, die je nach Zieltyp variieren. Geben Sie die erforderlichen Informationen in den leeren Feldern ein, um eine Zielzuordnung einzurichten.

>[!NOTE]
>
>Veröffentlichungsdaten sind optional. Wenn das Feld leer ist, wird das Ziel aktiv und läuft nie ab.

<!-- r_add_mappings_pop.xml -->

### Cookie-Zielfelder

Geben Sie in den [!UICONTROL Destination Mapping] Feldern die Schlüssel-Wert-Paare an, die zum Senden von Daten an das Ziel verwendet werden. Geben Sie den Schlüssel im ersten Feld und die Werte im zweiten ein. Ihr Cookie-Ziel-Pop könnte wie folgt aussehen:

![](assets/cookie_modal.PNG)

### URL-Zielfelder

Geben Sie in den Feldern [!UICONTROL URL] und die vollständige Standard- oder [!UICONTROL Secure URL] sichere Adresse an, die zum Senden der Daten an das Ziel verwendet wird.

![](assets/url_modal.PNG)

### Zielfelder Server-zu-Server

Geben Sie im [!UICONTROL Destination Value] Feld den Wert (Teil eines Schlüssel-Wert-Paars) an, mit dem Daten an das Ziel gesendet werden.

![](assets/s2s_modal.PNG)

>[!MORE_LIKE_THIS]
>
>* [Cookie-Ziel erstellen](../../features/destinations/create-cookie-destination.md)
>* [URL-Ziel erstellen](../../features/destinations/create-url-destination.md)


---
description: Beschreibt das Erstellen von Segmenten mit dem Segmentaufbau.
seo-description: Beschreibt das Erstellen von Segmenten mit dem Segmentaufbau.
seo-title: Segmentaufbau
solution: Audience Manager
title: Segmentaufbau
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 859e55fa5d93c7c56cef4bf2a112cdd4ff318d97

---


# Segmentaufbau {#segment-builder}

Beschreibt die erforderlichen und optionalen Schritte zum Erstellen eines Segments in [!UICONTROL Segment Builder].

## Videodemonstration

Beginn durch Anzeigen des Videos zum [Erstellen von Segmenten im Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). Das Video führt Sie durch den Prozess der Segmenterstellung. Lesen Sie die folgenden Abschnitte für weitere Informationen.

## Segment erstellen {#create-segment}

### Segmentaufbauabschnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] besteht aus 3 getrennten Abschnitten: [!UICONTROL Basic Information], [!UICONTROL Traits]und [!UICONTROL Destinations Mapping]. Um ein Segment zu erstellen, füllen Sie die erforderlichen Felder in den [!UICONTROL Basic Information] und in den [!UICONTROL Traits] Abschnitten aus. [!UICONTROL Destinations Mapping] sind optional. Weitere Hilfe finden Sie in den unten stehenden Anweisungen.

1. Im Abschnitt [Grundlegende Informationen](../../features/segments/segment-builder.md#segment-builder-controls-basics) :

   ![create-segment](assets/create-segment.png)

   * Benennen Sie das Segment. Die maximale Länge eines Segmentnamens beträgt 255 Zeichen.
   * Legen Sie den Segmentstatus fest (standardmäßig aktiv).
   * Wählen Sie eine Datenquelle. Mit dem ersten Dropdownmenü können Sie zwischen den Datenquellen von Audience Manager, Adobe Analytics-Report Suites oder beiden filtern. Wählen Sie dann im zweiten Dropdownmenü die Datenquelle aus. Wenn Sie Adobe Analytics-Report Suites nicht verwenden, ist die Datenquellenauswahl deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen eingestellt.
   * Wählen Sie eine Segmentzusammenführungsregel aus, die für die Segmentqualifizierung verwendet werden soll.
   * Weisen Sie das Datenspeicherung einem Segmentordner zu.

1. Im Abschnitt [Eigenschaften](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-properties](assets/segment-builder-traits.png)
   * Suchen Sie nach der Eigenschaft, die Sie einem Segment hinzufügen möchten, und klicken Sie auf **[!UICONTROL Add Trait]**. Hinzufügen einer anderen Eigenschaft, um eine Eigenschaftsgruppe zu erstellen.
   * Rufen Sie das Modal Erweiterte Suche auf, indem Sie auf **[!UICONTROL Browse All Traits]**. Suchen Sie nach Eigenschaften nach Name, ID, Beschreibung oder Datenquelle. Klicken Sie auf einen Ordner, während Sie suchen, um die Ergebnisse auf diesen Ordner und dessen Unterordner zu beschränken. Sie können Eigenschaften auch nach Eigenschaftstyp ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]und [!UICONTROL Algorithmic]) oder Populationstyp ([Geräte-ID](../../reference/ids-in-aam.md) und [geräteübergreifende ID](../../reference/ids-in-aam.md)) filtern.
      ![segment-builder-browser-properties](assets/segment-builder-browse-traits.png)
   * Beim Erstellen Ihres Segments erhalten Sie Empfehlungen [zu](trait-recommendations.md) den Live-Eigenschaften.
   * Klicken und ziehen Sie Eigenschaften, um separate Gruppen zu erstellen.
   * Bewegen Sie den Mauszeiger über Gruppen, um Beziehungen zu booleschen [!UICONTROL AND], [!UICONTROL OR]und [!UICONTROL AND NOT] Werten festzulegen.
   * Bewegen Sie den Mauszeiger über das Uhrensymbol, um der Eigenschaft [Neuigkeits- und Häufigkeitsregeln](../../features/segments/recency-and-frequency.md) hinzuzufügen.
   * Populationsdaten für Segmentsegmente beim Hinzufügen oder Entfernen von Eigenschaften. Klicken Sie auf **[!UICONTROL Calculate Estimates]** , um die geschätzten Populationszahlen anzuzeigen (oder zu aktualisieren). Weitere Informationen zu [Segmentpopulationsdaten](../../features/segments/segment-builder-data.md#segment-populations) finden Sie im Segmentaufbau.
   * Klicken Sie **[!UICONTROL Save]** nach Abschluss des Vorgangs auf .

1. *(Optional)* Ordnen Sie ein Segment einem Ziel im Abschnitt [Zielzuordnung](../../features/segments/segment-builder.md#segment-builder-controls-destinations) zu:
   * Suchen Sie nach dem Ziel und klicken Sie auf **[!UICONTROL Add Destination]**. Beachten Sie, dass das Ziel bereits vorhanden sein muss, bevor Sie es zu einem Segment hinzufügen können.
   * Klicken Sie **[!UICONTROL Save]** nach Abschluss des Vorgangs auf .

Sehen Sie sich das unten stehende Video an, um einen detaillierten Überblick über die Funktionsweise geräteübergreifender Metriken zu erhalten.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Segmentaufbau-Steuerelemente: Abschnitt &quot;Grundlegende Informationen&quot; {#segment-builder-controls-basics}

Mit [!UICONTROL Segment Builder]den [!UICONTROL the Basic Information] Einstellungen können Sie neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. Um ein neues Segment zu erstellen, geben Sie einen Namen und eine Datenquelle ein und wählen Sie einen Datenspeicherung-Ordner aus. Alle anderen Felder sind optional. Gehen Sie nach Abschluss zum [!UICONTROL Traits] Abschnitt.

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
   <td colname="col2"> <p>Ein Feld für eine benutzerdefinierte ID oder andere Firma-spezifische Informationen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Datenquelle</b> </td> 
   <td colname="col2"> <p>Verbindet das Segment mit einem bestimmten Datenanbieter. <p>Mit dem ersten Dropdownmenü können Sie zwischen den Datenquellen von Audience Manager, Adobe Analytics-Report Suites oder beiden filtern. Wählen Sie dann im zweiten Dropdownmenü die Datenquelle aus.</p><p> Wenn Sie Adobe Analytics-Report Suites nicht verwenden, ist die Datenquellenauswahl deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen eingestellt.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profil Merge Rule</b> </td> 
   <td colname="col2"> <p>Wählt die Profil Merge Rule aus, die für die Segmentqualifizierung verwendet werden soll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Aktiviert oder deaktiviert das Segment (standardmäßig aktiv). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Datenspeicherung von Ordnern</b> </td> 
   <td colname="col2"> <p>Legt fest, zu welcher Datenspeicherung das Segment gehört. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentaufbau-Steuerelemente: Eigenschaftenabschnitt {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder]diesem Abschnitt können Sie Eigenschaften in einem Segment verwalten, Eigenschaftsgruppen erstellen und Qualifizierungskriterien festlegen [!UICONTROL Traits] . Um einem Segment eine Eigenschaft hinzuzufügen, geben Sie den Eigenschaftsnamen in das Suchfeld ein und klicken Sie auf [!UICONTROL Add Trait]. Speichern Sie die Eigenschaft (sofern fertig) oder wechseln Sie zu [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Voraussetzungen:** Füllen Sie die erforderlichen Felder im [!UICONTROL Basic Information] Abschnitt aus.

| Feld | Beschreibung |
|--- |--- |
| Grundlegende Ansicht | Dieser Abschnitt enthält visuelle Steuerelemente, mit denen Sie: <ul><li>Erstellen Sie neue und verwalten Sie vorhandene Segmente.</li><li>Entfernen Sie Eigenschaften aus einem Segment.</li><li>Hinzufügen bis zu 50 (maximal) Eigenschaften zu einem Segment.</li><li>Ziehen Sie Eigenschaften per Drag &amp; Drop, um neue Gruppen zu erstellen.</li><li>Ansichten- und Eigenschaftsgruppen in einem Segment.</li><li>Legen Sie Qualifizierungskriterien mit booleschen Ausdrücken, Vergleichsoperatoren und Neuigkeits-/Häufigkeitseinstellungen fest.</li></ul> |
| Code-Ansicht | Öffnet eine Entwicklungs-Umgebung, mit der Sie Eigenschaften, Gruppen und Qualifikationsanforderungen mit Code anstelle der visuellen Benutzeroberfläche erstellen und verwalten können. Die Code-Ansicht ist nützlich, wenn Ihre Segmente: <ul><li>Enthält mehr als 50 Eigenschaften in einem einzelnen Segment. Hinweis: Segmente sind auf maximal 5000 Eigenschaften beschränkt.</li><li>Enthält viele Eigenschaftsgruppen.</li><li>Halten Sie komplexe Qualifikationsanforderungen ein.</li></ul> |
| Durchsuchen | Hilft Ihnen, Eigenschaften zu finden, die einem Segment hinzugefügt werden sollen. |
| Empfehlungen | Erhalten Sie Live-Empfehlungen für ähnliche Eigenschaften von Ihren Erstanbietereigenschaften und [!UICONTROL Audience Marketplace] -Daten-Feeds, die Sie abonniert haben. Hinzufügen Sie diese Empfehlungen an die Segmentregel, um Ihre Audience zu erweitern. Mehr darüber finden Sie unter [Eigenschaftsempfehlungen](trait-recommendations.md). |
| Marketplace Recommendations | Rufen Sie Live-Empfehlungen für ähnliche Eigenschaften aus [!UICONTROL Audience Marketplace] Datenfeeds ab, die Sie nicht abonniert haben. Mehr darüber finden Sie unter [Eigenschaftsempfehlungen](trait-recommendations.md). |
| Daten zur tatsächlichen und geschätzten Segmentgröße | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Eigenschaften aus einem Segment entfernen {#remove-traits}

Die Verwaltung der Eigenschaften in Ihren Segmenten ist ein wichtiger Bestandteil der Segmentfunktionalität. Gehen Sie wie folgt vor, wenn Sie Eigenschaften aus einem Segment entfernen müssen.

So entfernen Sie Eigenschaften aus einem Segment:

1. Wechseln Sie zu **Audiencen > Segmente**. Blättern Sie durch die Liste oder verwenden Sie die Suchfunktion, um das Segment zu finden, mit dem Sie arbeiten möchten.
2. Klicken Sie auf den Segmentnamen, um den Bildschirm mit den Segmentdetails zu öffnen.
3. Klicken Sie auf **Bearbeiten** , um den Segmentaufbau zu öffnen, und klicken Sie dann auf **Eigenschaften** , um das Eigenschaftenbedienfeld zu öffnen.
4. Bewegen Sie den Mauszeiger über die Eigenschaft, die Sie löschen möchten, und klicken Sie dann auf das X. Durch diese Aktion wird die Eigenschaft sofort aus Ihrem Segment entfernt.

## Segmentaufbau-Steuerelemente: Zuordnungsabschnitt für Ziele {#segment-builder-controls-destinations}

Im [!UICONTROL Segment Builder]Abschnitt &quot;Optional&quot;können Sie [!UICONTROL Destinations Mapping] Segmentdaten an ein Drittanbieter-, [!DNL cookie]Server- [!DNL URL]oder Server-zu-Server-Ziel senden. Um ein Ziel hinzuzufügen, suchen (oder suchen) Sie nach einem Ziel, geben Sie zielspezifische Informationen ein und klicken Sie auf **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Voraussetzungen

Füllen Sie die erforderlichen Felder in den [!UICONTROL Basic Information] Abschnitten und [!UICONTROL Traits] Abschnitten aus. Außerdem muss das Ziel bereits vorhanden sein.

### Suchwerkzeuge für Zielzuordnungen

Das **[!UICONTROL Destination Mappings]** Bedienfeld enthält Suchwerkzeuge, wie in der unten stehenden Tabelle beschrieben.

| Suchtyp | Beschreibung |
|---|---|
| **Suche nach Zielnamen** | Ermöglicht die Suche nach einem bestimmten Ziel anhand des Namens. Zur Suche geben Sie Beginn ein. Das Feld wird basierend auf Ihren Suchbegriffen automatisch ausgefüllt. Klicken Sie **[!UICONTROL Add Destination]** nach Abschluss des Vorgangs auf . |
| **Alle Ziele durchsuchen** | Durchsuchen Sie eine Liste *aller* verfügbaren Ziele. Wählen Sie Ziele aus und fügen Sie sie in der Popup-Liste zu Ihrem Segment hinzu. |

## Felder im Popup-Fenster &quot;Zielzuordnungen&quot; {#fields-in-dest-mappings}

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

>[!MORELIKETHIS]
>
>* [Cookie-Ziel erstellen](../../features/destinations/create-cookie-destination.md)
>* [URL-Ziel erstellen](../../features/destinations/create-url-destination.md)


---
description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-title: Analytics-Ziel konfigurieren
solution: Audience Manager
title: Analytics-Ziel konfigurieren
translation-type: tm+mt
source-git-commit: 3179b9007e102f7031cc4cc9e0da64f77cfa3eeb

---


# Analytics-Ziel konfigurieren

## Voraussetzungen {#requirements}

See [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Ihr Standard-Analytics-Ziel und neue Analytics-Ziele

| Analytics-Zieltyp | Beschreibung |
|---|---|
| Standardeinstellung | Der Name dieses Standardziels lautet &quot;Adobe Analytics&quot; , den Sie bearbeiten können. Zugeordnete Report Suite-IDs werden im Ordnerspeicher für Eigenschaften und Segmente Ihres Audience Managers angezeigt. <br>Audience Manager erstellt automatisch ein Ziel, wenn Ihr Konto: <br> <ul><li>Met the requirements described in the [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) documentation.</li><li>A [report suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[Einer Organisation eine Report Suite zugeordnet](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Neu | Um neue Analytics-Ziele zu erstellen, gehen Sie zu Zielgruppendaten &gt; Ziele &gt; Neues Ziel erstellen und befolgen Sie die Schritte für die einzelnen unten beschriebenen Abschnitte. |

## Schritt 1: Grundlegende Informationen bereitstellen

Dieser Abschnitt enthält Felder und Optionen, die den Analytics-Zielerstellungsprozess starten. So füllen Sie diesen Abschnitt aus:

1. Click **Basic Information** to expose the controls.
2. Geben Sie dem Ziel einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine genaue Beschreibung ist eine effektive Möglichkeit, weitere Informationen zu einem Ziel zu definieren oder bereitzustellen.
4. *(Optional)* Belassen Sie in der **Liste &quot;Plattform** &quot; den Standardsatz **auf&quot; Alle**«. Derzeit sind diese Optionen nicht verfügbar. Sie werden für die Unterstützung von Funktionen konzipiert, die zu einem späteren Zeitpunkt hinzugefügt werden können.
5. In the **Category** list, select **Adobe Experience Cloud**.
6. In the **Type** list, select **Adobe Analytics**.
7. Click **Save** to go to the Configuration settings or click **Data Export Labels** to apply export controls to the destination.

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. Sie können diese Einstellungen nicht ändern.

![basicinformation](assets/basicinformation.png)

## Schritt 2: Datenexportsteuerelemente konfigurieren

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So füllen Sie diesen Abschnitt aus:

1. Click **Data Export Controls** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) ). Bei Analytics-Zielen wird standardmäßig das Kontrollkästchen PII aktiviert.
3. Klicken Sie auf **Speichern**.

![exportcontrols](assets/exportControls.png)

## Schritt 3: Report Suites zuordnen

Im Abschnitt &quot;Konfiguration&quot; werden Ihre Analytics Report Suites aufgelistet, die für die serverseitige Weiterleitung aktiviert wurden. Wenn Sie mehrere Analytics-Ziele haben, schließen die diesen Ziele zugewiesenen Report Suites sich gegenseitig aus und werden von Audience Manager erzwungen. So füllen Sie diesen Abschnitt aus:

1. Click **Configuration** to expose the controls.
2. Wählen Sie eine (oder mehr) Report Suites aus, an die Sie Segmente senden möchten.
3. Klicken Sie auf **Speichern**.

![reportsuites](assets/reportSuites.png)

## Schritt 4: Segmentzuordnungen

Dieser Abschnitt enthält Optionen, mit denen Sie Segmente automatisch oder manuell zuordnen können.

| Option zuordnen | Beschreibung |
|---|---|
| Alle aktuellen und zukünftigen Segmente automatisch zuordnen | Diese Funktion sendet standardmäßig alle Segmente, die ein Besucher für einen Treffer pro Treffer auf Analytics qualifiziert. <br>Wenn ein Besucher zu mehr als 150 Audience Manager-Segmenten bei einem einzelnen Treffer gehört, werden nur die letzten 150 zuletzt qualifizierten Segmente an Analytics gesendet, während die verbleibende Liste abgeschnitten wird. Es wird ein zusätzliches Flag an Analytics gesendet, das darauf hinweist, dass die Segmentliste abgeschnitten wurde. Diese Aktion wird in der Dimension &quot;Name der Zielgruppe&quot; und&quot; 1&quot; in der Dimension &quot;Zielgruppen-ID&quot; als&quot; Zielgruppenlimit erreicht&quot; angezeigt. See the [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) for details. <br>Diese Option wirkt sich auch auf die Zielverfügbarkeit im [Segmentaufbau](/help/using/features/segments/segment-builder.md)aus. For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. Das Analytics-Ziel wird grau dargestellt und zeigt &quot;Analytics&quot; in der Spalte&quot; Typ&quot; des Zielbrowsers an. |
| Segmente manuell zuordnen | Diese Option legt die Suche und Durchsuchen-Steuerelemente fest, mit denen Sie auswählen können, welche Segmente Sie an Analytics senden möchten. <br>So suchen Sie nach einem Segment: <br> <ol><li>Geben Sie den Segmentnamen oder die ID in das Suchfeld ein.</li><li>Klicken Sie auf <b>Hinzufügen.</b></li><li>Continue to search and add segments or click <b>Done</b>.</li></ol><br>So suchen Sie nach einem Segment: <ol><li>Click <b>Browse all segments</b>. Dadurch wird eine Liste verfügbarer Segmente offen gelegt.</li><li>From the list, select the check box of the segment you want to use and click <b>Add selected segments</b>.</li><li>Click <b>Save</b> in the Add Mappings window. Sie können die Zuordnungen, Start- oder Enddaten nicht während der Beta-Version ändern.</li><li>Continue to browse and add segments or click <b>Done</b>.</li></ol> |

![mapsegments](assets/mapSegments.png)

## Nächste Schritte

Nachdem Sie ein Ziel erstellt und gespeichert haben, können Sie mit diesen Daten in Analytics arbeiten. Es kann jedoch einige Stunden dauern, bis Daten in Ihren ausgewählten Report Suites verfügbar sind. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).




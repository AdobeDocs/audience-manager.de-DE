---
description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-title: Analytics-Ziel konfigurieren
solution: Audience Manager
title: Analytics-Ziel konfigurieren
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Analytics-Ziel konfigurieren

## Voraussetzungen {#requirements}

Siehe [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Ihr Standard-Analytics-Ziel und neue Analytics-Ziele

| Analytics-Zieltyp | Beschreibung |
|---|---|
| Standardeinstellung | Der Name dieses Standardziels lautet "Adobe Analytics" , den Sie bearbeiten können. Zugeordnete Report Suite-IDs werden im Ordnerspeicher für Eigenschaften und Segmente Ihres Audience Managers angezeigt. <br>Audience Manager erstellt automatisch ein Ziel, wenn Ihr Konto: <br> <ul><li>Erfüllen Sie die in der Dokumentation [zu Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) beschriebenen Anforderungen.</li><li>Eine [Report Suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[Einer Organisation eine Report Suite zugeordnet](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Neu | Um neue Analytics-Ziele zu erstellen, gehen Sie zu Zielgruppendaten &gt; Ziele &gt; Neues Ziel erstellen und befolgen Sie die Schritte für die einzelnen unten beschriebenen Abschnitte. |

## Schritt 1: Grundlegende Informationen bereitstellen

Dieser Abschnitt enthält Felder und Optionen, die den Analytics-Zielerstellungsprozess starten. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie **auf Grundlegende Informationen** , um die Steuerelemente offenzulegen.
2. Geben Sie dem Ziel einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine genaue Beschreibung ist eine effektive Möglichkeit, weitere Informationen zu einem Ziel zu definieren oder bereitzustellen.
4. *(Optional)* Belassen Sie in der **Liste "Plattform** " den Standardsatz **auf" Alle**«. Derzeit sind diese Optionen nicht verfügbar. Sie werden für die Unterstützung von Funktionen konzipiert, die zu einem späteren Zeitpunkt hinzugefügt werden können.
5. Wählen Sie in der **Liste "Kategorie** " die Option **Adobe Experience Cloud**.
6. Wählen Sie in der **Liste "Typ** " die Option **" Adobe Analytics**«aus.
7. Klicken **Sie auf Speichern** , um zu den Konfigurationseinstellungen zu wechseln, oder klicken **Sie auf Datenexport-Beschriftungen** , um Exportsteuerelemente auf das Ziel anzuwenden.

>[!NOTE]
>
>Bei einem Analytics-Ziel sind standardmäßig die **Kontrollkästchen "Zielzuordnungen für Ausfüllziel"** und **" Segment-ID** " ausgewählt. Sie können diese Einstellungen nicht ändern.

![basicinformation](assets/basicinformation.png)

## Schritt 2: Datenexportsteuerelemente konfigurieren

Dieser Abschnitt enthält Optionen zum Anwenden [von Datenexportsteuerelementen](/help/using/features/data-export-controls.md) auf ein Analytics-Ziel. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken **Sie auf Datenexportsteuerelemente** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung, die dem auf das Ziel angewendeten Datenexportsteuerelement entspricht (siehe [Hinzufügen von Datenexportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) ). Bei Analytics-Zielen wird standardmäßig das Kontrollkästchen PII aktiviert.
3. Klicken Sie auf **Speichern**.

![exportcontrols](assets/exportControls.png)

## Schritt 3: Report Suites zuordnen

Im Abschnitt "Konfiguration" werden Ihre Analytics Report Suites aufgelistet, die für die serverseitige Weiterleitung aktiviert wurden. Wenn Sie mehrere Analytics-Ziele haben, schließen die diesen Ziele zugewiesenen Report Suites sich gegenseitig aus und werden von Audience Manager erzwungen. So füllen Sie diesen Abschnitt aus:

1. Klicken **Sie auf Konfiguration** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine (oder mehr) Report Suites aus, an die Sie Segmente senden möchten.
3. Klicken Sie auf **Speichern**.

![reportsuites](assets/reportSuites.png)

## Schritt 4: Segmentzuordnungen

Dieser Abschnitt enthält Optionen, mit denen Sie Segmente automatisch oder manuell zuordnen können.

| Option zuordnen | Beschreibung |
|---|---|
| Alle aktuellen und zukünftigen Segmente automatisch zuordnen | Diese Funktion sendet standardmäßig alle Segmente, die ein Besucher für einen Treffer pro Treffer auf Analytics qualifiziert. <br>Wenn ein Besucher zu mehr als 150 Audience Manager-Segmenten bei einem einzelnen Treffer gehört, werden nur die letzten 150 zuletzt qualifizierten Segmente an Analytics gesendet, während die verbleibende Liste abgeschnitten wird. Es wird ein zusätzliches Flag an Analytics gesendet, das darauf hinweist, dass die Segmentliste abgeschnitten wurde. Diese Aktion wird in der Dimension "Name der Zielgruppe" und" 1" in der Dimension "Zielgruppen-ID" als" Zielgruppenlimit erreicht" angezeigt. Weitere Informationen finden Sie in [den häufig gestellten Fragen](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) . <br>Diese Option wirkt sich auch auf die Zielverfügbarkeit im [Segmentaufbau](/help/using/features/segments/segment-builder.md)aus. Wenn ein Segment beispielsweise automatisch einem Analytics-Ziel zugeordnet wird, ist dieses Ziel nicht im [Zielgruppenzuordnungen](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) des Segmentaufbaus verfügbar. Das Analytics-Ziel wird grau dargestellt und zeigt "Analytics" in der Spalte" Typ" des Zielbrowsers an. |
| Segmente manuell zuordnen | Diese Option legt die Suche und Durchsuchen-Steuerelemente fest, mit denen Sie auswählen können, welche Segmente Sie an Analytics senden möchten. <br>So suchen Sie nach einem Segment: <br> <ol><li>Geben Sie den Segmentnamen oder die ID in das Suchfeld ein.</li><li>Klicken Sie auf <b>Hinzufügen.</b></li><li>Suchen Sie nach Segmenten, fügen Sie sie hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol><br>So suchen Sie nach einem Segment: <ol><li>Klicken <b>Sie auf Alle Segmente durchsuchen</b>. Dadurch wird eine Liste verfügbarer Segmente offen gelegt.</li><li>Wählen Sie in der Liste das Kontrollkästchen des Segments aus, das Sie verwenden möchten, und klicken <b>Sie auf Ausgewählte Segmente hinzufügen</b>.</li><li>Klicken <b>Sie</b> im Fenster Zuordnungen hinzufügen auf Speichern. Sie können die Zuordnungen, Start- oder Enddaten nicht während der Beta-Version ändern.</li><li>Navigieren Sie zum Durchsuchen und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol> |

![mapsegments](assets/mapSegments.png)

## Nächste Schritte

Nachdem Sie ein Ziel erstellt und gespeichert haben, können Sie mit diesen Daten in Analytics arbeiten. Es kann jedoch einige Stunden dauern, bis Daten in Ihren ausgewählten Report Suites verfügbar sind. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).




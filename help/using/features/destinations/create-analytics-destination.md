---
description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-title: Konfigurieren eines Analytics-Ziels
solution: Audience Manager
title: Konfigurieren eines Analytics-Ziels
feature: Adobe Analytics-Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 9%

---

# Konfigurieren eines Analytics-Ziels

## Anforderungen {#requirements}

Um ein Analytics-Ziel zu konfigurieren, muss Ihr Audience Manager über Administratorberechtigungen verfügen. Siehe [Benutzer erstellen](/help/using/features/administration/administration-overview.md#create-users) im Administrationshandbuch. Beachten Sie, dass die Berechtigung `CREATE_DESTINATIONS` [Platzhalter](/help/using/features/administration/administration-overview.md#wild-card-permissions) nicht ausreicht, um Analytics-Ziele zu erstellen.
Weitere Informationen finden Sie unter Voraussetzungen in [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Ihr standardmäßiges Analytics-Ziel und neue Analytics-Ziele

| Analytics-Zieltyp | Beschreibung |
|---|---|
| Standardeinstellung | Der Name dieses Standardziels ist &quot;Adobe Analytics&quot;, den Sie bearbeiten können. Zugeordnete Report Suite-IDs werden im Ordnerspeicher für Ihre Audience Manager-Eigenschaften und -Segmente angezeigt. <br>  Audience Manager erstellt automatisch ein Ziel, wenn Ihr Konto über Folgendes verfügt:  <br>  <ul><li>Erfüllen Sie die in der [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) -Dokumentation beschriebenen Anforderungen.</li><li>Eine [Report Suite](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) in Analytics.</li><li>[Eine Report Suite wurde einer Organisation](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) zugeordnet.</li></ul> |
| Neu | Um neue Analytics-Ziele zu erstellen, navigieren Sie zu Zielgruppendaten > Ziele > Neues Ziel erstellen und befolgen Sie die unten beschriebenen Schritte für jeden Abschnitt. |

## Schritt 1: Bereitstellung grundlegender Informationen

Dieser Abschnitt enthält Felder und Optionen, die den Erstellungsprozess für das Analytics-Ziel starten. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **Grundlegende Informationen** , um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine kurze Beschreibung ist eine effektive Möglichkeit, um weitere Informationen über ein Ziel zu definieren oder bereitzustellen.
4. *(Optional)* Behalten Sie in der  **** Plattformliste den Standardwert  **Alle** bei. Derzeit führen diese Optionen nichts aus. Sie wurden entwickelt, um Funktionen zu unterstützen, die zu einem späteren Zeitpunkt hinzugefügt werden können.
5. Wählen Sie in der Liste **Category** **Adobe Experience Cloud** aus.
6. Wählen Sie in der Liste **Typ** **Adobe Analytics** aus.
7. Klicken Sie auf **Speichern** , um zu den Konfigurationseinstellungen zu wechseln, oder klicken Sie auf **Datenexportbeschriftungen** , um Exportkontrollen auf das Ziel anzuwenden.

>[!NOTE]
>
>Für ein Analytics-Ziel sind standardmäßig das Kontrollkästchen **Zielzuordnung automatisch ausfüllen** und die Option **Segment-ID** aktiviert. Sie können diese Einstellungen nicht ändern.

![Basisinformationen](assets/basicinformation.png)

## Schritt 2: Konfigurieren von Datenexportkontrollen

Dieser Abschnitt enthält Optionen, die [Datenexportkontrollen](/help/using/features/data-export-controls.md) auf ein Analytics-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexport-Steuerelemente verwenden. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **Datenexportkontrollen** , um die Steuerelemente anzuzeigen.
1. Wählen Sie eine Beschriftung aus, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (siehe [Hinzufügen von Datenexportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) ). Bei Analytics-Zielen ist das Kontrollkästchen PII standardmäßig aktiviert.
1. Klicken Sie auf **Speichern**.

![exportControls](assets/exportControls.png)

## Schritt 3: Report Suites zuordnen

Im Abschnitt Konfiguration werden Ihre Analytics Report Suites aufgelistet, die für die serverseitige Weiterleitung aktiviert wurden. Wenn Sie über mehrere Analytics-Ziele verfügen, schließen sich die diesen Zielen zugewiesenen Report Suites gegenseitig aus und werden von Audience Manager erzwungen. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **Configuration** , um die Steuerelemente anzuzeigen.
1. Wählen Sie eine (oder mehrere) Report Suites aus, an die Sie Segmente senden möchten.
1. Klicken Sie auf **Speichern**.

![reportsuites](assets/reportSuites.png)

## Schritt 4: Segmentzuordnungen

Dieser Abschnitt enthält Optionen, mit denen Sie Segmente automatisch oder manuell zuordnen können.

| Zuordnungsoption | Beschreibung |
|---|---|
| Alle aktuellen und zukünftigen Segmente automatisch zuordnen | Diese Funktion ist standardmäßig ausgewählt und sendet alle Segmente, für die sich ein Besucher pro Treffer qualifiziert, an Analytics. <br>  Wenn ein Besucher bei einem einzelnen Treffer zu mehr als 150 Audience Manager-Segmenten gehört, werden nur die 150 am häufigsten qualifizierten Segmente an Analytics gesendet, während die verbleibende Liste abgeschnitten wird. Ein zusätzliches Flag wird an Analytics gesendet, das angibt, dass die Segmentliste abgeschnitten wurde. Diese Aktion wird als &quot;Zielgruppenlimit erreicht&quot;in der Dimension Zielgruppenname und als &quot;1&quot;in der Dimension Zielgruppen-ID angezeigt. Weitere Informationen finden Sie unter [FAQ](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) . <br>  Außerdem wirkt sich diese Option auf die Zielverfügbarkeit in  [Segment Builder](/help/using/features/segments/segment-builder.md) aus. Wenn beispielsweise ein Segment automatisch einem Analytics-Ziel zugeordnet wird, ist dieses Ziel nicht zur Auswahl im Abschnitt [Zielzuordnungen](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) des Segmentaufbaus verfügbar. Das Analytics-Ziel wird grau ausgeblendet und in der Spalte &quot;Typ&quot;des Ziel-Browsers wird &quot;Analytics&quot;angezeigt. |
| Manuelles Zuordnen von Segmenten | Diese Option zeigt Such- und Durchsuchen-Steuerelemente an, mit denen Sie auswählen können, welche Segmente Sie an Analytics senden möchten. <br>  So suchen Sie nach einem Segment:  <br>  <ol><li>Geben Sie den Segmentnamen oder die ID in das Suchfeld ein.</li><li>Klicken Sie auf <b>Hinzufügen.</b></li><li>Suchen Sie weiter und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol><br>  So suchen Sie nach einem Segment: <ol><li>Klicken Sie auf <b>Alle Segmente durchsuchen</b>. Dadurch wird eine Liste der verfügbaren Segmente angezeigt.</li><li>Aktivieren Sie in der Liste das Kontrollkästchen des zu verwendenden Segments und klicken Sie auf <b>Ausgewählte Segmente hinzufügen</b>.</li><li>Klicken Sie im Fenster Zuordnungen hinzufügen auf <b>Speichern</b> . Sie können die Zuordnungen, Start- und Enddaten während der Beta-Version nicht ändern.</li><li>Navigieren Sie weiter zu und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Nächste Schritte

Nachdem Sie ein Ziel erstellt und gespeichert haben, können Sie mit diesen Daten in Analytics arbeiten. Es kann jedoch einige Stunden dauern, bis Daten in den ausgewählten Report Suites verfügbar sind. Siehe [Zielgruppendaten in Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html) verwenden.

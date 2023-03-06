---
description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Konfigurieren eines Analytics-Ziels
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 5%

---

# Konfigurieren eines Analytics-Ziels

## Anforderungen {#requirements}

Um ein Analytics-Ziel zu konfigurieren, muss Ihr Audience Manager über Administratorberechtigungen verfügen. Siehe [Benutzer erstellen](/help/using/features/administration/administration-overview.md#create-users) im Administrationshandbuch. Beachten Sie Folgendes: `CREATE_DESTINATIONS` [Platzhalterberechtigung](/help/using/features/administration/administration-overview.md#wild-card-permissions) reicht nicht aus, um Analytics-Ziele zu erstellen.
Weitere Anforderungen finden Sie unter Voraussetzungen unter [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Ihr standardmäßiges Analytics-Ziel und neue Analytics-Ziele

| Analytics-Zieltyp | Beschreibung |
|---|---|
| Standardeinstellung | Der Name dieses Standardziels ist &quot;Adobe Analytics&quot;, den Sie bearbeiten können. Zugeordnete Report Suite-IDs werden im Ordnerspeicher für Ihre Audience Manager-Eigenschaften und -Segmente angezeigt. <br>  Audience Manager erstellt automatisch ein Ziel, wenn Ihr Konto über Folgendes verfügt: <br>  <ul><li>Erfüllen Sie die im Abschnitt [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html) Dokumentation.</li><li>A [Report Suite](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) in Analytics.</li></ul> |
| Neu | Um neue Analytics-Ziele zu erstellen, navigieren Sie zu Zielgruppendaten > Ziele > Neues Ziel erstellen und befolgen Sie die unten beschriebenen Schritte für jeden Abschnitt. |

## Audience Manager-Segmentqualifikationen in Adobe Analytics {#segment-qualifications}

Beim Senden von Segmentinformationen an ein Analytics-Ziel sendet Audience Manager nur die Segmente, für die sich der Besucher qualifiziert hat. Wenn ein Besucher aufhört, sich für ein Segment zu qualifizieren, lautet diese Information _not_ an Adobe Analytics weitergeleitet.

Betrachten Sie beispielsweise die Segmentregeln unten:

* Segment A: Eigenschaft 1 UND Eigenschaft 2
* Segment B: Eigenschaft 1 UND NICHT Eigenschaft 2

In Analytics-Berichten kann ein Profil für beide Segmente als qualifiziert angezeigt werden, auch wenn es sich nicht mehr für Segment B qualifiziert hat.

## Schritt 1: Bereitstellung grundlegender Informationen

Dieser Abschnitt enthält Felder und Optionen, die den Erstellungsprozess für das Analytics-Ziel starten. So schließen Sie diesen Abschnitt ab:

1. Klicken **Basisinformationen** um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine kurze Beschreibung ist eine effektive Möglichkeit, um weitere Informationen über ein Ziel zu definieren oder bereitzustellen.
4. *(Optional)* Im **Plattform** list festlegen, lassen Sie die Standardeinstellung auf **Alle**. Derzeit führen diese Optionen nichts aus. Sie wurden entwickelt, um Funktionen zu unterstützen, die zu einem späteren Zeitpunkt hinzugefügt werden können.
5. Im **Kategorie** Liste auswählen **Adobe Experience Cloud**.
6. Im **Typ** Liste auswählen **Adobe Analytics**.
7. Klicken **Speichern** , um die Konfigurationseinstellungen aufzurufen, oder klicken Sie auf **Datenexportbeschriftungen** um Ausfuhrkontrollen für das Ziel anzuwenden.

>[!NOTE]
>
>Bei einem Analytics-Ziel muss die Variable **Zielzuordnung automatisch ausfüllen** Kontrollkästchen und **Segment-ID** ist standardmäßig aktiviert. Sie können diese Einstellungen nicht ändern.

![Basisinformationen](assets/basicinformation.png)

## Schritt 2: Konfigurieren von Datenexportkontrollen

Dieser Abschnitt enthält die zutreffenden Optionen [Datenexportkontrollen](/help/using/features/data-export-controls.md) an ein Analytics-Ziel. Überspringen Sie diesen Schritt, wenn Sie keine Datenexport-Steuerelemente verwenden. So schließen Sie diesen Abschnitt ab:

1. Klicken **Datenexportkontrollen** um die Steuerelemente anzuzeigen.
1. Wählen Sie eine Beschriftung aus, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (siehe [Hinzufügen von Datenexportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) ). Bei Analytics-Zielen ist das Kontrollkästchen PII standardmäßig aktiviert.
1. Klicken Sie auf **Speichern**.

![exportControls](assets/exportControls.png)

## Schritt 3: Report Suites zuordnen

Im Abschnitt Konfiguration werden Ihre Analytics Report Suites aufgelistet, die für die serverseitige Weiterleitung aktiviert wurden. Wenn Sie über mehrere Analytics-Ziele verfügen, schließen sich die diesen Zielen zugewiesenen Report Suites gegenseitig aus und werden von Audience Manager erzwungen. So schließen Sie diesen Abschnitt ab:

1. Klicken **Konfiguration** um die Steuerelemente anzuzeigen.
1. Wählen Sie eine (oder mehrere) Report Suites aus, an die Sie Segmente senden möchten.
1. Klicken Sie auf **Speichern**.

![reportsuites](assets/reportSuites.png)

## Schritt 4: Segmentzuordnungen

Dieser Abschnitt enthält Optionen, mit denen Sie Segmente automatisch oder manuell zuordnen können.

| Zuordnungsoption | Beschreibung |
|---|---|
| Alle aktuellen und zukünftigen Segmente automatisch zuordnen | Diese Funktion ist standardmäßig ausgewählt und sendet alle Segmente, für die sich ein Besucher pro Treffer qualifiziert, an Analytics. <br>  Wenn ein Besucher bei einem einzelnen Treffer zu mehr als 150 Audience Manager-Segmenten gehört, werden nur die 150 am häufigsten qualifizierten Segmente an Analytics gesendet, während die verbleibende Liste abgeschnitten wird. Ein zusätzliches Flag wird an Analytics gesendet, das angibt, dass die Segmentliste abgeschnitten wurde. Diese Aktion wird als &quot;Zielgruppenlimit erreicht&quot;in der Dimension Zielgruppenname und als &quot;1&quot;in der Dimension Zielgruppen-ID angezeigt. Siehe [FAQs](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) für Details. <br>  Diese Option wirkt sich auch auf die Zielverfügbarkeit in aus [Segment Builder](/help/using/features/segments/segment-builder.md). Wenn beispielsweise ein Segment automatisch einem Analytics-Ziel zugeordnet wird, steht dieses Ziel nicht zur Auswahl in der [Zielzuordnungen](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) Abschnitt von Segment Builder. Das Analytics-Ziel wird grau ausgeblendet und in der Spalte &quot;Typ&quot;des Ziel-Browsers wird &quot;Analytics&quot;angezeigt. |
| Manuelles Zuordnen von Segmenten | Diese Option zeigt Such- und Durchsuchen-Steuerelemente an, mit denen Sie auswählen können, welche Segmente Sie an Analytics senden möchten. <br>  So suchen Sie nach einem Segment: <br>  <ol><li>Geben Sie den Segmentnamen oder die ID in das Suchfeld ein.</li><li>Klicken Sie auf <b>Hinzufügen.</b></li><li>Suchen Sie weiter und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol><br>  So suchen Sie nach einem Segment: <ol><li>Klicken <b>Alle Segmente durchsuchen</b>. Dadurch wird eine Liste der verfügbaren Segmente angezeigt.</li><li>Aktivieren Sie in der Liste das Kontrollkästchen des zu verwendenden Segments und klicken Sie auf <b>Ausgewählte Segmente hinzufügen</b>.</li><li>Klicken <b>Speichern</b> im Fenster Zuordnungen hinzufügen . Sie können die Zuordnungen, Start- und Enddaten während der Beta-Version nicht ändern.</li><li>Suchen Sie weiter und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol> ![mapsegments](assets/mapSegments.png) |

## Nächste Schritte

Nachdem Sie ein Ziel erstellt und gespeichert haben, können Sie mit diesen Daten in Analytics arbeiten. Es kann jedoch einige Stunden dauern, bis Daten in den ausgewählten Report Suites verfügbar sind. Siehe [Zielgruppendaten in Analytics verwenden](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).

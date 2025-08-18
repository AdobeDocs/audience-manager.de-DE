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
source-wordcount: '866'
ht-degree: 4%

---

# Konfigurieren eines Analytics-Ziels

## Anforderungen {#requirements}

Um ein Analytics-Ziel zu konfigurieren, müssen Ihre Audience Manager-Benutzenden über Administratorberechtigungen verfügen. Siehe [Benutzer erstellen](/help/using/features/administration/administration-overview.md#create-users) im Administrationshandbuch. Beachten Sie, dass die `CREATE_DESTINATIONS` [Platzhalterberechtigung](/help/using/features/administration/administration-overview.md#wild-card-permissions) nicht ausreicht, um Analytics-Ziele zu erstellen.
Weitere Anforderungen finden Sie unter Voraussetzungen in [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Ihr standardmäßiges Analytics-Ziel und neue Analytics-Ziele

| Analytics-Zieltyp | Beschreibung |
|---|---|
| Standardeinstellung | Der Name dieses Standardziels lautet &quot;Adobe Analytics&quot;, die Sie bearbeiten können. Zugeordnete Report Suite-IDs werden im Ordnerspeicher für Ihre Audience Manager-Eigenschaften und -Segmente angezeigt. <br>  Audience Manager erstellt automatisch ein Ziel, wenn Ihr Konto Folgendes enthält: <br>  <ul><li>Erfüllen Sie die in der Dokumentation zu [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html) beschriebenen Anforderungen.</li><li>Eine [Report Suite](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) in Analytics.</li></ul> |
| Neu | Um neue Analytics-Ziele zu erstellen, gehen Sie zu Zielgruppendaten > Ziele > Neues Ziel erstellen und führen Sie die Schritte für jeden Abschnitt aus, der unten beschrieben wird. |

## Audience Manager-Segmentqualifikationen in Adobe Analytics {#segment-qualifications}

Beim Senden von Segmentinformationen an ein Analytics-Ziel sendet Audience Manager nur die Segmente, für die sich der Besucher qualifiziert hat. Wenn sich ein Besucher nicht mehr für ein Segment qualifiziert, werden diese Informationen _nicht_ an Adobe Analytics weitergeleitet.

Betrachten Sie beispielsweise die folgenden Segmentregeln:

* Segment A: Eigenschaft 1 UND Eigenschaft 2
* Segment B: Eigenschaft 1 UND NICHT Eigenschaft 2

In Analytics-Berichten kann ein Profil für beide Segmente als qualifiziert angezeigt werden, auch wenn es sich nicht mehr für Segment B qualifiziert.

## Schritt 1: Bereitstellen grundlegender Informationen

Dieser Abschnitt enthält Felder und Optionen, mit denen der Prozess zur Erstellung des Analytics-Ziels gestartet wird. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **Grundlegende Informationen**, um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine knappe Beschreibung ist eine effektive Möglichkeit, um mehr Informationen über ein Ziel zu definieren oder bereitzustellen.
4. *(Optional)* Lassen Sie in der Liste **Platform** den Standardwert auf &quot;**&quot;**. Derzeit bewirken diese Optionen nichts. Sie unterstützen Funktionen, die zu einem späteren Zeitpunkt hinzugefügt werden können.
5. Wählen Sie in der **Kategorie**-Liste **Adobe Experience Cloud**.
6. Wählen Sie in **Liste** Typ“ **Adobe Analytics** aus.
7. Klicken Sie **Speichern**, um zu den Konfigurationseinstellungen zu wechseln, oder klicken Sie auf **Datenexportbeschriftungen**, um Exportsteuerungen auf das Ziel anzuwenden.

>[!NOTE]
>
>Bei einem Analytics-Ziel sind das Kontrollkästchen **Zielzuordnung automatisch ausfüllen** und die Option **Segment-ID** standardmäßig aktiviert. Diese Einstellungen können nicht geändert werden.

![Basisinformationen](assets/basicinformation.png)

## Schritt 2: Konfigurieren von Datenexportsteuerelementen

Dieser Abschnitt enthält Optionen, die [Datenexportsteuerelemente](/help/using/features/data-export-controls.md) auf ein Analytics-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie **Datenexportsteuerelemente**, um die Steuerelemente anzuzeigen.
1. Wählen Sie eine Kennzeichnung aus, die dem auf das Ziel angewendeten Datenexportsteuerelement entspricht (siehe [Hinzufügen von Datenexportkennzeichnungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) ). Bei Analytics-Zielen ist das Kontrollkästchen PII standardmäßig aktiviert.
1. Klicken Sie auf **Speichern**.

![exportControls](assets/exportControls.png)

## Schritt 3: Report Suites zuordnen

Im Abschnitt Konfiguration werden Ihre Analytics Report Suites aufgeführt, die für die Server-seitige Weiterleitung aktiviert wurden. Wenn Sie mehrere Analytics-Ziele haben, schließen sich die diesen Zielen zugewiesenen Report Suites gegenseitig aus und werden von Audience Manager durchgesetzt. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie **Konfiguration**, um die Steuerelemente anzuzeigen.
1. Wählen Sie eine (oder mehrere) Report Suites aus, an die Sie Segmente senden möchten.
1. Klicken Sie auf **Speichern**.

![ReportSuites](assets/reportSuites.png)

## Schritt 4: Segmentzuordnungen

Dieser Abschnitt enthält Optionen, mit denen Sie Segmente automatisch oder manuell zuordnen können.

| Zuordnungsoption | Beschreibung |
|---|---|
| Alle aktuellen und zukünftigen Segmente automatisch zuordnen | Standardmäßig ausgewählt, sendet diese Funktion alle Segmente, für die sich ein Besucher qualifiziert, pro Treffer an Analytics. <br>  Wenn ein Besucher zu mehr als 150 Audience Manager-Segmenten auf einmal gehört, werden nur die 150 zuletzt qualifizierten Segmente an Analytics gesendet. Die restliche Liste wird dabei abgeschnitten. Eine zusätzliche Markierung wird an Analytics gesendet, die angibt, dass die Segmentliste abgeschnitten wurde. Diese Aktion wird in der Dimension „Zielgruppenname“ als „Zielgruppenlimit erreicht“ und in der Dimension „Zielgruppen-ID“ als „1“ angezeigt. Weitere Informationen finden [ in ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) FAQs. <br>  Außerdem beeinflusst diese Option die Zielverfügbarkeit in [Segment Builder](/help/using/features/segments/segment-builder.md). Wenn beispielsweise ein Segment automatisch einem Analytics-Ziel zugeordnet wird, ist dieses Ziel nicht im Abschnitt [Zielzuordnungen](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) von Segment Builder verfügbar. Das Analytics-Ziel wird ausgegraut angezeigt und „Analytics“ wird in der Spalte Typ des Ziel-Browsers angezeigt. |
| Segmente manuell zuordnen | Diese Option stellt Steuerelemente zum Suchen und Durchsuchen bereit, mit denen Sie auswählen können, welche Segmente an Analytics gesendet werden sollen. <br>  So suchen Sie nach einem Segment: <br>  <ol><li>Geben Sie den Segmentnamen oder die ID in das Suchfeld ein.</li><li>Klicken Sie auf <b>Hinzufügen.</b></li><li>Fahren Sie mit der Suche und dem Hinzufügen von Segmenten fort oder klicken Sie auf <b>Fertig</b>.</li></ol><br>  So suchen Sie nach einem Segment: <ol><li>Klicken Sie <b>Alle Segmente durchsuchen</b>. Dadurch wird eine Liste der verfügbaren Segmente angezeigt.</li><li>Aktivieren Sie in der Liste das Kontrollkästchen des Segments, das Sie verwenden möchten, und klicken Sie auf <b>Ausgewählte Segmente hinzufügen</b>.</li><li>Klicken <b> im Fenster </b> hinzufügen auf „Speichern“. Sie können die Zuordnungen sowie das Start- und Enddatum während der Beta-Version nicht ändern.</li><li>Fahren Sie mit dem Durchsuchen und Hinzufügen von Segmenten fort oder klicken Sie auf <b>Fertig</b>.</li></ol> ![mapSegments](assets/mapSegments.png) |

## Nächste Schritte

Nachdem Sie ein Ziel erstellt und gespeichert haben, können Sie mit diesen Daten in Analytics arbeiten. Es kann jedoch einige Stunden dauern, bis die Daten in den ausgewählten Report Suites verfügbar sind. Siehe [Verwenden der Zielgruppendaten in Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).

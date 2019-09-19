---
description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-title: Analytics-Ziel konfigurieren
solution: Audience Manager
title: Analytics-Ziel konfigurieren
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Analytics-Ziel konfigurieren

## Voraussetzungen {#requirements}

Siehe [Zielgruppenanalyse](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Ihr Standard-Analytics-Ziel und Ihre neuen Analytics-Ziele

| Analytics-Zieltyp | Beschreibung |
|---|---|
| Standardeinstellung | Der Name dieses Standardziels ist "Adobe Analytics", das Sie bearbeiten können. Zugeordnete Report Suite-IDs werden im Ordnerspeicher für Ihre Audience Manager-Eigenschaften und -Segmente angezeigt. <br>  Audience Manager erstellt automatisch ein Ziel, wenn Ihr Konto über Folgendes verfügt: <br>  <ul><li>Erfüllen Sie die in der Dokumentation zu [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) beschriebenen Anforderungen.</li><li>Eine [Report Suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[Zuordnung einer Report Suite zu einer Organisation](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Neu | Gehen Sie zum Erstellen neuer Analytics-Ziele zu Zielgruppendaten &gt; Ziele &gt; Neues Ziel erstellen und befolgen Sie die Schritte für jeden Abschnitt, der unten beschrieben wird. |

## Schritt 1: Grundlegende Informationen bereitstellen

Dieser Abschnitt enthält Felder und Optionen, mit denen der Analytics-Zielerstellungsprozess gestartet wird. Um diesen Abschnitt abzuschließen:

1. Klicken Sie auf **Grundlegende Informationen** , um die Steuerelemente anzuzeigen.
1. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. *(Optional)* Beschreiben Sie das Ziel. Eine knappe Beschreibung ist eine effektive Methode, um mehr Informationen über ein Ziel zu definieren oder bereitzustellen.
1. *(Optional)* Belassen Sie in der Liste " **Plattform** "den Standardsatz auf **Alle**. Derzeit tun diese Optionen nichts. Sie unterstützen Funktionen, die später hinzugefügt werden können.
1. Wählen Sie in der Liste **Kategorie** die Option **Adobe Experience Cloud**.
1. Wählen Sie in der Liste **Typ** die Option **Adobe Analytics**.
1. Klicken Sie auf **Speichern** , um die Konfigurationseinstellungen aufzurufen, oder auf **Datenexportbeschriftungen** , um Exportsteuerelemente auf das Ziel anzuwenden.

>[!NOTE]
>
>Für ein Analytics-Ziel sind die Kontrollkästchen Zielzuordnung **automatisch ausfüllen** und **Segment-ID** standardmäßig aktiviert. Sie können diese Einstellungen nicht ändern.

![Basisinformationen](assets/basicinformation.png)

## Schritt 2: Datenexportsteuerelemente konfigurieren

Dieser Abschnitt enthält Optionen, die [Datenexportsteuerelemente](/help/using/features/data-export-controls.md) auf ein Analytics-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Steuerelemente für den Datenexport verwenden. Um diesen Abschnitt abzuschließen:

1. Klicken Sie auf **Datenexportsteuerelemente** , um die Steuerelemente anzuzeigen.
1. Wählen Sie eine Beschriftung aus, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (siehe [Hinzufügen von Datenexportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) ). Bei Analytics-Zielen ist das Kontrollkästchen PII standardmäßig aktiviert.
1. Klicken Sie auf **Speichern**.

![exportControls](assets/exportControls.png)

## Schritt 3: Report Suites zuordnen

Im Abschnitt "Konfiguration"werden Ihre Analytics Report Suites aufgelistet, die für die serverseitige Weiterleitung aktiviert wurden. Wenn Sie mehrere Analytics-Ziele haben, schließen sich die diesen Zielen zugewiesenen Report Suites gegenseitig aus und werden von Audience Manager erzwungen. Um diesen Abschnitt abzuschließen:

1. Klicken Sie auf **Konfiguration** , um die Steuerelemente anzuzeigen.
1. Wählen Sie eine (oder mehrere) Report Suites aus, an die Sie Segmente senden möchten.
1. Klicken Sie auf **Speichern**.

![reportsuites](assets/reportSuites.png)

## Schritt 4: Segmentzuordnungen

Dieser Abschnitt enthält Optionen, mit denen Sie Segmente automatisch oder manuell zuordnen können.

| Zuordnungsoption | Beschreibung |
|---|---|
| Automatische Zuordnung aller aktuellen und zukünftigen Segmente | Diese Funktion ist standardmäßig aktiviert und sendet alle Segmente, für die ein Besucher pro Treffer qualifiziert ist, an Analytics. <br>  Wenn ein Besucher bei einem einzelnen Treffer zu mehr als 150 Audience Manager-Segmenten gehört, werden nur die 150 zuletzt qualifizierten Segmente an Analytics gesendet, während die verbleibende Liste abgeschnitten wird. Ein zusätzliches Flag wird an Analytics gesendet, das angibt, dass die Segmentliste abgeschnitten wurde. Diese Aktion wird als "Zielgruppenbeschränkung erreicht"in der Dimension "Zielgruppenname"und als "1"in der Dimension "Zielgruppen-ID"angezeigt. Weitere Informationen finden Sie in den [häufig gestellten Fragen](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) . <br>  Diese Option wirkt sich auch auf die Zielverfügbarkeit im [Segmentaufbau](/help/using/features/segments/segment-builder.md)aus. Wenn beispielsweise ein Segment automatisch einem Analytics-Ziel zugeordnet wird, steht dieses Ziel im Abschnitt [Zielzuordnungen](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) des Segmentaufbaus nicht zur Auswahl zur Verfügung. Das Analytics-Ziel wird grau dargestellt und in der Spalte "Typ"des Ziel-Browsers wird "Analytics"angezeigt. |
| Segmente manuell zuordnen | Diese Option zeigt Such- und Durchsuchen-Steuerelemente an, mit denen Sie auswählen können, welche Segmente Sie an Analytics senden möchten. <br>  So suchen Sie nach einem Segment <br>  <ol><li>Geben Sie den Segmentnamen oder die ID in das Suchfeld ein.</li><li>Klicken Sie auf <b>Hinzufügen.</b></li><li>Suchen Sie weiter und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol><br>  So suchen Sie nach einem Segment: <ol><li>Klicken Sie auf Alle Segmente <b>durchsuchen</b>. Dadurch wird eine Liste der verfügbaren Segmente angezeigt.</li><li>Aktivieren Sie in der Liste das Kontrollkästchen des zu verwendenden Segments und klicken Sie auf "Ausgewählte Segmente <b>hinzufügen"</b>.</li><li>Klicken Sie im Fenster "Zuordnungen hinzufügen"auf <b>Speichern</b> . Sie können die Zuordnungen, Start- und Enddaten während der Beta-Version nicht ändern.</li><li>Suchen Sie weiter und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol> ![mapsegmente](assets/mapSegments.png) |

## Nächste Schritte

Nachdem Sie ein Ziel erstellt und gespeichert haben, können Sie mit diesen Daten in Analytics arbeiten. Es kann jedoch einige Stunden dauern, bis Daten in den ausgewählten Report Suites verfügbar sind. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).

---
description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Configure an Analytics Destination
translation-type: tm+mt
source-git-commit: fa39d070be9ec9f07e9da31de3efd151dd2c6cf1

---


# Configure an Analytics Destination

## Voraussetzungen {#requirements}

Zum Konfigurieren eines Analytics-Ziels muss Ihr Audience Manager-Benutzer über Administratorberechtigungen verfügen. Siehe Benutzer [erstellen](/help/using/features/administration/administration-overview.md#create-users) im Administrationshandbuch. Beachten Sie, dass das Vorhandensein der `CREATE_DESTINATIONS` Platzhalterberechtigung[ ](/help/using/features/administration/administration-overview.md#wild-card-permissions)nicht ausreicht, um Analytics-Ziele zu erstellen.
Weitere Anforderungen finden Sie unter Voraussetzungen in [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Ihr Standard-Analytics-Ziel und Ihre neuen Analytics-Ziele

| Analytics-Zieltyp | Beschreibung |
|---|---|
| Standardeinstellung | Der Name dieses Standardziels ist "Adobe Analytics", das Sie bearbeiten können. Zugeordnete Report Suite-IDs werden im Ordnerspeicher für Ihre Audience Manager-Eigenschaften und -Segmente angezeigt. <br>  Audience Manager erstellt automatisch ein Ziel, wenn Ihr Konto über Folgendes verfügt: <br>  <ul><li>Erfüllen Sie die in der Dokumentation zu [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) beschriebenen Anforderungen.</li><li>Eine [Report Suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[Mapped a report suite to an organization](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Neu | Gehen Sie zum Erstellen neuer Analytics-Ziele zu Zielgruppendaten &gt; Ziele &gt; Neues Ziel erstellen und befolgen Sie die Schritte für jeden Abschnitt, der unten beschrieben wird. |

## Schritt 1: Grundlegende Informationen bereitstellen

Dieser Abschnitt enthält Felder und Optionen, mit denen der Analytics-Zielerstellungsprozess gestartet wird. Um diesen Abschnitt abzuschließen:

1. Klicken Sie auf **Grundlegende Informationen** , um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine knappe Beschreibung ist eine effektive Methode, um mehr Informationen über ein Ziel zu definieren oder bereitzustellen.
4. *(Optional)* Belassen Sie in der Liste " **Plattform** "den Standardsatz auf **Alle**. Derzeit tun diese Optionen nichts. Sie unterstützen Funktionen, die später hinzugefügt werden können.
5. Wählen Sie in der Liste **Kategorie** die Option **Adobe Experience Cloud**.
6. Wählen Sie in der Liste **Typ** die Option **Adobe Analytics**.
7. Click **Save** to go to the Configuration settings or click **Data Export Labels** to apply export controls to the destination.

>[!NOTE]
>
>Für ein Analytics-Ziel sind die Kontrollkästchen Zielzuordnung **automatisch ausfüllen** und **Segment-ID** standardmäßig aktiviert. You cannot change these settings.

![basicinformation](assets/basicinformation.png)

## Step 2: Configure Data Export Controls

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. Skip this step if you do not use data export controls. To complete this section:

1. Click Data Export Controls to expose the controls.****
1. Select a label that corresponds to the data export control applied to the destination (see Add Data Export Labels to a Destination ). [](/help/using/features/destinations/add-data-export-labels.md) For Analytics destinations, the PII check box is selected by default.
1. Klicken Sie auf **Speichern**.

![exportcontrols](assets/exportControls.png)

## Step 3: Map Report Suites

The Configuration section lists your Analytics Report Suites that have been enabled for server-side forwarding. If you have multiple Analytics destinations, the report suites assigned to these destinations will be mutually exclusive and enforced by Audience Manager. To complete this section:

1. Klicken Sie auf **Konfiguration** , um die Steuerelemente anzuzeigen.
1. Wählen Sie eine (oder mehrere) Report Suites aus, an die Sie Segmente senden möchten.
1. Klicken Sie auf **Speichern**.

![reportsuites](assets/reportSuites.png)

## Schritt 4: Segmentzuordnungen

Dieser Abschnitt enthält Optionen, mit denen Sie Segmente automatisch oder manuell zuordnen können.

| Zuordnungsoption | Beschreibung |
|---|---|
| Automatische Zuordnung aller aktuellen und zukünftigen Segmente | Diese Funktion ist standardmäßig aktiviert und sendet alle Segmente, für die ein Besucher pro Treffer qualifiziert ist, an Analytics. <br>  If a visitor belongs to more than 150 Audience Manager segments on a single hit, only the 150-most recently qualified segments are sent to Analytics, while the remaining list is truncated. Ein zusätzliches Flag wird an Analytics gesendet, das angibt, dass die Segmentliste abgeschnitten wurde. Diese Aktion wird als "Zielgruppenbeschränkung erreicht"in der Dimension "Zielgruppenname"und als "1"in der Dimension "Zielgruppen-ID"angezeigt. Weitere Informationen finden Sie in den [häufig gestellten Fragen](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) . <br>  Diese Option wirkt sich auch auf die Zielverfügbarkeit im [Segmentaufbau](/help/using/features/segments/segment-builder.md)aus. Wenn beispielsweise ein Segment automatisch einem Analytics-Ziel zugeordnet wird, steht dieses Ziel im Abschnitt [Zielzuordnungen](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) des Segmentaufbaus nicht zur Auswahl zur Verfügung. Das Analytics-Ziel wird grau dargestellt und in der Spalte "Typ"des Ziel-Browsers wird "Analytics"angezeigt. |
| Segmente manuell zuordnen | Diese Option zeigt Such- und Durchsuchen-Steuerelemente an, mit denen Sie auswählen können, welche Segmente Sie an Analytics senden möchten. <br>  So suchen Sie nach einem Segment <br>  <ol><li>Geben Sie den Segmentnamen oder die ID in das Suchfeld ein.</li><li>Klicken Sie auf <b>Hinzufügen.</b></li><li>Suchen Sie weiter und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol><br>  So suchen Sie nach einem Segment: <ol><li>Klicken Sie auf Alle Segmente <b>durchsuchen</b>. Dadurch wird eine Liste der verfügbaren Segmente angezeigt.</li><li>Aktivieren Sie in der Liste das Kontrollkästchen des zu verwendenden Segments und klicken Sie auf "Ausgewählte Segmente <b>hinzufügen"</b>.</li><li>Klicken Sie im Fenster "Zuordnungen hinzufügen"auf <b>Speichern</b> . Sie können die Zuordnungen, Start- und Enddaten während der Beta-Version nicht ändern.</li><li>Suchen Sie weiter und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol> ![mapsegmente](assets/mapSegments.png) |

## Nächste Schritte

Nachdem Sie ein Ziel erstellt und gespeichert haben, können Sie mit diesen Daten in Analytics arbeiten. Es kann jedoch einige Stunden dauern, bis Daten in den ausgewählten Report Suites verfügbar sind. See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).

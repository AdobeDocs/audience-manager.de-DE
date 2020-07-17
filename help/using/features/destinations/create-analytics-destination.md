---
description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-description: Mit Audience Analytics können Sie Audience Manager-Segmente an Analytics senden. Um diese Funktion zu verwenden, erstellen Sie in Audience Manager Analytics-Ziel- und Zuordnungssegmente.
seo-title: Konfigurieren eines Analytics-Ziels
solution: Audience Manager
title: Konfigurieren eines Analytics-Ziels
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 9%

---


# Konfigurieren eines Analytics-Ziels

## Anforderungen {#requirements}

Zum Konfigurieren eines Analytics-Ziels muss der Audience Manager über Administratorrechte verfügen. Siehe Benutzer [erstellen](/help/using/features/administration/administration-overview.md#create-users) im Administrationshandbuch. Beachten Sie, dass die Berechtigung für `CREATE_DESTINATIONS` Platzhalter [](/help/using/features/administration/administration-overview.md#wild-card-permissions) nicht ausreicht, um Analytics-Ziele zu erstellen.
Weitere Informationen finden Sie unter Voraussetzungen in [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Ihr standardmäßiges Analytics-Ziel und neue Analytics-Ziele

| Analytics-Zieltyp | Beschreibung |
|---|---|
| Standardeinstellung | Der Name dieses Standardziels lautet &quot;Adobe Analytics&quot;, das Sie bearbeiten können. Zugeordnete Report Suite-IDs werden in der Datenspeicherung der Audience Manager für Eigenschaften und Segmente angezeigt. <br>  Audience Manager erstellt automatisch ein Ziel, wenn Ihr Konto <br>  <ul><li>Erfüllen Sie die in der Dokumentation zur [Audience Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) beschriebenen Anforderungen.</li><li>Eine [Report Suite](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) in Analytics.</li><li>[Zuordnung einer Report Suite zu einer Organisation](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html).</li></ul> |
| Neu | Um neue Analytics-Ziele zu erstellen, gehen Sie zu &quot;Audience-Daten&quot;> &quot;Ziele&quot;> &quot;Neues Ziel erstellen&quot;und befolgen Sie die unten beschriebenen Schritte. |

## Schritt 1: Grundlegende Informationen bereitstellen

Dieser Abschnitt enthält Felder und Optionen, die den Analytics-Zielerstellungsprozess Beginn haben. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **Grundlegende Informationen** , um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine knappe Beschreibung ist eine effektive Methode, um mehr Informationen über ein Ziel zu definieren oder bereitzustellen.
4. *(Optional)* Lassen Sie in der Liste &quot; **Plattform** &quot;die Standardeinstellung auf **Alle**. Zurzeit tun diese Optionen nichts. Sie unterstützen Funktionen, die zu einem späteren Zeitpunkt hinzugefügt werden können.
5. Wählen Sie in der Liste **Kategorie** die Option **Adobe Experience Cloud**.
6. Wählen Sie in der Liste **Typ** die Option **Adobe Analytics**.
7. Klicken Sie auf **Speichern** , um die Konfigurationseinstellungen aufzurufen, oder auf **Datenexportbeschriftungen** , um Exportsteuerelemente auf das Ziel anzuwenden.

>[!NOTE]
>
>Bei einem Analytics-Ziel sind die Kontrollkästchen Zielzuordnung **automatisch ausfüllen** und **Segment-ID** standardmäßig aktiviert. Sie können diese Einstellungen nicht ändern.

![Basisinformationen](assets/basicinformation.png)

## Schritt 2: Datenexportsteuerelemente konfigurieren

Dieser Abschnitt enthält Optionen, mit denen [Datenexportsteuerelemente](/help/using/features/data-export-controls.md) auf ein Analytics-Ziel angewendet werden. Überspringen Sie diesen Schritt, wenn Sie keine Steuerelemente für den Datenexport verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **Datenexportsteuerelemente** , um die Steuerelemente anzuzeigen.
1. Wählen Sie eine Beschriftung aus, die der für das Ziel geltenden Datenexportkontrolle entspricht (siehe [Hinzufügen Datenexportbeschriftungen für ein Ziel](/help/using/features/destinations/add-data-export-labels.md) ). Bei Analytics-Zielen ist das Kontrollkästchen PII standardmäßig aktiviert.
1. Klicken Sie auf **Speichern**.

![exportControls](assets/exportControls.png)

## Schritt 3: Report Suites zuordnen

Im Abschnitt &quot;Konfiguration&quot;werden Ihre Analytics Report Suites Liste, die für die serverseitige Weiterleitung aktiviert wurden. Wenn Sie mehrere Analytics-Ziele haben, schließen sich die diesen Zielen zugewiesenen Report Suites gegenseitig aus und werden von Audience Manager erzwungen. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **Konfiguration** , um die Steuerelemente anzuzeigen.
1. Wählen Sie eine (oder mehrere) Report Suites aus, an die Sie Segmente senden möchten.
1. Klicken Sie auf **Speichern**.

![reportsuites](assets/reportSuites.png)

## Schritt 4: Segmentzuordnungen

Dieser Abschnitt enthält Optionen, mit denen Sie Segmente automatisch oder manuell zuordnen können.

| Zuordnungsoption | Beschreibung |
|---|---|
| Automatisches Zuordnen aller aktuellen und zukünftigen Segmente | Standardmäßig aktiviert sendet diese Funktion alle Segmente, für die ein Besucher pro Treffer qualifiziert ist, an Analytics. <br>  Wenn ein Besucher bei einem einzelnen Treffer zu mehr als 150 Audience Manager gehört, werden nur die zuletzt qualifizierten Segmente an Analytics gesendet, während die verbleibende Liste abgeschnitten wird. An Analytics wird eine zusätzliche Markierung gesendet, die angibt, dass die Liste des Segments abgeschnitten wurde. Diese Aktion wird als &quot;Begrenzung der Audience erreicht&quot;in der Dimension &quot;Audiencen-Name&quot;und als &quot;1&quot;in der Dimension &quot;Audiencen-ID&quot;angezeigt. Weitere Informationen finden Sie in den [häufig gestellten Fragen](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) . <br>  Diese Option wirkt sich auch auf die Zielverfügbarkeit im [Segmentaufbau](/help/using/features/segments/segment-builder.md)aus. Wenn beispielsweise ein Segment automatisch einem Analytics-Ziel zugeordnet wird, steht dieses Ziel im Abschnitt &quot; [Zielzuordnungen](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) &quot;des Segmentaufbaus nicht zur Auswahl zur Verfügung. Das Analytics-Ziel wird grau dargestellt und in der Spalte &quot;Typ&quot;des Destination-Browsers wird &quot;Analytics&quot;angezeigt. |
| Segmente manuell zuordnen | Diese Option zeigt Such- und Durchsuchen-Steuerelemente an, mit denen Sie auswählen können, welche Segmente Sie an Analytics senden möchten. <br>  So suchen Sie nach einem Segment <br>  <ol><li>Geben Sie den Segmentnamen oder die ID in das Suchfeld ein.</li><li>Klicken Sie auf <b>Hinzufügen.</b></li><li>Suchen Sie weiter und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol><br>  So suchen Sie nach einem Segment: <ol><li>Klicken Sie auf Alle Segmente <b>durchsuchen</b>. Dadurch wird eine Liste verfügbarer Segmente verfügbar gemacht.</li><li>Aktivieren Sie in der Liste das Kontrollkästchen des zu verwendenden Segments und klicken Sie auf <b>Hinzufügen Segmente</b>.</li><li>Klicken Sie im Fenster Hinzufügen Zuordnungen auf <b>Speichern</b> . Sie können die Zuordnungen, den Beginn oder das Enddatum während der Betaversion nicht ändern.</li><li>Gehen Sie weiter zum Durchsuchen und fügen Sie Segmente hinzu oder klicken Sie auf <b>Fertig</b>.</li></ol> ![mapsegmente](assets/mapSegments.png) |

## Nächste Schritte

Nachdem Sie ein Ziel erstellt und gespeichert haben, können Sie mit diesen Daten in Analytics arbeiten. Es kann jedoch einige Stunden dauern, bis Daten in den ausgewählten Report Suites verfügbar sind. See [Use the Audience Data in Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).

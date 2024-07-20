---
description: Mithilfe der Berichte zur Aktivitätsnutzung können Sie die Aktivitätsnutzung für Ihre Audience Manager-Instanz anzeigen und verfolgen, sodass Sie Ihre tatsächliche Nutzung mit Ihrer vertraglichen Verpflichtung vergleichen können.
keywords: Aktivität, Nutzung, Reporting, Bindung
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: Berichte zur Aktivitätsnutzung
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Überblick {#overview}

Mit dem [!UICONTROL Activity Usage Report] können Sie die Aktivitätsnutzung Ihrer Audience Manager-Instanz anzeigen und verfolgen und erhalten eine klare Vorstellung davon, wie Ihre Aktivitätsnutzung im Vergleich zu Ihrer vertraglichen Verpflichtung aussieht.

Darüber hinaus können Sie die [!UICONTROL Activity Usage Report] herunterladen, wann immer Sie benötigen, um Datensätze zu speichern und benutzerdefinierte Analysen zu erstellen.

## Zu beachten {#considerations}

Der [!UICONTROL Activity Usage Report] ist für alle Audience Manager mit [Administratorrechten](edit-account-settings.md) verfügbar.

>[!IMPORTANT]
>
>Der [!UICONTROL Activity Usage Report] zeigt die Nutzungsstatistiken Ihrer Audience Manager-Instanz an. Wenden Sie sich bei Abrechnungsanfragen im Zusammenhang mit Ihrer Aktivitätsnutzung an Ihren Adobe-Support-Mitarbeiter.

## Nutzungsszenarios {#use-cases}

Es gibt zwei Hauptanwendungsfälle von [!UICONTROL Activity Usage Report]:

* **Verfolgen der tatsächlichen Nutzung der Instanzaktivität anhand Ihrer Aktivitätsverwendungszusage**: Die meisten Audience Manager verfügen über eine monatliche geschätzte Aktivitätszusage pro Instanz, die dann in einer jährlichen Aktivitätszusage für alle Instanzen zusammengefasst wird. Dieser Bericht ist zwar kein Abrechnungsbericht, kann aber hilfreiche Anleitungen dazu bieten, ob Sie die zugesagte Aktivitätsnutzung überschreiten.
* **Validierung auf Implementierungsänderungen**: Wenn Sie Ihre Implementierung kürzlich aktualisiert haben, z. B. die Einrichtung der [!DNL Adobe Analytics] serverseitigen Weiterleitung oder die Änderung der [!DNL Adobe Target] Server-Aufrufeinstellungen, können Sie mit diesem Bericht überprüfen, ob das neue Aktivitätsvolumen mit Ihrem erwarteten Aktivitätsvolumen übereinstimmt.

## Verwenden des [!UICONTROL Activity Usage Report] {#using}

Um die [!UICONTROL Activity Usage Report] anzuzeigen, melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Verwenden Sie als Nächstes den Filter **[!UICONTROL Reporting Interval]** , um das Zeitintervall auszuwählen, für das der Bericht generiert werden soll. Sie können zwischen 30, 60, 90 Tagen oder einem benutzerdefinierten Datumsbereich wählen.

Sobald Ihr Bericht geladen wurde, können Sie eine Aufschlüsselung Ihrer [!UICONTROL Activities] für den ausgewählten Zeitraum sehen.

[!UICONTROL Activities] definiert die Gesamtsumme aller Onsite- und Offsite-Interaktionen mit Audience Manager und unterteilt in die folgenden Kategorien:

* **[!UICONTROL Server Calls]**: Jedes Datenerfassungs- oder Abrufereignis, das von Websites, Servern, E-Mails, Mobile Apps oder anderen Systemen an den Audience Manager gesendet wird.
* **[!UICONTROL Pixel Calls](ehemals [!UICONTROL Impression Server Calls])**: Daten, die aus Anzeigen erfasst wurden (z. B. Impressionsvolumen von einer Targeting-Plattform) oder E-Mail-Impressions-Aufrufe an Audience Manager. Dazu muss der Parameter `d_event` in der Abfragezeichenfolge vorhanden sein.
* **[!UICONTROL On-Boarded Records]**: Eindeutige Datensätze, die aus Ihrem eigenen Customer Relationship Management System (CRM) oder anderen Offline-Datendateien erfasst werden, z. B. Callcenter-Datensätze, Geräte-IDs und benutzerdefinierte Daten-Feeds von externen Datenanbietern.
* **[!UICONTROL Log File Records]**: Eindeutige Datensätze aus Protokolldateien, die von einer Targeting-Plattform in Audience Manager aufgenommen werden.

>[!NOTE]
>
>Ein eindeutiger Datensatz definiert jeden einzelnen Datensatz in einer Datei, die von Adobe im Auftrag eines Audience Manager gespeichert wird.

Außerdem können Sie die [!UICONTROL Activity Usage Trends]-Diagrammtypen verwenden, um zwischen zwei Diagrammtypen zu wechseln.

![aur-ui-graphs](assets/aur-ui-graphs.png)

Sie können auch mit dem Mauszeiger über ein bestimmtes Datum in der Timeline fahren, um die detaillierte Verwendung dieses Datums anzuzeigen.

![aur-hover](assets/aur-hover.png)

## Exportieren von [!UICONTROL Activity Usage Reports] {#export}

Um einen besseren Überblick über die Nutzungsstufe Ihrer Audience Manager-Aktivität zu erhalten, können Sie den [!UICONTROL Activity Usage Report] basierend auf der Art der Datensätze exportieren, die Sie einbeziehen möchten.

![aur-export](assets/aur-export.png)

Die **[!UICONTROL Onboarded Records Breakdown]** - und **[!UICONTROL Onsite Server Calls Breakdown]** -Berichte bieten den detailliertesten Einblick in die für diese Aktivitäten verfügbaren Quelldaten. Das diesen Aufschlüsselungen zugeordnete Volumen basiert auf Ihrer Implementierung.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Dieser Bericht enthält integrierte Datensätze, die nach Datenquelle aufgeschlüsselt sind.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Dieser Bericht enthält eine Aufschlüsselung der Server-Aufrufe aus drei Quellen: [!UICONTROL Analytics], [!UICONTROL Target] und [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Hierbei handelt es sich um abrechnungsfähige Server-Aufrufe, die von allen [!UICONTROL Adobe Analytics] -Instanzen an Audience Manager übergeben werden, einschließlich der serverseitigen Weiterleitung. Sekundäre Server-Aufrufe oder doppelte Server-Aufrufe (wie die serverseitige Weiterleitung von mehreren Report Suites) sind keine abrechnungsfähigen Aktivitäten, daher sind sie nicht in dieser Aufschlüsselung enthalten.
* **[!UICONTROL Target]**: Hierbei handelt es sich um serverseitige Aufrufe von [!UICONTROL Adobe Target] zu Audience Manager, um Audience Manager-Segmentdaten im Rahmen einer Server-zu-Server-Integration abzurufen.
* **[!UICONTROL Other]**: Umfasst Aufrufe von anderen Websites oder Systemen (Partner-Sites, direkte Server-Aufrufe usw.), mobile Browser-/App-Aufrufe über die Aufrufe [!DNL SDK], [!DNL DIL], Ereignis-Aufrufe und [!DNL DCS]. Enthält auch Aufrufe von [!DNL Target] , wenn diese als Cookie-Integration (und nicht von Server zu Server) eingerichtet wurden.

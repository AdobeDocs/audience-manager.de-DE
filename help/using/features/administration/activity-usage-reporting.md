---
description: Die Berichte zur Aktivitätsnutzung helfen Ihnen, die Aktivitätsnutzung für Ihre Audience Manager-Instanz anzuzeigen und zu verfolgen, sodass Sie Ihre tatsächliche Nutzung mit Ihrer vertraglichen Verpflichtung vergleichen können.
keywords: Aktivität, Nutzung, Reporting, Verpflichtung
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

Darüber hinaus können Sie die [!UICONTROL Activity Usage Report] zur Aufbewahrung von Aufzeichnungen und benutzerdefinierten Analysen herunterladen, wann immer Sie sie benötigen.

## Zu beachten {#considerations}

Die [!UICONTROL Activity Usage Report] steht allen Audience Manager-Benutzern mit &quot;[&quot; ](edit-account-settings.md).

>[!IMPORTANT]
>
>Im [!UICONTROL Activity Usage Report] werden die Statistiken zur Aktivitätsnutzung Ihrer Audience Manager-Instanz angezeigt. Falls Sie Fragen zur Rechnungsstellung bezüglich Ihrer Aktivitätsnutzung haben, wenden Sie sich bitte an Ihren Adobe-Ansprechpartner.

## Nutzungsszenarios {#use-cases}

Es gibt zwei Hauptanwendungsfälle der [!UICONTROL Activity Usage Report]:

* **Tracking der tatsächlichen Instanzaktivitätsnutzung anhand Ihrer Aktivitätsnutzungsverpflichtung**: Die meisten Kunden verfügen über eine monatliche geschätzte Aktivitätsverpflichtung pro Audience Manager-Instanz, die dann in einer jährlichen Aktivitätsverpflichtung über alle Instanzen hinweg kumuliert wird. Dieser Bericht ist zwar kein Abrechnungsbericht, aber er kann hilfreiche Hinweise darüber geben, ob die zugesicherte Aktivitätsnutzung überschritten wird.
* **Validierung auf Implementierungsänderungen**: Wenn Sie Ihre Implementierung kürzlich aktualisiert haben, z. B. [!DNL Adobe Analytics] Server-seitige Weiterleitung einrichten oder Ihre [!DNL Adobe Target] Server-Aufrufeinstellungen ändern, kann dieser Bericht Ihnen dabei helfen zu überprüfen, ob das neue Aktivitätsvolumen mit Ihrem erwarteten Aktivitätsvolumen übereinstimmt.

## Verwenden der [!UICONTROL Activity Usage Report] {#using}

Um die [!UICONTROL Activity Usage Report] anzuzeigen, melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Verwenden Sie als Nächstes den **[!UICONTROL Reporting Interval]**, um das Zeitintervall auszuwählen, für das der Bericht generiert werden soll. Sie können zwischen 30, 60, 90 Tagen oder einem benutzerdefinierten Datumsbereich wählen.

Sobald Ihr Bericht geladen ist, können Sie eine Aufschlüsselung Ihrer [!UICONTROL Activities] für den ausgewählten Zeitraum sehen.

[!UICONTROL Activities] die Gesamtsumme aller Onsite- und Offsite-Interaktionen mit Audience Manager zu definieren, aufgeteilt in die folgenden Kategorien:

* **[!UICONTROL Server Calls]**: Jedes Datenerfassungs- oder Abrufereignis, das von Websites, Servern, E-Mails, Mobile Apps oder anderen Systemen an den Audience Manager gesendet wird.
* **[!UICONTROL Pixel Calls] (früher als [!UICONTROL Impression Server Calls] bezeichnet)** Daten, die aus Anzeigen erfasst werden (z. B. das Impressionsvolumen von einer Zielgruppenbestimmungsplattform) oder E-Mail-Impressionsaufrufe an Audience Manager. Diese erfordern das Vorhandensein des `d_event` Parameters in der Abfragezeichenfolge.
* **[!UICONTROL On-Boarded Records]**: Eindeutige Datensätze, die von Ihrem eigenen CRM (Customer Relationship Management System) oder anderen Offline-Datendateien aufgenommen werden, wie Callcenter-Datensätze, Geräte-IDs und benutzerdefinierte Daten-Feeds von externen Datenanbietern.
* **[!UICONTROL Log File Records]**: Eindeutige Einträge aus Protokolldateien, die von einer Zielplattform in den Audience Manager aufgenommen wurden.

>[!NOTE]
>
>Ein eindeutiger Datensatz definiert jeden einzelnen Datensatz von Daten in einer Datei, die von Adobe im Namen eines Audience Manager-Kunden gespeichert wird.

Darüber hinaus können Sie die [!UICONTROL Activity Usage Trends] Diagrammtypen verwenden, um zwischen zwei Diagrammtypen zu wechseln.

![aur-ui-graphs](assets/aur-ui-graphs.png)

Sie können den Cursor auch über ein bestimmtes Datum in der Zeitleiste bewegen, um die detaillierte Verwendung für dieses Datum anzuzeigen.

![Luft-Hover](assets/aur-hover.png)

## [!UICONTROL Activity Usage Reports] exportieren {#export}

Um einen besseren Überblick über die Nutzungsaktivitäten Ihrer Audience Manager zu erhalten, können Sie die [!UICONTROL Activity Usage Report] je nach dem Typ der Datensätze exportieren, die Sie einbeziehen möchten.

![AuR-Export](assets/aur-export.png)

Die **[!UICONTROL Onboarded Records Breakdown]**- und **[!UICONTROL Onsite Server Calls Breakdown]**-Berichte bieten die detailliertesten Einblicke in die für diese Aktivitäten verfügbaren Quelldaten. Das diesen Aufschlüsselungen zugewiesene Volumen hängt von Ihrer Implementierung ab.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Dieser Bericht enthält integrierte Datensätze, aufgeschlüsselt nach Datenquelle.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Dieser Bericht enthält eine Aufschlüsselung der Server-Aufrufe aus drei Quellen: [!UICONTROL Analytics], [!UICONTROL Target] und [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Hierbei handelt es sich um kostenpflichtige Server-Aufrufe, die von allen [!UICONTROL Adobe Analytics]-Instanzen an den Audience Manager weitergeleitet werden, einschließlich Server-seitiger Weiterleitung. Sekundäre Server-Aufrufe oder doppelte Server-Aufrufe (wie im Fall der Server-seitigen Weiterleitung von mehreren Report Suites) sind keine kostenpflichtigen Aktivitäten und daher nicht in dieser Aufschlüsselung enthalten.
* **[!UICONTROL Target]**: Hierbei handelt es sich um Server-seitige Aufrufe von [!UICONTROL Adobe Target] an Audience Manager, um Audience Manager-Segmentdaten als Teil einer Server-zu-Server-Integration abzurufen.
* **[!UICONTROL Other]**: Umfasst Anrufe von einer anderen Website oder einem anderen System (Partner-Sites, direkte Server-Aufrufe usw.), mobile Browser-/App-Aufrufe über die [!DNL SDK], [!DNL DIL], Ereignisaufrufe und [!DNL DCS]. Enthält auch Aufrufe von [!DNL Target], wenn als Cookie-Integration (und nicht als Server-zu-Server-Integration) eingerichtet.

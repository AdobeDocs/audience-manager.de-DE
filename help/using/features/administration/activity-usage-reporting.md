---
description: Die Berichte zur Aktivitätsnutzung helfen Ihnen, die Aktivitätsnutzung für Ihre Audience Manager-Instanz anzuzeigen und zu verfolgen, sodass Sie Ihre tatsächliche Nutzung mit Ihrer vertraglichen Verpflichtung vergleichen können.
keywords: activity, usage, reporting, commitment
seo-description: Die Berichte zur Aktivitätsnutzung helfen Ihnen, die Aktivitätsnutzung für Ihre Audience Manager-Instanz anzuzeigen und zu verfolgen, sodass Sie Ihre tatsächliche Nutzung mit Ihrer vertraglichen Verpflichtung vergleichen können.
seo-title: Berichte zur Aktivitätsnutzung
solution: Audience Manager
title: Berichte zur Aktivitätsnutzung
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 7a3914af8fb225508f57724a75fe2547aac3f241

---


# Berichte zur Aktivitätsnutzung

## Überblick {#overview}

Die [!UICONTROL Activity Usage Report] hilft Ihnen, die Aktivitätsnutzung Ihrer Audience Manager-Instanz anzuzeigen und zu verfolgen, und gibt Ihnen eine klare Vorstellung davon, wie Ihre Aktivitätsnutzung mit Ihrer vertraglichen Verpflichtung verglichen wird.

Darüber hinaus können Sie die Datei [!UICONTROL Activity Usage Report] jederzeit herunterladen, um Aufzeichnungen und benutzerdefinierte Analysen zu erstellen.

## Zu beachten {#considerations}

Der [!UICONTROL Activity Usage Report] ist für alle Audience Manager-Benutzer mit [Administratorrechten](edit-account-settings.md)verfügbar.

> [!IMPORTANT]
>
> Der [!UICONTROL Activity Usage Report] zeigt die Statistiken zur Aktivitätsnutzung Ihrer Audience Manager-Instanz an. Wenden Sie sich bei Fragen zur Abrechnung im Zusammenhang mit Ihrer Aktivitätsnutzung an Ihren Adobe-Kundenbetreuer.

## Nutzungsszenarios {#use-cases}

Es gibt zwei wichtige Anwendungsfälle des [!UICONTROL Activity Usage Report]:

* **Verfolgung der tatsächlichen Nutzung der Instanzaktivität mit Ihrer Aktivitätsnutzung**: Die meisten Kunden verfügen über eine geschätzte monatliche Aktivitätsbereitstellung pro Audience Manager-Instanz, die dann in einer jährlichen Aktivitätsverpflichtung in allen Fällen kumuliert wird. Dieser Bericht ist zwar kein Rechnungsbericht, kann aber hilfreiche Anleitungen dazu bieten, ob Sie die zugesagte Aktivitätsnutzung überschreiten.
* **Überprüfung auf Änderungen** der Implementierung: Wenn Sie Ihre Implementierung kürzlich aktualisiert haben, z. B. die Einrichtung der serverseitigen Analytics-Weiterleitung oder die Änderung der Einstellungen für den Target-Server-Aufruf, hilft Ihnen dieser Bericht bei der Überprüfung, ob das neue Aktivitätsvolumen mit Ihrem erwarteten Aktivitätsvolumen übereinstimmt.

## Verwenden des Aktivitätsnutzungsberichts {#using}

Melden Sie sich [!UICONTROL Activity Usage Report]zum Anzeigen des Berichts bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]**>**[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Wählen Sie dann mit dem **[!UICONTROL Reporting Interval]**Filter das Zeitintervall aus, für das der Bericht generiert werden soll. Sie können zwischen 30, 60, 90 Tagen oder einem benutzerdefinierten Datumsbereich wählen.

Sobald Ihr Bericht geladen wurde, können Sie eine Aufschlüsselung Ihrer Daten [!UICONTROL Activities] für den ausgewählten Zeitraum sehen.

[!UICONTROL Activities] definieren Sie die Gesamtsumme aller Onsite- und Offsite-Interaktionen mit Audience Manager, aufgeteilt in die folgenden Kategorien:

* **[!UICONTROL Server Calls]**: Alle Datenerfassungs- oder -abrufereignisse, die von Websites, Servern, E-Mail, mobilen Anwendungen oder anderen Systemen an Audience Manager gesendet werden.
* **[!UICONTROL Pixel Calls](früher bekannt als[!UICONTROL Impression Server Calls])**: Daten, die aus Anzeigen (z. B. Impressionsvolumen von einer Targeting-Plattform) oder E-Mail-Impressionsaufrufen von Audience Manager erfasst wurden. Diese erfordern das Vorhandensein des `d_event` Parameters in der Abfragezeichenfolge.
* **[!UICONTROL On-Boarded Records]**: Eindeutige Datensätze, die von Ihrem eigenen CRM-System (Customer Relationship Management System) oder anderen Offlinedatendateien wie Call-Center-Aufzeichnungen, Geräte-IDs und benutzerdefinierte Datenfeeds von externen Datenanbietern erfasst werden.
* **[!UICONTROL Log File Records]**: Eindeutige Datensätze aus Protokolldateien, die von einer Targeting-Plattform in Audience Manager aufgenommen wurden.

> [!NOTE]
> Ein eindeutiger Datensatz definiert jeden einzelnen Datensatz in einer Datei, die von Adobe im Auftrag eines Audience Manager-Kunden gespeichert wird.

Außerdem können Sie die [!UICONTROL Activity Usage Trends] Diagrammtypen verwenden, um zwischen zwei Diagrammtypen zu wechseln.

![aur-ui-graphs](assets/aur-ui-graphs.png)

Sie können den Cursor auch über ein bestimmtes Datum in der Zeitleiste bewegen, um die detaillierte Verwendung für dieses Datum anzuzeigen.

![aur-hover](assets/aur-hover.png)

## Exportieren von Berichten zur Aktivitätsnutzung {#export}

Um einen besseren Überblick über die Nutzungsstufe Ihrer Audience Manager-Aktivität zu erhalten, können Sie die Datei [!UICONTROL Activity Usage Report] basierend auf dem gewünschten Datensatztyp exportieren.

![aur-export](assets/aur-export.png)

Die Berichte **[!UICONTROL Onboarded Records Breakdown]**und**[!UICONTROL Onsite Server Calls Breakdown]** Berichte bieten den granulärsten Einblick in die für diese Aktivitäten verfügbaren Quelldaten. Das Volumen, das diesen Aufschlüsselungen zugeordnet wird, hängt von Ihrer Implementierung ab.

### Aufschlüsselung der Onboarded-Datensätze {#onboarded-breakdown}

Dieser Bericht enthält nicht an Bord befindliche Datensätze, die nach Datenquelle aufgeschlüsselt sind.

### Aufschlüsselung von Onsite-Serveraufrufen {#onsite-breakdown}

Dieser Bericht enthält eine Aufschlüsselung der Serveraufrufe aus drei Quellen: [!UICONTROL Analytics], [!UICONTROL Target]und [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Hierbei handelt es sich um abrechnungsfähige Server-Aufrufe, die von allen Adobe Analytics-Instanzen an Audience Manager weitergeleitet werden, einschließlich der serverseitigen Weiterleitung. Sekundäre Serveraufrufe oder doppelte Serveraufrufe (wie im Falle der serverseitigen Weiterleitung aus mehreren Report Suites) sind keine abrechnungsfähigen Aktivitäten, daher werden sie nicht in diese Aufschlüsselung einbezogen.
* **[!UICONTROL Target]**: Dies sind serverseitige Aufrufe von Adobe Target zu Audience Manager, um Audience Manager-Segmentdaten im Rahmen einer Server-zu-Server-Integration abzurufen.
* **[!UICONTROL Other]**: Umfasst Aufrufe von anderen Websites oder Systemen (Partner-Sites, direkte Server-Aufrufe usw.), mobilen Browser-/App-Aufrufe über die[!DNL SDK],[!DNL DIL]Ereignisaufrufe und[!DNL DCS]-Aufrufe. Umfasst auch Aufrufe von[!DNL Target]Cookies, die als Cookie-Integration (nicht als Server-zu-Server) eingerichtet wurden.

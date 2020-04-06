---
description: Mit dem Berichte zur Aktivität-Nutzung können Sie die Nutzung der Aktivität für Ihre Audience Manager-Instanz verfolgen und die Ansicht Ihrer Daten verfolgen. So können Sie Ihre tatsächliche Nutzung mit Ihrer vertraglichen Verpflichtung vergleichen.
keywords: activity, usage, reporting, commitment
seo-description: Mit dem Berichte zur Aktivität-Nutzung können Sie die Nutzung der Aktivität für Ihre Audience Manager-Instanz verfolgen und die Ansicht Ihrer Daten verfolgen. So können Sie Ihre tatsächliche Nutzung mit Ihrer vertraglichen Verpflichtung vergleichen.
seo-title: Berichte zur Aktivität
solution: Audience Manager
title: Berichte zur Aktivität
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Berichte zur Aktivität

## Überblick {#overview}

Die [!UICONTROL Activity Usage Report] hilft Ihnen bei der Ansicht und Verfolgung der Aktivität in Ihrer Audience Manager-Instanz und gibt Ihnen eine klare Vorstellung davon, wie die Nutzung Ihrer Aktivität mit Ihrer vertraglichen Verpflichtung verglichen wird.

Darüber hinaus können Sie die [!UICONTROL Activity Usage Report] , wann immer Sie möchten, für die Aufbewahrung von Datensätzen und benutzerspezifische Analyse herunterladen.

## Zu beachten {#considerations}

Der [!UICONTROL Activity Usage Report] ist für alle Audience Manager-Benutzer mit [Administratorrechten](edit-account-settings.md)verfügbar.

>[!IMPORTANT]
>
>Der [!UICONTROL Activity Usage Report] zeigt die Nutzungsstatistik der Aktivität Ihrer Audience Manager-Instanz an. Wenden Sie sich bei Fragen zur Rechnungsstellung im Zusammenhang mit Ihrer Aktivität an Ihren Adobe-Kundenbetreuer.

## Nutzungsszenarios {#use-cases}

Es gibt zwei wichtige Anwendungsfälle des [!UICONTROL Activity Usage Report]:

* **Verfolgung der tatsächlichen Nutzung der Instanznutzung im Vergleich zu Ihrer Aktivität-Nutzungszusage**: Die meisten Kunden haben eine geschätzte monatliche Aktivität pro Audience Manager-Instanz, die dann in einer jährlichen Aktivität für alle Instanzen zusammengefasst wird. Dieser Bericht ist zwar kein Rechnungsbericht, kann aber hilfreiche Anleitungen dazu bieten, ob Sie die zugesagte Aktivität überschreiten.
* **Überprüfung auf Änderungen** der Implementierung: Wenn Sie Ihre Implementierung kürzlich aktualisiert haben, z. B. die Einrichtung der serverseitigen Analytics-Weiterleitung oder die Änderung der Serveraufrufeinstellungen für die Zielgruppe, können Sie mit diesem Bericht überprüfen, ob das Volumen der neuen Aktivität dem erwarteten Volumen der Aktivität entspricht.

## Verwenden des Aktivität-Nutzungsberichts {#using}

Melden Sie sich [!UICONTROL Activity Usage Report]zum Anzeigen des Berichts bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Wählen Sie dann mit dem **[!UICONTROL Reporting Interval]** Filter das Zeitintervall aus, für das der Bericht generiert werden soll. Sie können zwischen 30, 60, 90 Tagen oder einem benutzerdefinierten Datumsbereich wählen.

Sobald Ihr Bericht geladen wurde, können Sie eine Aufschlüsselung Ihrer Daten [!UICONTROL Activities] für den ausgewählten Zeitraum sehen.

[!UICONTROL Activities] definieren Sie die Aggregat-Gesamtanzahl aller Onsite- und Offsite-Interaktionen mit Audience Manager, aufgeteilt in die folgenden Kategorien:

* **[!UICONTROL Server Calls]**: Alle Datenerfassungs- oder -abruf-Ereignisse, die von Websites, Servern, E-Mail, mobilen Anwendungen oder anderen Systemen an Audience Manager gesendet werden.
* **[!UICONTROL Pixel Calls](früher bekannt als[!UICONTROL Impression Server Calls])**: Daten, die aus Anzeigen (z. B. Impressionsvolumen von einer Targeting-Plattform) oder E-Mail-Impressionsaufrufen an Audience Manager erfasst wurden. Diese erfordern das Vorhandensein des`d_event`Parameters in der Abfrage-Zeichenfolge.
* **[!UICONTROL On-Boarded Records]**: Eindeutige Datensätze, die von Ihrem eigenen CRM-System (Customer Relationship Management System) oder anderen Offlinedatendateien wie Call-Center-Aufzeichnungen, Geräte-IDs und benutzerdefinierte Datenfeeds von externen Datenanbietern erfasst werden.
* **[!UICONTROL Log File Records]**: Eindeutige Datensätze aus Protokolldateien, die von einer Targeting-Plattform in Audience Manager aufgenommen wurden.

>[!NOTE]
>
>Ein eindeutiger Datensatz definiert jeden einzelnen Datensatz in einer Datei, die von Adobe im Auftrag eines Audience Manager-Kunden gespeichert wird.

Außerdem können Sie die [!UICONTROL Activity Usage Trends] Diagrammtypen verwenden, um zwischen zwei Diagrammtypen zu wechseln.

![aur-ui-graphs](assets/aur-ui-graphs.png)

Sie können den Cursor auch über ein bestimmtes Datum in der Zeitleiste bewegen, um die detaillierte Verwendung für dieses Datum anzuzeigen.

![aur-hover](assets/aur-hover.png)

## Exportieren von Berichten zur Aktivität {#export}

Um einen besseren Überblick über die Verwendungsstufe Ihrer Audience Manager-Aktivität zu erhalten, können Sie die Datei [!UICONTROL Activity Usage Report] auf Grundlage der Datensatztypen exportieren, die Sie einbeziehen möchten.

![aur-export](assets/aur-export.png)

Die Berichte **[!UICONTROL Onboarded Records Breakdown]** und **[!UICONTROL Onsite Server Calls Breakdown]** Berichte bieten den granulärsten Einblick in die für diese Aktivitäten verfügbaren Quelldaten. Das Volumen, das diesen Aufschlüsselungen zugeordnet wird, hängt von Ihrer Implementierung ab.

### Aufschlüsselung der Onboarded-Datensätze {#onboarded-breakdown}

Dieser Bericht enthält nicht an Bord befindliche Datensätze, die nach Datenquelle aufgeschlüsselt sind.

### Aufschlüsselung von Onsite-Serveraufrufen {#onsite-breakdown}

Dieser Bericht enthält eine Aufschlüsselung der Server-Aufrufe aus drei Quellen: [!UICONTROL Analytics], [!UICONTROL Target]und [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Hierbei handelt es sich um abrechnungsfähige Serveraufrufe, die von allen Adobe Analytics-Instanzen an Audience Manager weitergeleitet werden, einschließlich der serverseitigen Weiterleitung. Sekundäre Serveraufrufe oder Duplikat-Server-Aufrufe (wie bei serverseitiger Weiterleitung aus mehreren Report Suites) sind keine abrechnungsfähigen Aktivitäten, daher werden sie in dieser Aufschlüsselung nicht berücksichtigt.
* **[!UICONTROL Target]**: Dies sind serverseitige Aufrufe von Adobe Zielgruppe zu Audience Manager, um die Segmentdaten von Audience Manager im Rahmen einer Server-zu-Server-Integration abzurufen.
* **[!UICONTROL Other]**: Umfasst Aufrufe von anderen Websites oder Systemen (Partner-Sites, direkte Server-Aufrufe usw.), mobilen Browser-/App-Aufrufe über die [!DNL SDK], [!DNL DIL]Ereignis- und [!DNL DCS] Anrufe. Umfasst auch Aufrufe von [!DNL Target] Cookies, die als Cookie-Integration (nicht als Server-zu-Server) eingerichtet wurden.

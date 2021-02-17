---
description: Aktivität Usage Berichte hilft Ihnen bei der Ansicht und Verfolgung der Nutzung der Aktivität für Ihre Audience Manager-Instanz, sodass Sie Ihre tatsächliche Nutzung mit Ihrer vertraglichen Verpflichtung vergleichen können.
keywords: Aktivität, Nutzung, Berichte, Bindung
seo-description: Aktivität Usage Berichte hilft Ihnen bei der Ansicht und Verfolgung der Nutzung der Aktivität für Ihre Audience Manager-Instanz, sodass Sie Ihre tatsächliche Nutzung mit Ihrer vertraglichen Verpflichtung vergleichen können.
seo-title: Berichte zur Aktivitätsnutzung
solution: Audience Manager
title: Berichte zur Aktivitätsnutzung
topic: Activity Usage Reporting
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 6%

---


# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Überblick {#overview}

Mit dem [!UICONTROL Activity Usage Report] können Sie die Aktivitätsnutzung Ihrer Audience Manager-Instanz anzeigen und verfolgen und erhalten eine klare Vorstellung davon, wie Ihre Aktivitätsnutzung im Vergleich zu Ihrer vertraglichen Verpflichtung aussieht.

Außerdem können Sie die [!UICONTROL Activity Usage Report] jederzeit herunterladen, um die Aufzeichnung und benutzerdefinierte Analyse zu verwalten.

## Zu beachten {#considerations}

Das [!UICONTROL Activity Usage Report] steht allen Audience Manager mit [Administratorberechtigungen](edit-account-settings.md) zur Verfügung.

>[!IMPORTANT]
>
>Das [!UICONTROL Activity Usage Report] zeigt die Nutzungsstatistik der Aktivität Ihrer Audience Manager-Instanz an. Wenden Sie sich bei Fragen zur Rechnungsstellung im Zusammenhang mit Ihrer Aktivität an Ihren Kundenbetreuer.

## Nutzungsszenarios {#use-cases}

Es gibt zwei Hauptverwendungsfälle von [!UICONTROL Activity Usage Report]:

* **Verfolgung der tatsächlichen Nutzung der Instanznutzung im Vergleich zu Ihrer Aktivität-Nutzungszusage**: Die meisten Kunden haben eine monatliche geschätzte Aktivität pro Instanz, die dann zu einer jährlichen Aktivität in allen Fällen kumuliert wird. Dieser Bericht ist zwar kein Rechnungsbericht, kann aber hilfreiche Anleitungen dazu bieten, ob Sie die zugesagte Aktivität überschreiten.
* **Überprüfung auf Änderungen** der Implementierung: Wenn Sie Ihre Implementierung kürzlich aktualisiert haben, z. B. die Einrichtung der  [!DNL Adobe Analytics] serverseitigen Weiterleitung oder die Änderung der  [!DNL Adobe Target] Serveraufrufeinstellungen, hilft Ihnen dieser Bericht bei der Überprüfung, ob das Volumen der neuen Aktivität mit dem erwarteten Volumen der Aktivität übereinstimmt.

## Wenn die [!UICONTROL Activity Usage Report] {#using}

Um das [!UICONTROL Activity Usage Report] anzuzeigen, melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Verwenden Sie anschließend den Filter **[!UICONTROL Reporting Interval]**, um das Zeitintervall auszuwählen, für das der Bericht generiert werden soll. Sie können zwischen 30, 60, 90 Tagen oder einem benutzerdefinierten Datumsbereich wählen.

Nach dem Laden des Berichts wird eine Aufschlüsselung Ihrer [!UICONTROL Activities] für den ausgewählten Zeitraum angezeigt.

[!UICONTROL Activities] definieren Sie die Aggregat-Gesamtsumme aller Onsite- und Offsite-Interaktionen mit Audience Manager, aufgeteilt in die folgenden Kategorien:

* **[!UICONTROL Server Calls]**: Alle Datenerfassungs- oder -abruf-Ereignisse, die von Websites, Servern, E-Mail, mobilen Anwendungen oder anderen Systemen an Audience Manager gesendet werden.
* **[!UICONTROL Pixel Calls](früher bekannt als  [!UICONTROL Impression Server Calls])**: Daten, die aus Anzeigen (z. B. Impressionsvolumen von einer Targeting-Plattform) oder E-Mail-Impressionsaufrufen an Audience Manager gesammelt wurden. Dazu muss der Parameter `d_event` in der Abfrage-Zeichenfolge vorhanden sein.
* **[!UICONTROL On-Boarded Records]**: Eindeutige Datensätze, die von Ihrem eigenen CRM-System (Customer Relationship Management System) oder anderen Offlinedatendateien wie Call-Center-Aufzeichnungen, Geräte-IDs und benutzerdefinierte Datenfeeds von externen Datenanbietern erfasst werden.
* **[!UICONTROL Log File Records]**: Eindeutige Datensätze aus Protokolldateien, die von einer Targeting-Plattform in Audience Manager aufgenommen wurden.

>[!NOTE]
>
>Ein eindeutiger Datensatz definiert jeden einzelnen Datensatz in einer Datei, die von der Adobe im Auftrag eines Audience Manager gespeichert wird.

Außerdem können Sie die Diagrammtypen [!UICONTROL Activity Usage Trends] verwenden, um zwischen zwei Diagrammtypen zu wechseln.

![aur-ui-graphs](assets/aur-ui-graphs.png)

Sie können den Cursor auch über ein bestimmtes Datum in der Zeitleiste bewegen, um die detaillierte Verwendung für dieses Datum anzuzeigen.

![aur-hover](assets/aur-hover.png)

## Exportieren von [!UICONTROL Activity Usage Reports] {#export}

Um einen besseren Überblick über die Nutzungsstufe Ihrer Audience Manager-Aktivität zu erhalten, können Sie das [!UICONTROL Activity Usage Report] basierend auf dem Typ der Datensätze exportieren, die Sie einbeziehen möchten.

![aur-export](assets/aur-export.png)

Die Berichte **[!UICONTROL Onboarded Records Breakdown]** und **[!UICONTROL Onsite Server Calls Breakdown]** bieten den granulärsten Einblick in die für diese Aktivitäten verfügbaren Quelldaten. Das Volumen, das diesen Aufschlüsselungen zugeordnet wird, hängt von Ihrer Implementierung ab.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Dieser Bericht enthält nicht an Bord befindliche Datensätze, die nach Datenquelle aufgeschlüsselt sind.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Dieser Bericht enthält eine Aufschlüsselung der Server-Aufrufe aus drei Quellen: [!UICONTROL Analytics], [!UICONTROL Target] und [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Hierbei handelt es sich um abrechnungsfähige Serveraufrufe, die von allen  [!UICONTROL Adobe Analytics] Instanzen an Audience Manager weitergeleitet werden, einschließlich der serverseitigen Weiterleitung. Sekundär Serveraufrufe oder Duplikat-Server-Aufrufe (wie bei serverseitiger Weiterleitung aus mehreren Report Suites) sind keine abrechnungsfähigen Aktivitäten, daher werden sie nicht in diese Aufschlüsselung einbezogen.
* **[!UICONTROL Target]**: Dies sind serverseitige Aufrufe von  [!UICONTROL Adobe Target] zu Audience Manager, um Audience Manager-Segmentdaten im Rahmen einer Server-zu-Server-Integration abzurufen.
* **[!UICONTROL Other]**: Umfasst Aufrufe von anderen Websites oder Systemen (Partner-Sites, direkte Server-Aufrufe usw.), mobilen Browser-/App-Aufrufe über die  [!DNL SDK],  [!DNL DIL]Ereignis- und  [!DNL DCS] Anrufe. Umfasst auch Aufrufe von [!DNL Target], wenn diese als Cookie-Integration (nicht als Server-zu-Server) eingerichtet wurden.

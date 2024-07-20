---
description: Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf die Zeit aus, die zum Verarbeiten Ihrer Daten und Generieren von Berichtsergebnissen benötigt wird. In diesem Abschnitt wird beschrieben, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Außerdem handelt es sich bei den hier beschriebenen Zeitrahmen und Zeitplänen nur um allgemeine Richtlinien. Diese Zeitpläne stellen keine Service-Level-Vereinbarungen (SLAs) oder Verpflichtungen im Zusammenhang mit der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeitpläne und Zeitpläne jederzeit ohne Vorankündigung zu ändern.
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: Auswirkungen von Datenbereitstellungs- und Dateiverarbeitungszeiten auf Berichte
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 1%

---

# Auswirkungen von Datenbereitstellungs- und Dateiverarbeitungszeiten auf Berichte{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf die Zeit aus, die zum Verarbeiten Ihrer Daten und Generieren von Berichtsergebnissen benötigt wird. In diesem Abschnitt wird beschrieben, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Außerdem handelt es sich bei den hier beschriebenen Zeitrahmen und Zeitplänen nur um allgemeine Richtlinien. Diese Zeitpläne stellen keine Service-Level-Vereinbarungen (SLAs) oder Verpflichtungen im Zusammenhang mit der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeitpläne und Zeitpläne jederzeit ohne Vorankündigung zu ändern.

## Berichtsnummern {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

In der folgenden Tabelle sind die Zeitintervalle in unseren allgemeinen und Echtzeitberichten aufgeführt und beschrieben.


| Datentyp | Beschreibung |
|---|---|
| Echtzeitdaten | Die Echtzeit-Zahlen für heute gelten für die Stunden 00:00 bis 23:59:59 UTC von gestern. |
| Allgemeine Berichtsdaten | Die Daten in den [allgemeinen Berichten](../reporting/general-reports.md#general-reports-overview) hängen vom erfolgreichen Abschluss anderer Auftragsprozesse und der Menge der an einem bestimmten Tag empfangenen Daten ab. Meistens sollten [!UICONTROL General Report] -Daten täglich um 18:00 UTC aktualisiert werden. |

## Eingehende und ausgehende Dateiübertragungen {#inbound-outbound-file-transfers}

[!DNL Audience Manager] verarbeitet und sendet eingehende und ausgehende [!UICONTROL Server-to-Server (S2S)] Dateiübertragungen gemäß den in diesem Abschnitt beschriebenen Zeitplänen. Angesichts dieser Zeitpläne und der Cut-off-Zeiten können Sie Abweichungen bei neuen Segmenten zwischen Echtzeit- und Gesamtsegmentzahlen feststellen.

| Dateityp | Beschreibung |
|---|---|
| Aufnahme eingehender Dateien (Offline-Daten) | Die Dateiverarbeitung wird zweimal täglich ausgeführt. Diese Verfahren erfassen Daten und bereiten sie für die Bereitstellung vor. Die Zeiten für die Dateibereitstellung variieren, da sie von der Gesamtzahl der zu verarbeitenden Kundendaten betroffen sind. Sie sollten eine maximale Latenz von 48 Stunden zwischen dem Zeitpunkt erwarten, zu dem die Datei in Audience Manager hochgeladen wird, und dem Zeitpunkt, zu dem die Daten für die Berichterstellung und Aktivierung verfügbar sind. |
| Ausgehende (Export-)Dateien | Die Dateiverarbeitung und -zustellung erfolgt einmal täglich, etwa um 14:00 UTC. Beachten Sie, dass die Verarbeitung und der Versand von der Gesamtzahl und Größe dieser Dateien betroffen sind. In einigen Fällen kann die Dateiverarbeitung bis zu 24 Stunden verzögern. In diesem Fall sendet Audience Manager 2 Dateien für einen bestimmten Tag anstelle von 1. Wir werden unsere Kunden benachrichtigen, wenn Audience Manager die Verarbeitung einer Datei ganz beenden muss. Unter diesen Umständen ist es schwierig, die Lieferzeiten für ausgehende Daten abzuschätzen. Um festzustellen, ob Sie einen vollständigen Dateisatz erhalten haben, überprüfen Sie den Zeitstempel und suchen Sie nach fehlenden Tagen. Dies ist ein 13-stelliger UNIX-UTC-Zeitstempel, der den Zeitpunkt der Erstellung der Datei aufzeichnet. Siehe [Ausgehende Datenübertragungen in Echtzeit](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Protokolldateien für Anzeigen-Server | Die Dateiverarbeitung wird nahezu in Echtzeit ausgeführt, um Protokolldateidatensätze aufzunehmen, sobald die stündlichen Dateien bereit sind. Der Prozess zur Vorbereitung der Dateien für die Berichterstellung wird einmal täglich ausgeführt. Die Zeiten für die Dateibereitstellung variieren, da sie von der Gesamtzahl der zu verarbeitenden Kundendaten betroffen sind. Sie sollten von einer maximalen Latenz von 48 Stunden zwischen dem Zeitpunkt, zu dem Sie die Datei in den Audience Manager hochladen, und dem Zeitpunkt ausgehen, zu dem die Daten für die Berichterstellung und Aktivierung verfügbar sind. |

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zur Erfassung von eingehenden Kundendaten](../faq/faq-inbound-data-ingestion.md)

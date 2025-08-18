---
description: Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf die Zeit aus, die für die Verarbeitung Ihrer Daten und die Generierung von Berichtsergebnissen benötigt wird. Der Inhalt in diesem Abschnitt beschreibt, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Auch die hier beschriebenen Zeitrahmen und Zeitpläne sind nur allgemeine Richtlinien. Diese Zeitpläne stellen keine Service Level Agreements (SLAs) oder Verpflichtungen im Zusammenhang mit der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeitrahmen und Zeitpläne jederzeit und ohne Vorankündigung zu ändern.
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: Wie sich Datenversand- und Dateiverarbeitungszeiten auf Berichte auswirken
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 1%

---

# Wie sich Datenversand- und Dateiverarbeitungszeiten auf Berichte auswirken{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf die Zeit aus, die für die Verarbeitung Ihrer Daten und die Generierung von Berichtsergebnissen benötigt wird. Der Inhalt in diesem Abschnitt beschreibt, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Auch die hier beschriebenen Zeitrahmen und Zeitpläne sind nur allgemeine Richtlinien. Diese Zeitpläne stellen keine Service Level Agreements (SLAs) oder Verpflichtungen im Zusammenhang mit der Datenbereitstellung dar. Adobe behält sich das Recht vor, die Zeitrahmen und Zeitpläne jederzeit und ohne Vorankündigung zu ändern.

## Berichtszahlen {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

In der folgenden Tabelle werden die Zeitintervalle in unseren allgemeinen Berichten und Echtzeitberichten aufgelistet und beschrieben.


| Datentyp | Beschreibung |
|---|---|
| Echtzeitdaten | Die Echtzeitzahlen für heute sind für die Stunden 00::00 bis 23::59: UTC von gestern. |
| Allgemeine Berichtsdaten | Die Daten in [Allgemeine Berichte](../reporting/general-reports.md#general-reports-overview) hängen vom erfolgreichen Abschluss anderer Auftragsvorgänge und der Menge der für einen bestimmten Tag empfangenen Daten ab. In den meisten Fällen sollten [!UICONTROL General Report] Daten täglich um 18 % :00 werden. |

## Eingehende und ausgehende Dateiübertragungen {#inbound-outbound-file-transfers}

[!DNL Audience Manager] verarbeitet und sendet eingehende und ausgehende [!UICONTROL Server-to-Server (S2S)]-Dateiübertragungen gemäß den in diesem Abschnitt beschriebenen Zeitplänen. Angesichts dieser Zeitpläne und der Annahmeschlüsse kann es zu Diskrepanzen bei neuen Segmenten zwischen der Echtzeit- und der Gesamtsegmentanzahl kommen.

| Dateityp | Beschreibung |
|---|---|
| Aufnahme eingehender Dateien (Offline-Daten) | Die Dateiverarbeitung wird zweimal täglich ausgeführt. Diese Verfahren nehmen Daten auf und bereiten sie für die Bereitstellung vor. Die Dateibereitstellungszeiten variieren, da sie von der Gesamtmenge der zu verarbeitenden Kundendaten beeinflusst werden. Zwischen dem Zeitpunkt, zu dem die Datei in Audience Manager hochgeladen wird, und dem Zeitpunkt, zu dem die Daten für das Reporting und die Aktivierung verfügbar sind, sollte eine maximale Latenz von 48 Stunden erwartet werden. |
| Ausgehende Dateien (Export) | Dateiverarbeitung und -versand erfolgen einmal täglich um ca. 14 :00 UTC. Beachten Sie, dass die Verarbeitung und der Versand von der Gesamtzahl und Größe dieser Dateien beeinflusst werden. In einigen Fällen kann es zu einer Verzögerung der Dateiverarbeitung von bis zu 24 Stunden kommen. In diesem Fall sendet Audience Manager zwei Dateien für einen bestimmten Tag anstelle von einem. Wir werden unsere Kunden in dem seltenen Fall benachrichtigen, in dem Audience Manager die Verarbeitung einer Datei vollständig einstellen muss. Unter diesen Bedingungen ist es schwierig, die Lieferzeiten für ausgehende Daten zu schätzen. Um festzustellen, ob Sie einen vollständigen Satz von Dateien erhalten haben, überprüfen Sie den Zeitstempel und suchen Sie nach fehlenden Tagen. Dies ist ein 13-stelliger UNIX-UTC-Zeitstempel, der den Zeitpunkt aufzeichnet, zu dem die Datei erstellt wurde. Siehe [Ausgehende Datenübertragungen in Echtzeit](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Anzeigen-Server-Protokolldateien | Die Dateiverarbeitung wird nahezu in Echtzeit ausgeführt, um Protokolldateieinträge aufzunehmen, da die stündlichen Dateien bereit sind. Der Prozess zur Vorbereitung der Dateien für das Reporting wird einmal täglich ausgeführt. Die Dateibereitstellungszeiten variieren, da sie von der Gesamtmenge der zu verarbeitenden Kundendaten beeinflusst werden. Zwischen dem Zeitpunkt, zu dem Sie die Datei in Audience Manager hochladen, und dem Zeitpunkt, zu dem die Daten für das Reporting und die Aktivierung verfügbar sind, sollte eine maximale Latenz von 48 Stunden erwartet werden. |

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zur Erfassung von eingehenden Kundendaten](../faq/faq-inbound-data-ingestion.md)

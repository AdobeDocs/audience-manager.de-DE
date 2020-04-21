---
description: Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf den Zeitraum aus, der für die Verarbeitung Ihrer Daten und die Generierung von Berichtsergebnissen benötigt wird. In diesem Abschnitt wird beschrieben, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Die hier beschriebenen Zeitrahmen und Zeitpläne sind ebenfalls nur allgemeine Richtlinien. Diese Pläne stellen keine Serviceleistungsvereinbarungen (SLAs) oder Verpflichtungen im Zusammenhang mit dem Versand von Daten dar. Adobe behält sich das Recht vor, die Zeiträume und Zeitpläne jederzeit und ohne Vorankündigung zu ändern.
seo-description: Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf den Zeitraum aus, der für die Verarbeitung Ihrer Daten und die Generierung von Berichtsergebnissen benötigt wird. In diesem Abschnitt wird beschrieben, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Die hier beschriebenen Zeitrahmen und Zeitpläne sind ebenfalls nur allgemeine Richtlinien. Diese Pläne stellen keine Serviceleistungsvereinbarungen (SLAs) oder Verpflichtungen im Zusammenhang mit dem Versand von Daten dar. Adobe behält sich das Recht vor, die Zeiträume und Zeitpläne jederzeit und ohne Vorankündigung zu ändern.
seo-title: Auswirkungen von Versand- und Dateiverarbeitungszeiten auf Berichte
solution: Audience Manager
title: Auswirkungen von Versand- und Dateiverarbeitungszeiten auf Berichte
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: 6bdf79b17ec96ed0d54ed97ab5d69fadb68763b5

---


# Auswirkungen von Versand- und Dateiverarbeitungszeiten auf Berichte{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager erhält täglich eine enorme Datenmenge. Dies wirkt sich auf den Zeitraum aus, der für die Verarbeitung Ihrer Daten und die Generierung von Berichtsergebnissen benötigt wird. In diesem Abschnitt wird beschrieben, wie sich diese Zeitintervalle auf Ihr Audience Manager-Konto auswirken. Die hier beschriebenen Zeitrahmen und Zeitpläne sind ebenfalls nur allgemeine Richtlinien. Diese Pläne stellen keine Serviceleistungsvereinbarungen (SLAs) oder Verpflichtungen im Zusammenhang mit dem Versand von Daten dar. Adobe behält sich das Recht vor, die Zeiträume und Zeitpläne jederzeit und ohne Vorankündigung zu ändern.

## Berichte {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

In der folgenden Tabelle sind die Zeitintervalle in unseren allgemeinen und Echtzeitberichten aufgeführt und beschrieben.


| Datentyp | Beschreibung |
|---|---|
| Echtzeitdaten | Echtzeit-Nummern für heute gelten für die Stunden 00:00 bis 23:59:59 UTC von gestern. |
| Allgemeine Berichtsdaten | Die Daten in den [allgemeinen Berichten](../reporting/general-reports.md#general-reports-overview) hängen vom erfolgreichen Abschluss anderer Auftragsabläufe und der Menge der an einem bestimmten Tag empfangenen Daten ab. In den meisten Fällen sollten die [!UICONTROL General Report] Daten täglich um 18.00 Uhr UTC aktualisiert werden. |

## Dateiübertragungen in- und ausgehende {#inbound-outbound-file-transfers}

[!DNL Audience Manager] verarbeitet und sendet eingehende und ausgehende [!UICONTROL Server-to-Server (S2S)] Dateiübertragungen gemäß den in diesem Abschnitt beschriebenen Zeitplänen. Angesichts dieser Zeitpläne und der Cut-off-Zeiten können bei neuen Segmenten zwischen Echtzeit- und Gesamtsegmentzahlen Diskrepanzen auftreten.

| Dateityp | Beschreibung |
|---|---|
| Inbound File Ingestion (Offlinedaten) | Die Dateiverarbeitung wird zweimal täglich ausgeführt. Diese Verfahren erfassen Daten und bereiten sie für den Versand vor. Die Versand der Datei variieren, da sie von der Gesamtanzahl der zu verarbeitenden Kundendaten betroffen sind. Sie sollten eine maximale Latenz von 48 Stunden zwischen dem Zeitpunkt, zu dem die Datei in Audience Manager hochgeladen wird, und dem Zeitpunkt erwarten, zu dem die Daten für Berichte und Aktivierung verfügbar sind. |
| Ausgehende Dateien (Export) | Die Dateiverarbeitung und der Versand erfolgt einmal täglich um etwa 14:00 Uhr UTC. Denken Sie daran, dass die Gesamtanzahl und -größe dieser Dateien Auswirkungen auf die Verarbeitung und den Versand haben. In einigen Fällen kann es zu einer Verzögerung bei der Dateiverarbeitung bis zu 24 Stunden kommen. In diesem Fall sendet Audience Manager 2 Dateien für einen bestimmten Tag anstelle von 1. In seltenen Fällen, in denen Audience Manager die Verarbeitung einer Datei ganz einstellen muss, werden wir unsere Kunden benachrichtigen. Angesichts dieser Umstände ist es schwierig, die Versand für ausgehende Daten zu schätzen. Um festzustellen, ob Sie einen vollständigen Satz von Dateien erhalten haben, überprüfen Sie den Zeitstempel und suchen Sie nach fehlenden Tagen. Dies ist ein 13-stelliger UNIX UTC-Zeitstempel, der den Zeitpunkt der Erstellung der Datei aufzeichnet. Siehe [Ausgehende Datenübertragungen](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)in Echtzeit. |
| Protokolldateien des Anzeigenservers | Die Dateiverarbeitung wird in Echtzeit ausgeführt, um Protokolldateidatensätze zu erfassen, sobald die stündlichen Dateien bereit sind. Der Vorgang zum Vorbereiten der Dateien für den Berichte wird einmal täglich ausgeführt. Die Versand der Datei variieren, da sie von der Gesamtanzahl der zu verarbeitenden Kundendaten betroffen sind. Sie sollten eine maximale Latenz von 48 Stunden zwischen dem Zeitpunkt, zu dem Sie die Datei in Audience Manager hochladen, und dem Zeitpunkt erwarten, zu dem die Daten für Berichte und Aktivierung verfügbar sind. |

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten](../faq/faq-inbound-data-ingestion.md)


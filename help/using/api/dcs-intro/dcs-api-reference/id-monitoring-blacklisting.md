---
description: Der DCS überwacht die erhaltenen IDs und listet diejenigen auf, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden.
keywords: id;Monitoring;Blacklisting;dcs
seo-description: Der DCS überwacht die erhaltenen IDs und listet diejenigen auf, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden.
seo-title: ID-Überwachung und Blacklisting
solution: Audience Manager
title: ID-Überwachung und Blacklisting
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID-Überwachung und Blacklisting

Die [!UICONTROL DCS] überwacht die IDs, die sie erhält, und führt diejenigen auf, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden.

## Überblick

Zum Schutz der Audience Manager-Infrastruktur vor böswilligen Aktivitäten [!UICONTROL DCS] verwendet die Gruppe einen erweiterten Algorithmus, um die erhaltenen IDs zu überwachen. Dabei kann es sich um [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) oder [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) handeln. Ausführliche Erläuterungen zu den von Audience Manager unterstützten IDs finden Sie unter [IDs in Audience Manager](../../../reference/ids-in-aam.md) .

Die [!UICONTROL DCS] überwacht die Häufigkeit, mit der sie diese IDs erhält, um potenzielle bösartige Aktivitäten zu erkennen. Wenn der [!UICONTROL DCS] Benutzer eine ungewöhnlich große Anzahl von [!UICONTROL DCS] Anforderungen für eine bestimmte ID in kurzer Zeit erkennt, wird diese ID auf die schwarze Liste gesetzt.

## Fehlercodes

Sie können die schwarzen IDs anhand der Fehlercodes identifizieren, die vom [!UICONTROL DCS]. Die Fehlercodes, die Sie möglicherweise erhalten, sind:

* 303: Blockierte Kunden-ID;
* 306: Blockierte deklarierte Geräte-ID;
* 307: Blockierter Profilvorgang für ID.

Einzelheiten zu den Fehlercodes, die Sie möglicherweise erhalten, finden Sie unter [DCS-Fehlercodes, -Meldungen und -Beispiele](dcs-error-codes.md) .

## Nicht-schwarze Liste

Blacklist-IDs sollten in zukünftigen Anforderungen nicht verwendet werden, da sie zu fehlerhaften Datenberichten führen. Die [!UICONTROL DCS] Option zur Aufhebung der schwarzen Liste von IDs wird nicht unterstützt.

## Auswirkungen auf die ID-Synchronisierung

[!UICONTROL DCS] -Aufrufe können einen oder mehrere ID-Typen enthalten. Aufrufe, die eine einzelne ID enthalten, werden vollständig ignoriert, wenn diese ID auf der Blacklist steht, und in diesem Fall findet keine ID-Synchronisierung statt.

Wenn ein Aufruf mit mehreren IDs auch eine ID in der schwarzen Liste enthält, ignoriert der [!UICONTROL DCS] Aufruf die schwarze Liste und verwendet nur die verbleibenden, nicht in der schwarzen Liste aufgeführten IDs für die Synchronisierung.

## Ursachen und Fehlerbehebungen für ID Blacklisting

Die häufigste Ursache für die Sperrung von IDs ist die falsche Integration zwischen der Kundeninfrastruktur und Audience Manager. Wenn Sie eine in der schwarzen Liste aufgeführte ID identifizieren, überprüfen Sie Ihre Audience Manager-Integrationen gründlich. Ausführliche Erläuterungen zur Konfiguration von Audience Manager für die Verwendung mit anderen Experience Cloud-Lösungen oder externen Systemen finden Sie in den **Implementierungs- und Integrationsanleitungen** .

Eine weitere häufige Ursache für die Sperrung von IDs ist das Indizieren von Bots (Webcrawler), was im Allgemeinen zu einer Zunahme des Traffics führt, sodass dieselben IDs mehrmals an die [!UICONTROL DCS] gesendet werden. Wenn Sie die Indizierung von Bots als Grund für die schwarze Liste von IDs identifizieren, sollten Sie den Bot-Zugriff auf Ihre Website einschränken.

Wenn Sie Probleme mit der Integration nur schwer erkennen können, wenden Sie sich bitte an den Kundensupport. Bevor Sie eine Supportanfrage öffnen, stellen Sie sicher, dass das `.har` `HTTP` Archiv Ihres Browsers bereit ist. Dieses Archiv hilft dem Supportteam herauszufinden, warum die ID-Blacklist auftrat.
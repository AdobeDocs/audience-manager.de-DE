---
description: Das DCS überwacht die empfangenen IDs und die schwarzen Listen, die in einer kurzen Zeitspanne ungewöhnlich hoch gesendet werden.
keywords: id; Überwachung; blacklisting; dcs
seo-description: Das DCS überwacht die empfangenen IDs und die schwarzen Listen, die in einer kurzen Zeitspanne ungewöhnlich hoch gesendet werden.
seo-title: ID-Überwachung und Blacklisting
solution: Audience Manager
title: ID-Überwachung und Blacklisting
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID-Überwachung und Blacklisting

The [!UICONTROL DCS] monitors the IDs it receives and blacklists those that are being sent at an unusually high rate over a short period of time.

## Überblick

To protect the Audience Manager infrastructure against malicious activity, the [!UICONTROL DCS] uses an advanced algorithm to monitor the IDs it receives. These can be [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), or [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). See [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) for detailed explanations of the IDs supported by Audience Manager.

The [!UICONTROL DCS] monitors the frequency at which it receives these IDs to detect potential malicious activity. When the [!UICONTROL DCS] detects an unusually large amount of [!UICONTROL DCS] requests for any given ID in a short amount of time, that ID is blacklisted.

## Fehlercodes

You can identify blacklisted IDs by the error codes received from the [!UICONTROL DCS]. Folgende Fehlercodes können Sie erhalten:

* 303: Blockierte Kunden-ID;
* 306: Blockierte Geräte-ID;
* 307: Blockierter Profilvorgang für ID.

See [DCS Error Codes, Messages, and Examples](dcs-error-codes.md) for details on the error codes that you may receive.

## Schwarze Auflistung

Ids mit schwarzen Listen sollten in zukünftigen Anforderungen nicht verwendet werden, da sie zu falschen Datenberichten führen. The [!UICONTROL DCS] does not support un-blacklisting of IDs.

## Auswirkungen auf die ID-Synchronisierung

[!UICONTROL DCS] Aufrufe können einen oder mehrere Typen von IDs enthalten. Aufrufe mit einer einzelnen ID werden vollständig ignoriert, wenn diese ID auf der schwarzen Liste aufgeführt ist und in diesem Fall keine ID-Synchronisierung stattfindet.

When a multiple ID call also includes a blacklisted ID, the [!UICONTROL DCS] disregards the blacklisted ID and only uses the remaining, non-blacklisted IDs for synchronization.

## Ursachen und Fehlerbehebungen für die ID-Blacklisting

Die häufigste Ursache von IDs, die in der schwarzen Liste aufgeführt werden, ist die falsche Integration zwischen der Kundeninfrastruktur und Audience Manager. Wenn Sie eine ID mit einer schwarzen Liste identifizieren, sollten Sie Ihre Audience Manager-Integrationen gründlich überprüfen. See **Implementation and Integration Guides** for detailed explanations of how you should configure Audience Manager to work with other Experience Cloud solutions or external systems.

Another frequent cause of blacklisted IDs are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!UICONTROL DCS] multiple times. Wenn Sie die Indexierung als Grund für die ID-Blacklisting identifizieren, sollten Sie den Bot-Zugriff auf Ihre Website beschränken.

Wenn Sie Probleme mit der Identifizierung von Integrationsproblemen haben, wenden Sie sich nicht an den Kundensupport. Prior to opening a support request, make sure to keep the `.har` `HTTP` archive of your browser ready. Dieses Archiv hilft dem Supportteam, die ID-Blacklisting zu identifizieren.
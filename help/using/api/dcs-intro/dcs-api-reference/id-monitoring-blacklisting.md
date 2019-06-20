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

Der Monitor [!UICONTROL DCS] überwacht die empfangenen IDs und die Blacklist, die in einer kurzen Zeitspanne ungewöhnlich hoch gesendet werden.

## Überblick

Um die Audience Manager-Infrastruktur gegen böswillige Aktivitäten zu schützen, verwenden Sie [!UICONTROL DCS] einen erweiterten Algorithmus zur Überwachung der empfangenen IDs. Dies können [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) oder [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) sein. Detaillierte Beschreibungen der von Audience Manager unterstützten IDs finden Sie unter [Index von IDs in Audience Manager](../../../reference/ids-in-aam.md) .

Der Monitor [!UICONTROL DCS] überwacht die Häufigkeit, mit der diese IDs empfangen werden, um potenziell schädliche Aktivitäten zu erkennen. Wenn eine [!UICONTROL DCS] ungewöhnlich große Menge an [!UICONTROL DCS] Anforderungen für eine bestimmte ID in kurzer Zeit erkannt wird, wird diese ID auf der schwarzen Liste aufgeführt.

## Fehlercodes

Sie können ids mit schwarzen Listen anhand der von [!UICONTROL DCS]Ihnen empfangenen Fehlercodes identifizieren. Folgende Fehlercodes können Sie erhalten:

* 303: Blockierte Kunden-ID;
* 306: Blockierte Geräte-ID;
* 307: Blockierter Profilvorgang für ID.

Einzelheiten zu den möglicherweise empfangenen Fehlercodes finden Sie unter [DCS-Fehlercodes, Meldungen und Beispiele](dcs-error-codes.md) .

## Schwarze Auflistung

Ids mit schwarzen Listen sollten in zukünftigen Anforderungen nicht verwendet werden, da sie zu falschen Datenberichten führen. Die [!UICONTROL DCS] nicht-schwarze Liste von IDs wird nicht unterstützt.

## Auswirkungen auf die ID-Synchronisierung

[!UICONTROL DCS] Aufrufe können einen oder mehrere Typen von IDs enthalten. Aufrufe mit einer einzelnen ID werden vollständig ignoriert, wenn diese ID auf der schwarzen Liste aufgeführt ist und in diesem Fall keine ID-Synchronisierung stattfindet.

Wenn ein mehrfacher ID-Aufruf ebenfalls eine ID mit schwarzen Listen enthält, wird die [!UICONTROL DCS] Blacklist ignoriert und nur die verbleibenden, nicht schwarzen IDs für die Synchronisierung verwendet.

## Ursachen und Fehlerbehebungen für die ID-Blacklisting

Die häufigste Ursache von IDs, die in der schwarzen Liste aufgeführt werden, ist die falsche Integration zwischen der Kundeninfrastruktur und Audience Manager. Wenn Sie eine ID mit einer schwarzen Liste identifizieren, sollten Sie Ihre Audience Manager-Integrationen gründlich überprüfen. Detaillierte Erläuterungen zur Konfiguration von Audience Manager für die Verwendung mit anderen Experience Cloud-Lösungen oder externen Systemen finden Sie unter **Implementierungs- und Integrationsleitfaden** .

Eine weitere häufige Ursache von schwarzen ids sind Indizierungsbots (Webcrawler), die im Allgemeinen zu Traffic-Steigerungen führen und zu denselben IDs führen, die an mehrere Male [!UICONTROL DCS] gesendet werden. Wenn Sie die Indexierung als Grund für die ID-Blacklisting identifizieren, sollten Sie den Bot-Zugriff auf Ihre Website beschränken.

Wenn Sie Probleme mit der Identifizierung von Integrationsproblemen haben, wenden Sie sich nicht an den Kundensupport. Achten Sie vor dem Öffnen einer Supportanfrage darauf, das `.har``HTTP` Archiv Ihres Browsers bereit zu halten. Dieses Archiv hilft dem Supportteam, die ID-Blacklisting zu identifizieren.
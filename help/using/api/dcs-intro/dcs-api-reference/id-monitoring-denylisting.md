---
description: Der DES überwacht die IDs, die er erhält, und fügt die IDs, die in einer ungewöhnlich hohen Senderate über einen kurzen Zeitraum gesendet werden, zu einer Blockierungsliste hinzu.
keywords: id;monitoring;dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: ID-Überwachung und -Auf die Blockierungsliste setz
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# ID-Überwachung und -Auf die Blockierungsliste setz

Der [!DNL DCS] überwacht die IDs, die er erhält, und fügt die IDs, die in einer ungewöhnlich hohen Senderate über einen kurzen Zeitraum gesendet werden, zu einer Blockierungsliste hinzu.

## Überblick

Zum Schutz der Audience Manager-Infrastruktur vor schädlichen Aktivitäten verwendet [!DNL DCS] einen erweiterten Algorithmus, um die empfangenen IDs zu überwachen. Dabei kann es sich um [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) oder [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) handeln. Detaillierte Erläuterungen der vom Audience Manager unterstützten IDs finden Sie unter [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md).

Der [!DNL DCS] überwacht die Häufigkeit, mit der diese IDs empfangen werden, um potenzielle schädliche Aktivitäten zu erkennen. Wenn der [!DNL DCS] in kurzer Zeit eine ungewöhnlich große Anzahl von [!DNL DCS] -Anfragen für eine bestimmte ID erkennt, wird diese ID einer Blockierungsliste hinzugefügt.

## Fehlercodes

Sie können zu einer Blockierungsliste hinzugefügte IDs anhand der Fehlercodes identifizieren, die von der [!DNL DCS] empfangen wurden. Die Fehlercodes, die Sie möglicherweise erhalten, sind:

* 303: Blockierte Kunden-ID;
* 306: Blockierte deklarierte Geräte-ID;
* 307: Vorgang &quot;Blocked profile&quot;für ID.

Einzelheiten zu den möglicherweise empfangenen Fehlercodes finden Sie unter [DCS-Fehlercodes, Meldungen und Beispiele](dcs-error-codes.md) .

## Entfernen von IDs aus Blockierungslisten

IDs, die zu Blockierungslisten hinzugefügt wurden, sollten in zukünftigen Anfragen nicht verwendet werden, da sie zu fehlerhaften Datenberichten führen. Das Entfernen von IDs aus Blockierungslisten wird von [!DNL DCS] nicht unterstützt.

## Auswirkungen auf die ID-Synchronisierung

[!DNL DCS] -Aufrufe können eine oder mehrere Arten von IDs enthalten. Aufrufe, die eine einzelne ID enthalten, werden vollständig ignoriert, wenn diese ID zu einer Blockierungsliste hinzugefügt wird. In diesem Fall erfolgt keine ID-Synchronisierung.

Wenn ein Aufruf mit mehreren IDs auch eine auf die Blockierungsliste gesetzt ID enthält, ignoriert der [!DNL DCS] die verweigerte ID und verwendet nur die verbleibenden zulässigen IDs für die Synchronisierung.

## Ursachen und Fehlerbehebungen für den ID-Auf die Blockierungsliste setz

Die häufigste Ursache für das Hinzufügen von IDs zu Blockierungslisten ist die falsche Integration zwischen Kundeninfrastruktur und Audience Manager. Wenn Sie eine auf die Blockierungsliste gesetzt ID identifizieren, überprüfen Sie Ihre Audience Manager-Integrationen sorgfältig. Detaillierte Informationen dazu, wie Sie Audience Manager für die Verwendung mit anderen Experience Cloud-Lösungen oder externen Systemen konfigurieren sollten, finden Sie unter **Implementierungs- und Integrationshandbücher** .

Eine weitere häufige Ursache für das Hinzufügen von IDs zu Blockierungslisten ist die Indizierung von Bots (Webcrawlern), was im Allgemeinen zu einem Anstieg des Traffics führt, sodass dieselben IDs mehrmals an die [!DNL DCS] gesendet werden. Wenn Sie Indizierungs-Bots als Grund für IDs identifizieren, die zu Blockierungslisten hinzugefügt werden, sollten Sie den Bot-Zugriff auf Ihre Website einschränken.

Wenn Sie Probleme mit der Integration nur schwer erkennen können, wenden Sie sich an den Support. Stellen Sie vor dem Öffnen einer Support-Anfrage sicher, dass Sie das Archiv `.har` `HTTP` Ihres Browsers bereit halten. Dieses Archiv hilft dem Support-Team dabei, herauszufinden, warum die ID zu einer Blockierungsliste hinzugefügt wurde.

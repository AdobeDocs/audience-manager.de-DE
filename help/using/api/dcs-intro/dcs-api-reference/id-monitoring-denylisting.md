---
description: Der DES überwacht die IDs, die er erhält, und fügt die IDs, die in einer ungewöhnlich hohen Senderate über einen kurzen Zeitraum gesendet werden, zu einer Blockierungsliste hinzu.
keywords: id;monitoring;dcs
seo-description: Der DES überwacht die IDs, die er erhält, und fügt die IDs, die in einer ungewöhnlich hohen Senderate über einen kurzen Zeitraum gesendet werden, zu einer Blockierungsliste hinzu.
seo-title: ID-Überwachung und Blockierungsauflistung
solution: Audience Manager
title: ID-Überwachung und Blockierungsauflistung
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 2%

---

# ID-Überwachung und Blockierungsauflistung

Der [!DNL DCS] überwacht die IDs, die er empfängt, und fügt die IDs, die in einer ungewöhnlich hohen Senderate über einen kurzen Zeitraum gesendet werden, zu einer Blockierungsliste hinzu.

## Überblick

Zum Schutz der Audience Manager-Infrastruktur vor schädlichen Aktivitäten verwendet das [!DNL DCS] einen erweiterten Algorithmus, um die IDs zu überwachen, die es empfängt. Dabei kann es sich um [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) oder [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) handeln. Detaillierte Erläuterungen der vom Audience Manager unterstützten IDs finden Sie unter [Index der IDs in Audience Manager](../../../reference/ids-in-aam.md).

Der [!DNL DCS] überwacht die Häufigkeit, mit der diese IDs empfangen werden, um potenzielle schädliche Aktivitäten zu erkennen. Wenn [!DNL DCS] in kurzer Zeit ungewöhnlich viele [!DNL DCS] -Anfragen für eine bestimmte ID erkennt, wird diese ID einer Blockierungsliste hinzugefügt.

## Fehlercodes

Sie können einer Blockierungsliste hinzugefügte IDs anhand der Fehlercodes identifizieren, die von [!DNL DCS] empfangen wurden. Die Fehlercodes, die Sie möglicherweise erhalten, sind:

* 303: Blockierte Kunden-ID;
* 306: Blockierte deklarierte Geräte-ID;
* 307: Vorgang &quot;Blocked profile&quot;für ID.

Weitere Informationen zu den möglicherweise empfangenen Fehlercodes finden Sie unter [DCS-Fehlercodes, Nachrichten und Beispiele](dcs-error-codes.md).

## Entfernen von IDs aus Blockierungslisten

IDs, die zu Blockierungslisten hinzugefügt wurden, sollten in zukünftigen Anfragen nicht verwendet werden, da sie zu fehlerhaften Datenberichten führen. Das [!DNL DCS] unterstützt nicht das Entfernen von IDs aus Blockierungslisten.

## Auswirkungen auf die ID-Synchronisierung

[!DNL DCS] -Aufrufe können eine oder mehrere Arten von IDs enthalten. Aufrufe, die eine einzelne ID enthalten, werden vollständig ignoriert, wenn diese ID zu einer Blockierungsliste hinzugefügt wird. In diesem Fall erfolgt keine ID-Synchronisierung.

Wenn ein Aufruf mit mehreren IDs auch eine auf die Blockierungsliste gesetzt ID enthält, ignoriert das [!DNL DCS] die abgelehnte ID und verwendet nur die verbleibenden zulässigen IDs für die Synchronisierung.

## Ursachen und Fehlerbehebungen für den ID-Auf die Blockierungsliste setz

Die häufigste Ursache für das Hinzufügen von IDs zu Blockierungslisten ist die falsche Integration zwischen Kundeninfrastruktur und Audience Manager. Wenn Sie eine auf die Blockierungsliste gesetzt ID identifizieren, überprüfen Sie Ihre Audience Manager-Integrationen sorgfältig. Detaillierte Erläuterungen dazu, wie Sie Audience Manager für die Verwendung mit anderen Experience Cloud-Lösungen oder externen Systemen konfigurieren sollten, finden Sie unter **Implementierungs- und Integrationshandbücher** .

Eine weitere häufige Ursache für das Hinzufügen von IDs zu Blockierungslisten ist die Indizierung von Bots (Webcrawler), die im Allgemeinen zu einem Anstieg des Traffics führen, was dazu führt, dass dieselben IDs mehrmals an die gesendet werden. [!DNL DCS] Wenn Sie Indizierungs-Bots als Grund für IDs identifizieren, die zu Blockierungslisten hinzugefügt werden, sollten Sie den Bot-Zugriff auf Ihre Website einschränken.

Wenn Sie Probleme mit der Integration nur schwer erkennen können, wenden Sie sich an den Support. Bevor Sie eine Support-Anfrage öffnen, stellen Sie sicher, dass Sie das `.har` `HTTP`-Archiv Ihres Browsers bereit halten. Dieses Archiv hilft dem Support-Team dabei, herauszufinden, warum die ID zu einer Blockierungsliste hinzugefügt wurde.

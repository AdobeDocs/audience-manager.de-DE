---
description: Der DCS überwacht die IDs, die er erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, einer Deny-Liste hinzu.
keywords: id;monitoring;dcs
seo-description: Der DCS überwacht die IDs, die er erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, einer Deny-Liste hinzu.
seo-title: ID-Überwachung und -Denylierung
solution: Audience Manager
title: ID-Überwachung und -Denylierung
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID-Überwachung und -Denylierung

Die [!UICONTROL DCS] überwacht die IDs, die sie erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, einer Deny-Liste hinzu.

## Überblick

Zum Schutz der Audience Manager-Infrastruktur vor böswilliger Aktivität [!UICONTROL DCS] verwendet der Algorithmus einen erweiterten Algorithmus, um die erhaltenen IDs zu überwachen. Dabei kann es sich um [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) oder [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) handeln. Detaillierte Informationen zu den vom Audience Manager unterstützten IDs finden Sie unter [IDs in Audience Manager](../../../reference/ids-in-aam.md) .

Die [!UICONTROL DCS] überwacht die Häufigkeit, mit der sie diese IDs erhält, um potenzielle bösartige Aktivitäten zu erkennen. Wenn der [!UICONTROL DCS] Benutzer eine ungewöhnlich große Anzahl von [!UICONTROL DCS] Anfragen für eine bestimmte ID in kurzer Zeit erkennt, wird diese ID zu einer Liste zum Ablehnen hinzugefügt.

## Fehlercodes

Sie können IDs identifizieren, die zu einer Liste zum Verweigern hinzugefügt wurden, indem Sie die Fehlercodes identifizieren, die vom [!UICONTROL DCS]. Die Fehlercodes, die Sie möglicherweise erhalten, sind:

* 303: Blockierte Kunden-ID;
* 306: Blockierte deklarierte Geräte-ID;
* 307: Blockierter Profil-Vorgang für ID.

Einzelheiten zu den Fehlercodes, die Sie möglicherweise erhalten, finden Sie unter [DCS-Fehlercodes, -Meldungen und -Beispiele](dcs-error-codes.md) .

## Entfernen von IDs aus Listen verweigern

IDs, die hinzugefügt wurden, um Listen zu verweigern, sollten in zukünftigen Anforderungen nicht verwendet werden, da sie zu einem fehlerhaften Berichte der Daten führen. Das [!UICONTROL DCS] unterstützt nicht das Entfernen von IDs aus der Ablehnen von Listen.

## Auswirkungen auf die ID-Synchronisierung

[!UICONTROL DCS] -Aufrufe können einen oder mehrere ID-Typen enthalten. Aufrufe, die eine einzelne ID enthalten, werden vollständig ignoriert, wenn diese ID zu einer Liste zum Ablehnen hinzugefügt wird, und in diesem Fall findet keine ID-Synchronisierung statt.

Wenn ein Aufruf mit mehreren IDs auch eine ID enthält, die nicht aufgeführt ist, wird die verweigerte ID ignoriert und verwendet nur die verbleibenden zulässigen IDs für die Synchronisierung. [!UICONTROL DCS]

## Ursachen und Fehlerbehebungen für die ID-Denylierung

Die häufigste Ursache für die Hinzufügung von IDs zur Ablehnung von Listen ist die fehlerhafte Integration zwischen Kundeninfrastruktur und Audience Manager. Wenn Sie eine ID in der Liste &quot;Verweigert&quot;identifizieren, überprüfen Sie Ihre Audience Manager-Integrationen gründlich. Detaillierte Anweisungen zum Konfigurieren von Audience Manager für die Verwendung mit anderen Experience Cloud-Lösungen oder externen Systemen finden Sie in den **Implementierungs- und Integrationsanleitungen** .

Eine weitere häufige Ursache dafür, dass IDs hinzugefügt werden, um Listen zu verweigern, ist das Indizieren von Bots (Webcrawler), was in der Regel zu Datenverkehrssteigerungen führt, sodass dieselben IDs mehrmals an die [!UICONTROL DCS] gesendet werden. Wenn Sie die Indizierung von Bots als Grund für IDs identifizieren, die hinzugefügt werden, um Listen zu verweigern, sollten Sie den Bot-Zugriff auf Ihre Website einschränken.

Wenn Sie Probleme mit der Integration nur schwer identifizieren können, wenden Sie sich bitte an den Kundensupport. Bevor Sie eine Supportanfrage öffnen, stellen Sie sicher, dass das `.har` `HTTP` Archiv Ihres Browsers bereit ist. Dieses Archiv hilft dem Supportteam herauszufinden, warum die ID zu einer Liste zum Ablehnen hinzugefügt wurde.
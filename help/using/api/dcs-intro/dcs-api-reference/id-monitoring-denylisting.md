---
description: Der DCS überwacht die IDs, die er erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, einer Blockierungsliste hinzu.
keywords: id;monitoring;dcs
seo-description: Der DCS überwacht die IDs, die er erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, einer Blockierungsliste hinzu.
seo-title: ID-Überwachung und Blockierungsauflistung
solution: Audience Manager
title: ID-Überwachung und Blockierungsauflistung
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID-Überwachung und Blockierungsauflistung

Die [!DNL DCS] überwacht die erhaltenen IDs und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, einer Blockierungsliste hinzu.

## Überblick

Um die Audience Manager-Infrastruktur vor böswilliger Aktivität zu schützen, [!DNL DCS] verwendet die Gruppe einen erweiterten Algorithmus, um die erhaltenen IDs zu überwachen. Dabei kann es sich um [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) oder [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) handeln. Eine ausführliche Erläuterung der von Audience Manager unterstützten IDs finden Sie unter [IDs in Audience Manager](../../../reference/ids-in-aam.md) .

Die [!DNL DCS] überwacht die Häufigkeit, mit der sie diese IDs erhält, um potenzielle bösartige Aktivitäten zu erkennen. Wenn der [!DNL DCS] Benutzer eine ungewöhnlich große Anzahl von [!DNL DCS] Anforderungen für eine bestimmte ID in kurzer Zeit erkennt, wird diese ID einer Blockierungsliste hinzugefügt.

## Fehlercodes

Sie können IDs identifizieren, die einer Blockierungsliste durch die Fehlercodes hinzugefügt werden, die vom [!DNL DCS]. Die Fehlercodes, die Sie möglicherweise erhalten, sind:

* 303: Blockierte Kunden-ID;
* 306: Blockierte deklarierte Geräte-ID;
* 307: Blockierter Profil-Vorgang für ID.

Einzelheiten zu den Fehlercodes, die Sie möglicherweise erhalten, finden Sie unter [DCS-Fehlercodes, -Meldungen und -Beispiele](dcs-error-codes.md) .

## Entfernen von IDs aus Blockierungslisten

IDs, die zu Blockierungslisten hinzugefügt wurden, sollten in zukünftigen Anforderungen nicht verwendet werden, da sie zu einem fehlerhaften Berichte der Daten führen. Das Entfernen von IDs aus Blockierungslisten wird [!DNL DCS] nicht unterstützt.

## Auswirkungen auf die ID-Synchronisierung

[!DNL DCS] -Aufrufe können einen oder mehrere ID-Typen enthalten. Aufrufe, die eine einzelne ID enthalten, werden vollständig ignoriert, wenn diese ID einer Blockierungsliste hinzugefügt wird. In diesem Fall findet keine ID-Synchronisierung statt.

Wenn ein Aufruf mit mehreren IDs auch eine auf die Blockierungsliste gesetzt ID enthält, wird die verweigerte ID [!DNL DCS] ignoriert und nur die verbleibenden zulässigen IDs für die Synchronisierung verwendet.

## Ursachen und Fehlerbehebungen bei der Blockierungsauflistung von ID-IDs

Die häufigste Ursache dafür, dass Blockierungslisten IDs hinzugefügt werden, ist die fehlerhafte Integration zwischen Kundeninfrastruktur und Audience Manager. Wenn Sie eine auf die Blockierungsliste gesetzt ID identifizieren, überprüfen Sie Ihre Audience Manager-Integrationen gründlich. Detaillierte Informationen dazu, wie Sie Audience Manager für die Verwendung mit anderen Experience Cloud- oder externen  konfigurieren sollten, finden Sie unter **Implementierungs- und Integrationsanleitungen** .

Eine weitere häufige Ursache dafür, dass Blockierungslisten IDs hinzugefügt werden, ist das Indizieren von Bots (Webcrawler), was im Allgemeinen zu Datenverkehrssteigerungen führt, sodass dieselben IDs mehrmals an die [!DNL DCS] gesendet werden. Wenn Sie die Indizierung von Bots als Grund dafür identifizieren, dass Blockierungslisten IDs hinzugefügt werden, sollten Sie den Bot-Zugriff auf Ihre Website einschränken.

Wenn Sie Probleme mit der Integration nur schwer identifizieren können, wenden Sie sich bitte an den Kundensupport. Bevor Sie eine Supportanfrage öffnen, stellen Sie sicher, dass das `.har` `HTTP` Archiv Ihres Browsers bereit ist. Dieses Archiv hilft dem Supportteam, herauszufinden, warum die ID zu einer Blockierungsliste hinzugefügt wurde.
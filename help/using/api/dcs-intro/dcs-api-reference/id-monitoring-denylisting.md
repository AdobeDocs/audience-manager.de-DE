---
description: Der DCS überwacht die IDs, die er erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, einer Blockierungsliste hinzu.
keywords: id;Monitoring;dcs
seo-description: Der DCS überwacht die IDs, die er erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, einer Blockierungsliste hinzu.
seo-title: ID-Überwachung und Blockierungsauflistung
solution: Audience Manager
title: ID-Überwachung und Blockierungsauflistung
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 2%

---


# ID-Überwachung und Blockierungsauflistung

Das [!DNL DCS] überwacht die IDs, die es erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, einer Blockierungsliste hinzu.

## Überblick

Zum Schutz der Audience Manager-Infrastruktur vor böswilliger Aktivität verwendet das [!DNL DCS] einen erweiterten Algorithmus, um die erhaltenen IDs zu überwachen. Dazu können [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) oder [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) gehören. Ausführliche Erläuterungen zu den von Audience Manager unterstützten IDs finden Sie unter [IDs in Audience Manager](../../../reference/ids-in-aam.md).

Das [!DNL DCS] überwacht die Häufigkeit, mit der es diese IDs erhält, um potenzielle bösartige Aktivitäten zu erkennen. Wenn [!DNL DCS] eine ungewöhnlich große Anzahl von [!DNL DCS]-Anforderungen für eine bestimmte ID in kurzer Zeit erkennt, wird diese ID einer Blockierungsliste hinzugefügt.

## Fehlercodes

Sie können IDs identifizieren, die einer Blockierungsliste durch die Fehlercodes hinzugefügt werden, die von [!DNL DCS] empfangen werden. Die Fehlercodes, die Sie möglicherweise erhalten, sind:

* 303: Blockierte Kunden-ID;
* 306: Blockierte deklarierte Geräte-ID;
* 307: Blockierter Profil-Vorgang für ID.

Einzelheiten zu den Fehlercodes, die Sie möglicherweise erhalten, finden Sie unter [DCS-Fehlercodes, Meldungen und Beispiele](dcs-error-codes.md).

## Entfernen von IDs aus Blockierungslisten

IDs, die zu Blockierungslisten hinzugefügt wurden, sollten in zukünftigen Anforderungen nicht verwendet werden, da sie zu einem fehlerhaften Berichte der Daten führen. Das [!DNL DCS] unterstützt nicht das Entfernen von IDs aus Blockierungslisten.

## Auswirkungen auf die ID-Synchronisierung

[!DNL DCS] -Aufrufe können einen oder mehrere ID-Typen enthalten. Aufrufe, die eine einzelne ID enthalten, werden vollständig ignoriert, wenn diese ID einer Blockierungsliste hinzugefügt wird. In diesem Fall findet keine ID-Synchronisierung statt.

Wenn ein Aufruf mit mehreren IDs auch eine auf die Blockierungsliste gesetzt ID enthält, ignoriert das [!DNL DCS] die verweigerte ID und verwendet nur die verbleibenden zulässigen IDs für die Synchronisierung.

## Ursachen und Fehlerbehebungen bei der Blockierungsauflistung von ID-IDs

Die häufigste Ursache dafür, dass Blockierungslisten IDs hinzugefügt werden, ist die fehlerhafte Integration zwischen Kundeninfrastruktur und Audience Manager. Wenn Sie eine auf die Blockierungsliste gesetzt ID identifizieren, überprüfen Sie Ihre Audience Manager-Integrationen gründlich. Detaillierte Anweisungen zum Konfigurieren von Audience Manager für die Verwendung mit anderen Experience Cloud- oder externen Systemen finden Sie unter **Implementierungs- und Integrationsleitfäden**.

Eine weitere häufige Ursache dafür, dass Blockierungslisten IDs hinzugefügt werden, ist das Indizieren von Bots (Webcrawler), was im Allgemeinen zu Traffic-Zunahmen führt, sodass dieselben IDs mehrmals an die [!DNL DCS] gesendet werden. Wenn Sie die Indizierung von Bots als Grund dafür identifizieren, dass Blockierungslisten IDs hinzugefügt werden, sollten Sie den Bot-Zugriff auf Ihre Website einschränken.

Wenn Sie Probleme mit der Integration nur schwer identifizieren können, wenden Sie sich bitte an den Kundensupport. Bevor Sie eine Supportanfrage öffnen, stellen Sie sicher, dass das `.har` `HTTP`-Archiv Ihres Browsers bereit ist. Dieses Archiv hilft dem Supportteam, herauszufinden, warum die ID zu einer Blockierungsliste hinzugefügt wurde.
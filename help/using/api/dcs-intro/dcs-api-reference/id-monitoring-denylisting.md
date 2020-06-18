---
description: Der DCS überwacht die IDs, die er erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, zu einer blockierungsliste hinzu.
keywords: id;monitoring;dcs
seo-description: Der DCS überwacht die IDs, die er erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, zu einer blockierungsliste hinzu.
seo-title: ID-Überwachung und -Denylierung
solution: Audience Manager
title: ID-Überwachung und -Denylierung
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID-Überwachung und -Denylierung

Die [!DNL DCS] überwacht die IDs, die sie erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, zu einer blockierungsliste hinzu.

## Überblick

Um die Audience Manager-Infrastruktur vor böswilliger Aktivität zu schützen, [!DNL DCS] verwendet die Gruppe einen erweiterten Algorithmus, um die erhaltenen IDs zu überwachen. Dabei kann es sich um [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) oder [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) handeln. Eine ausführliche Erläuterung der von Audience Manager unterstützten IDs finden Sie unter [IDs in Audience Manager](../../../reference/ids-in-aam.md) .

Die [!DNL DCS] überwacht die Häufigkeit, mit der sie diese IDs erhält, um potenzielle bösartige Aktivitäten zu erkennen. Wenn der [!DNL DCS] Benutzer eine ungewöhnlich große Anzahl von [!DNL DCS] Anfragen für eine bestimmte ID in kurzer Zeit erkennt, wird diese ID einer blockierungsliste hinzugefügt.

## Fehlercodes

Sie können IDs identifizieren, die zu einer blockierungsliste hinzugefügt werden, indem Sie die Fehlercodes identifizieren, die vom [!DNL DCS]. Die Fehlercodes, die Sie möglicherweise erhalten, sind:

* 303: Blockierte Kunden-ID;
* 306: Blockierte deklarierte Geräte-ID;
* 307: Blockierter Profil-Vorgang für ID.

Einzelheiten zu den Fehlercodes, die Sie möglicherweise erhalten, finden Sie unter [DCS-Fehlercodes, -Meldungen und -Beispiele](dcs-error-codes.md) .

## Entfernen von IDs aus blockierungsliste

IDs, die zu blockierungsliste hinzugefügt wurden, sollten in zukünftigen Anforderungen nicht verwendet werden, da sie zu einem fehlerhaften Berichte der Daten führen. Das Entfernen von IDs aus blockierungsliste wird [!DNL DCS] nicht unterstützt.

## Auswirkungen auf die ID-Synchronisierung

[!DNL DCS] -Aufrufe können einen oder mehrere ID-Typen enthalten. Aufrufe, die eine einzelne ID enthalten, werden vollständig ignoriert, wenn diese ID einer blockierungsliste hinzugefügt wird. In diesem Fall findet keine ID-Synchronisierung statt.

Wenn ein Aufruf mit mehreren IDs auch eine ID enthält, die nicht aufgeführt ist, wird die verweigerte ID ignoriert und verwendet nur die verbleibenden zulässigen IDs für die Synchronisierung. [!DNL DCS]

## Ursachen und Fehlerbehebungen für die ID-Denylierung

Die häufigste Ursache für das Hinzufügen von IDs zu blockierungsliste ist die fehlerhafte Integration zwischen Kundeninfrastruktur und Audience Manager. Wenn Sie eine ID in der Liste &quot;Verweigert&quot;identifizieren, überprüfen Sie Ihre Audience Manager-Integrationen sorgfältig. Detaillierte Informationen dazu, wie Sie Audience Manager für die Verwendung mit anderen Experience Cloud- oder externen  konfigurieren sollten, finden Sie unter **Implementierungs- und Integrationsanleitungen** .

Eine weitere häufige Ursache dafür, dass blockierungsliste IDs hinzugefügt werden, ist das Indizieren von Bots (Webcrawler), was im Allgemeinen zu Datenverkehrssteigerungen führt, sodass dieselben IDs mehrmals an die [!DNL DCS] gesendet werden. Wenn Sie die Indizierung von Bots als Grund für IDs identifizieren, die blockierungsliste hinzugefügt werden, sollten Sie den Bot-Zugriff auf Ihre Website einschränken.

Wenn Sie Probleme mit der Integration nur schwer identifizieren können, wenden Sie sich bitte an den Kundensupport. Bevor Sie eine Supportanfrage öffnen, stellen Sie sicher, dass das `.har` `HTTP` Archiv Ihres Browsers bereit ist. Dieses Archiv hilft dem Supportteam, herauszufinden, warum die ID zu einer blockierungsliste hinzugefügt wurde.
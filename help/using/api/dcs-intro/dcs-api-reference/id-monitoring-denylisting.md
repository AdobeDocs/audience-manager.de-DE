---
description: Der DCS überwacht die empfangenen IDs und fügt die IDs, die über einen kurzen Zeitraum mit ungewöhnlich hoher Rate gesendet werden, zu einer Blockierungsliste hinzu.
keywords: ID;Überwachung;DCS
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: ID-Überwachung und -Blockierungsauflistung
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# ID-Überwachung und -Blockierungsauflistung

Der [!DNL DCS] überwacht die empfangenen IDs und fügt die IDs, die über einen kurzen Zeitraum mit ungewöhnlich hoher Rate gesendet werden, zu einer Blockierungsliste hinzu.

## Überblick

Um die Audience Manager-Infrastruktur vor böswilligen Aktivitäten zu schützen, verwendet die [!DNL DCS] einen erweiterten Algorithmus, um die empfangenen IDs zu überwachen. Dabei kann es sich um [!UICONTROL Data Provider Unique User ID] ([!UICONTROL CRM ID]), [!UICONTROL Audience Manager Unique User ID] ([!UICONTROL AAM UUID]) oder [!UICONTROL Experience Cloud ID] ([!UICONTROL ECID]) handeln. Unter [ID-Index in Audience Manager](../../../reference/ids-in-aam.md) finden Sie detaillierte Erläuterungen zu den von Audience Manager unterstützten IDs.

Der [!DNL DCS] überwacht die Häufigkeit, mit der er diese IDs erhält, um potenzielle bösartige Aktivitäten zu erkennen. Wenn der [!DNL DCS] in kurzer Zeit eine ungewöhnlich große Anzahl von [!DNL DCS]-Anfragen für eine bestimmte ID erkennt, wird diese ID zu einer Blockierungsliste hinzugefügt.

## Fehler-Codes

Kennungen, die einer Blockierungsliste hinzugefügt wurden, können anhand der vom [!DNL DCS] empfangenen Fehlercodes identifiziert werden. Die Fehler-Codes, die Sie möglicherweise erhalten, sind:

* 303: Blockierte Kunden-ID;
* 306: Blockierte deklarierte Geräte-ID;
* 307: Blockierter Profilvorgang für ID.

Siehe [DCS-Fehler-Codes, Meldungen und Beispiele](dcs-error-codes.md) für Details zu den Fehler-Codes, die Sie möglicherweise erhalten.

## Entfernen von IDs aus Blockierungslisten

IDs, die Blockierungslisten hinzugefügt wurden, sollten in zukünftigen Anfragen nicht verwendet werden, da sie zu falschen Datenberichten führen. Das [!DNL DCS] unterstützt nicht das Entfernen von IDs aus Blockierungslisten.

## Auswirkungen auf die ID-Synchronisierung

[!DNL DCS] Aufrufe können einen oder mehrere ID-Typen enthalten. Aufrufe, die eine einzige ID enthalten, werden vollständig ignoriert, wenn diese ID zu einer Blockierungsliste hinzugefügt wird und in diesem Fall keine ID-Synchronisierung erfolgt.

Wenn ein Aufruf mit mehreren IDs auch eine auf die Blockierungsliste gesetzt ID enthält, ignoriert der [!DNL DCS] die verweigerte ID und verwendet nur die verbleibenden zulässigen IDs für die Synchronisierung.

## Ursachen und Fehlerbehebungen für die ID-Blockierungsauflistung

Die häufigste Ursache für das Hinzufügen von IDs zu Blockierungslisten ist die fehlerhafte Integration zwischen der Kundeninfrastruktur und Audience Manager. Wenn Sie eine auf die Blockierungsliste gesetzt ID identifizieren, sollten Sie Ihre Audience Manager-Integrationen gründlich überprüfen. Unter **Implementierungs- und Integrationshandbücher** finden Sie detaillierte Erläuterungen dazu, wie Sie Audience Manager für die Zusammenarbeit mit anderen Experience Cloud-Lösungen oder externen Systemen konfigurieren sollten.

Eine weitere häufige Ursache für das Hinzufügen von IDs zu Blockierungslisten sind Indizierungs-Bots (Web-Crawler), die in der Regel zu einem Anstieg des Traffics führen, was dazu führt, dass dieselben IDs mehrmals an die [!DNL DCS] gesendet werden. Wenn Sie Indizierungs-Bots als Grund für das Hinzufügen von IDs zu Blockierungslisten angeben, sollten Sie den Bot-Zugriff auf Ihre Website einschränken.

Wenn Sie Schwierigkeiten haben, Integrationsprobleme zu identifizieren, zögern Sie nicht, sich an den Support zu wenden. Bevor Sie eine Support-Anfrage öffnen, sollten Sie das `.har` `HTTP`-Archiv Ihres Browsers bereithalten. Dieses Archiv hilft dem Support-Team zu ermitteln, warum die ID zu einer Blockierungsliste hinzugefügt wurde.

---
description: Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-description: Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-title: Stapeldatenübermittlungsprozess beschrieben
solution: Audience Manager
title: Stapeldatenübermittlungsprozess beschrieben
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---


# Stapeldatenübermittlungsprozess beschrieben {#batch-data-transfer-process-described}

Eine allgemeine Übersicht darüber, wie [!DNL Audience Manager] ein asynchroner Batch-Datenaustausch mit einem Drittanbieter durchgeführt wird.

## Batch-Datenintegration

<!-- c_async.xml -->

Die Batch-Datenintegration speichert Besucher-Informationen auf unseren Servern und synchronisiert diese mit Daten, die regelmäßig von einem Anbieter gesendet werden. Der Prozess der asynchronen Datenübertragung ist nützlich, wenn:

* Eine sofortige Datenübertragung ist nicht erforderlich.
* Datenerfassung zum Aufbau eines großen Pools segmentierter Benutzer.
* Sie möchten Datendiskrepanzen und `HTTP` Aufrufe vom Browser reduzieren.

![](assets/s2s_70.png)

## Schritte zur Datenintegration

1. Ein Benutzer besucht eine Kunden-Site.
1. Audience Manager und der Drittanbieter für Daten weisen dem Besucher eine eindeutige ID zu (üblicherweise mit einem Cookie).
1. Audience Manager ruft den Drittanbieter-Datenanbieter auf, um Besucher-IDs zuzuordnen.
1. Bei einer geplanten Anforderung, die in der Regel täglich erfolgt, werden die Segmentdaten des Besuchers zwischen Audience Manager und Ihrem Drittanbieter ausgetauscht.
1. Bei jeder Verarbeitung einer eingehenden [!UICONTROL Server-to-Server] Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet. Weitere Informationen finden Sie unter [Beispielmeldung an Partner nach der eingehenden Verarbeitung](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
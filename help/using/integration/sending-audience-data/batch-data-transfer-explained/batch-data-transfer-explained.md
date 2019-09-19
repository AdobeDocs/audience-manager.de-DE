---
description: Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-description: Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-title: Stapeldatenübermittlungsprozess beschrieben
solution: Audience Manager
title: Stapeldatenübermittlungsprozess beschrieben
uuid: a9ee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Stapeldatenübermittlungsprozess beschrieben {#batch-data-transfer-process-described}

Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.

## Batch-Datenintegration

<!-- c_async.xml -->

Der Prozess der Batch-Datenintegration speichert Besucherinformationen auf unseren Servern und synchronisiert diese Materialien in regelmäßigen Abständen mit Daten, die von einem Anbieter gesendet werden. Der Prozess der asynchronen Datenübertragung ist nützlich, wenn:

* Eine sofortige Datenübertragung ist nicht erforderlich.
* Datenerfassung zum Aufbau eines großen Pools segmentierter Benutzer.
* Sie möchten Datendiskrepanzen und `HTTP` Aufrufe vom Browser reduzieren.

![](assets/s2s_70.png)

## Schritte zur Datenintegration

1. Ein Benutzer besucht eine Kunden-Site.
1. Audience Manager und der Drittanbieter für Daten weisen dem Besucher eine eindeutige ID zu (üblicherweise mit einem Cookie).
1. Audience Manager ruft den Drittanbieter-Datenanbieter auf, Besucher-IDs zuzuordnen.
1. Bei einer geplanten Anforderung, die in der Regel in einem täglichen Intervall erfolgt, werden Besuchersegmentdaten zwischen Audience Manager und Ihrem Drittanbieter ausgetauscht.
1. Bei jeder Verarbeitung einer eingehenden [!UICONTROL Server-to-Server] Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet. Weitere Informationen finden Sie unter [Beispielmeldung an Partner nach der eingehenden Verarbeitung](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
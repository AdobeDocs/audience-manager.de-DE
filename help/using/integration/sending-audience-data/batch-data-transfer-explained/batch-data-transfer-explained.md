---
description: Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-description: Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-title: Beschreibung des Batch-Datenübertragungsprozesses
solution: Audience Manager
title: Beschreibung des Batch-Datenübertragungsprozesses
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 7%

---


# Beschreibung des Batch-Datenübertragungsprozesses {#batch-data-transfer-process-described}

Eine allgemeine Übersicht darüber, wie [!DNL Audience Manager] einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.

## Batch-Datenintegration

<!-- c_async.xml -->

Die Batch-Datenintegration speichert Besucher-Informationen auf unseren Servern und synchronisiert diese mit Daten, die regelmäßig von einem Anbieter gesendet werden. Der Prozess der asynchronen Datenübertragung ist nützlich, wenn:

* Eine sofortige Datenübertragung ist nicht erforderlich.
* Datenerfassung zum Aufbau eines großen Pools segmentierter Benutzer.
* Sie möchten Datendiskrepanzen und `HTTP`-Aufrufe vom Browser reduzieren.

![](assets/s2s_70.png)

## Schritte zur Datenintegration

1. Ein Benutzer besucht eine Kunden-Site.
1. [!DNL Audience Manager] und der Drittanbieter für Daten weist dem Besucher eine eindeutige ID zu (üblicherweise mit einem Cookie).
1. [!DNL Audience Manager] ruft den Drittanbieter auf, Besucher-IDs zuzuordnen.
1. Bei einer geplanten Anforderung, die in der Regel in einem täglichen Intervall erfolgt, werden die Segmentdaten des Besuchers zwischen [!DNL Audience Manager] und Ihrem Drittanbieter ausgetauscht.
1. Bei jeder Verarbeitung einer eingehenden [!UICONTROL Server-to-Server]-Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet. Weitere Informationen finden Sie unter [Beispielmeldung an Partner nach der eingehenden Verarbeitung](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).

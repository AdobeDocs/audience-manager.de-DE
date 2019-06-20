---
description: Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-description: Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-title: Batch-Datenübertragungsprozess beschrieben
solution: Audience Manager
title: Batch-Datenübertragungsprozess beschrieben
uuid: a 9 eee 940-151 c -44 f 8-9 fe 9-8 ab 47 d 8 fa 45 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Batch-Datenübertragungsprozess beschrieben {#batch-data-transfer-process-described}

Eine allgemeine Übersicht darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.

## Batch-Datenintegration

<!-- c_async.xml -->

Der Batch-Datenintegrationsprozess speichert Besucherinformationen auf unseren Servern und synchronisiert dieses Material mit Daten, die von einem Anbieter in regelmäßigen Abständen gesendet werden. Der asynchrone Datenübertragungsprozess ist nützlich, wenn:

* Sofortige Datenübertragungen sind nicht erforderlich.
* Erfassen von Daten, um einen großen Pool segmentierter Benutzer zu erstellen.
* Sie möchten Datendiskrepanzen und `HTTP` Aufrufe vom Browser verringern.

![](assets/s2s_70.png)

## Datenintegrationsschritte

1. Ein Benutzer besucht eine Kunden-Site.
1. Audience Manager und der Drittanbieter-Datenanbieter weisen dem Besucher eine eindeutige ID zu (normalerweise mit einem Cookie).
1. Audience Manager ruft den Drittanbieter-Datenprovider auf, um Besucher-IDs abzugleichen.
1. Eine geplante Anforderung (üblicherweise in einem täglichen Intervall) umgeht Besuchersegmentdaten zwischen Audience Manager und Ihrem Drittanbieter-Datenanbieter.
1. Wenn eine Inbound [!UICONTROL Server-to-Server] -Datei verarbeitet wird, wird ein Beleg per E-Mail an Partnerlösungen gesendet und, falls konfiguriert, dem Partner. Weitere Informationen finden Sie unter [Beispielnachricht für Partner nach der eingehenden Verarbeitung](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
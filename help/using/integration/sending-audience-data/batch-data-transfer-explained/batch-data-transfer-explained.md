---
description: Ein allgemeiner Überblick darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Beschriebener Batch-Datenübertragungsprozess
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Beschriebener Batch-Datenübertragungsprozess {#batch-data-transfer-process-described}

Ein allgemeiner Überblick darüber, wie [!DNL Audience Manager] einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.

## Batch-Datenintegration

<!-- c_async.xml -->

Der Batch-Datenintegrationsprozess speichert Besucherinformationen auf unseren Servern und synchronisiert dieses Material mit Daten, die von einem Anbieter in regelmäßigen Abständen gesendet werden. Der asynchrone Datenübertragungsprozess ist nützlich, wenn:

* Sofortige Datenübertragungen sind nicht erforderlich.
* Erfassen von Daten, um einen großen Pool segmentierter Benutzender zu erstellen.
* Sie möchten Datendiskrepanzen reduzieren und Aufrufe aus dem Browser `HTTP`.

![](assets/s2s_70.png)

## Schritte zur Datenintegration

1. Ein Benutzer besucht eine Kunden-Site.
1. [!DNL Audience Manager] und der Drittanbieter weisen dem Besucher eine eindeutige ID zu (in der Regel mit einem Cookie).
1. [!DNL Audience Manager] ruft den Drittanbieter-Datenanbieter auf, Besucher-IDs abzugleichen.
1. Bei einer geplanten Anfrage werden in der Regel in einem täglichen Intervall Besuchersegmentdaten zwischen [!DNL Audience Manager] und dem Drittanbieter ausgetauscht.
1. Bei jeder Verarbeitung einer eingehenden [!UICONTROL Server-to-Server]-Datei wird eine Quittung per E-Mail an die Partnerlösungen und, falls konfiguriert, an den Partner gesendet. Weitere Informationen finden Sie unter [Beispielnachricht an Partner nach der eingehenden Verarbeitung](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).

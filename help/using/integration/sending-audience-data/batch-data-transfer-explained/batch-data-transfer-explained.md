---
description: Ein allgemeiner Überblick darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-description: Ein allgemeiner Überblick darüber, wie Audience Manager einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.
seo-title: Beschreibung des Batch-Datenübertragungsprozesses
solution: Audience Manager
title: Beschreibung des Batch-Datenübertragungsprozesses
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Übertragungen von Inbound-Daten
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# Beschreibung des Batch-Datenübertragungsprozesses {#batch-data-transfer-process-described}

Ein allgemeiner Überblick darüber, wie [!DNL Audience Manager] einen asynchronen Batch-Datenaustausch mit einem Drittanbieter durchführt.

## Batch-Datenintegration

<!-- c_async.xml -->

Der Prozess der Batch-Datenintegration speichert Besucherinformationen auf unseren Servern und synchronisiert dieses Material mit Daten, die von einem Provider in regelmäßigen Abständen gesendet werden. Der Prozess der asynchronen Datenübertragung ist nützlich, wenn:

* Eine sofortige Datenübertragung ist nicht erforderlich.
* Erfassen von Daten zum Erstellen eines großen Pools segmentierter Benutzer.
* Sie möchten Datendiskrepanzen und `HTTP` -Aufrufe aus dem Browser reduzieren.

![](assets/s2s_70.png)

## Datenintegrationsschritte

1. Ein Benutzer besucht eine Kunden-Site.
1. [!DNL Audience Manager] und der Datenanbieter eines Drittanbieters dem Besucher eine eindeutige ID zuweist (normalerweise mit einem Cookie).
1. [!DNL Audience Manager] ruft den Drittanbieter für Daten auf, um Besucher-IDs zuzuordnen.
1. Bei einer geplanten Anforderung, die normalerweise in einem täglichen Intervall erfolgt, werden Besuchersegmentdaten zwischen [!DNL Audience Manager] und Ihrem Drittanbieter ausgetauscht.
1. Bei jeder Verarbeitung einer eingehenden [!UICONTROL Server-to-Server]-Datei wird eine Quittung per E-Mail an Partnerlösungen und, falls konfiguriert, an den Partner gesendet. Weitere Informationen finden Sie unter [Beispielnachricht an Partner nach der eingehenden Verarbeitung](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).

---
description: Ein allgemeiner Überblick darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter von Inhalten durchführt
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Beschreibung des Echtzeit-Datenübertragungsprozesses
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---


# Beschreibung des Echtzeit-Datenübertragungsprozesses{#real-time-data-transfer-process-described}

Ein allgemeiner Überblick darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter von Inhalten durchführt

<!-- real-time-data-transfer-explained.xml -->

## Echtzeitdatenübertragungen

Bei Echtzeit-Datenübertragungen werden Segment-IDs gesendet und empfangen, wenn ein Benutzer Ihre Site besucht oder Maßnahmen ergreift. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie Benutzer sofort qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

## Datenintegrationsschritte

Der Echtzeit-Datenintegrationsprozess funktioniert wie folgt:

1. Ein Benutzer besucht die Site eines Kunden, die Audience Manager-Code enthält.
1. Audience Manager lädt einen iframe und ruft unsere [!UICONTROL Data Collection Server] ( [!DNL DCS]) auf.
1. Der [!DNL DCS] ruft den Drittanbieter-Server (in Echtzeit) auf, um zu überprüfen, ob der Anbieter über Segmentinformationen zum Benutzer verfügt.
1. Der Inhaltsanbieter gibt Segmentinformationen zu diesem Benutzer an den Audience Manager zurück.
1. Audience Manager erhält diese Segmentinformationen und stellt sie für das Targeting und das Erstellen neuer Eigenschaften und Segmente bereit.

![](assets/rt_reduce70.png)
---
description: Ein allgemeiner Überblick darüber, wie Audience Manager Echtzeitdatenübertragungen mit einem Drittanbieter von Inhalten durchführt.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Verfahren zur Echtzeit-Datenübertragung - Beschreibung
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---


# Verfahren zur Echtzeit-Datenübertragung - Beschreibung{#real-time-data-transfer-process-described}

Ein allgemeiner Überblick darüber, wie Audience Manager Echtzeitdatenübertragungen mit einem Drittanbieter von Inhalten durchführt.

<!-- real-time-data-transfer-explained.xml -->

## Echtzeit-Datenübertragungen

Bei Echtzeit-Datenübertragungen werden Segment-IDs gesendet und empfangen, wenn ein Benutzer Ihre Site besucht oder eine Aktion auf Ihrer Site ausführt. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie Benutzende qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

## Schritte zur Datenintegration

Der Echtzeit-Datenintegrationsprozess funktioniert wie folgt:

1. Ein Besucher besucht die Website eines Kunden, die Audience Manager-Code enthält.
1. Audience Manager lädt einen iFrame und ruft unsere [!UICONTROL Data Collection Server] auf ( [!DNL DCS]).
1. Der [!DNL DCS] ruft den Drittanbieterserver (in Echtzeit) auf, um zu überprüfen, ob der Anbieter über Segmentinformationen zum Benutzer verfügt.
1. Der Inhaltsanbieter gibt Segmentinformationen zu diesem Benutzer an den Audience Manager zurück.
1. Audience Manager erhält diese Segmentinformationen und stellt sie für das Targeting und das Erstellen neuer Eigenschaften und Segmente zur Verfügung.

![](assets/rt_reduce70.png)
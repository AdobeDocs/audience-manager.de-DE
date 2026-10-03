---
description: Ein allgemeiner Überblick darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter von Inhalten durchführt.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Verfahren zur Echtzeit-Datenübertragung - Beschreibung
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%
---

# Verfahren zur Echtzeit-Datenübertragung - Beschreibung{#real-time-data-transfer-process-described}

Ein allgemeiner Überblick darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter von Inhalten durchführt.

<!-- real-time-data-transfer-explained.xml -->

## Echtzeit-Datenübertragungen

Bei Echtzeit-Datenübertragungen werden Segment-IDs gesendet und empfangen, wenn ein Benutzer Ihre Site besucht oder eine Aktion auf Ihrer Site ausführt. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie Benutzende qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

## Schritte zur Datenintegration

Der Echtzeit-Datenintegrationsprozess funktioniert wie folgt:

1. Ein Benutzer besucht die Website eines Kunden, die Audience Manager-Code enthält.
1. Audience Manager lädt einen iFrame und ruft unsere [!UICONTROL Data Collection Server] auf ( [!DNL DCS]).
1. Der [!DNL DCS] ruft den Drittanbieterserver (in Echtzeit) auf, um zu überprüfen, ob der Anbieter über Segmentinformationen zum Benutzer verfügt.
1. Der Inhaltsanbieter gibt Segmentinformationen zu diesem Benutzer an Audience Manager zurück.
1. Audience Manager erhält diese Segmentinformationen und stellt sie für das Targeting und das Erstellen neuer Eigenschaften und Segmente zur Verfügung.

![](assets/rt_reduce70.png)
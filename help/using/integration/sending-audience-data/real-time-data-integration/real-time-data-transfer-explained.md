---
description: Eine allgemeine Übersicht darüber, wie Audience Manager Datenübertragungen in Echtzeit mit einem Content Provider eines Drittanbieters durchführt.
seo-description: Eine allgemeine Übersicht darüber, wie Audience Manager Datenübertragungen in Echtzeit mit einem Content Provider eines Drittanbieters durchführt.
seo-title: Beschriebener Datenübertragungsprozess in Echtzeit
solution: Audience Manager
title: Beschriebener Datenübertragungsprozess in Echtzeit
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Beschriebener Datenübertragungsprozess in Echtzeit{#real-time-data-transfer-process-described}

Eine allgemeine Übersicht darüber, wie Audience Manager Datenübertragungen in Echtzeit mit einem Content Provider eines Drittanbieters durchführt.

<!-- real-time-data-transfer-explained.xml -->

## Datenübertragung in Echtzeit

Echtzeit-Datenübertragungen senden und empfangen Segment-IDs als Benutzerbesuche oder Aktionen auf Ihrer Site. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie Benutzer sofort qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

## Schritte zur Datenintegration

Die Datenintegration in Echtzeit funktioniert wie folgt:

1. Ein Benutzer besucht die Site eines Kunden, die Audience Manager-Code enthält.
1. Audience Manager lädt einen iframe und ruft unser [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]) auf.
1. Der Drittanbieterserver [!UICONTROL DCS] ruft (in Echtzeit) auf, um zu prüfen, ob der Anbieter Segmentinformationen über den Benutzer hat.
1. Der Content Provider gibt Segmentinformationen zu diesem Benutzer an Audience Manager zurück.
1. Audience Manager erhält diese Segmentinformationen und stellt sie für das Targeting und das Erstellen neuer Eigenschaften und Segmente bereit.

![](assets/rt_reduce70.png)
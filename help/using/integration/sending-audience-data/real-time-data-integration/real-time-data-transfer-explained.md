---
description: Eine allgemeine Übersicht darüber, wie Audience Manager Datenübertragungen in Echtzeit mit einem Content Provider eines Drittanbieters durchführt.
seo-description: Eine allgemeine Übersicht darüber, wie Audience Manager Datenübertragungen in Echtzeit mit einem Content Provider eines Drittanbieters durchführt.
seo-title: Beschriebener Datenübertragungsprozess in Echtzeit
solution: Audience Manager
title: Beschriebener Datenübertragungsprozess in Echtzeit
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Datentransferprozess in Echtzeit beschrieben{#real-time-data-transfer-process-described}

Eine allgemeine Übersicht darüber, wie Audience Manager Datenübertragungen in Echtzeit mit einem Content Provider eines Drittanbieters durchführt.

<!-- real-time-data-transfer-explained.xml -->

## Datenübertragung in Echtzeit

Echtzeit-Datenübertragungen senden und empfangen Segment-IDs als Benutzerbesuche oder ergreifen Aktionen auf Ihrer Site. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie Benutzer sofort qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

## Schritte zur Datenintegration

Der Datenintegrationsprozess in Echtzeit funktioniert wie folgt:

1. Ein Benutzer besucht die Site eines Kunden, die Audience Manager-Code enthält.
1. Audience Manager lädt einen iframe und ruft unser [!UICONTROL Data Collection Server] ( [!DNL DCS]) auf.
1. Das [!DNL DCS] ruft den Drittanbieter-Server (in Echtzeit) auf, um zu prüfen, ob der Anbieter Segmentinformationen über den Benutzer hat.
1. Der Content Provider gibt Segmentinformationen über diesen Benutzer an den Audience Manager zurück.
1. Audience Manager erhält diese Segmentinformationen und stellt sie für Targeting und das Erstellen neuer Eigenschaften und Segmente bereit.

![](assets/rt_reduce70.png)
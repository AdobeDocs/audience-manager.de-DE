---
description: Eine allgemeine Übersicht darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter-Content-Provider durchführt.
seo-description: Eine allgemeine Übersicht darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter-Content-Provider durchführt.
seo-title: Beschriebenen Echtzeit-Datenübertragungsprozess
solution: Audience Manager
title: Beschriebenen Echtzeit-Datenübertragungsprozess
uuid: b 68781 b 3-0 b 7 a -442 d -8 e 44-2 db 2474849 a 4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Beschriebenen Echtzeit-Datenübertragungsprozess{#real-time-data-transfer-process-described}

Eine allgemeine Übersicht darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter-Content-Provider durchführt.

<!-- real-time-data-transfer-explained.xml -->

## Echtzeit-Datenübertragungen

Datenübertragungen in Echtzeit senden und empfangen Segment-IDs als Benutzerbesuche oder werden auf Ihrer Site ausgeführt. synchrone Datenübertragungen sind normalerweise sinnvoll, wenn Sie Benutzer direkt qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

## Datenintegrationsschritte

Der Echtzeit-Datenintegrationsprozess funktioniert wie folgt:

1. Ein Benutzer besucht die Site eines Kunden, die den Audience Manager-Code enthält.
1. Audience Manager lädt einen iframe und sendet einen Aufruf an unseren [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. Der [!UICONTROL DCS] Server ruft den Drittanbieterserver (in Echtzeit) auf, um zu überprüfen, ob der Anbieter über Segmentinformationen zum Benutzer verfügt.
1. Der Content Provider gibt Segmentinformationen zu diesem Benutzer an den Audience Manager zurück.
1. Audience Manager empfängt diese Segmentinformationen und stellt es für das Targeting und das Erstellen neuer Eigenschaften und Segmente bereit.

![](assets/rt_reduce70.png)
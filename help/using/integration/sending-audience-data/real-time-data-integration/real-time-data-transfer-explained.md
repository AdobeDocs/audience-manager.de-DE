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


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

Eine allgemeine Übersicht darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter-Content-Provider durchführt.

<!-- real-time-data-transfer-explained.xml -->

## Echtzeit-Datenübertragungen

Datenübertragungen in Echtzeit senden und empfangen Segment-IDs als Benutzerbesuche oder werden auf Ihrer Site ausgeführt. synchrone Datenübertragungen sind normalerweise sinnvoll, wenn Sie Benutzer direkt qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

## Datenintegrationsschritte

Der Echtzeit-Datenintegrationsprozess funktioniert wie folgt:

1. Ein Benutzer besucht die Site eines Kunden, die den Audience Manager-Code enthält.
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. Der Content Provider gibt Segmentinformationen zu diesem Benutzer an den Audience Manager zurück.
1. Audience Manager empfängt diese Segmentinformationen und stellt es für das Targeting und das Erstellen neuer Eigenschaften und Segmente bereit.

![](assets/rt_reduce70.png)
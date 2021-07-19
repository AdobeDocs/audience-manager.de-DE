---
description: Ein allgemeiner Überblick darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter von Inhalten durchführt.
seo-description: Ein allgemeiner Überblick darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter von Inhalten durchführt.
seo-title: Beschreibung des Echtzeit-Datenübertragungsprozesses
solution: Audience Manager
title: Beschreibung des Echtzeit-Datenübertragungsprozesses
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Übertragungen von Inbound-Daten
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---


# Beschreibung des Echtzeit-Datenübertragungsprozesses{#real-time-data-transfer-process-described}

Ein allgemeiner Überblick darüber, wie Audience Manager Echtzeit-Datenübertragungen mit einem Drittanbieter von Inhalten durchführt.

<!-- real-time-data-transfer-explained.xml -->

## Echtzeit-Datenübertragungen

Bei Echtzeit-Datenübertragungen werden Segment-IDs gesendet und empfangen, wenn ein Benutzer Ihre Site besucht oder Maßnahmen ergreift. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie Benutzer sofort qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

## Datenintegrationsschritte

Der Echtzeit-Datenintegrationsprozess funktioniert wie folgt:

1. Ein Benutzer besucht die Site eines Kunden, die Audience Manager-Code enthält.
1. Audience Manager lädt einen iFrame und sendet einen Aufruf an [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. Der [!DNL DCS] ruft den Drittanbieter-Server (in Echtzeit) auf, um zu überprüfen, ob der Anbieter über Segmentinformationen zum Benutzer verfügt.
1. Der Inhaltsanbieter gibt Segmentinformationen zu diesem Benutzer an den Audience Manager zurück.
1. Audience Manager erhält diese Segmentinformationen und stellt sie für das Targeting und das Erstellen neuer Eigenschaften und Segmente bereit.

![](assets/rt_reduce70.png)
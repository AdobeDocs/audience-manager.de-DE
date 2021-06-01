---
description: Server-zu-Server-APIs (S2S) bieten Code und Methoden, mit denen Sie DCS-Benutzerdaten senden und empfangen und mit diesen Informationen in Ihren eigenen Systemen oder Anwendungen arbeiten können.
seo-description: Server-zu-Server-APIs (S2S) bieten Code und Methoden, mit denen Sie DCS-Benutzerdaten senden und empfangen und mit diesen Informationen in Ihren eigenen Systemen oder Anwendungen arbeiten können.
seo-title: DCS-APIs für Server-zu-Server-Datenübertragungen
solution: Audience Manager
title: DCS-APIs für Server-zu-Server-Datenübertragungen
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---

# DCS-APIs für Server-zu-Server-Datenübertragungen{#dcs-apis-for-server-to-server-data-transfers}

Server-zu-Server ([!UICONTROL S2S]) [!DNL API]s bieten Code und Methoden, mit denen Sie [!DNL DCS] Benutzerdaten senden und empfangen und mit diesen Informationen in Ihren eigenen Systemen oder Anwendungen arbeiten können.

## Häufige Anwendungsfälle {#common-use-cases}

[!UICONTROL Server-to-server] -Übertragungen können Ihnen dabei helfen, Landingpages oder andere Interaktionen auf der Grundlage von Besucherinteressen anzupassen. Einige gängige Anwendungsfälle sind:

* Personalisierung vor Ort: Anpassen des Besuchererlebnisses auf Ihrer Site durch dynamisches Hinzufügen relevanter Inhalte und Aktionsaufrufe basierend auf den Segmenten, zu denen sie gehören.
* Verbesserter Kundendienst: Importieren Sie [!DNL Audience Manager]-Segmente in ein [!DNL CRM] oder ein anderes System durch eine Server-zu-Server-Datenübertragung. Diese Daten können Anrufdienst- oder Online-Chat-Benutzern relevante, personalisierte Informationen über einen Kunden liefern.

## Voraussetzungen: Benutzer-IDs und regionale Servernamen {#requirements}

Für [!UICONTROL DCS API] sind Benutzer-IDs und Regions-IDs erforderlich, um Datenanforderungen zu validieren und vorzunehmen.

* Die Benutzer-ID ist erforderlich, da Sie Daten mit einem bestimmten Besucher verknüpfen müssen.
* Die Regions-ID ist erforderlich, um Aufrufe mit einem Servernamen zu verknüpfen, da Benutzerdaten in Rechenzentren gespeichert werden, die geografisch den Besuchern der Site am nächsten sind.

## Erste Schritte {#getting-started}

In diesem Handbuch werden derzeit folgende Themen behandelt:

* Rufen Sie die Benutzer- und Regions-IDs aus den [!DNL DCS] -Dateien ab, die Sie möglicherweise bereits als [!DNL Audience Manager]-Kunde erhalten haben.

* Rufen Sie die Benutzer- und Regions-IDs ab, wenn Sie [!DNL Visitor ID Service] verwenden.
* Rufen Sie [!DNL DCS] auf, nachdem Sie über die Benutzer- und Regions-ID verfügen.

Wir fügen neue Methoden hinzu, sobald sie verfügbar werden. Erste Schritte finden Sie in den folgenden Abschnitten.

* [Abrufen von Benutzer-IDs und Regionen über eine DCS-Antwort](dcs-aam-ids.md)
* [Abrufen von Benutzer-IDs und Regionen über die Experience Cloud-ID..](dcs-mcid-ids.md)
* [Ausführen von Server-zu-Server-DCS-API-Aufrufen](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS-API-Referenz ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)


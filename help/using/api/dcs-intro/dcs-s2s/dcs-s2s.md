---
description: Server-zu-Server-(S2S-)APIs stellen Code und Methoden bereit, mit denen Sie DCS-Benutzerdaten senden und empfangen und mit diesen Informationen in Ihren eigenen Systemen oder Anwendungen arbeiten können.
seo-description: Server-zu-Server-(S2S-)APIs stellen Code und Methoden bereit, mit denen Sie DCS-Benutzerdaten senden und empfangen und mit diesen Informationen in Ihren eigenen Systemen oder Anwendungen arbeiten können.
seo-title: DCS-APIs für Server-zu-Server-Datenübertragungen
solution: Audience Manager
title: DCS-APIs für Server-zu-Server-Datenübertragungen
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS-APIs für Server-zu-Server-Datenübertragungen{#dcs-apis-for-server-to-server-data-transfers}

Server-zu-Server ([!UICONTROL S2S]) [!DNL API][!UICONTROL DCS] bieten Code und Methoden, mit denen Sie Benutzerdaten senden und empfangen und mit denen Sie in Ihren eigenen Systemen oder Anwendungen mit diesen Informationen arbeiten können.

## Häufige Anwendungsfälle {#common-use-cases}

[!UICONTROL Server-to-server] Transfers können Ihnen dabei helfen, Einstiegsseiten oder andere Interaktionen je nach Besucherinteressen anzupassen. Zu den häufigen Anwendungsfällen zählen:

* Personalisierung vor Ort: Sie können das Erlebnis eines Besuchers auf Ihrer Site anpassen, indem Sie entsprechend den Segmenten, zu denen er gehört, relevante Inhalte und Aktionsaufrufe dynamisch hinzufügen.
* Verbessern Sie den Kundenservice: Importieren Sie [!DNL Audience Manager] Segmente über eine Server-zu-Server-Datenübertragung in ein [!DNL CRM] oder ein anderes System. Diese Daten können Call-Service- oder Online-Chat-Operatoren relevante, personalisierte Informationen über einen Kunden bereitstellen.

## Anforderungen: Benutzer-IDs und regionale Servernamen {#requirements}

Für [!UICONTROL DCS API] die Überprüfung und Durchführung von Datenanforderungen sind Benutzer-IDs und Regions-IDs erforderlich.

* Die Benutzer-ID ist erforderlich, da Sie Daten mit einem bestimmten Besucher verknüpfen müssen.
* Die Regions-ID ist erforderlich, um Aufrufe mit einem Servernamen zu verknüpfen, da Benutzerdaten in Rechenzentren gespeichert werden, die den Site-Besuchern geografisch am nächsten stehen.

## Erste Schritte {#getting-started}

In diesem Handbuch werden derzeit folgende Schritte beschrieben:

* Besorgen Sie sich die Benutzer- und Regions-IDs aus den [!UICONTROL DCS] Dateien, die Sie möglicherweise bereits als [!DNL Audience Manager] Kunde erhalten haben.

* Rufen Sie die Benutzer- und Regions-IDs ab, wenn Sie die [!DNL Visitor ID Service]Variable verwenden.
* Rufen Sie die [!UICONTROL DCS] nach der Benutzer- und Regions-ID an.

Wir werden neue Methoden hinzufügen, sobald sie verfügbar werden. Die ersten Schritte finden Sie in den folgenden Abschnitten.

* [Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort](dcs-aam-ids.md)
* [Erhalten Sie Benutzer-IDs und Regionen mit der Experience Cloud ID...](dcs-mcid-ids.md)
* [Ausführen von Server-zu-Server-DCS-API-Aufrufen](dcs-s2s-calls.md)

>[!MORE_LIKE_THIS]
>
>* [DCS API-Referenz](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)


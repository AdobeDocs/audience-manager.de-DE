---
description: Server-zu-Server-(S2S-)APIs stellen Code und Methoden bereit, mit denen Sie DCS-Benutzerdaten senden und empfangen und mit diesen Informationen in Ihren eigenen Systemen oder Anwendungen arbeiten können.
seo-description: Server-zu-Server-(S2S-)APIs stellen Code und Methoden bereit, mit denen Sie DCS-Benutzerdaten senden und empfangen und mit diesen Informationen in Ihren eigenen Systemen oder Anwendungen arbeiten können.
seo-title: DCS-APIs für Server-zu-Server-Datenübertragungen
solution: Audience Manager
title: DCS-APIs für Server-zu-Server-Datenübertragungen
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 11%

---


# DCS-APIs für Server-zu-Server-Datenübertragungen{#dcs-apis-for-server-to-server-data-transfers}

Server-zu-Server ([!UICONTROL S2S]) [!DNL API]s stellen Code und Methoden bereit, mit denen Sie [!DNL DCS]-Benutzerdaten senden und empfangen können und mit denen Sie in Ihren eigenen Systemen oder Anwendungen mit diesen Informationen arbeiten können.

## Allgemeine Verwendungsfälle {#common-use-cases}

[!UICONTROL Server-to-server] Transfers können Ihnen dabei helfen, Landingpages oder andere Interaktionen auf der Grundlage der Interessen des Besuchers anzupassen. Zu den häufigen Anwendungsfällen zählen:

* Personalisierung vor Ort: Passen Sie das Erlebnis eines Besuchers auf Ihrer Site an, indem Sie entsprechend den Segmenten, zu denen er gehört, relevante Inhalte und Aktionsaufrufe dynamisch hinzufügen.
* Verbessern Sie den Kundenservice: Importieren Sie [!DNL Audience Manager]-Segmente in ein [!DNL CRM]- oder ein anderes System durch eine Server-zu-Server-Datenübertragung. Diese Daten können Call-Service- oder Online-Chat-Operatoren relevante, personalisierte Informationen über einen Kunden bereitstellen.

## Anforderungen: Benutzer-IDs und regionale Servernamen {#requirements}

Für [!UICONTROL DCS API] sind Benutzer-IDs und Regions-IDs erforderlich, um Datenanforderungen zu validieren und durchzuführen.

* Die Benutzer-ID ist erforderlich, da Sie Daten mit einem bestimmten Besucher verknüpfen müssen.
* Die Regions-ID ist erforderlich, um Aufrufe an einen Servernamen zurückzubinden, da Benutzerdaten in Rechenzentren gespeichert werden, die geografisch am nächsten zu Site-Besuchern liegen.

## Erste Schritte {#getting-started}

In diesem Handbuch werden derzeit folgende Schritte beschrieben:

* Besorgen Sie sich die Benutzer- und Regions-IDs aus den [!DNL DCS]-Dateien, die Sie möglicherweise bereits als [!DNL Audience Manager]-Kunde erhalten haben.

* Rufen Sie die Benutzer- und Regions-IDs ab, wenn Sie [!DNL Visitor ID Service] verwenden.
* Rufen Sie das [!DNL DCS] auf, nachdem Sie die Benutzer- und Regions-ID haben.

Wir werden neue Methoden hinzufügen, sobald sie verfügbar werden. Die ersten Schritte finden Sie in den folgenden Abschnitten.

* [Abrufen von Benutzer-IDs und Regionen über eine DCS-Antwort](dcs-aam-ids.md)
* [Abrufen von Benutzer-IDs und Regionen über die Experience Cloud-ID...](dcs-mcid-ids.md)
* [Ausführen von Server-zu-Server-DCS-API-Aufrufen](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS-API-Referenz ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)


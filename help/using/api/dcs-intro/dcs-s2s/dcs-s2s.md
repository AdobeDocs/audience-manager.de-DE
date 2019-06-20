---
description: Server-to-Server (S 2 S)-apis stellen Code und Methoden bereit, mit denen Sie DCS-Benutzerdaten senden und empfangen können und mit diesen Informationen in Ihren eigenen Systemen oder Anwendungen arbeiten können.
seo-description: Server-to-Server (S 2 S)-apis stellen Code und Methoden bereit, mit denen Sie DCS-Benutzerdaten senden und empfangen können und mit diesen Informationen in Ihren eigenen Systemen oder Anwendungen arbeiten können.
seo-title: DCS apis für Server-zu-Server-Datenübertragungen
solution: Audience Manager
title: DCS apis für Server-zu-Server-Datenübertragungen
uuid: 8 c 369166-c 8 a 7-46 b 0-9913-4 c 027 f 5 b 1 df 9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS APIs for Server-to-Server Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s provide code and methods that let you send and receive [!UICONTROL DCS] user data and work with this information in your own systems or applications.

## Common Use Cases {#common-use-cases}

[!UICONTROL Server-to-server] Mithilfe von Übertragungen können Sie Einstiegsseiten oder andere Interaktionen basierend auf Besucherinteressen anpassen. Einige gängige Einsatzfälle sind:

* Personalisierung auf der Site: Passen Sie das Erlebnis eines Besuchers auf Ihre Site an, indem Sie dynamisch relevante Inhalte und Aktionsaufrufe basierend auf den Segmenten hinzufügen, denen sie angehören.
* Improve customer service: Import [!DNL Audience Manager] segments into a [!DNL CRM] or other system through a server-to-server data transfer. Diese Daten können Call-Service oder Online-Chat-Operatoren mit relevanten, personalisierten Informationen über einen Kunden bereitstellen.

## Requirements: User IDs and Regional Server Names {#requirements}

The [!UICONTROL DCS API] requires user IDs and region IDs to validate and make data requests.

* Die Benutzer-ID ist erforderlich, da Sie Daten einem bestimmten Besucher zuordnen müssen.
* Die Regions-ID ist erforderlich, um Aufrufe an einen Servernamen zurückzubinden und da Benutzerdaten in Datenzentren gespeichert werden, die den Site-Besuchern geografisch am nächsten sind.

## Erste Schritte {#getting-started}

Dieses Handbuch behandelt derzeit:

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

Wir fügen neue Methoden hinzu, sobald sie verfügbar werden. Lesen Sie die folgenden Abschnitte, um zu beginnen.

* [Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort](dcs-aam-ids.md)
* [Benutzer-IDs und Regionen über die Experience Cloud ID abrufen…](dcs-mcid-ids.md)
* [Server-zu-Server-DCS API-Aufrufe erstellen](dcs-s2s-calls.md)

>[!MORE_ LIKE_ THIS]
>
>* [DCS-API-Referenz](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)


---
description: Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.
seo-description: Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.
seo-title: Ziel-API-Methoden
solution: Audience Manager
title: Ziel-API-Methoden
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ziel-API-Methoden {#destination-api-methods}

Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.

<!-- c_destinations_api.xml -->

In Audience Manager ist ein Ziel ein beliebiges anderes System (Anzeigen-Server, [!DNL DSP]Werbenetzwerk, Austausch, Ihr eigenes Erstanbieter-Cookie usw.) , für die Sie Daten freigeben möchten.

## Zieltypen: URL und Cookie {#destination-types}

Listet die vom `destinationType` Parameter verwendeten Variablen auf. Geben Sie an `push` oder `ADS` arbeiten Sie mit einem [!UICONTROL URL] oder [!UICONTROL cookie destination]. Sie können keine [!UICONTROL server-to-server destinations] mit den verfügbaren [!DNL API] Zielmethoden erstellen.

<!-- r_destination_types.xml -->

| API-Zieltyp | UI-Zieltyp |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_LIKE_THIS]
>
>* [Auswählen eines Zieltyps](../../../features/destinations/destinations.md)


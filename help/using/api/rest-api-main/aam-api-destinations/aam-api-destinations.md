---
description: Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.
seo-description: Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.
seo-title: Ziel-API-Methoden
solution: Audience Manager
title: Ziel-API-Methoden
uuid: 048 bcdb 9-2 b 31-46 f 4-8 b 80-4 ba 25 bf 66640
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ziel-API-Methoden {#destination-api-methods}

Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.

<!-- c_destinations_api.xml -->

In Audience Manager ist ein Ziel ein anderes System (Werbeserver, [!DNL DSP]Werbenetzwerk, Exchange, Ihr eigenes Erstanbieter-Cookie usw.) , für die Sie Daten freigeben möchten.

## Zieltypen: URL und Cookie {#destination-types}

Listet die vom `destinationType` Parameter verwendeten Variablen auf. Geben Sie an `push` oder `ADS` arbeiten Sie mit einem [!UICONTROL URL] oder [!UICONTROL cookie destination]. Sie können nicht [!UICONTROL server-to-server destinations] mit den verfügbaren Zielmethoden [!DNL API] erstellen.

<!-- r_destination_types.xml -->

| API-Zieltyp | UI-Zieltyp |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORE_ LIKE_ THIS]
>
>* [Auswählen eines Zieltyps](../../../features/destinations/destinations.md)


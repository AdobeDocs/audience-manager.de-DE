---
description: Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: API-Methoden für Ziele
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 0%

---

# API-Methoden für Ziele {#destination-api-methods}

Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.

<!-- c_destinations_api.xml -->

Im Audience Manager ist ein Ziel ein anderes System (Adserver, [!DNL DSP], Werbenetzwerk, Austausch, Ihr eigenes Erstanbieter-Cookie usw.) , für die Sie Daten freigeben möchten.

## Zieltypen: URL und Cookie {#destination-types}

Führt die vom Parameter `destinationType` verwendeten Variablen auf. Geben Sie `push` oder `ADS` an, um mit einer [!UICONTROL URL] oder [!UICONTROL cookie destination] zu arbeiten. Sie können [!UICONTROL server-to-server destinations] nicht mit den verfügbaren Ziel-[!DNL API]-Methoden erstellen.

<!-- r_destination_types.xml -->

| API-Zieltyp | UI-Zieltyp |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Auswählen eines Zieltyps](../../../features/destinations/destinations.md)

---
description: Methoden, mit denen Sie programmgesteuert mit Zielfunktionen arbeiten können.
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

Methoden, mit denen Sie programmgesteuert mit Zielfunktionen arbeiten können.

<!-- c_destinations_api.xml -->

In Audience Manager ist ein Ziel jedes andere System (Werbeserver, [!DNL DSP], Werbenetzwerk, Exchange, Ihr eigenes Erstanbieter-Cookie usw.), für das Sie Daten freigeben möchten.

## Zieltypen: URL und Cookie {#destination-types}

Listet die vom `destinationType` Parameter verwendeten Variablen auf. Geben Sie `push` oder `ADS` an, um mit einem [!UICONTROL URL] oder einer [!UICONTROL cookie destination] zu arbeiten. Sie können keine [!UICONTROL server-to-server destinations] mit den verfügbaren [!DNL API] erstellen.

<!-- r_destination_types.xml -->

| API-Zieltyp | Benutzeroberflächen-Zieltyp |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Auswählen eines Zieltyps](../../../features/destinations/destinations.md)

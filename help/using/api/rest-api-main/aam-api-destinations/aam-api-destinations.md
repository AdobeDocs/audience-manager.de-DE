---
description: Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.
seo-description: Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.
seo-title: 'API-Methoden für Ziele '
solution: Audience Manager
title: 'API-Methoden für Ziele '
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 15%

---


# API-Methoden für Ziele {#destination-api-methods}

Methoden, mit denen Sie programmatisch mit Zielfunktionen arbeiten können.

<!-- c_destinations_api.xml -->

Im Audience Manager ist ein Ziel ein beliebiges anderes System (Anzeigenserver, [!DNL DSP], Werbenetzwerk, Austausch, Ihr eigenes Erstanbieter-Cookie usw.) für das Sie Daten freigeben möchten.

## Zieltypen: URL und Cookie {#destination-types}

Liste der Variablen, die vom Parameter `destinationType` verwendet werden. Geben Sie `push` oder `ADS` an, um mit einem [!UICONTROL URL] oder [!UICONTROL cookie destination] zu arbeiten. Sie können [!UICONTROL server-to-server destinations] nicht mit den verfügbaren Methoden [!DNL API] erstellen.

<!-- r_destination_types.xml -->

| API-Zieltyp | UI-Zieltyp |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Auswählen eines Zieltyps](../../../features/destinations/destinations.md)


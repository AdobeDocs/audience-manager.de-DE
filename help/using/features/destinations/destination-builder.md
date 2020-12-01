---
description: Mit dem Destination Builder können Sie cookie- oder DNL-URL-Ziele erstellen. Sie können mit dem Destination Builder keine Server-zu-Server-(S2S-)Ziele erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein S2S-Ziel einzurichten. Der Destination Builder befindet sich unter "Audience-Daten"> "Ziele".
seo-description: Mit dem Destination Builder können Sie cookie- oder DNL-URL-Ziele erstellen. Sie können mit dem Destination Builder keine Server-zu-Server-(S2S-)Ziele erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein S2S-Ziel einzurichten. Der Destination Builder befindet sich unter "Audience-Daten"> "Ziele".
seo-title: Destination Builder
solution: Audience Manager
title: Zielaufbau
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---


# Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] ermöglicht die Erstellung von Cookie-basierten Zielen oder  [!DNL URL] Zielen. Sie können keine Server-zu-Server-Ziele ([!DNL S2S]) mit [!UICONTROL Destination Builder] erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein [!DNL S2S]-Ziel einzurichten. [!UICONTROL Destination Builder] befindet sich in  **[!UICONTROL Audience Data > Destinations]**.

## Zielaufbau-Einstellungen {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] umfasst die folgenden Abschnitte und Einstellungen:

| [!UICONTROL Destination Builder] Abschnitt | Zielsetzung |
|--- |--- |
| Basisinformationen | Dient zum Benennen des Ziels, zum Beschreiben und Auswählen des Zieltyps ([!DNL URL] oder [!DNL cookie]) und der Plattform (all, [!DNL Android], browser oder [!DNL iOS]). |
| Konfiguration | Umfasst Steuerelemente für: <br/><ul><li>Übermittlung von Schlüsselwertdaten an [!DNL URL]-Ziele. Sie können Daten als einzelne oder serialisierte Schlüssel/Wert-Paare senden. Weitere Informationen finden Sie unter [Zielserialisierung](../../features/destinations/key-value-pairs.md#destination-serialized) und [Standardwerte und Serielle Schlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md). </li><li>Elemente eines Cookie-Ziels wie Cookie-Name, Domäne, Größe, Ablaufintervall, Datenformat usw.</li></ul> |
| Segmentzuordnungen | Sie können die: <br/><ul><li>Suchen, Hinzufügen und Verwalten von Segmenten, die mit allen Zieltypen verknüpft sind. </li><li>Legen Sie Versandprioritäten für einzelne Segmente fest (nur für [!DNL cookie]-basierte Segmente).</li></ul> |

## Data Versand-Methoden {#data-delivery-methods}

Senden Sie Informationen an ein Ziel, indem Sie sie über eine [!DNL URL]-Zeichenfolge, durch Schreiben an einen Browser [!DNL cookie] oder durch Offline-Server-zu-Server-Datenübertragung übermitteln.

* [!DNL URL] und cookie-basierte Ziele senden Daten synchron, wenn ein Benutzer auf einer Seite aktiv wird.
* Die Datenübertragung von Server zu Server ist asynchron und kann lange nach dem Verlassen der Seite durch einen Benutzer erfolgen. Der ausgewählte Versand hängt von Ihren Geschäftsanforderungen und davon ab, wie ein bestimmter Datenpartner Daten empfangen möchte oder kann.

Weitere Informationen finden Sie unter [So wählen Sie einen Zieltyp](../../features/destinations/destinations.md) aus.
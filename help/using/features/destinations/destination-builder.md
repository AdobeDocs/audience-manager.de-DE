---
description: Mit Destination Builder können Sie Cookie-basierte oder DNL-URL-Ziele erstellen. Sie können mit Destination Builder keine Server-zu-Server-Ziele (S2S) erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein S2S-Ziel einzurichten. Der Destination Builder befindet sich unter Zielgruppendaten > Ziele .
seo-description: Mit Destination Builder können Sie Cookie-basierte oder DNL-URL-Ziele erstellen. Sie können mit Destination Builder keine Server-zu-Server-Ziele (S2S) erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein S2S-Ziel einzurichten. Der Destination Builder befindet sich unter Zielgruppendaten > Ziele .
seo-title: Destination Builder
solution: Audience Manager
title: Destination Builder
feature: Zielgrundlagen
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] Ermöglicht die Erstellung von Cookie-basierten oder - [!DNL URL] Zielen. Sie können keine Server-zu-Server-Ziele ([!DNL S2S]) mit [!UICONTROL Destination Builder] erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein [!DNL S2S]-Ziel einzurichten. [!UICONTROL Destination Builder] befindet sich in  **[!UICONTROL Audience Data > Destinations]**.

## Einstellungen des Zielaufbaus {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] besteht aus den folgenden Abschnitten und Einstellungen:

| [!UICONTROL Destination Builder] Abschnitt | Zielsetzung |
|--- |--- |
| Basisinformationen | Wird verwendet, um das Ziel zu benennen, es zu beschreiben und den Zieltyp ([!DNL URL] oder [!DNL cookie]) sowie die Plattform (all, [!DNL Android], browser oder [!DNL iOS]) auszuwählen. |
| Konfiguration | Enthält Steuerelemente für: <br/><ul><li>Übergeben von Schlüssel-Wert-Daten an [!DNL URL]-Ziele. Sie können Daten als einzelne oder serialisierte Schlüssel-Wert-Paare senden. Weitere Informationen finden Sie unter [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized) und [Standard- und Serial Key-Value-Paare](../../features/destinations/key-value-pairs.md). </li><li>Elemente eines Cookie-Ziels wie Cookie-Name, Domäne, Größe, Ablaufintervall, Datenformat usw.</li></ul> |
| Segmentzuordnungen | Sie können die: <br/><ul><li>Suchen, Hinzufügen und Verwalten von Segmenten, die mit allen Zieltypen verknüpft sind. </li><li>Legen Sie Versandprioritäten für einzelne Segmente fest (nur für [!DNL cookie]-basierte Segmente).</li></ul> |

## Datenbereitstellungsmethoden {#data-delivery-methods}

Senden Sie Informationen an ein Ziel, indem Sie sie über eine [!DNL URL]-Zeichenfolge, durch Schreiben an einen Browser [!DNL cookie] oder durch Offline-Server-zu-Server-Datenübertragungen übergeben.

* [!DNL URL] und Cookie-basierte Ziele übermitteln Daten synchron, wenn ein Benutzer Aktionen auf einer Seite ausführt.
* Die Übertragung von Server-zu-Server-Daten erfolgt asynchron und kann lange nach dem Verlassen der Seite durch einen Benutzer erfolgen. Der ausgewählte Versandtyp hängt von Ihren Geschäftsanforderungen ab und davon, wie ein bestimmter Datenpartner Daten empfangen möchte oder empfangen kann.

Weitere Informationen finden Sie unter [Auswählen eines Zieltyps](../../features/destinations/destinations.md) .

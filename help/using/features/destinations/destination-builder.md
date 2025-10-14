---
description: Mit Destination Builder können Sie Cookie-basierte oder DNL-URL-Ziele erstellen. Sie können mit Destination Builder keine Server-zu-Server-Ziele (S2S) erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein S2S-Ziel einzurichten. Der Destination Builder befindet sich unter Zielgruppendaten > Ziele .
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Ziel-Builder
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Ziel-Builder {#destination-builder}

[!UICONTROL Destination Builder] können Sie Cookie-basierte oder [!DNL URL] Ziele erstellen. Sie können keine Server-zu-Server-Ziele ([!DNL S2S]) mit [!UICONTROL Destination Builder] erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein [!DNL S2S] einzurichten. [!UICONTROL Destination Builder] befindet sich in **[!UICONTROL Audience Data > Destinations]**.

## Einstellungen von Destination Builder {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] besteht aus den folgenden Abschnitten und Einstellungen:

| [!UICONTROL Destination Builder] | Zielsetzung |
|--- |--- |
| Basisinformationen | Wird verwendet, um das Ziel zu benennen, zu beschreiben und den Zieltyp ([!DNL URL] oder [!DNL cookie]) und die Plattform (alle, [!DNL Android], Browser oder [!DNL iOS]) auszuwählen. |
| Konfiguration | Enthält Steuerelemente für: <br/><ul><li>Übergeben von Schlüsselwertdaten an [!DNL URL] Ziele. Sie können Daten als einzelne oder serialisierte Schlüssel-Wert-Paare senden. Weitere Informationen finden Sie unter [Zielserialisierung](../../features/destinations/key-value-pairs.md#destination-serialized) und [Standard- und serielle Schlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md). </li><li>Elemente eines Cookie-Ziels wie Cookie-Name, Domain, Größe, Ablaufintervall, Datenformat usw.</li></ul> |
| Segmentzuordnungen | Ermöglicht Folgendes: <br/><ul><li>Suchen, Hinzufügen und Verwalten von Segmenten, die mit allen Zieltypen verknüpft sind. </li><li>Festlegen von Versandprioritäten für einzelne Segmente (nur für [!DNL cookie] Segmente).</li></ul> |

## Datenbereitstellungsmethoden {#data-delivery-methods}

Senden Sie Informationen an ein Ziel, indem Sie sie über eine [!DNL URL] Zeichenfolge, durch Schreiben in eine Browser-[!DNL cookie] oder durch Offline-Server-zu-Server-Datenübertragungen übergeben.

* [!DNL URL]- und Cookie-basierte Ziele übertragen Daten synchron, wenn ein Benutzer eine Aktion auf einer Seite ausführt.
* Die Server-zu-Server-Datenübertragung erfolgt asynchron und kann lange nach Verlassen der Seite durch einen Benutzer erfolgen. Der von Ihnen ausgewählte Versandtyp hängt von Ihren Geschäftsanforderungen ab und davon, wie ein bestimmter Datenpartner Daten empfangen möchte oder kann.

Weitere Informationen finden [&#x200B; unter „Auswählen &#x200B;](../../features/destinations/destinations.md) Zieltyps“.

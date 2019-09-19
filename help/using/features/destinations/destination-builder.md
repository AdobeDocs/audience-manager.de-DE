---
description: Mit dem Destination Builder können Sie cookie- oder DNL-URL-Ziele erstellen. Sie können mit dem Destination Builder keine Server-zu-Server-(S2S-)Ziele erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein S2S-Ziel einzurichten. Der Destination Builder befindet sich unter Zielgruppendaten > Ziele.
seo-description: Mit dem Destination Builder können Sie cookie- oder DNL-URL-Ziele erstellen. Sie können mit dem Destination Builder keine Server-zu-Server-(S2S-)Ziele erstellen, aber Sie können deren Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein S2S-Ziel einzurichten. Der Destination Builder befindet sich unter Zielgruppendaten > Ziele.
seo-title: Zielaufbau
solution: Audience Manager
title: Zielaufbau
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# Zielaufbau {#destination-builder}

[!UICONTROL Destination Builder] können Sie Cookie-basierte Ziele oder [!DNL URL] Ziele erstellen. Sie können keine Server-zu-Server-([!DNL S2S]) Ziele mit erstellen, [!UICONTROL Destination Builder]aber die Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein [!DNL S2S] Ziel einzurichten. [!UICONTROL Destination Builder] befindet sich in **[!UICONTROL Audience Data > Destinations]**.

## Zielaufbau-Einstellungen {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] umfasst die folgenden Abschnitte und Einstellungen:

| [!UICONTROL Destination Builder] Abschnitt | Zielsetzung |
|--- |--- |
| Basisinformationen | Dient zum Benennen des Ziels, zum Beschreiben und Auswählen des Zieltyps ([!DNL URL] oder [!DNL cookie]) und der Plattform (alle, [!DNL Android]Browser oder [!DNL iOS]). |
| Konfiguration | Umfasst Steuerelemente für: <br/><ul><li>Übermittlung von Schlüsselwertdaten an [!DNL URL] Ziele. Sie können Daten als einzelne oder serialisierte Schlüssel/Wert-Paare senden. Weitere Informationen finden Sie unter [Zielreihenbildung](../../features/destinations/key-value-pairs.md#destination-serialized) und [Standard- und Serial-Schlüsselwertpaare](../../features/destinations/key-value-pairs.md). </li><li>Elemente eines Cookie-Ziels wie Cookie-Name, Domäne, Größe, Ablaufintervall, Datenformat usw.</li></ul> |
|  Segmentzuordnungen | Sie können die: <br/><ul><li>Suchen, Hinzufügen und Verwalten von Segmenten, die mit allen Zieltypen verknüpft sind. </li><li>Legen Sie Bereitstellungsprioritäten für einzelne Segmente fest (nur für [!DNL cookie]basierte Segmente).</li></ul> |

## Datenbereitstellungsmethoden {#data-delivery-methods}

Senden Sie Informationen an ein Ziel, indem Sie sie über eine [!DNL URL] Zeichenfolge, durch Schreiben an einen Browser [!DNL cookie]oder durch Offline-Server-Datenübertragungen weiterleiten.

* [!DNL URL] und cookie-basierte Ziele senden Daten synchron, wenn ein Benutzer auf einer Seite aktiv wird.
* Die Datenübertragung von Server zu Server ist asynchron und kann lange nach dem Verlassen der Seite durch einen Benutzer erfolgen. Der von Ihnen ausgewählte Liefertyp hängt von Ihren Geschäftsanforderungen und davon ab, wie ein bestimmter Datenpartner Daten empfangen möchte oder kann.

Weitere Informationen finden Sie unter [Auswählen eines Zieltyps](../../features/destinations/destinations.md) .
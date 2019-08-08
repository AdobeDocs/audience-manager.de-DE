---
description: Mit Zielaufbau können Sie Cookie- oder DNL-URL-Ziele erstellen. Server-to-Server (S 2 S)-Ziele können nicht mit Destination Builder erstellt werden, Sie können jedoch ihre Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein S 2 S-Ziel einzurichten. Der Zielaufbau befindet sich unter Zielgruppendaten > Ziele.
seo-description: Mit Zielaufbau können Sie Cookie- oder DNL-URL-Ziele erstellen. Server-to-Server (S 2 S)-Ziele können nicht mit Destination Builder erstellt werden, Sie können jedoch ihre Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein S 2 S-Ziel einzurichten. Der Zielaufbau befindet sich unter Zielgruppendaten > Ziele.
seo-title: Zielaufbau
solution: Audience Manager
title: Zielaufbau
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# Zielaufbau {#destination-builder}

[!UICONTROL Destination Builder] ermöglicht es Ihnen, Cookie-basierte oder [!DNL URL] Ziele zu erstellen. Server-to-Server ([!DNL S2S])-Ziele können nicht erstellt werden, [!UICONTROL Destination Builder]Sie können jedoch ihre Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein [!DNL S2S] Ziel einzurichten. [!UICONTROL Destination Builder] befindet **[!UICONTROL Audience Data > Destinations]**.

## Ziel-Builder-Einstellungen {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] besteht aus den folgenden Abschnitten und Einstellungen:

| [!UICONTROL Destination Builder] Abschnitt | Zielsetzung |
|--- |--- |
| Basisinformationen | Dient zum Benennen des Ziels, der Beschreibung und des Zieltyps ([!DNL URL] oder [!DNL cookie]) sowie der Plattform (alle [!DNL Android], Browser oder [!DNL iOS]). |
| Konfiguration | Enthält Steuerelemente für: <br/><ul><li>Übergabe von Schlüsselwertdaten an [!DNL URL] Ziele. Sie können Daten als einzelne oder serialisierte Schlüssel-Wert-Paare senden. Weitere Informationen finden Sie unter [Zielserialisierung](../../features/destinations/key-value-pairs.md#destination-serialized) sowie [Standard- und Serienschlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md). </li><li>Elemente eines Cookie-Ziels wie Cookie-Name, Domäne, Größe, Ablaufintervall, Datenformat usw.</li></ul> |
| Segmentzuordnungen | Sie können die: <br/><ul><li>Suchen, Hinzufügen und Verwalten von Segmenten, die mit allen Zieltypen verknüpft sind. </li><li>Legen Sie die Bereitstellungsprioritäten für einzelne Segmente fest (nur [!DNL cookie]für -basierte Segmente).</li></ul> |

## Datenbereitstellungsmethoden {#data-delivery-methods}

Senden Sie Informationen an ein Ziel, indem Sie sie über eine [!DNL URL] Zeichenfolge übermitteln, in einen Browser [!DNL cookie]schreiben oder über Offline-Server-zu-Server-Datenübertragungen.

* [!DNL URL] und cookie-basierte Ziele werden synchron übertragen, da ein Benutzer Aktionen auf einer Seite durchführt.
* Die Server-zu-Server-Datenübertragung ist asynchron und kann lange auftreten, nachdem ein Benutzer die Seite verlassen hat. Der Auslieferungstyp, den Sie auswählen, hängt von Ihren geschäftlichen Anforderungen ab und davon, wie ein bestimmter Datenpartner Daten empfangen möchte oder kann.

Weitere [Informationen finden Sie unter Auswählen eines Zieltyps](../../features/destinations/destinations.md) .
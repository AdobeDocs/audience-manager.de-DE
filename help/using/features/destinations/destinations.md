---
description: In Audience Manager ist ein Ziel ein Drittanbietersystem (Anzeigen-Server, DSP, Werbenetzwerk usw.) , für die Sie Daten freigeben möchten. Zielaufbau ist das Tool, mit dem Sie Cookies, URL oder Server-to-Server-Ziele erstellen und verwalten.
keywords: Integrationscode, Ziel, Ziel-Überblick, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel
seo-description: In Audience Manager ist ein Ziel ein Drittanbietersystem (Anzeigen-Server, DSP, Werbenetzwerk usw.) , für die Sie Daten freigeben möchten. Zielaufbau ist das Tool, mit dem Sie Cookies, URL oder Server-to-Server-Ziele erstellen und verwalten.
seo-title: Ziele
solution: Audience Manager
title: Ziele
uuid: 5 c 7 dbdec-f 73 f -46 fe -9 f 12-7685 e 8 d 7334 f
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Übersicht über Ziele {#destinations}

In Audience Manager ist ein Ziel ein Drittanbietersystem (Werbeserver, [!DNL DSP]Werbenetzwerk usw.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] ist das Tool zum Erstellen und Verwalten von Cookies, [!DNL URL]oder Server-to-Server-Zielen.

## Zweck und Vorteile {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] können [!UICONTROL Destination Builder] Sie Ziele erstellen und Informationen über segmentierte Benutzer an Ihren Datenpartner senden. Dies hilft Ihnen:

* **Datenwert schützen:** Anstatt alle Benutzerdaten an ein Ziel zu senden, können [!UICONTROL Destination Builder] Sie bestimmte Informationen nur über qualifizierte Benutzer teilen.
* **Handeln Sie mit Ihren Daten:** Durch das Senden von Daten an einen Zielpartner können sie qualifizierte Zielgruppensegmente schnell entwickeln und gezielt ansprechen.
* **Technischer Aufwand reduzieren:** Geschäftsbenutzer können Ziele auf der [!UICONTROL Destination Builder] Benutzeroberfläche sicher einrichten. Dadurch wird die Zeit für Tests vor der Bereitstellung reduziert. Mit, [!UICONTROL Destination Builder]verwalten, verwalten und löschen Sie Ziele, wenn Sie sich ändern, ohne einen langen Entwicklungszyklus.

## Technische Aspekte {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Die Datenbereitstellung hängt davon ab, wie Ihr Datenpartner Ziel-Informationen erhalten möchte oder kann. Technische oder technische Einschränkungen können verhindern, dass ein Ziel Daten, [!DNL URL]Cookies oder Server-zu-Server-Prozesse empfängt. Wenden Sie sich an Ihren Partner von Drittanbietern, um zu bestimmen, welche Methode sie verwenden können.

## Geschäftliche Aspekte {#business-considerations}

Geschäftsentscheidungen für die Auswahl einer Auslieferungsmethode über einen anderen hängen von den technischen Fähigkeiten Ihres Zielpartners ab und davon, was Sie mit qualifizierten Benutzerinformationen tun möchten. Beispielsweise können die Optionen durch technische Einschränkungen eingeschränkt werden, wenn ein Ziel keine Daten von einer bestimmten Auslieferungsmethode empfangen kann. Wenn es jedoch keine technischen Probleme gibt, können Sie Informationen basierend darauf senden, wie Sie diese Daten handeln möchten. Beispiel:

* [!DNL URL]Ziele, die auf Cookies basieren, funktionieren fast synchron mit Benutzeraktionen auf einer Seite.
* Server-zu-Server-Methoden eignen sich gut für das Erstellen tiefer Zielgruppensegmente im Laufe der Zeit.

## Zieltypen und typische Verwendungen {#destination-types}

Anhand der Beispiele in der folgenden Tabelle können Sie erkennen, wann ein bestimmtes Ziel und die Unterschiede zwischen den einzelnen Typen verwendet werden.

| Zieltyp | Wird normalerweise verwendet, wenn | Beispiel  | Zu beachten |
|--- |--- |--- |--- |
| **URL** oder **Cookie** | Sie müssen Daten sofort übertragen, damit ein Ziel sofort auf einem qualifizierten Benutzer ausgeführt werden kann. | Senden von Daten von einer Einkaufsschutzsite. Verwenden Sie eine URL oder ein Cookie-Ziel, um den Benutzer zu qualifizieren und sofort erneut zu Targeting. | <ul><li>Überträgt nur Daten zu neuen Besuchern. </li><li>Besucher müssen erneut angezeigt werden, um sich für das Segment qualifizieren zu können.</li></ul> |
| **Server-to-Server** | <ul><li>Sofortige Datenübertragung ist nicht erforderlich.</li><li>Erfassen von Daten zum Erstellen eines großen Zielgruppenpools qualifizierter Benutzer.</li></ul> | Erfassen von Daten über einen bestimmten Zeitraum (Stunden oder Tage), um sie in einer Kampagne zu verwenden, die zu einem späteren Zeitpunkt ausgeführt wird. | <ul><li>Überträgt Daten zu neuen und vorherigen Site-Besuchern. </li><li>Besucher müssen nicht erneut angezeigt werden, um sich für andere Segmente qualifizieren zu können.</li></ul> |

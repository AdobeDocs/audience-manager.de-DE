---
description: In Audience Manager ist ein Ziel ein beliebiges Drittanbietersystem (Anzeigenserver, DSP, Werbungsnetzwerk usw.) , für die Sie Daten freigeben möchten. Der Destination Builder ist das Tool, mit dem Sie Cookies-, URL- oder Server-zu-Server-Ziele erstellen und verwalten.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: In Audience Manager ist ein Ziel ein beliebiges Drittanbietersystem (Anzeigenserver, DSP, Werbungsnetzwerk usw.) , für die Sie Daten freigeben möchten. Der Destination Builder ist das Tool, mit dem Sie Cookies-, URL- oder Server-zu-Server-Ziele erstellen und verwalten.
seo-title: Ziele
solution: Audience Manager
title: Ziele
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: 431a254f1a70958db29621a59acc6239d2a6b005

---


# Zielübersicht {#destinations}

In Audience Manager ist ein Ziel ein beliebiges Drittanbietersystem (Anzeigenserver, [!DNL DSP]Werbungsnetzwerk usw.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] ist das Tool, das Sie zum Erstellen und Verwalten von Cookie- [!DNL URL]oder Server-zu-Server-Zielen verwendet haben.

## Zweck und Vorteile {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] und [!UICONTROL Destination Builder] können Sie Ziele erstellen und Informationen zu segmentierten Benutzern an Ihren Datenpartner senden. Dies hilft Ihnen,

* **** Datenwert schützen: Statt alle Benutzerdaten an ein Ziel zu senden, [!UICONTROL Destination Builder] können Sie nur bestimmte Informationen zu qualifizierten Benutzern freigeben.
* **** Nehmen Sie an Ihren Daten teil: Durch das Senden von Daten an einen Zielpartner können diese schnell qualifizierte Zielgruppensegmente entwickeln und gezielt ansprechen.
* **** Reduzierung der technischen Kosten: Geschäftsbenutzer können Ziele auf der [!UICONTROL Destination Builder] Benutzeroberfläche sicher einrichten. Auf diese Weise wird die für Tests vor der Bereitstellung erforderliche Zeit reduziert. Mit [!UICONTROL Destination Builder]dieser Funktion können Sie Ziele erstellen, verwalten und löschen, wenn sich Ihre geschäftlichen Anforderungen ändern, ohne einen langen Entwicklungszyklus zu durchlaufen.

## Technische Aspekte {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Die Datenbereitstellung hängt davon ab, wie Ihr Datenpartner Zielinformationen erhalten möchte oder kann. Technische oder technische Einschränkungen können verhindern, dass ein Ziel Daten über [!DNL URL]-, Cookie- oder Server-zu-Server-Prozesse empfängt. Arbeiten Sie mit Ihrem Drittanbieter zusammen, um zu ermitteln, welche Methode Sie verwenden können.

## Geschäftliche Aspekte {#business-considerations}

Geschäftsentscheidungen zur Auswahl einer Zustellungsmethode im Vergleich zu einer anderen hängen von den technischen Fähigkeiten Ihres Ziellingpartners und von den Vorteilen qualifizierter Benutzerinformationen ab. Beispielsweise können technische Einschränkungen Ihre Optionen einschränken, wenn ein Ziel keine Daten über eine bestimmte Zustellungsmethode empfangen kann. Wenn jedoch keine technischen Probleme auftreten, können Sie Informationen senden, die darauf basieren, wie Sie mit diesen Daten vorgehen möchten. Beispiel:

* [!DNL URL]s- und cookie-basierte Ziele funktionieren fast synchron mit Benutzeraktionen auf einer Seite.
* Server-zu-Server-Methoden eignen sich gut zum Aufbau von Segmenten für große Zielgruppen im Laufe der Zeit.

## Zieltypen und typische Verwendungen {#destination-types}

Die Beispiele in der folgenden Tabelle helfen Ihnen dabei, zu verstehen, wann ein bestimmtes Ziel verwendet werden soll und welche Unterschiede zwischen den einzelnen Typen bestehen.

| Zieltyp | Wird normalerweise verwendet, wenn | Beispiel  | Zu beachten |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Sie müssen Daten an andere Adobe Experience Cloud-Lösungen senden. | Senden von Daten an Adobe Analytics |  |
| **[!UICONTROL People-Based Destinations]** | Sie müssen Zielgruppensegmente an benutzerbasierte Umgebungen wie Facebook senden. | Auslieferung personalisierter Angebote an Bestandskunden anhand ihrer Einkaufshistorie | Zielgruppen-Targeting erfolgt über Hash-IDs. Siehe [Benutzerbasierte Ziele](people-based-destinations-overview.md) |
| **[!UICONTROL Device-Based Destinations]**(** Server-zu-Server **) | <ul><li>Eine sofortige Datenübertragung ist nicht erforderlich.</li><li>Erfassen von Daten zum Aufbau eines großen Zielgruppenpools qualifizierter Benutzer.</li></ul> | Datenerfassung im Zeitverlauf (Stunden oder Tage), um sie in einem Kampagnensatz zu verwenden, der zu einem späteren Zeitpunkt ausgeführt werden soll. | <ul><li>Überträgt Daten zu neuen und vorherigen Site-Besuchern. </li><li>Besucher müssen nicht mehr angezeigt werden, um sich für andere Segmente zu qualifizieren.</li></ul> |
| **[!UICONTROL Custom Destinations]**(** URL **oder** Cookie **) | Sie müssen Daten sofort übertragen, damit ein Ziel sofort Aktionen an einen qualifizierten Benutzer durchführen kann. | Senden von Daten von einer Ticketeinkaufssite. Verwenden Sie eine URL oder ein Cookie-Ziel, um den Benutzer zu qualifizieren und das Targeting sofort durchzuführen. | <ul><li>Überträgt nur Daten zu neuen Besuchern. </li><li>Besucher müssen erneut angezeigt werden, um sich für das Segment zu qualifizieren.</li></ul> |


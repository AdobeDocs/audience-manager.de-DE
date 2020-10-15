---
description: Im Audience Manager ist ein Ziel ein Drittanbietersystem (Anzeigenserver, DSP, Werbenetzwerk usw.), für das Sie Daten freigeben möchten. Verwenden Sie das Destination Builder-Tool, um Cookies-, URL- oder Server-zu-Server-Ziele zu erstellen und zu verwalten.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: Im Audience Manager ist ein Ziel ein Drittanbietersystem (Anzeigenserver, DSP, Werbenetzwerk usw.), für das Sie Daten freigeben möchten. Der Destination Builder ist das Tool zum Erstellen und Verwalten von Cookie-, URL- oder Server-zu-Server-Zielen.
seo-title: 'Ziele '
solution: Audience Manager
title: 'Ziele '
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 8027f278aa2b879b6cb277f44caf4b62dc75e2c3
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 14%

---


# [!UICONTROL Destinations] Überblick {#destinations}

In Audience Manager, a [!UICONTROL destination] is any third-party system (ad server, [!DNL DSP], ad network, etc.) für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] ist das Tool, das Sie zum Erstellen und Verwalten [!UICONTROL cookie], [!DNL URL]oder [!UICONTROL server-to-server destinations]Verwalten verwenden.

## Zweck und Vorteile {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] und [!UICONTROL Destination Builder] können Sie Informationen zu segmentierten Benutzern erstellen [!UICONTROL destinations] und an Ihren Datenpartner senden. Dies hilft Ihnen,

* **Protect-Datenwert:** Statt alle Benutzerdaten an eine [!UICONTROL destination]zu senden, können [!UICONTROL Destination Builder] Sie nur bestimmte Informationen über qualifizierte Benutzer freigeben.
* **Nehmen Sie Maßnahmen in Bezug auf Ihre Daten vor:** Durch das Senden von Daten an einen [!UICONTROL destination] Partner können Sie schnell qualifizierte Segmente für Audiencen entwickeln und Zielgruppen erstellen.
* **Reduzierung des technischen Verwaltungsaufwands:** Geschäftsbenutzer können [!UICONTROL destinations] sicher auf der [!UICONTROL Destination Builder] Oberfläche eingerichtet werden. Auf diese Weise wird die für Tests vor der Bereitstellung erforderliche Zeit verkürzt. Mit [!UICONTROL Destination Builder]diesen Funktionen erstellen, verwalten und löschen Sie, [!UICONTROL destinations] wenn sich Ihre geschäftlichen Anforderungen ändern, ohne einen langen Entwicklungszyklus zu durchlaufen.

## Technische Aspekte {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Data Versand hängt davon ab, wie Ihr Datenpartner [!UICONTROL destination] Informationen erhalten möchte oder kann. Technische oder technische Einschränkungen können verhindern, dass ein [!UICONTROL destination] Benutzer Daten über [!DNL URL], [!UICONTROL cookie]oder [!UICONTROL server-to-server] Prozesse empfängt. Arbeiten Sie mit Ihrem Drittanbieter zusammen, um zu ermitteln, welche Methode Sie verwenden können.

## Geschäftliche Aspekte {#business-considerations}

Geschäftsentscheidungen bei der Auswahl einer Versand-Methode im Vergleich zu einer anderen hängen von den technischen Fähigkeiten Ihres [!UICONTROL destination] Partners und davon ab, was Sie mit qualifizierten Benutzerinformationen tun möchten. Technische Einschränkungen können beispielsweise Ihre Optionen einschränken, wenn ein Benutzer keine Daten mit einer bestimmten Versand-Methode empfangen [!UICONTROL destination] kann. Wenn jedoch keine technischen Probleme auftreten, können Sie Informationen senden, die darauf basieren, wie Sie mit diesen Daten vorgehen möchten. Beispiel:

* [!DNL URL]s und [!UICONTROL cookie-based destinations] arbeiten fast synchron mit Benutzeraktionen auf einer Seite.
* [!UICONTROL Server-to-server] Methoden eignen sich gut zum Aufbau von Segmenten mit tiefen Audiencen im Laufe der Zeit.

## [!UICONTROL Destination] Typen und typische Verwendungen {#destination-types}

Die Beispiele in der folgenden Tabelle helfen Ihnen dabei, zu verstehen, wann ein bestimmter Typ verwendet werden soll [!UICONTROL destination] und welche Unterschiede zwischen den einzelnen Typen bestehen.

| [!UICONTROL Destination] Geben Sie | Wird normalerweise verwendet, wenn | Beispiel | Zu beachten |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Sie müssen Daten an andere Adobe Experience Cloud-Lösungen senden. | Senden von Daten an Adobe Analytics |  |
| **[!UICONTROL People-Based Destinations]** | Sie müssen Audiencen-Segmente an benutzerbasierte Umgebung wie Facebook senden. | Auslieferung personalisierter Angebot an Bestandskunden anhand ihrer Einkaufshistorie | Audiencen-Targeting erfolgt über Hash-IDs. Siehe [Benutzerbasierte Ziele](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-zu-Server**) | <ul><li>Eine sofortige Datenübertragung ist nicht erforderlich.</li><li>Erfassen von Daten zum Aufbau eines großen Benutzerpools mit qualifizierten Audiencen.</li></ul> | Datenerfassung im Zeitverlauf (Stunden oder Tage) zur Verwendung in einer Kampagne, die zu einem späteren Zeitpunkt ausgeführt werden soll. | <ul><li>Überträgt Daten zu neuen und vorherigen Site-Besuchern. </li><li>Besucher müssen nicht mehr angezeigt werden, um sich für andere Segmente qualifizieren zu können.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** oder **Cookie**) | Sie müssen Daten sofort übertragen, damit ein Ziel sofort Aktionen an einen qualifizierten Benutzer durchführen kann. | Senden von Daten von einer Ticketeinkaufssite. Verwenden Sie einen [!UICONTROL URL] oder [!UICONTROL cookie destination] , um den Benutzer zu qualifizieren und eine sofortige Zielgruppe durchzuführen. | <ul><li>Überträgt nur Daten zu neuen Besuchern. </li><li>Besucher müssen erneut angezeigt werden, um sich für das Segment qualifizieren zu können.</li></ul> |

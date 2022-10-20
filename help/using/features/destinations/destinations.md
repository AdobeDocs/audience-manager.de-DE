---
description: Entdecken Sie die Vorteile, Typen und Verwendungen von Zielen – allen Drittanbietersystemen, in denen Sie Daten freigeben, wie z. B. ein Adserver oder DSP. Verwenden Sie Destination Builder, um Cookies, URLs oder Server-zu-Server-Ziele zu erstellen und zu verwalten.
keywords: Integrationscode, Ziel, Zielübersicht, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel
landing-page-description: Entdecken Sie die Vorteile, Typen und Verwendungen von Zielen – allen Drittanbietersystemen, in denen Sie Daten freigeben, wie z. B. ein Adserver oder DSP. Verwenden Sie Destination Builder, um Cookies, URLs oder Server-zu-Server-Ziele zu erstellen und zu verwalten.
seo-title: Destinations
solution: Audience Manager
title: Ziele
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 15%

---

# [!UICONTROL Destinations] Überblick {#destinations}

Im Audience Manager wird eine [!UICONTROL destination] ist ein Drittanbietersystem (Adserver, [!DNL DSP], Werbenetzwerk usw.) für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] ist das Tool, das Sie zum Erstellen und Verwalten von [!UICONTROL cookie], [!DNL URL]oder [!UICONTROL server-to-server destinations].

## Zweck und Vorteile {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] und [!UICONTROL Destination Builder] Erstellen [!UICONTROL destinations] und senden Sie Informationen über segmentierte Benutzer an Ihren Datenpartner. Dies hilft Ihnen bei Folgendem:

* **Protect-Datenwert:** Anstatt alle Benutzerdaten an eine [!UICONTROL destination], [!UICONTROL Destination Builder] können Sie bestimmte Informationen nur über qualifizierte Benutzer freigeben.
* **Ergreifen Sie Maßnahmen bezüglich Ihrer Daten:** Senden von Daten an eine [!UICONTROL destination] -Partner hilft ihnen, schnell qualifizierte Zielgruppensegmente zu entwickeln und auszuwählen.
* **Reduzierung des technischen Verwaltungsaufwands:** Geschäftsbenutzer können [!UICONTROL destinations] sicher in [!UICONTROL Destination Builder] -Schnittstelle. Dadurch wird der Zeitaufwand für Tests vor der Bereitstellung reduziert. Mit [!UICONTROL Destination Builder], erstellen, verwalten und löschen Sie [!UICONTROL destinations] da sich Ihre Geschäftsanforderungen ändern, ohne einen langen Entwicklungszyklus durchlaufen zu müssen.

## Technische Aspekte {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Die Datenbereitstellung hängt davon ab, wie Ihr Datenpartner Daten empfangen möchte oder kann [!UICONTROL destination] Informationen. Technische oder technische Beschränkungen können [!UICONTROL destination] von Datenempfängern über [!DNL URL], [!UICONTROL cookie]oder [!UICONTROL server-to-server] Prozesse. Ermitteln Sie gemeinsam mit Ihrem Drittanbieter-Partner, welche Methode er verwenden kann.

## Geschäftliche Aspekte {#business-considerations}

Geschäftsentscheidungen zur Auswahl einer Versandmethode im Vergleich zu einer anderen hängen von den technischen Fähigkeiten Ihrer [!UICONTROL destination] Partner und was Sie mit qualifizierten Benutzerinformationen tun möchten. Beispielsweise können technische Einschränkungen Ihre Optionen einschränken, wenn ein [!UICONTROL destination] kann keine Daten nach einer bestimmten Versandmethode empfangen. Wenn jedoch keine technischen Probleme auftreten, können Sie Informationen senden, die darauf basieren, wie Sie mit diesen Daten vorgehen möchten. Beispiel:

* [!DNL URL]s und [!UICONTROL cookie-based destinations] Arbeiten fast synchron mit Benutzeraktionen auf einer Seite.
* [!UICONTROL Server-to-server] -Methoden eignen sich gut zum Erstellen von tiefen Zielgruppensegmenten im Zeitverlauf.

## [!UICONTROL Destination] Typen und typische Verwendungen {#destination-types}

Die Beispiele in der folgenden Tabelle veranschaulichen, wann eine bestimmte [!UICONTROL destination] und die Unterschiede zwischen den einzelnen Typen.

| [!UICONTROL Destination] Geben Sie | Wird normalerweise verwendet, wenn | Beispiel | Zu beachten |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Sie müssen Daten an andere Adobe Experience Cloud-Lösungen senden. | Senden von Daten an Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Sie müssen Zielgruppensegmente an personenbasierte Umgebungen wie Facebook senden. | Bereitstellung personalisierter Angebote für bestehende Kunden basierend auf ihrer Einkaufshistorie | Zielgruppen-Targeting erfolgt über Hash-IDs. Siehe [Benutzerbasierte Ziele](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-zu-Server**) | <ul><li>Eine sofortige Datenübertragung ist nicht erforderlich.</li><li>Erfassen von Daten zum Erstellen eines großen Zielgruppen-Pools mit qualifizierten Benutzern.</li></ul> | Erfassen von Daten über einen Zeitraum (Stunden oder Tage), um sie in einer Kampagne zu verwenden, die zu einem späteren Zeitpunkt ausgeführt werden soll. | <ul><li>Überträgt Daten zu neuen und vorherigen Site-Besuchern. </li><li>Besucher müssen nicht erneut angezeigt werden, um sich für andere Segmente zu qualifizieren.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** oder **Cookie**) | Sie müssen Daten sofort übertragen, damit ein Ziel sofort Aktionen für einen qualifizierten Benutzer ausführen kann. | Senden von Daten von einer Ticketkauf-Website. Verwenden Sie eine [!UICONTROL URL] oder [!UICONTROL cookie destination] , um den Benutzer zu qualifizieren und das Targeting sofort erneut durchzuführen. | <ul><li>Überträgt nur Daten zu neuen Besuchern. </li><li>Besucher müssen erneut angezeigt werden, um sich für das Segment zu qualifizieren.</li></ul> |

---
description: Im Audience Manager ist ein Ziel ein Drittanbietersystem (Anzeigenserver, DSP, Werbenetzwerk usw.), für das Sie Daten freigeben möchten. Destination Builder ist das Tool, mit dem Sie Cookie-, URL- oder Server-Ziele erstellen und verwalten.
keywords: Integrationscode, Ziel, Zielübersicht, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel
landing-page-description: Ein Ziel ist ein Drittanbietersystem, z. B. ein Adserver oder DSP, mit dem Daten geteilt werden. Verwenden Sie das Destination Builder-Tool, um Cookie-, URL- oder Server-zu-Server-Ziele zu erstellen und zu verwalten.
seo-title: 'Ziele '
solution: Audience Manager
title: Ziele
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Zielgrundlagen
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# [!UICONTROL Destinations] Überblick {#destinations}

Im Audience Manager ist ein [!UICONTROL destination] ein Drittanbietersystem (Anzeigenserver, [!DNL DSP], Anzeigennetzwerk usw.), für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] ist das Tool, das Sie zum Erstellen und Verwalten  [!UICONTROL cookie],  [!DNL URL]oder  [!UICONTROL server-to-server destinations]verwendet haben.

## Zweck und Vorteile {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] und  [!UICONTROL Destination Builder] ermöglichen es Ihnen, Informationen zu segmentierten Benutzern zu erstellen  [!UICONTROL destinations] und an Ihren Datenpartner zu senden. Dies hilft Ihnen bei Folgendem:

* **Protect-Datenwert:** Anstatt alle Benutzerdaten an eine zu senden,  [!UICONTROL destination]  [!UICONTROL Destination Builder] können Sie nur bestimmte Informationen über qualifizierte Benutzer freigeben.
* **Maßnahmen für Ihre Daten ergreifen:** Durch das Senden von Daten an einen  [!UICONTROL destination] Partner können Sie schnell qualifizierte Zielgruppensegmente entwickeln und ansprechen.
* **Reduzierung des technischen Verwaltungsaufwands:** Geschäftsbenutzer können  [!UICONTROL destinations] sicher in der  [!UICONTROL Destination Builder] Benutzeroberfläche einrichten. Dadurch wird der Zeitaufwand für Tests vor der Bereitstellung reduziert. Mit [!UICONTROL Destination Builder] können Sie [!UICONTROL destinations] erstellen, verwalten und löschen, wenn sich Ihre Geschäftsanforderungen ändern, ohne einen langen Entwicklungszyklus zu durchlaufen.

## Technische Aspekte {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Die Datenbereitstellung hängt davon ab, wie Ihr Datenpartner [!UICONTROL destination]-Informationen erhalten möchte oder kann. Technische oder technische Einschränkungen können verhindern, dass ein [!UICONTROL destination] Daten über [!DNL URL]-, [!UICONTROL cookie]- oder [!UICONTROL server-to-server]-Prozesse erhält. Ermitteln Sie gemeinsam mit Ihrem Drittanbieter-Partner, welche Methode er verwenden kann.

## Geschäftliche Aspekte {#business-considerations}

Geschäftsentscheidungen zur Auswahl einer Versandmethode im Vergleich zu einer anderen hängen von den technischen Möglichkeiten Ihres [!UICONTROL destination]-Partners und dem, was Sie mit qualifizierten Benutzerinformationen tun möchten, ab. Beispielsweise können technische Einschränkungen Ihre Optionen einschränken, wenn ein [!UICONTROL destination] keine Daten von einer bestimmten Versandmethode empfangen kann. Wenn jedoch keine technischen Probleme auftreten, können Sie Informationen senden, die darauf basieren, wie Sie mit diesen Daten vorgehen möchten. Beispiel:

* [!DNL URL]s und  [!UICONTROL cookie-based destinations] funktionieren fast synchron mit Benutzeraktionen auf einer Seite.
* [!UICONTROL Server-to-server] -Methoden eignen sich gut zum Erstellen von tiefen Zielgruppensegmenten im Zeitverlauf.

## [!UICONTROL Destination] Typen und typische Verwendungen  {#destination-types}

Anhand der Beispiele in der folgenden Tabelle können Sie erkennen, wann ein bestimmtes [!UICONTROL destination] verwendet werden soll und welche Unterschiede zwischen den einzelnen Typen bestehen.

| [!UICONTROL Destination] Geben Sie | Wird normalerweise verwendet, wenn | Beispiel | Zu beachten |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Sie müssen Daten an andere Adobe Experience Cloud-Lösungen senden. | Senden von Daten an Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Sie müssen Zielgruppensegmente an personenbasierte Umgebungen wie Facebook senden. | Bereitstellung personalisierter Angebote für bestehende Kunden basierend auf ihrer Einkaufshistorie | Zielgruppen-Targeting erfolgt über Hash-IDs. Siehe [People-Based Destinations](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-zu-Server**) | <ul><li>Eine sofortige Datenübertragung ist nicht erforderlich.</li><li>Erfassen von Daten zum Erstellen eines großen Zielgruppen-Pools mit qualifizierten Benutzern.</li></ul> | Erfassen von Daten über einen Zeitraum (Stunden oder Tage), um sie in einer Kampagne zu verwenden, die zu einem späteren Zeitpunkt ausgeführt werden soll. | <ul><li>Überträgt Daten zu neuen und vorherigen Site-Besuchern. </li><li>Besucher müssen nicht erneut angezeigt werden, um sich für andere Segmente zu qualifizieren.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URLor  **Cookie**) | Sie müssen Daten sofort übertragen, damit ein Ziel sofort Aktionen für einen qualifizierten Benutzer ausführen kann. | Senden von Daten von einer Ticketkauf-Website. Verwenden Sie einen [!UICONTROL URL] oder [!UICONTROL cookie destination], um den Benutzer zu qualifizieren und sofort ein erneutes Targeting durchzuführen. | <ul><li>Überträgt nur Daten zu neuen Besuchern. </li><li>Besucher müssen erneut angezeigt werden, um sich für das Segment zu qualifizieren.</li></ul> |

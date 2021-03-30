---
description: Im Audience Manager ist ein Ziel ein Drittanbietersystem (Anzeigenserver, DSP, Werbenetzwerk usw.), für das Sie Daten freigeben möchten. Destination Builder ist das Tool, mit dem Sie Cookie-, URL- oder Server-Ziele erstellen und verwalten.
keywords: Integrationscode, Ziel, Zielübersicht, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel
landing-page-description: Ein Ziel ist ein Drittanbietersystem, z. B. ein Adserver oder DSP, mit dem Daten geteilt werden. Verwenden Sie das Destination Builder-Tool, um Cookie-, URL- oder Server-zu-Server-Ziele zu erstellen und zu verwalten.
seo-title: 'Ziele '
solution: Audience Manager
title: Ziele
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Zielgrundlagen
translation-type: tm+mt
source-git-commit: e6348c85e7df6428802d54b2c90385ce95f50e1a
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---


# [!UICONTROL Destinations] Überblick {#destinations}

In Audience Managern ist ein [!UICONTROL destination] ein Drittanbietersystem (Anzeigenserver, [!DNL DSP], Anzeigennetzwerk usw.) für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] ist das Tool, das Sie zum Erstellen und Verwalten  [!UICONTROL cookie],  [!DNL URL]oder  [!UICONTROL server-to-server destinations]Verwalten verwendet haben.

## Zweck und Vorteile {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] und  [!UICONTROL Destination Builder] können Sie Informationen zu segmentierten Benutzern erstellen  [!UICONTROL destinations] und an Ihren Datenpartner senden. Dies hilft Ihnen,

* **Protect-Datenwert:** Anstatt alle Benutzerdaten an eine zu senden,  [!UICONTROL destination]  [!UICONTROL Destination Builder] können Sie nur bestimmte Informationen über qualifizierte Benutzer freigeben.
* **Vorgehen bei Ihren Daten:** Daten an einen  [!UICONTROL destination] Partner senden hilft ihnen, schnell qualifizierte Audiencen zu entwickeln und zu Zielgruppen.
* **Reduzierung des technischen Verwaltungsaufwands:** Geschäftsbenutzer können  [!UICONTROL destinations] sicher auf der  [!UICONTROL Destination Builder] Oberfläche einrichten. Auf diese Weise wird die für Tests vor der Bereitstellung erforderliche Zeit verkürzt. Mit [!UICONTROL Destination Builder] können Sie [!UICONTROL destinations] erstellen, verwalten und löschen, wenn sich Ihr Unternehmen ändert, ohne einen langen Entwicklungszyklus zu durchlaufen.

## Technische Aspekte {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Data Versand hängt davon ab, wie Ihr Datenpartner [!UICONTROL destination]-Informationen erhalten möchte oder kann. Technische oder technische Einschränkungen können verhindern, dass ein [!UICONTROL destination] Daten über [!DNL URL]-, [!UICONTROL cookie]- oder [!UICONTROL server-to-server]-Prozesse empfängt. Arbeiten Sie mit Ihrem Drittanbieter zusammen, um zu ermitteln, welche Methode Sie verwenden können.

## Geschäftliche Aspekte {#business-considerations}

Geschäftsentscheidungen zur Auswahl einer Versand-Methode im Vergleich zu einer anderen hängen von den technischen Möglichkeiten Ihres [!UICONTROL destination]-Partners und davon ab, was Sie mit qualifizierten Benutzerinformationen tun möchten. Technische Einschränkungen können beispielsweise Ihre Optionen einschränken, wenn ein [!UICONTROL destination] keine Daten nach einer bestimmten Versand-Methode empfangen kann. Wenn jedoch keine technischen Probleme auftreten, können Sie Informationen senden, die darauf basieren, wie Sie mit diesen Daten vorgehen möchten. Beispiel:

* [!DNL URL]s und  [!UICONTROL cookie-based destinations] funktionieren fast synchron mit Benutzeraktionen auf einer Seite.
* [!UICONTROL Server-to-server] Methoden eignen sich gut zum Aufbau von Segmenten mit tiefen Audiencen im Laufe der Zeit.

## [!UICONTROL Destination] Typen und typische Verwendungen  {#destination-types}

Die Beispiele in der folgenden Tabelle können Ihnen dabei helfen, zu verstehen, wann ein bestimmtes [!UICONTROL destination] verwendet werden soll und welche Unterschiede zwischen den einzelnen Typen bestehen.

| [!UICONTROL Destination] Geben Sie | Wird normalerweise verwendet, wenn | Beispiel | Zu beachten |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Sie müssen Daten an andere Adobe Experience Cloud-Lösungen senden. | Senden von Daten an Adobe Analytics |  |
| **[!UICONTROL People-Based Destinations]** | Sie müssen Audiencen-Segmente an benutzerbasierte Umgebung wie Facebook senden. | Auslieferung personalisierter Angebot an Bestandskunden anhand ihrer Einkaufshistorie | Audiencen-Targeting erfolgt über Hash-IDs. Siehe [Benutzerbasierte Ziele](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-zu-Server**) | <ul><li>Eine sofortige Datenübertragung ist nicht erforderlich.</li><li>Erfassen von Daten zum Aufbau eines großen Benutzerpools mit qualifizierten Audiencen.</li></ul> | Datenerfassung im Zeitverlauf (Stunden oder Tage) zur Verwendung in einer Kampagne, die zu einem späteren Zeitpunkt ausgeführt werden soll. | <ul><li>Überträgt Daten zu neuen und vorherigen Site-Besuchern. </li><li>Besucher müssen nicht mehr angezeigt werden, um sich für andere Segmente qualifizieren zu können.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URLs oder  **Cookies**) | Sie müssen Daten sofort übertragen, damit ein Ziel sofort Aktionen an einen qualifizierten Benutzer durchführen kann. | Senden von Daten von einer Ticketeinkaufssite. Verwenden Sie einen [!UICONTROL URL] oder [!UICONTROL cookie destination], um den Benutzer zu qualifizieren und sofort eine erneute Zielgruppe durchzuführen. | <ul><li>Überträgt nur Daten zu neuen Besuchern. </li><li>Besucher müssen erneut angezeigt werden, um sich für das Segment qualifizieren zu können.</li></ul> |

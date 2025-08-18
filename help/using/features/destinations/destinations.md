---
description: Entdecken Sie die Vorteile, Typen und Verwendungen von Zielen – allen Drittanbietersystemen, in denen Sie Daten freigeben, wie z. B. ein Adserver oder DSP. Verwenden Sie Destination Builder, um Cookies, URLs oder Server-zu-Server-Ziele zu erstellen und zu verwalten.
keywords: Integrationscode, Ziel, Zielübersicht, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel, Ziel
landing-page-description: Entdecken Sie die Vorteile, Typen und Verwendungen von Zielen – allen Drittanbietersystemen, in denen Sie Daten freigeben, wie z. B. ein Adserver oder DSP. Verwenden Sie Destination Builder, um Cookies, URLs oder Server-zu-Server-Ziele zu erstellen und zu verwalten.
short-description: Entdecken Sie die Vorteile, Typen und Verwendungen von Zielen – allen Drittanbietersystemen, in denen Sie Daten freigeben, wie z. B. ein Adserver oder DSP. Verwenden Sie Destination Builder, um Cookies, URLs oder Server-zu-Server-Ziele zu erstellen und zu verwalten.
seo-title: Destinations
solution: Audience Manager
title: Ziele
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 19%

---

# [!UICONTROL Destinations] {#destinations}

In Audience Manager ist ein [!UICONTROL destination] jedes Drittanbietersystem (Werbeserver, [!DNL DSP], Werbenetzwerk usw.), für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] ist das Tool, mit dem Sie [!UICONTROL cookie], [!DNL URL] oder [!UICONTROL server-to-server destinations] erstellen und verwalten.

## Zweck und Vorteile {#purposes}

<!-- c_destinations.xml -->

Mit [!UICONTROL Destinations] und [!UICONTROL Destination Builder] können Sie [!UICONTROL destinations] erstellen und Informationen zu segmentierten Benutzern an Ihren Datenpartner senden. Dies hilft Ihnen bei Folgendem:

* **Datenwert schützen** Anstatt alle Benutzerdaten an einen [!UICONTROL destination] zu senden, können [!UICONTROL Destination Builder] bestimmte Informationen nur über qualifizierte Benutzer freigeben.
* **Ihre Daten bearbeiten:** Senden von Daten an einen [!UICONTROL destination] hilft Ihnen, schnell qualifizierte Zielgruppensegmente zu entwickeln und anzusprechen.
* **Geringerer technischer Aufwand:** Business-Anwender können [!UICONTROL destinations] sicher in der [!UICONTROL Destination Builder] einrichten. Dadurch wird der Zeitaufwand für Tests vor der Bereitstellung reduziert. Mit [!UICONTROL Destination Builder] können Sie [!UICONTROL destinations] erstellen, verwalten und löschen, wenn sich Ihre Geschäftsanforderungen ändern, ohne dabei einen langen Entwicklungszyklus durchlaufen zu müssen.

## Technische Aspekte {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Die Datenbereitstellung hängt davon ab, wie Ihr Datenpartner [!UICONTROL destination] Informationen erhalten möchte oder kann. Technische oder technische Einschränkungen können verhindern, dass ein [!UICONTROL destination] Daten über [!DNL URL]-, [!UICONTROL cookie]- oder [!UICONTROL server-to-server] erhält. Arbeiten Sie mit Ihrem Drittanbieterpartner zusammen, um zu bestimmen, welche Methode er verwenden kann.

## Geschäftliche Aspekte {#business-considerations}

Geschäftsentscheidungen zur Auswahl einer Versandmethode gegenüber einer anderen hängen von den technischen Möglichkeiten Ihres [!UICONTROL destination] und davon ab, was Sie mit qualifizierten Benutzerinformationen machen möchten. Beispielsweise können technische Einschränkungen Ihre Optionen einschränken, wenn ein [!UICONTROL destination] keine Daten von einer bestimmten Versandmethode empfangen kann. Wenn jedoch keine technischen Probleme auftreten, können Sie Informationen senden, die darauf basieren, wie Sie diese Daten bearbeiten möchten. Beispiel:

* [!DNL URL] und [!UICONTROL cookie-based destinations] arbeiten fast synchron mit Benutzeraktionen auf einer Seite.
* [!UICONTROL Server-to-server] Methoden eignen sich gut, um im Laufe der Zeit tiefe Zielgruppensegmente zu erstellen.

## [!UICONTROL Destination] und typische Verwendungszwecke {#destination-types}

Die Beispiele in der folgenden Tabelle helfen Ihnen zu verstehen, wann ein bestimmter [!UICONTROL destination] verwendet wird und welche Unterschiede es zwischen den einzelnen Typen gibt.

| [!UICONTROL Destination] | Wird normalerweise verwendet, wenn | Beispiel | Zu beachten |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Sie müssen Daten an andere Adobe Experience Cloud-Lösungen senden. | Senden von Daten an Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Sie müssen Zielgruppensegmente an personenbasierte Umgebungen wie Facebook senden. | Bereitstellen personalisierter Angebote für Bestandskunden auf der Grundlage ihrer Kaufhistorie | Zielgruppen-Targeting erfolgt über Hash-Kennungen. Siehe [Benutzerbasierte Ziele](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-zu-Server**) | <ul><li>Eine sofortige Datenübertragung ist nicht erforderlich.</li><li>Erfassen von Daten, um einen großen Zielgruppen-Pool qualifizierter Benutzer zu erstellen.</li></ul> | Erfassen von Daten im Zeitverlauf (Stunden oder Tage), um sie in einer Kampagne zu verwenden, die zu einem späteren Zeitpunkt ausgeführt werden soll. | <ul><li>Überträgt Daten über neue und frühere Site-Besucher. </li><li>Besucher müssen nicht erneut gesehen werden, um sich für andere Segmente zu qualifizieren.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** oder **Cookie**) | Sie müssen Daten sofort übertragen, damit ein Ziel sofort eine Aktion bei einem qualifizierten Benutzer durchführen kann. | Senden von Daten von einer Ticketkauf-Website. Verwenden Sie eine [!UICONTROL URL] oder einen [!UICONTROL cookie destination], um den Benutzer zu qualifizieren, und führen Sie das Targeting sofort erneut aus. | <ul><li>Überträgt nur Daten über neue Besucher. </li><li>Besucher müssen erneut gesehen werden, um sich für das Segment zu qualifizieren.</li></ul> |

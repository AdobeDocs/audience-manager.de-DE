---
description: Verwenden Sie personenbasierte Ziele, um First-Party-Zielgruppensegmente an personenbasierte Umgebungen zu senden. Diese Umgebungen sind geschlossene Ökosysteme, die zu einer Entität gehören, die den Inhalt steuert, der in ihr angezeigt wird. Dazu gehören Social-Media-Plattformen wie Facebook und andere Plattformen, die zur Personalisierung der angezeigten Inhalte auf Kundenkonten angewiesen sind.
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Übersicht und Anwendungsfälle
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# Übersicht und Anwendungsfälle {#overview-use-cases}

Verwenden Sie [!DNL People-Based Destinations] , um Erstanbieter-Zielgruppensegmente an personenbasierte Umgebungen zu senden. Diese Umgebungen sind geschlossene Ökosysteme, die zu einer Entität gehören, die den Inhalt steuert, der in ihr angezeigt wird. Dazu gehören soziale Plattformen wie [!DNL Facebook] und andere Plattformen, die zur Personalisierung der angezeigten Inhalte auf Kundenkonten angewiesen sind.

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Verwendung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um Rechtsberatung zu erhalten.

## Überblick {#overview}

[!DNL People-Based Destinations] können Sie eine Segmentierung auf Online- und Offline-Daten anwenden, um Zielgruppensegmente basierend auf [Hash-Kennungen](people-based-destinations-prerequisites.md#hashing-requirements) wie E-Mail-Adressen zu erstellen. Anschließend können Sie diese Segmente an ummauerte Gärten wie [!DNL Facebook] senden, wo Sie Ihre Zielgruppe auf den sozialen Plattformen ansprechen können. [!DNL People-Based Destinations] können Ihnen helfen:

* Targeting von Offline- und Online-Zielgruppen in Plattformen wie [!DNL Facebook] auf der Grundlage von gehashten E-Mail-Adressen;
* Ergänzung der bestehenden Geräte- und Cookie-Targeting-Funktionen von Audience Manager;
* Vermeidung von Kosten im Zusammenhang mit Onboarding-Lösungen von Drittanbietern;
* Vermeidung von Kosten im Zusammenhang mit der Entwicklung benutzerdefinierter Workflows beim Daten-Onboarding;
* Audiences in Umgebungen ohne Cookies ansprechen;
* Targeting von Zielgruppen durch Deduplizierung von gehashten E-Mail-Adressen, die mit Kunden-IDs abgeglichen werden.

Sie können [!DNL People-Based Destinations] verwenden, um hochwertige Kunden zu segmentieren und anzusprechen, die Ihre Website möglicherweise nicht besucht haben, oder das Targeting von Kunden einzustellen, die bereits offline konvertiert haben. Darüber hinaus können Sie [!DNL Profile Merge Rules] nutzen, um Ihre Offline-First-Party-Daten mit Ihren Online-First-Party-Daten, einschließlich Kundendaten aus anderen Adobe Experience Cloud-Lösungen, zu kombinieren, um Ihre Werbemaßnahmen in den Social Media zu optimieren.

![PBD-Overview](assets/pbd-overview.png)

## Verfügbarkeit {#availability}

[!DNL People-Based Destinations] ist eine Premium-Audience Manager-Integration. Wenden Sie sich an Ihren Adobe-Support-Mitarbeiter, um diese Premium-Funktion nutzen zu können.

## Warum Sie [!UICONTROL People-Based Destinations] verwenden sollten {#why-use}

**Bieten Sie Ihren Kunden konsistente kanalübergreifende Erlebnisse, indem Sie Ihre gesamte Zielgruppensegmentierung innerhalb von Audience Manager verwalten.**

Wenn Sie Ihre Zielgruppensegmente nicht über den Audience Manager in personenbasierten Kanälen aktivieren, werden die Kundenerlebnisse beim Besuch Ihrer Website und bei dem, was die Kundinnen und Kunden beispielsweise in ihren [!DNL Facebook]-Feeds sehen, unterschiedlich dargestellt. Ein konsistentes Targeting über verschiedene Kanäle hinweg kann Ihren Anzeigenumsatz steigern und gleichzeitig Ihre Anzeigenausgaben optimieren.

**Zielgruppen in personenbasierten Kanälen erreichen, ohne dass eine dedizierte Datenintegrationslösung oder benutzerdefinierte Workflows zum Senden von Zielgruppen erforderlich sind.**

Bei der „traditionelleren“ Methode der Zielgruppenbestimmung über personenbasierte Kanäle müssen Sie Ihre Kundendaten in einem Format exportieren, das von der Plattform akzeptiert wird, auf der Sie werben möchten, und dann die dedizierte Onboarding-Methode der Plattform verwenden, um Ihre Kundendaten in Ihr Advertiser-Konto einzubringen. Dies ist alles manuelle Arbeit, die Sie für jede Plattform tun müssen, für die Sie werben möchten. Darüber hinaus können verschiedene Plattformen unterschiedliche Anforderungen an das Datenformat haben, was den Prozess noch mühsamer macht.

![PBD-Overview](assets/pbd-diagram.png)

Mit Audience Manager können Sie [!DNL People-Based Destinations] Ihre Kundendaten zentralisieren, Zielgruppensegmente erstellen und über mehrere personenbasierte Kanäle aktivieren. Sie können all dies über die Audience Manager-Benutzeroberfläche tun, wodurch der zusätzliche Arbeitsaufwand beim manuellen Hochladen von Daten auf jede Plattform vermieden wird und Sie wertvolle Zeit im Prozess sparen.

**Erstellen und Aktivieren von Zielgruppensegmenten aus reinen Offline-Profilen.**

[!DNL People-Based Destinations] das Problem zu lösen, dass Sie zuvor nur Zielgruppensegmente basierend auf der Geräteaktivität aktivieren konnten. Mit [!DNL People-Based Destinations] können Sie Segmente aus rein Offline-Daten aus Ihren eigenen [!DNL CRM] erstellen und in personenbasierten Plattformen aktivieren. Darüber hinaus können Sie Ihre Offline-Daten mit Gerätedaten korrelieren, die Sie bereits im Audience Manager haben.

**Nutzen Sie die Data Governance- und Datenschutzkontrollen von Audience Manager, um Kundendaten sicher zu verarbeiten.**

[!DNL People-Based Destinations] erfordert, dass Sie nur irreversibel gehashte Kennungen verwenden. Dadurch wird das Risiko verringert, dass Kundendaten manuell in jede Zielplattform hochgeladen werden.

Sehen Sie sich das folgende Video an, um einen Überblick über den Datenfluss bei der Verwendung von [!UICONTROL People-Based Destinations] zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/32169?captions=ger)

## Nutzungsszenarios {#use-cases}

Damit Sie besser verstehen können, wie und wann Sie [!DNL People-Based Destinations] verwenden sollten, finden Sie hier zwei Beispielanwendungsfälle, die Audience Manager-Kunden mit dieser Funktion bewältigen können.

### Anwendungsfall #1 {#use-case-1}

Ein Online-Händler möchte bestehende Kunden über soziale Plattformen erreichen und ihnen personalisierte Angebote basierend auf ihren vorherigen Bestellungen zeigen. Mit [!DNL People-Based Destinations] kann der Online-Händler gehashte E-Mail-Adressen von seinem eigenen [!DNL CRM] in den Audience Manager aufnehmen, Segmente aus seinen eigenen Offline-Daten erstellen und diese Segmente an die sozialen Plattformen senden, auf denen er werben möchte, und so seine Werbeausgaben optimieren.

### Anwendungsfall #2 {#use-case-2}

Eine Fluggesellschaft hat verschiedene Kundenstufen (Bronze, Silber und Gold) und möchte jeder dieser Stufen über soziale Plattformen personalisierte Angebote bieten. Das Unternehmen verwendet Audience Manager zur Analyse der Kundenaktivität auf der Website. Allerdings verwenden nicht alle Kunden die Mobile App der Fluggesellschaft, und einige von ihnen haben sich nicht auf der Website des Unternehmens angemeldet. Die einzigen Kennungen, die das Unternehmen zu diesen Kunden hat, sind Mitgliedschafts-IDs und E-Mail-Adressen.

Um sie über Social Media und ähnliche personenbasierte Kanäle anzusprechen, können sie die Kundendaten aus ihren [!DNL CRM] in den Audience Manager integrieren und die gehashten E-Mail-Adressen als Kennungen verwenden.

Als Nächstes können sie ihre Offline-Daten mit ihren vorhandenen Online-Aktivitätseigenschaften kombinieren, um neue Zielgruppensegmente zu erstellen, die sie über [!DNL People-Based Destinations] ansprechen können.

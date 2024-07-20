---
description: Verwenden Sie benutzerbasierte Ziele, um Erstanbieter-Zielgruppensegmente an personenbasierte Umgebungen zu senden. Diese Umgebungen sind geschlossene Ökosysteme, die zu einer Entität gehören, die den innerhalb dieser Umgebung angezeigten Inhalt steuert. Dazu gehören soziale Plattformen wie Facebook und andere Plattformen, die zur Personalisierung der angezeigten Inhalte auf Kundenkonten angewiesen sind.
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

Verwenden Sie [!DNL People-Based Destinations] , um Erstanbieter-Zielgruppensegmente an personenbasierte Umgebungen zu senden. Diese Umgebungen sind geschlossene Ökosysteme, die zu einer Entität gehören, die den innerhalb dieser Umgebung angezeigten Inhalt steuert. Dazu gehören soziale Plattformen wie [!DNL Facebook] und andere Plattformen, die zur Personalisierung der angezeigten Inhalte auf Kundenkonten angewiesen sind.

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

## Überblick {#overview}

Mit [!DNL People-Based Destinations] können Sie die Segmentierung auf Online- und Offline-Daten anwenden, um Zielgruppensegmente basierend auf [Hash-Kennungen](people-based-destinations-prerequisites.md#hashing-requirements) zu erstellen, z. B. E-Mail-Adressen. Anschließend können Sie diese Segmente an &quot;eingesetzte Gärten&quot;wie [!DNL Facebook] senden, wo Sie Ihre Zielgruppe auf den sozialen Plattformen ansprechen können. [!DNL People-Based Destinations] kann Ihnen dabei helfen:

* Targeting von Offline- und Online-Zielgruppen in Plattformen wie [!DNL Facebook] basierend auf Hash-E-Mail-Adressen;
* Ergänzung vorhandener Geräte- und Cookie-Targeting-Funktionen von Audience Manager;
* Beseitigung von Kosten im Zusammenhang mit Onboarding-Lösungen für Drittanbieterdaten;
* Beseitigung von Kosten im Zusammenhang mit der Entwicklung benutzerdefinierter Onboarding-Workflows für Daten;
* Targeting von Zielgruppen in Cookie-losen Umgebungen;
* Targeting von Zielgruppen durch Deduplizierung von mit Kunden-IDs übereinstimmenden Hash-E-Mail-Adressen.

Mit [!DNL People-Based Destinations] können Sie Kunden mit hohem Wert segmentieren und ansprechen, die Ihre Website möglicherweise nicht besucht haben, oder die Zielgruppenbestimmung für Kunden beenden, die bereits offline konvertiert wurden. Darüber hinaus können Sie mit [!DNL Profile Merge Rules] Ihre Offline-Erstanbieterdaten mit Ihren Online-Erstanbieterdaten, einschließlich Kundendaten aus anderen Adobe Experience Cloud-Lösungen, kombinieren, um Ihre Social-Media-Werbemaßnahmen zu optimieren.

![pbd-overview](assets/pbd-overview.png)

## Verfügbarkeit {#availability}

[!DNL People-Based Destinations] ist eine Premium-Audience Manager-Integration. Wenden Sie sich an Ihren Adobe-Support-Mitarbeiter, um diese Premium-Funktion nutzen zu können.

## Warum Sie [!UICONTROL People-Based Destinations] verwenden sollten {#why-use}

**Stellen Sie Ihren Kunden konsistente kanalübergreifende Erlebnisse bereit, indem Sie Ihre gesamte Zielgruppensegmentierung innerhalb von Audience Manager verwalten.**

Wenn Sie Ihre Zielgruppensegmente nicht über Audience Manager in benutzerbezogenen Kanälen aktivieren, führt dies zu unzusammenhängenden Erlebnissen zwischen dem, was Ihre Kunden beim Besuch Ihrer Website sehen, und dem, was sie beispielsweise in ihren [!DNL Facebook] -Feeds sehen. Ein konsistentes Targeting über Kanäle hinweg kann Ihren Anzeigenumsatz erhöhen und gleichzeitig Ihre Anzeigenausgaben optimieren.

**Erreichen Sie Zielgruppen in benutzerbezogenen Kanälen, ohne dass hierfür eine spezielle Lösung für das Onboarding von Daten oder benutzerdefinierte Workflows erforderlich ist.**

Die &quot;herkömmlichere&quot;Methode zum Targeting von Zielgruppen über benutzerbasierte Kanäle hinweg besteht darin, dass Sie Ihre Kundendaten in ein Format exportieren müssen, das von der Plattform akzeptiert wird, auf der Sie eine Anzeige tätigen möchten, und dann die spezielle Onboarding-Methode der Plattform verwenden müssen, um Ihre Kundendaten an Ihr Advertiser-Konto zu übertragen. Dies ist alles eine manuelle Arbeit, die Sie für jede Plattform durchführen müssen, auf der Sie Werbung machen möchten. Darüber hinaus können verschiedene Plattformen unterschiedliche Anforderungen an das Datenformat haben, was den Prozess noch ermüdender macht.

![pbd-overview](assets/pbd-diagram.png)

Durch [!DNL People-Based Destinations] hilft Ihnen Audience Manager bei der Zentralisierung Ihrer Kundendaten, dem Erstellen von Zielgruppensegmenten und der Aktivierung über mehrere personenbasierte Kanäle hinweg. Dies alles ist über die Benutzeroberfläche von Audience Manager möglich, sodass Sie keine zusätzlichen Daten manuell auf jede Plattform hochladen müssen, wodurch Sie wertvolle Verarbeitungszeit sparen.

**Erstellen und aktivieren Sie Zielgruppensegmente aus reinen Offline-Profilen.**

[!DNL People-Based Destinations] Beheben Sie das Problem, dass Sie zuvor nur Zielgruppensegmente basierend auf der Geräteaktivität aktivieren konnten. Mit [!DNL People-Based Destinations] können Sie Segmente aus reinen Offline-Daten aus Ihren eigenen [!DNL CRM] erstellen und sie auf benutzerbezogenen Plattformen aktivieren. Darüber hinaus können Sie Ihre Offline-Daten mit den Gerätedaten korrelieren, die Sie bereits in Audience Manager haben.

**Nutzen Sie die Data Governance- und Datenschutzkontrollen von Audience Manager, um Kundendaten sicher zu verarbeiten.**

[!DNL People-Based Destinations] erfordert, dass Sie nur irreversibel gehashte Kennungen verwenden. Dadurch wird das Risiko reduziert, das mit dem manuellen Hochladen von Kundendaten in die einzelnen Zielplattformen verbunden ist.

Sehen Sie sich das folgende Video an, um einen Überblick über den Datenfluss bei Verwendung von [!UICONTROL People-Based Destinations] zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Nutzungsszenarios {#use-cases}

Um Ihnen zu helfen, besser zu verstehen, wie und wann Sie [!DNL People-Based Destinations] verwenden sollten, finden Sie hier zwei Beispielanwendungsfälle, die Audience Manager mit dieser Funktion lösen können.

### Nutzungsszenario 1 {#use-case-1}

Ein Online-Einzelhändler möchte bestehende Kunden über soziale Plattformen erreichen und ihnen personalisierte Angebote basierend auf ihren bisherigen Bestellungen zeigen. Mit [!DNL People-Based Destinations] kann der Online-Einzelhändler Hash-E-Mail-Adressen von seinem eigenen [!DNL CRM] an den Audience Manager erfassen, Segmente aus eigenen Offline-Daten erstellen und diese Segmente an die Social-Plattformen senden, auf denen er werben möchte, und so seine Werbeausgaben optimieren.

### Nutzungsszenario 2 {#use-case-2}

Eine Fluggesellschaft hat verschiedene Kundenstufen (Bronze, Silber und Gold) und möchte über soziale Plattformen für jede dieser Ebenen personalisierte Angebote bereitstellen. Das Unternehmen verwendet Audience Manager zur Analyse der Kundenaktivität auf der Website. Es wird jedoch nicht von allen Kunden die App der Fluglinie verwendet, und einige von ihnen haben sich nicht bei der Website des Unternehmens angemeldet. Die einzigen Identifikatoren, die das Unternehmen über diese Kunden hat, sind Mitgliedschafts-IDs und E-Mail-Adressen.

Um sie über Social Media und ähnliche personenbasierte Kanäle hinweg anzusprechen, können sie die Kundendaten aus ihrem [!DNL CRM] in den Audience Manager integrieren und die Hash-E-Mail-Adressen als Kennungen verwenden.

Anschließend können sie ihre Offline-Daten mit ihren vorhandenen Online-Aktivitätsmerkmalen kombinieren, um neue Zielgruppensegmente zu erstellen, die sie über [!DNL People-Based Destinations] ansprechen können.

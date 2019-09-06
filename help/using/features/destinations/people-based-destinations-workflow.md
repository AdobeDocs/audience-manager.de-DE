---
description: Benutzerbasierte Ziele bieten verschiedene Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für benutzerbasierte Ziele ausführen müssen.
seo-description: 'Benutzerbasierte Ziele bieten verschiedene Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für benutzerbasierte Ziele ausführen müssen.  '
seo-title: Hinweise zur Implementierung von benutzerbasierten Zielen
solution: Audience Manager
title: Implementierungshandbuch
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Implementierungshandbuch {#implementation-guidance}

[!DNL People-Based Destinations] bietet verschiedene Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je [!DNL People-Based Destinations]nach Szenario befolgen müssen.

## Überblick {#overview}

Die Konfiguration führt [!DNL People-Based Destinations] Sie durch mehrere Abschnitte von Audience Manager und erfordert unterschiedliche Einstellungen und Datenmethoden, je nachdem, welche Art von Kundendaten Sie bereits in Audience Manager haben und welche Zielgruppen-Targeting Sie durchführen möchten.

>[!IMPORTANT]
> Lesen Sie vor dem Konfigurieren [!DNL People-Based Destinations]diesen Artikel sorgfältig und vollständig. Nach dem Lesen dieses Handbuchs sollten Sie über ein klares Verständnis des Szenarios verfügen, das [!DNL People-Based Destinations]Sie aktivieren werden.

Vor der Verwendung müssen sechs Implementierungsaspekte geklärt [!DNL People-Based Destinations]werden. In diesem Artikel erfahren Sie, was Ihre aktuelle Konfiguration ist, damit Sie die Implementierungsschritte für Ihr Szenario genau verfolgen können.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definieren Ihres Verwendungsszenarios {#defining-your-use-case}

Bevor Sie mit der Implementierung [!DNL People-Based Destinations]beginnen, müssen Sie klar den Verwendungsfall definieren, für den Sie diese Funktion verwenden werden. Sie können [!DNL People-Based Destinations] Zielgruppen auf zwei Arten basierend auf der Zielgruppenaktivität einsetzen:

**A) Zielgruppentargeting basierend auf kombinierten Online- und Offline-Benutzeraktivitäten**. In diesem Szenario möchten Sie vorhandene Zielgruppendaten aus Audience Manager mit Daten aus Ihrem internen [!DNL CRM] System kombinieren und die resultierenden Zielgruppensegmente senden. [!DNL People-Based Destinations] Hier ein Beispiel für dieses Szenario:

Ihr Unternehmen, eine Fluglinie, hat verschiedene Kundenstufen (Bronze, Silber und Gold) und Sie möchten jede Ebene mit personalisierten Angeboten über soziale Plattformen bereitstellen. Mit Audience Manager können Sie Kundenaktivitäten auf Ihrer Website analysieren. Jedoch verwenden nicht alle Kunden die mobile App der Fluglinie, und einige davon melden sich nicht einmal bei der Website des Unternehmens an. Ihre Kundendaten sind hauptsächlich auf Mitgliedschafts-IDs und E-Email-Adressen beschränkt.

Um sie über soziale Netzwerke und ähnliche benutzerbasierte Kanäle als Ziel auszuwählen, können Sie die [Hash-E-Email-Adressen](people-based-destinations-prerequisites.md) in Audience Manager übernehmen und sie mit vorhandenen Online-Aktivitätseigenschaften kombinieren, um neue Zielgruppensegmente zu erstellen. Als Nächstes können Sie diese Segmente verwenden, um Ihre Zielgruppe als Ziel auszuwählen [!DNL People-Based Destinations].

**B) Zielgruppentargeting, das ausschließlich auf Offline-Benutzeraktivitäten basiert**. In diesem Szenario enthält Ihr [!DNL CRM] System Kunden-E-Email-Adressen und andere Kundenattribute, aber Kunden haben Ihre Website überhaupt nicht interagiert, sodass Sie keine Kundenaktivität in Audience Manager haben. Hier ein Beispiel für dieses Szenario:

Ihr Unternehmen, ein Telekommunikationsdienstleister, hält Kundendaten wie E-Mail-Adressen und Kaufpläne in einem internen [!DNL CRM]Bereich an. Sie möchten auf bestehende Kunden in sozialen Plattformen abzielen, um ihnen auf Grundlage ihrer bestehenden Abonnements Upgradepakete anzubieten. Dazu können Sie Hash-Kunden-E-Email-Adressen in Audience Manager erfassen und auf der Grundlage vorhandener Kundenabonnements Segmente erstellen. Anschließend können Sie diese Segmente senden, um [!DNL People-Based Destinations] Ihre Kunden mit personalisierten Angeboten zu versorgen.

## 2. Definieren des Typs der zielgerichteten E-Mail-Adressen {#define-target-email}

Der zweite Schritt bei der Definition Ihrer Implementierungsstrategie besteht darin, zu entscheiden, welche Art von Kunden-E-Mail-Adressen als Ziel dienen sollen.

**A) Zielgruppentargeting basierend auf authentifizierten E-Email-Adressen**. In diesem Szenario haben Ihre Benutzer mehrere Konten, die mehreren E-Mail-Adressen zugeordnet sind, und Sie möchten sie mit personalisierten Angeboten auswählen, basierend auf der E-Mail-Adresse, die sie auf Ihrer Website in Echtzeit authentifizieren.

**B) Zielgruppen-Targeting basierend auf allen verknüpften E-Email-Adressen**. In diesem Szenario haben Ihre Benutzer mehrere Konten, die mehreren E-Mail-Adressen zugeordnet sind, und möchten sie für alle verknüpften E-Mail-Adressen unabhängig von der authentifizierten Aktivität als Ziel auswählen.

## 3. Identifizieren Sie die Art der Kunden-IDs (CRM-IDs), die Sie haben. {#identify-customer-id}

Für Zielgruppen ist es [!DNL People-Based Destinations] erforderlich, [dass Sie SHA 256-Hash](people-based-destinations-prerequisites.md) -Versionen Ihrer Kunden-E-Email-Adressen senden. Je nach Ihrer vorhandenen Audience Manager-Konfiguration können Sie sich in einem der beiden folgenden Szenarien befinden:

**A) Ihre Audience Manager-Kunden-IDs ([dpuuids](../../reference/ids-in-aam.md)) sind bereits Kleinbuchstaben, Hash-E-Email-Adressen**. In diesem Szenario können Sie diese vorhandenen IDs verwenden, um Ihre Zielgruppen als Ziel festzulegen [!DNL People-Based Destinations].

**B) Ihre Audience Manager-Kunden-IDs ([dpuuids](../../reference/ids-in-aam.md)) sind nicht Kleinbuchstaben, Hash-E-Email-Adressen**. In diesem Szenario können Ihre vorhandenen Kunden-IDs nicht gesendet [!DNL People-Based Destinations]werden. Sie müssen [!DNL People-Based Destinations]eine ID-Synchronisierung zwischen Ihren vorhandenen Kunden-IDs und Kleinschreibung, Hash-Versionen Ihrer E-Email-Adressen durchführen. Dies erfolgt entweder durch [eine dateibasierte ID-Synchronisierung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) oder durch [Deklarieren deklarierter IDs](../declared-ids.md).

## 4. Trait-Qualifizierung {#trait-qualification}

Um Ihre Zielgruppe genau zu erreichen, [!DNL People-Based Destinations]müssen Ihre Benutzer je nach zielgruppenbasiertem Zielgruppentyp entweder für regelbasierte oder für persönliche Eigenschaften qualifiziert sein.

**A) Qualifizieren Sie Kunden-IDs und Geräte-IDs in Echtzeit für regelbasierte Eigenschaften**. Diese Option gilt für Anwendungsfall A von [1. Definieren Ihres Verwendungsszenarios](people-based-destinations-workflow.md#defining-your-use-case). Wenn Ihr Plan Zielgruppen auf Grundlage der Online- und Offline-Aktivität ist, qualifizieren Sie Ihre Zielgruppe wahrscheinlich bereits für [regelbasierte Eigenschaften](../traits/trait-qualification-reference.md).

**B) Onboard-Eigenschaften gegen Kunden-IDs über eingehende Datendateien**. Diese Option gilt für Anwendungsfall B von [1. Definieren Ihres Verwendungsszenarios](people-based-destinations-workflow.md#defining-your-use-case). Wenn Sie Ihre Zielgruppe auf Grundlage einer reinen Offline-Aktivität ausrichten, müssen Sie Kunden-IDs für eingehende Eigenschaften durch [eingehende Datendateien qualifizieren](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Erstellen oder Beschriften von Datenquellen- und Onboard-Hash-E-Mail-Adressen {#create-label-data-sources}

Je nach Art der Kunden-IDs, die Sie in Audience Manager haben (siehe [3. Identifizieren Sie die Art der Kunden-IDs (CRM-IDs), die Sie haben](people-based-destinations-workflow.md#identify-customer-id), in einem der folgenden Szenarien:

**A) Eine vorhandene Datenquelle beschriften**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([dpuuids](../../reference/ids-in-aam.md)) bereits Kleinbuchstaben, Hash-E-Email-Adressen sind. In diesem Fall müssen Sie die Datenquelle bezeichnen, die Sie die IDs als [!DNL PII] Datenquelle speichern. Einzelheiten zu den Datenquelleneinstellungen finden Sie unter [Datenquelleneinstellungen](../datasources-list-and-settings.md) . Sie müssen sicherstellen, dass die Option "Nicht mit personenbezogenen identifizierbaren Informationen verknüpfen" nicht aktiviert ist.

**B) Erstellen Sie eine neue Datenquelle**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([dpuuids](../../reference/ids-in-aam.md)) keine Hash-E-Email-Adressen sind. In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen und die Hash-E-Mail-Adressen für diese Konfiguration aufrufen. Dies kann auf zweierlei Weise erfolgen:

* Verwenden Sie die dateibasierte ID-Synchronisierung. Unter [Name und Content-Anforderungen für ID-Synchronisierungsdateien](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) finden Sie Informationen darüber, wie die ID-Synchronisierungsdateien aussehen sollten. Wenn Sie diese Methode verwenden, können Sie alle Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank auswählen.
* Deklarieren Sie mit deklarierten [IDs](../declared-ids.md) Hash-E-Email-Adressen, wenn Sie authentifizierte Kunden-IDs übergeben. Bei Verwendung dieser Methode zielt Audience Manager nur auf die Hash-E-Email-Adressen von Benutzern ab, die online authentifiziert wurden. Die E-Email-Adressen, die über Facebook angesprochen werden, sind nur diejenigen in den deklarierten ID-Ereignisaufrufen. Andere E-Email-Adressen, die mit der Kunden-ID verknüpft sind, werden nicht in Echtzeit aktiviert.

## 6. Verwenden Sie eine Regel zum Profilzusammenführen für die Segmentierung {#use-profile-merge-rules}

Je nach verwendetem Verwendungsfall (siehe [1. Definition Ihres Anwendungsszenarios](people-based-destinations-workflow.md#defining-your-use-case)), gibt es zwei Möglichkeiten [!DNL Profile Merge Rules] zur Segmentierung.

**A) Verwenden Sie vorhandene[!DNL Profile Merge Rules]**. Diese Option gilt für den ersten Anwendungsfall (Zielgruppentargeting basierend auf kombinierter Online- und Offline-Benutzeraktivität). In diesem Szenario verfügen Sie über eine bestehende Kundenaktivität in Audience Manager und haben bereits mindestens eine Profilzusammenführungsregel definiert, die Sie in der Segmentierung verwendet haben. In diesem Fall müssen Sie keine neuen [!DNL Profile Merge Rules]erstellen.

**B) Erstellen Sie eine neue[!DNL All Cross-Device Profiles], Zusammenführungsregel**. Diese Option gilt für den zweiten Anwendungsfall (Zielgruppentargeting basierend auf Offline-Benutzeraktivität). In diesem Szenario leiten Sie Offline-Kundendaten von Ihrem [!DNL CRM] in Audience Manager ein und möchten Segmente aus diesen Daten erstellen. Fügt hierfür eine neue, vierte Profilzusammenführungsregel [!DNL People-Based Destinations] ein, die aufgerufen **[!DNL All Cross-Device Profiles]** wird. Diese Regel müssen Sie verwenden, wenn Sie reine Offline-Daten segmentieren.

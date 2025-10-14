---
description: Personenbasierte Ziele bieten mehrere Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. Dieser Artikel bietet einen Überblick über die Implementierungsschritte, die Sie für personenbasierte Ziele je nach Szenario ausführen müssen.
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: Implementierungsleitlinien
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 2%

---

# Implementierungsleitlinien {#implementation-guidance}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Verwendung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um Rechtsberatung zu erhalten.

[!DNL People-Based Destinations] bietet verschiedene Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. Dieser Artikel bietet einen Überblick über die Implementierungsschritte, die Sie je nach Szenario [!DNL People-Based Destinations] ausführen müssen.

## Überblick {#overview}

Die Konfiguration von [!DNL People-Based Destinations] führt Sie durch mehrere Abschnitte von Audience Manager und erfordert verschiedene Einstellungen und Methoden zum Daten-Onboarding, je nachdem, welche Art von Kundendaten Sie bereits in Audience Manager haben und welche Art von Zielgruppen-Targeting Sie durchführen möchten.

>[!IMPORTANT]
> Bevor Sie [!DNL People-Based Destinations] konfigurieren, lesen Sie diesen Artikel sorgfältig und vollständig. Nach dem Lesen dieses Handbuchs sollten Sie über ein klares Verständnis des Szenarios verfügen, das Sie über [!DNL People-Based Destinations] aktivieren werden.

Es gibt sechs Implementierungsaspekte, die Sie vor der Verwendung von [!DNL People-Based Destinations] klären müssen. In diesem Artikel erfahren Sie, was Ihre aktuelle Konfiguration ist, damit Sie die Implementierungsschritte für Ihr Szenario korrekt ausführen können.

![pbd-implementation](assets/pbd-implementation.png)

## &#x200B;1. Definieren des Anwendungsfalls {#defining-your-use-case}

Bevor Sie mit der Implementierung von [!DNL People-Based Destinations] beginnen, müssen Sie den Anwendungsfall klar definieren, für den Sie diese Funktion verwenden werden. Sie können [!DNL People-Based Destinations] verwenden, um Zielgruppen basierend auf der Zielgruppenaktivität auf zwei Arten anzusprechen:

**A) Zielgruppen-Targeting basierend auf Ihrer kombinierten Online- und Offline-Benutzeraktivität**. In diesem Szenario möchten Sie bestehende Zielgruppendaten aus Audience Manager mit Daten aus Ihrem internen [!DNL CRM] kombinieren und die resultierenden Zielgruppensegmente an [!DNL People-Based Destinations] senden. Hier ist ein Beispiel, das dieses Szenario veranschaulicht:

Ihr Unternehmen, eine Fluggesellschaft, verfügt über verschiedene Kundenstufen (Bronze, Silber und Gold), und Sie möchten jeder dieser Stufen über soziale Plattformen personalisierte Angebote unterbreiten. Sie verwenden Audience Manager, um die Kundenaktivität auf Ihrer Website zu analysieren. Allerdings verwenden nicht alle Kunden die Mobile App der Fluggesellschaft, und einige von ihnen haben sich nicht auf der Website des Unternehmens angemeldet. Ihre Kundendaten sind größtenteils auf Mitgliedschafts-IDs und E-Mail-Adressen beschränkt.

Um sie über Social Media und ähnliche personenbasierte Kanäle anzusprechen, können Sie Ihre [gehashten E-Mail-](people-based-destinations-prerequisites.md) in Audience Manager einbinden und sie mit Ihren vorhandenen Online-Aktivitätseigenschaften kombinieren, um neue Zielgruppensegmente zu erstellen. Als Nächstes können Sie diese Segmente verwenden, um Ihre Zielgruppe mithilfe von [!DNL People-Based Destinations] anzusprechen.

**B) Zielgruppen-Targeting ausschließlich auf der Grundlage Ihrer Offline-Benutzeraktivität**. In diesem Szenario enthält Ihr [!DNL CRM]-System Ihre E-Mail-Adressen und andere Kundenattribute, aber Kundinnen und Kunden haben überhaupt nicht mit Ihrer Website interagiert, sodass Sie keine Kundenaktivität in Audience Manager haben. Hier ist ein Beispiel, das dieses Szenario veranschaulicht:

Ihr Unternehmen, ein Telekommunikationsdienstleister, bewahrt Kundendaten wie E-Mail-Adressen und erworbene Telekom-Pläne in einem internen [!DNL CRM] auf. Sie möchten bestehende Kundinnen und Kunden auf Social-Media-Plattformen ansprechen, um ihnen Upgrade-Pakete basierend auf ihren bestehenden Abonnements anzubieten. Dazu können Sie Ihre gehashten Kunden-E-Mail-Adressen in Audience Manager aufnehmen und Segmente basierend auf den bestehenden Kundenabonnements erstellen. Anschließend können Sie diese Segmente an [!DNL People-Based Destinations] senden, um Ihre Kunden mit personalisierten Angeboten anzusprechen.

## &#x200B;2. Typ der anvisierten E-Mail-Adressen definieren {#define-target-email}

Der zweite Schritt bei der Definition Ihrer Implementierungsstrategie besteht darin, zu entscheiden, auf welche Art von Kunden-E-Mail-Adressen Sie abzielen möchten.

**A) Zielgruppen-Targeting basierend auf Ihren authentifizierten E-Mail-Adressen**. In diesem Szenario haben Ihre Benutzerinnen und Benutzer mehrere Konten, die mit mehreren E-Mail-Adressen verknüpft sind, und Sie möchten sie in Echtzeit mit personalisierten Angeboten ansprechen, die nur auf der E-Mail-Adresse basieren, über die sie sich auf Ihrer Website authentifizieren.

**B) Audience-Targeting basierend auf allen Ihren zugehörigen E-Mail-Adressen**. In diesem Szenario haben Ihre Benutzer mehrere Konten, die mit mehreren E-Mail-Adressen verknüpft sind, und Sie möchten sie auf alle zugehörigen E-Mail-Adressen ausrichten, unabhängig von der authentifizierten Aktivität.

## &#x200B;3. Identifizieren Sie den Typ Ihrer Kunden-IDs (CRM-IDs) {#identify-customer-id}

Zur Zielgruppenbestimmung in [!DNL People-Based Destinations] müssen Sie [SHA256-Hash](people-based-destinations-prerequisites.md)-Versionen Ihrer Kunden-E-Mail-Adressen senden. Abhängig von Ihrer bestehenden Audience Manager-Konfiguration können Sie sich in einem der beiden folgenden Szenarien befinden:

**A) Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) werden bereits in Kleinbuchstaben geschrieben und als Hash-E-Mail-Adressen**. In diesem Szenario können Sie diese vorhandenen IDs verwenden, um Ihre Zielgruppen in [!DNL People-Based Destinations] anzusprechen.

**B) Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) werden nicht in Kleinbuchstaben geschrieben, sondern als Hash-E-Mail-Adressen**. In diesem Szenario können Ihre vorhandenen Kunden-IDs nicht an [!DNL People-Based Destinations] gesendet werden. Um [!DNL People-Based Destinations] verwenden zu können, müssen Sie eine ID-Synchronisierung zwischen Ihren vorhandenen Kunden-IDs und den in Kleinbuchstaben gehashten Versionen Ihrer Kunden-E-Mail-Adressen durchführen. Dies erfolgt entweder durch [dateibasierte ID-Synchronisierung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) oder durch Verwendung [deklarierten IDs](../declared-ids.md).

## &#x200B;4. Qualifizierung von Eigenschaften {#trait-qualification}

Um Ihre Zielgruppe in [!DNL People-Based Destinations] genau anzusprechen, müssen sich Ihre Benutzerinnen und Benutzer je nach Art der Zielgruppenbestimmung, die Sie durchführen möchten, entweder für regelbasierte oder für integrierte Eigenschaften qualifizieren.

**A) Qualifizieren Sie Ihre Kunden- und Geräte-IDs in Echtzeit für regelbasierte Eigenschaften**. Diese Option gilt für Anwendungsfall A aus [1. Anwendungsfall definieren](people-based-destinations-workflow.md#defining-your-use-case). Wenn Sie planen, Zielgruppen auf der Grundlage von Online- und Offline-Aktivitäten anzusprechen, qualifizieren Sie Ihre Zielgruppe höchstwahrscheinlich bereits für [regelbasierte Eigenschaften](../traits/trait-and-segment-qualification-reference.md).

**B) Integrieren von Eigenschaften mit Ihren Kunden-IDs über eingehende Datendateien**. Diese Option gilt für Anwendungsfall B aus [1. Anwendungsfall definieren](people-based-destinations-workflow.md#defining-your-use-case). Wenn Ihre Zielgruppe auf der Grundlage einer reinen Offline-Aktivität ausgewählt wird, müssen Sie Kunden-IDs für integrierte Eigenschaften über [eingehende Datendateien) &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## &#x200B;5. Erstellen oder Kennzeichnen von Datenquellen und integrierten Hash-E-Mail-Adressen {#create-label-data-sources}

Je nach dem Typ der Kunden-IDs, die Sie in Audience Manager haben (siehe [3. Identifizieren Sie den Typ der von Ihnen verwendeten Kunden-IDs (CRM](people-based-destinations-workflow.md#identify-customer-id)IDs). Sie befinden sich in einem der folgenden Szenarien:

**A) Eine vorhandene Datenquelle beschriften**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) bereits in Kleinbuchstaben geschrieben und als Hash-E-Mail-Adressen verwendet werden. In diesem Fall müssen Sie Ihre Datenquelle, in der Sie die IDs speichern, als [!DNL PII] Datenquelle kennzeichnen. Siehe [Einstellungen für Data Source](../datasources-list-and-settings.md) für Details zu den Datenquelleneinstellungen. Sie müssen sicherstellen, dass die Option Kann nicht mit persönlich identifizierbaren Informationen verknüpft werden deaktiviert ist.

**B) Erstellen Sie eine neue Datenquelle**. Diese Option gilt für Szenarien, in denen Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) keine Hash-E-Mail-Adressen sind. In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen und Ihre gehashten E-Mail-Adressen dagegen einbinden. Dies ist auf zwei Arten möglich:

* Verwenden Sie die dateibasierte ID-Synchronisierung. Einzelheiten dazu, wie ID-Synchronisierungsdateien aussehen sollten, finden Sie unter [Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). Bei Verwendung dieser Methode können Sie alle Ihre gehashten E-Mail-Adressen aus Ihrer [!DNL CRM]-Datenbank als Ziel auswählen.
* Verwenden Sie [deklarierte IDs](../declared-ids.md), um Ihre gehashten E-Mail-Adressen zu deklarieren, wenn Sie authentifizierte Kunden-IDs übergeben. Wenn Sie diese Methode verwenden, richtet sich Audience Manager in Ihrem Namen nur an Ihre Hash-E-Mail-Adressen von Benutzern, die sich online authentifiziert haben. Die E-Mail-Adressen, die in personenbasierten Kanälen angesprochen werden, sind nur diejenigen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit aktiviert.

## &#x200B;6. Verwenden einer Profilzusammenführungsregel für die Segmentierung {#use-profile-merge-rules}

Je nach Anwendungsfall (siehe [1. Bei der Definition Ihres Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case)) gibt es zwei Möglichkeiten, [!DNL Profile Merge Rules] für die Segmentierung zu verwenden.

**A) Vorhandene[!DNL Profile Merge Rules]** verwenden. Diese Option gilt für den ersten Anwendungsfall (Zielgruppen-Targeting basierend auf kombinierter Online- und Offline-Benutzeraktivität). In diesem Szenario haben Sie eine bestehende Kundenaktivität in Audience Manager und bereits mindestens eine Profilzusammenführungsregel definiert, die Sie in der Segmentierung verwendet haben. In diesem Fall müssen Sie keine neuen [!DNL Profile Merge Rules] erstellen.

**B) Erstellen Sie eine neue, [!DNL All Cross-Device Profiles] Zusammenführungsregel**. Diese Option gilt für den zweiten Anwendungsfall (Zielgruppen-Targeting ausschließlich basierend auf Offline-Benutzeraktivität). In diesem Szenario bringen Sie Ihre Offline-Kundendaten aus Ihrer [!DNL CRM] in Audience Manager und möchten Segmente aus diesen Daten erstellen. Zu diesem Zweck führt [!DNL People-Based Destinations] eine neue vierte Profilzusammenführungsregel namens **[!DNL All Cross-Device Profiles]** ein. Dies ist die Regel, die Sie bei der Segmentierung von rein Offline-Daten verwenden müssen.

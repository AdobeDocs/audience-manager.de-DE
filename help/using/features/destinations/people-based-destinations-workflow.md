---
description: People-Based Destinations bietet je nach Struktur Ihrer Kundendaten mehrere Implementierungsstrategien. Dieser Artikel bietet einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für People-basierte Ziele ausführen müssen.
seo-description: 'People-Based Destinations bietet je nach Struktur Ihrer Kundendaten mehrere Implementierungsstrategien. Dieser Artikel bietet einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für People-basierte Ziele ausführen müssen.  '
seo-title: Implementierungsleitfaden für personenbasierte Ziele
solution: Audience Manager
title: Durchführungsleitlinien
feature: Benutzerbasierte Ziele
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# Durchführungsleitlinien {#implementation-guidance}

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

[!DNL People-Based Destinations] bietet je nach Struktur Ihrer Kundendaten mehrere Implementierungsstrategien. Dieser Artikel bietet einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für [!DNL People-Based Destinations] ausführen müssen.

## Überblick {#overview}

Die Konfiguration von [!DNL People-Based Destinations] führt Sie durch mehrere Bereiche des Audience Managers und erfordert je nach Art der Kundendaten, die Sie bereits im Audience Manager haben, und der Zielgruppen-Targeting, die Sie durchführen möchten, unterschiedliche Einstellungen und Methoden zum Onboarding von Daten.

>[!IMPORTANT]
> Bevor Sie [!DNL People-Based Destinations] konfigurieren, sollten Sie diesen Artikel sorgfältig und vollständig lesen. Nach dem Lesen dieses Handbuchs sollten Sie über ein klares Verständnis des Szenarios verfügen, das Sie über [!DNL People-Based Destinations] aktivieren werden.

Es gibt sechs Implementierungsaspekte, die Sie vor der Verwendung von [!DNL People-Based Destinations] klären müssen. Dieser Artikel hilft Ihnen, Ihre aktuelle Konfiguration zu verstehen, sodass Sie die Implementierungsschritte für Ihr Szenario ordnungsgemäß ausführen können.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Anwendungsfall definieren {#defining-your-use-case}

Bevor Sie mit der Implementierung von [!DNL People-Based Destinations] beginnen, müssen Sie den Anwendungsfall klar definieren, für den Sie diese Funktion verwenden werden. Sie können [!DNL People-Based Destinations] auf zwei Arten verwenden, um Zielgruppen auf Basis der Zielgruppenaktivität anzusprechen:

**A) Zielgruppen-Targeting basierend auf Ihrer kombinierten Online- und Offline-Benutzeraktivität**. In diesem Szenario möchten Sie bestehende Zielgruppendaten aus dem Audience Manager mit Daten aus Ihrem internen [!DNL CRM]-System kombinieren und die resultierenden Zielgruppensegmente an [!DNL People-Based Destinations] senden. Hier ist ein Beispiel, das dieses Szenario veranschaulicht:

Ihr Unternehmen, eine Fluggesellschaft, hat verschiedene Kundenebenen (Bronze, Silber und Gold) und Sie möchten jeder dieser Ebenen personalisierte Angebote über soziale Plattformen bereitstellen. Mit Audience Manager analysieren Sie die Kundenaktivität auf Ihrer Website. Es wird jedoch nicht von allen Kunden die App der Fluglinie verwendet, und einige von ihnen haben sich nicht bei der Website des Unternehmens angemeldet. Ihre Kundendaten sind größtenteils auf Mitgliedschafts-IDs und E-Mail-Adressen beschränkt.

Um sie über Social Media und ähnliche personenbasierte Kanäle hinweg anzusprechen, können Sie Ihre [Hash-E-Mail-Adressen](people-based-destinations-prerequisites.md) in Audience Manager einbinden und sie mit Ihren vorhandenen Online-Aktivitätsmerkmalen kombinieren, um neue Zielgruppensegmente zu erstellen. Als Nächstes können Sie diese Segmente verwenden, um Ihre Zielgruppe über [!DNL People-Based Destinations] anzusprechen.

**B) Zielgruppen-Targeting, das ausschließlich auf Ihrer Offline-Benutzeraktivität** basiert. In diesem Szenario enthält Ihr [!DNL CRM] -System Ihre E-Mail-Adressen und andere Kundenattribute Ihrer Kunden. Kunden haben jedoch überhaupt nicht mit Ihrer Website interagiert, sodass Sie keine Kundenaktivität in Audience Manager haben. Hier ist ein Beispiel, das dieses Szenario veranschaulicht:

Ihr Unternehmen, ein Telekommunikationsdienstleister, bewahrt Kundendaten wie E-Mail-Adressen und erworbene Telekommunikationspläne in einem internen [!DNL CRM] auf. Sie möchten bestehende Kunden in sozialen Plattformen ansprechen, um ihnen Upgrade-Pakete basierend auf ihren bestehenden Abonnements anzubieten. Dazu können Sie Ihre gehashten Kunden-E-Mail-Adressen in Audience Manager erfassen und Segmente basierend auf bestehenden Kundenabonnenten erstellen. Anschließend können Sie diese Segmente an [!DNL People-Based Destinations] senden, um Ihre Kunden mit personalisierten Angeboten anzusprechen.

## 2. Definieren des Typs der zielgerichteten E-Mail-Adressen {#define-target-email}

Der zweite Schritt bei der Definition Ihrer Implementierungsstrategie besteht darin, zu entscheiden, welche Art von Kunden-E-Mail-Adressen Sie als Ziel auswählen möchten.

**A) Zielgruppen-Targeting basierend auf Ihren authentifizierten E-Mail-Adressen**. In diesem Szenario haben Ihre Benutzer mehrere Konten, die mehreren E-Mail-Adressen zugeordnet sind, und Sie möchten ihnen personalisierte Angebote unterbreiten, die nur auf der E-Mail-Adresse basieren, die sie auf Ihrer Website authentifizieren, und zwar in Echtzeit.

**B) Zielgruppen-Targeting basierend auf all Ihren zugehörigen E-Mail-Adressen**. In diesem Szenario haben Ihre Benutzer mehrere Konten, die mehreren E-Mail-Adressen zugeordnet sind, und Sie möchten sie unabhängig von der authentifizierten Aktivität über alle zugehörigen E-Mail-Adressen hinweg ansprechen.

## 3. Identifizieren Sie den Typ der Kunden-IDs (CRM-IDs), die Sie haben {#identify-customer-id}

Für das Targeting von Zielgruppen in [!DNL People-Based Destinations] müssen Sie [SHA256-Hash](people-based-destinations-prerequisites.md)-Versionen Ihrer E-Mail-Adressen Ihrer Kunden senden. Abhängig von Ihrer bestehenden Audience Manager-Konfiguration können Sie sich in einem der beiden folgenden Szenarien befinden:

**A) Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) sind bereits in Kleinbuchstaben geschrieben und Hash-E-Mail-Adressen**. In diesem Szenario können Sie diese vorhandenen IDs verwenden, um Ihre Zielgruppen in [!DNL People-Based Destinations] anzusprechen.

**B) Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) sind keine E-Mail-Adressen mit Hash-Namen** in Kleinbuchstaben. In diesem Szenario können Ihre vorhandenen Kunden-IDs nicht an [!DNL People-Based Destinations] gesendet werden. Um [!DNL People-Based Destinations] zu verwenden, müssen Sie eine ID-Synchronisierung zwischen Ihren vorhandenen Kunden-IDs und den gehashten Kleinbuchstaben Ihrer Kunden-E-Mail-Adressen durchführen. Dies erfolgt entweder durch [dateibasierte ID-Synchronisierung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) oder durch Verwendung von [deklarierten IDs](../declared-ids.md).

## 4. Eigenschaftsqualifikation {#trait-qualification}

Um Ihre Zielgruppe in [!DNL People-Based Destinations] präzise anzusprechen, müssen sich Ihre Benutzer je nach Zielgruppen-Targeting-Typ für regelbasierte oder integrierte Eigenschaften qualifizieren.

**A) Qualifizieren Sie Ihre Kunden-IDs und Geräte-IDs in Echtzeit für regelbasierte Eigenschaften**. Diese Option gilt für den Anwendungsfall A von [1. Definieren Ihres Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case). Wenn Sie Zielgruppen auf Basis von Online- und Offline-Aktivitäten ansprechen möchten, qualifizieren Sie Ihre Zielgruppe höchstwahrscheinlich bereits für [regelbasierte Eigenschaften](../traits/trait-and-segment-qualification-reference.md).

**B) Integrierte Eigenschaften für Ihre Kunden-IDs über eingehende Datendateien**. Diese Option gilt für den Anwendungsfall B von [1. Definieren Ihres Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case). Beim Targeting Ihrer Zielgruppe auf der Basis rein offline geführter Aktivitäten müssen Sie Kunden-IDs über [eingehende Datendateien](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) für integrierte Eigenschaften qualifizieren.

## 5. Data Sources und integrierte Hash-E-Mail-Adressen erstellen oder beschriften {#create-label-data-sources}

Abhängig vom Typ der Kunden-IDs, die Sie in Audience Manager haben (siehe [3. Identifizieren Sie den Typ der Kunden-IDs (CRM-IDs), die Sie haben](people-based-destinations-workflow.md#identify-customer-id). Sie befinden sich in einem der folgenden Szenarien:

**A) Vorhandene Datenquelle beschriften**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) bereits in Kleinbuchstaben und Hash-E-Mail-Adressen enthalten. In diesem Fall müssen Sie Ihre Datenquelle, in der Sie die IDs speichern, als [!DNL PII] Datenquelle beschriften. Weitere Informationen zu den Datenquelleneinstellungen finden Sie unter [Datenquelleneinstellungen](../datasources-list-and-settings.md) . Sie müssen sicherstellen, dass die Option Nicht an persönlich identifizierbare Informationen gebunden werden nicht deaktiviert ist.

**B) Erstellen Sie eine neue Datenquelle**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) keine Hash-E-Mail-Adressen sind. In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen und Ihre Hash-E-Mail-Adressen mit einbinden. Dazu gibt es zwei Möglichkeiten:

* Verwenden Sie die dateibasierte ID-Synchronisierung. Einzelheiten dazu, wie ID-Synchronisierungsdateien aussehen sollten, finden Sie unter [Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). Bei Verwendung dieser Methode können Sie alle Ihre Hash-E-Mail-Adressen aus Ihrer [!DNL CRM]-Datenbank als Ziel auswählen.
* Verwenden Sie [deklarierte IDs](../declared-ids.md), um beim Übergeben authentifizierter Kunden-IDs Ihre Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode wendet Audience Manager in Ihrem Namen nur Hash-E-Mail-Adressen von Benutzern an, die sich online authentifiziert haben. Die E-Mail-Adressen, die in benutzerbezogenen Kanälen angesprochen werden, sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit aktiviert.

## 6. Verwenden einer Profilzusammenführungsrichtlinie für die Segmentierung {#use-profile-merge-rules}

Abhängig von Ihrem Anwendungsfall (siehe [1. Wenn Sie Ihren Anwendungsfall ](people-based-destinations-workflow.md#defining-your-use-case) definieren, gibt es zwei Möglichkeiten, [!DNL Profile Merge Rules] für die Segmentierung zu verwenden.

**A) Vorhandene verwenden[!DNL Profile Merge Rules]**. Diese Option gilt für den ersten Anwendungsfall (Zielgruppen-Targeting basierend auf kombinierter Online- und Offline-Benutzeraktivität). In diesem Szenario verfügen Sie über bestehende Kundenaktivitäten in Audience Manager und haben bereits mindestens eine Profilzusammenführungsrichtlinie definiert, die Sie für die Segmentierung verwendet haben. In diesem Fall müssen Sie keine neuen [!DNL Profile Merge Rules] erstellen.

**B) Erstellen Sie eine neue  [!DNL All Cross-Device Profiles] Zusammenführungsregel**. Diese Option gilt für den zweiten Anwendungsfall (Zielgruppen-Targeting, das ausschließlich auf Offline-Benutzeraktivitäten basiert). In diesem Szenario bringen Sie Ihre Offline-Kundendaten aus Ihrem [!DNL CRM] in Audience Manager und möchten aus diesen Daten Segmente erstellen. Dazu führt [!DNL People-Based Destinations] eine neue, vierte Profilzusammenführungsrichtlinie mit dem Namen **[!DNL All Cross-Device Profiles]** ein. Dies ist die Regel, die Sie bei der Segmentierung von reinen Offline-Daten verwenden müssen.

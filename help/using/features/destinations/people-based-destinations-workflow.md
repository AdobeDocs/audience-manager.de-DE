---
description: Personalisierte Ziele bieten mehrere Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für benutzerbasierte Ziele ausführen müssen.
seo-description: 'Personalisierte Ziele bieten mehrere Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für benutzerbasierte Ziele ausführen müssen.  '
seo-title: Implementierungsleitlinien für benutzerspezifische Ziele
solution: Audience Manager
title: Durchführungsleitlinien
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Durchführungsleitlinien {#implementation-guidance}

[!DNL People-Based Destinations] bietet mehrere Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario ausführen [!DNL People-Based Destinations]müssen.

## Überblick {#overview}

Die Konfiguration von [!DNL People-Based Destinations] führt Sie durch mehrere Abschnitte von Audience Manager und erfordert unterschiedliche Einstellungen und Dateneingabemethoden, je nachdem, welche Art von Kundendaten Sie bereits in Audience Manager haben und welche Art von Zielgruppen-Targeting Sie durchführen möchten.

>[!IMPORTANT]
> Lesen Sie vor der Konfiguration [!DNL People-Based Destinations]diesen Artikel sorgfältig und vollständig durch. Nach dem Lesen dieses Handbuchs sollten Sie sich mit dem Szenario, das Sie aktivieren, klar auskennen [!DNL People-Based Destinations].

Es gibt sechs Implementierungsaspekte, die Sie vor der Verwendung klären müssen [!DNL People-Based Destinations]. Dieser Artikel hilft Ihnen, zu verstehen, was Ihre aktuelle Konfiguration ist, sodass Sie die Implementierungsschritte für Ihr Szenario korrekt ausführen können.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definieren des Anwendungsfalls {#defining-your-use-case}

Bevor Sie mit der Implementierung beginnen [!DNL People-Based Destinations]müssen Sie den Verwendungsfall, für den Sie diese Funktion verwenden werden, klar definieren. Sie können Zielgruppen auf zwei Arten und basierend auf der Zielgruppenaktivität [!DNL People-Based Destinations] als Ziel auswählen:

**A) Zielgruppen-Targeting basierend auf kombinierter Online- und Offline-Benutzeraktivität**. In diesem Szenario möchten Sie vorhandene Zielgruppendaten aus Audience Manager mit Daten aus Ihrem internen [!DNL CRM] System kombinieren und die resultierenden Zielgruppensegmente an [!DNL People-Based Destinations]senden. Hier ist ein Beispiel, das dieses Szenario illustriert:

Ihr Unternehmen, eine Fluggesellschaft, hat verschiedene Kundenstufen (Bronze, Silver und Gold) und Sie möchten jeder dieser Stufen personalisierte Angebote über soziale Plattformen bereitstellen. Mit Audience Manager können Sie die Kundenaktivität auf Ihrer Website analysieren. Nicht alle Kunden verwenden jedoch die mobile App der Fluggesellschaft, und einige von ihnen haben sich noch nie bei der Website des Unternehmens angemeldet. Ihre Kundendaten sind meist auf Mitgliedschafts-IDs und E-Mail-Adressen beschränkt.

Um sie über soziale Medien und ähnliche benutzerbasierte Kanäle hinweg als Ziel festzulegen, können Sie die [Hash-E-Mail-Adressen](people-based-destinations-prerequisites.md) in Audience Manager einbinden und sie mit den vorhandenen Online-Aktivitätsmerkmalen kombinieren, um neue Zielgruppensegmente zu erstellen. Als Nächstes können Sie diese Segmente verwenden, um Ihre Zielgruppe zielgerichtet zu gestalten [!DNL People-Based Destinations].

**B) Zielgruppen-Targeting, das ausschließlich auf Offline-Benutzeraktivitäten** basiert. In diesem Szenario enthält Ihr [!DNL CRM] System E-Mail-Adressen und andere Kundenattribute von Kunden, aber Kunden haben noch gar nicht mit Ihrer Website interagiert, sodass Sie keine Kundenaktivität in Audience Manager haben. Hier ist ein Beispiel, das dieses Szenario illustriert:

Ihr Unternehmen, ein Anbieter von Telekommunikationsdiensten, speichert Kundendaten wie E-Mail-Adressen und erworbene Telekommunikationspläne in einem internen [!DNL CRM]Bereich. Sie möchten bestehende Kunden in sozialen Plattformen gezielt ansprechen, um ihnen Upgradepakete basierend auf ihren bestehenden Abonnements anzubieten. Dazu können Sie Hash-E-Mail-Adressen von Kunden in Audience Manager erfassen und Segmente basierend auf bestehenden Kundenabonnements erstellen. Anschließend können Sie diese Segmente versenden, um Ihre Kunden mit personalisierten Angeboten [!DNL People-Based Destinations] als Ziel auszuwählen.

## 2. Definieren des Typs der zielgerichteten E-Mail-Adressen {#define-target-email}

Der zweite Schritt bei der Definition Ihrer Implementierungsstrategie ist die Entscheidung, welche Art von E-Mail-Adressen von Kunden Sie als Ziel auswählen möchten.

**A) Zielgruppen-Targeting auf Basis authentifizierter E-Mail-Adressen**. In diesem Szenario verfügen Ihre Benutzer über mehrere Konten, die mehreren E-Mail-Adressen zugeordnet sind, und Sie möchten sie mit personalisierten Angeboten in Echtzeit ansprechen, die nur auf der E-Mail-Adresse basieren, die sie auf Ihrer Website authentifizieren.

**B) Zielgruppen-Targeting auf Basis aller verknüpften E-Mail-Adressen**. In diesem Szenario haben Ihre Benutzer mehrere Konten, die mehreren E-Mail-Adressen zugeordnet sind, und Sie möchten sie unabhängig von der authentifizierten Aktivität auf alle zugehörigen E-Mail-Adressen ausrichten.

## 3. Identifizieren Sie den Typ der Kunden-IDs (CRM-IDs), die Sie haben {#identify-customer-id}

Für das Targeting von Zielgruppen in [!DNL People-Based Destinations] müssen Sie [SHA256-Hash](people-based-destinations-prerequisites.md) -Versionen Ihrer E-Mail-Adressen Ihrer Kunden senden. Je nach Ihrer vorhandenen Audience Manager-Konfiguration befinden Sie sich in einem der folgenden beiden Szenarien:

**A) Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) sind bereits in Kleinbuchstaben und mit Hashing versehen**. In diesem Szenario können Sie diese vorhandenen IDs verwenden, um Ihre Zielgruppen in [!DNL People-Based Destinations]auszurichten.

**B) Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) sind nicht in Kleinbuchstaben, sondern Hash-E-Mail-Adressen**. In diesem Szenario können Ihre vorhandenen Kunden-IDs nicht an gesendet werden [!DNL People-Based Destinations]. Zur Verwendung [!DNL People-Based Destinations]müssen Sie eine ID-Synchronisierung zwischen Ihren bestehenden Kunden-IDs und den Kleinbuchstaben- und Hash-Versionen Ihrer E-Mail-Adressen Ihrer Kunden durchführen. Dazu verwenden Sie entweder die [dateibasierte ID-Synchronisierung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) oder [deklarierte IDs](../declared-ids.md).

## 4. Qualifikation der Eigenschaften {#trait-qualification}

Um Ihr Zielpublikum genau auszurichten, [!DNL People-Based Destinations]müssen Ihre Benutzer sich je nach Zielgruppen-Targeting, die Sie durchführen möchten, für regelbasierte oder Onboarded-Eigenschaften qualifizieren.

**A) Qualifizieren Sie Kunden-IDs und Geräte-IDs in Echtzeit für regelbasierte Eigenschaften**. Diese Option gilt für den Anwendungsfall A von [1. Definieren des Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case). Wenn Ihr Ziel auf Zielgruppen basierend auf Online- und Offline-Aktivitäten ausgerichtet werden soll, qualifizieren Sie Ihre Zielgruppe höchstwahrscheinlich bereits für [regelbasierte Eigenschaften](../traits/trait-qualification-reference.md).

**B) Integrierte Eigenschaften gegen Kunden-IDs über eingehende Datendateien**. Diese Option gilt für den Anwendungsfall B von [1. Definieren des Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case). Beim Targeting Ihrer Zielgruppe auf der Grundlage rein Offline-Aktivität müssen Sie Kunden-IDs für integrierte Eigenschaften durch [eingehende Datendateien](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)qualifizieren.

## 5. Erstellen oder Beschriften von Datenquellen und integrierten Hash-E-Mail-Adressen {#create-label-data-sources}

Abhängig vom Typ der Kunden-IDs, die Sie in Audience Manager haben (siehe [3). Identifizieren Sie den Typ der Kunden-IDs (CRM-IDs), die Sie haben](people-based-destinations-workflow.md#identify-customer-id), und Sie finden sich in einem der folgenden Szenarien:

**A) Beschriften einer vorhandenen Datenquelle**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) bereits in Kleinbuchstaben mit Hash-E-Mail-Adressen versehen sind. In diesem Fall müssen Sie die Datenquelle, in der Sie die IDs speichern, als [!DNL PII] Datenquelle beschriften. Einzelheiten zu den Einstellungen für die Datenquelle finden Sie unter [Datenquelleneinstellungen](../datasources-list-and-settings.md) . Sie müssen sicherstellen, dass die Option "An personenbezogene Daten nicht gebunden werden können"nicht aktiviert ist.

**B) Erstellen Sie eine neue Datenquelle**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) keine Hash-E-Mail-Adressen sind. In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen und die dazugehörigen Hash-E-Mail-Adressen einbinden. Sie können dies auf zwei Arten tun:

* Verwenden Sie die dateibasierte ID-Synchronisierung. Einzelheiten dazu, wie ID-Synchronisierungsdateien aussehen sollten, finden Sie unter [Name und Inhaltsanforderungen für ID-Synchronisierungsdateien](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) . Bei Verwendung dieser Methode können Sie alle Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank als Ziel auswählen.
* Verwenden Sie [deklarierte IDs](../declared-ids.md) , um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode wendet Audience Manager nur die Hash-E-Mail-Adressen von Benutzern an, die sich online authentifiziert haben. Die E-Mail-Adressen, die über Facebook erreicht werden, sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit aktiviert.

## 6. Eine Regel zur Profilzusammenführung für die Segmentierung verwenden {#use-profile-merge-rules}

Je nach Anwendungsfall (siehe [1). Definieren des Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case)) gibt es zwei Möglichkeiten, die für die Segmentierung verwendet werden [!DNL Profile Merge Rules] können.

**A) Vorhandene verwenden[!DNL Profile Merge Rules]**. Diese Option gilt für den ersten Anwendungsfall (Zielgruppen-Targeting auf der Grundlage der kombinierten Online- und Offline-Benutzeraktivität). In diesem Szenario haben Sie in Audience Manager über bestehende Kundenaktivitäten verfügen und bereits mindestens eine Profilzusammenführungsregel definiert, die Sie für die Segmentierung verwendet haben. In diesem Fall müssen Sie keine neuen erstellen [!DNL Profile Merge Rules].

**B) Erstellen Sie eine neue[!DNL All Cross-Device Profiles]Merge-Regel**. Diese Option gilt für den zweiten Anwendungsfall (Zielgruppen-Targeting, das ausschließlich auf Offline-Benutzeraktivität basiert). In diesem Szenario bringen Sie Offline-Kundendaten aus Ihrem [!DNL CRM] in Audience Manager und möchten aus diesen Daten Segmente erstellen. Dazu führt Sie [!DNL People-Based Destinations] eine neue, vierte Regel zur Profilzusammenführung mit dem Namen **[!DNL All Cross-Device Profiles]**. Diese Regel müssen Sie bei der Segmentierung von reinen Offlinedaten verwenden.

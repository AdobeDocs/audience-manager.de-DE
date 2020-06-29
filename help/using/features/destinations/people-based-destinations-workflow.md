---
description: Personalisierte Ziele Angebote bieten verschiedene Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für bevölkerungsbasierte Ziele ausführen müssen.
seo-description: 'Personalisierte Ziele Angebote bieten verschiedene Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für bevölkerungsbasierte Ziele ausführen müssen.  '
seo-title: Implementierungsleitlinien für benutzerspezifische Ziele
solution: Audience Manager
title: Durchführungsleitlinien
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 0%

---


# Durchführungsleitlinien {#implementation-guidance}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

[!DNL People-Based Destinations] Angebot mehrerer Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario ausführen [!DNL People-Based Destinations]müssen.

## Überblick {#overview}

Die Konfiguration von [!DNL People-Based Destinations] führt Sie durch mehrere Bereiche des Audience Managers und erfordert unterschiedliche Einstellungen und Dateneingabemethoden, je nachdem, welche Kundendaten Sie bereits im Audience Manager haben und welche Art von Audience-Targeting Sie durchführen möchten.

>[!IMPORTANT]
> Lesen Sie vor der Konfiguration [!DNL People-Based Destinations]diesen Artikel sorgfältig und vollständig durch. Nach dem Lesen dieses Handbuchs sollten Sie sich mit dem Szenario, das Sie aktivieren, klar auskennen [!DNL People-Based Destinations].

Es gibt sechs Implementierungsaspekte, die Sie vor der Verwendung klären müssen [!DNL People-Based Destinations]. Dieser Artikel hilft Ihnen, zu verstehen, was Ihre aktuelle Konfiguration ist, sodass Sie die Implementierungsschritte für Ihr Szenario korrekt ausführen können.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definieren des Anwendungsfalls {#defining-your-use-case}

Bevor Sie mit der Implementierung beginnen, müssen Sie [!DNL People-Based Destinations]den Anwendungsfall, für den Sie diese Funktion verwenden werden, klar definieren. Sie können Audiencen [!DNL People-Based Destinations] zur Zielgruppe auf zwei Arten verwenden, je nach Aktivität der Audience:

**A) Audiencen-Targeting auf Basis Ihrer kombinierten Online- und Offline-Aktivität**. In diesem Szenario sollten Sie vorhandene Daten aus der Audience des Audience Managers mit Daten aus Ihrem internen [!DNL CRM] System kombinieren und die resultierenden Audiencen an [!DNL People-Based Destinations]senden. Hier ist ein Beispiel, das dieses Szenario illustriert:

Ihre Firma, eine Fluggesellschaft, verfügt über verschiedene Kundenstufen (Bronze, Silver und Gold) und Sie möchten jeder dieser Stufen personalisierte Angebot über soziale Plattformen bereitstellen. Mit Audience Manager können Sie die Aktivität Ihrer Kunden auf Ihrer Website analysieren. Nicht alle Kunden verwenden jedoch die mobile App der Fluggesellschaft, und einige von ihnen haben sich noch nicht bei der Website der Firma angemeldet. Ihre Kundendaten sind meist auf Mitgliedschafts-IDs und E-Mail-Adressen beschränkt.

Um sie über soziale Netzwerke und ähnliche personalisierte Kanal hinweg Zielgruppe, können Sie Ihre [Hash-E-Mail-Adressen](people-based-destinations-prerequisites.md) in Audience Manager setzen und sie mit Ihren bestehenden Online-Aktivitäten-Eigenschaften kombinieren, um neue Audiencen zu erstellen. Anschließend können Sie diese Segmente verwenden, um Ihre Audience durch [!DNL People-Based Destinations]zu Zielgruppen.

**B) Audiencen-Targeting, das ausschließlich auf Ihrer Offline-Aktivität** basiert. In diesem Fall enthält Ihr [!DNL CRM] System Ihre E-Mail-Adressen und andere Kundenattribute, aber die Kunden haben noch gar nicht mit Ihrer Website interagiert, sodass Sie keine Aktivität im Audience Manager haben. Hier ist ein Beispiel, das dieses Szenario illustriert:

Ihre Firma, ein Anbieter von Telekommunikationsdiensten, speichert Kundendaten wie E-Mail-Adressen und erworbene Telekommunikationspläne in einem eigenen Haus [!DNL CRM]. Sie möchten bestehende Kunden auf Social-Plattformen Zielgruppe haben, um sie auf der Grundlage ihrer bestehenden Abonnement zu einem Upgrade-Angebot zu bewegen. Dazu können Sie Ihre Hash-E-Mail-Adressen von Kunden in Audience Manager eintragen und Segmente auf Basis der bestehenden Abonnement erstellen. Anschließend können Sie diese Segmente an Ihre Kunden [!DNL People-Based Destinations] mit personalisierten Angeboten senden.

## 2. Definieren des Typs der zielgerichteten E-Mail-Adressen {#define-target-email}

Der zweite Schritt bei der Definition Ihrer Implementierungsstrategie besteht darin, zu entscheiden, welche Art von E-Mail-Adressen von Kunden Zielgruppe werden sollen.

**A) Audiencen-Targeting auf Basis Ihrer authentifizierten E-Mail-Adressen**. In diesem Fall haben Ihre Benutzer mehrere Konten, die mehreren E-Mail-Adressen zugeordnet sind, und Sie möchten diese mit personalisierten Angeboten in Echtzeit Zielgruppe haben, die nur auf der E-Mail-Adresse basieren, die sie auf Ihrer Website authentifizieren.

**B) Audiencen-Targeting auf Basis all Ihrer zugehörigen E-Mail-Adressen**. In diesem Fall haben Ihre Benutzer mehrere Konten, die mehreren E-Mail-Adressen zugeordnet sind, und Sie möchten diese unabhängig von der authentifizierten Aktivität über alle zugehörigen E-Mail-Adressen hinweg Zielgruppe haben.

## 3. Identifizieren Sie den Typ der Kunden-IDs (CRM-IDs), die Sie haben {#identify-customer-id}

Beim Targeting von Audiencen in [!DNL People-Based Destinations] müssen Sie [SHA256-Hashversionen](people-based-destinations-prerequisites.md) Ihrer E-Mail-Adressen senden. Abhängig von Ihrer bestehenden Audience Manager-Konfiguration befinden Sie sich in einem der folgenden beiden Szenarien:

**A) Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) sind bereits in Kleinbuchstaben und mit Hashing-E-Mail-Adressen** versehen. In diesem Szenario können Sie diese vorhandenen IDs verwenden, um Ihre Audiencen in [!DNL People-Based Destinations]zu Zielgruppen.

**B) Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) sind nicht in Kleinbuchstaben, sondern Hash-E-Mail-Adressen**. In diesem Szenario können Ihre vorhandenen Kunden-IDs nicht an gesendet werden [!DNL People-Based Destinations]. Zur Verwendung [!DNL People-Based Destinations]müssen Sie eine ID-Synchronisierung zwischen Ihren bestehenden Kunden-IDs und den Kleinbuchstaben- und Hash-Versionen Ihrer E-Mail-Adressen Ihrer Kunden durchführen. Dazu verwenden Sie entweder die [dateibasierte ID-Synchronisierung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) oder [deklarierte IDs](../declared-ids.md).

## 4. Qualifikation der Eigenschaften {#trait-qualification}

Um Ihre Audience präzise in [!DNL People-Based Destinations]zu Zielgruppen, müssen Ihre Benutzer sich je nach Typ des Audiencen-Targeting, das Sie durchführen möchten, für regelbasierte oder Onboarded-Eigenschaften qualifizieren.

**A) Qualifizieren Sie Ihre Kunden-IDs und Geräte-IDs in Echtzeit für regelbasierte Eigenschaften**. Diese Option gilt für den Anwendungsfall A von [1. Definieren des Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case). Wenn Ihre Zielgruppe von Audiencen auf der Grundlage der Online- und Offline-Aktivität erfolgen soll, qualifizieren Sie Ihre Audience höchstwahrscheinlich bereits für [regelbasierte Eigenschaften](../traits/trait-and-segment-qualification-reference.md).

**B) Integrierte Eigenschaften für Ihre Kunden-IDs über eingehende Datendateien**. Diese Option gilt für den Anwendungsfall B von [1. Definieren des Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case). Beim Targeting Ihrer Audience auf der Grundlage einer rein Offline-Aktivität müssen Sie Kunden-IDs für integrierte Eigenschaften durch [eingehende Datendateien](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)qualifizieren.

## 5. Erstellen oder Beschriften von Datenquellen und integrierten Hash-E-Mail-Adressen {#create-label-data-sources}

Abhängig vom Typ der Kunden-IDs, die Sie in Audience Manager haben (siehe [3). Identifizieren Sie den Typ der Kunden-IDs (CRM-IDs), die Sie haben](people-based-destinations-workflow.md#identify-customer-id), und Sie finden sich in einem der folgenden Szenarien:

**A) Beschriften einer vorhandenen Datenquelle**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) bereits in Kleinbuchstaben und Hash-E-Mail-Adressen enthalten sind. In diesem Fall müssen Sie Ihre Datenquelle beschriften, in der Sie die IDs als [!DNL PII] Datenquelle speichern. Einzelheiten zu den Einstellungen für die Datenquelle finden Sie unter [Datenquelleneinstellungen](../datasources-list-and-settings.md) . Sie müssen sicherstellen, dass die Option &quot;An personenbezogene Daten nicht gebunden werden können&quot;nicht aktiviert ist.

**B) Erstellen Sie eine neue Datenquelle**. Diese Option gilt für den Fall, dass Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) keine Hash-E-Mail-Adressen sind. In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen und Ihre Hash-E-Mail-Adressen mit einbeziehen. Sie können dies auf zwei Arten tun:

* Verwenden Sie die dateibasierte ID-Synchronisierung. Einzelheiten dazu, wie ID-Synchronisierungsdateien aussehen sollten, finden Sie unter [Name und Inhaltsanforderungen für ID-Synchronisierungsdateien](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) . Bei Verwendung dieser Methode können Sie alle Ihre Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank Zielgruppe haben.
* Verwenden Sie [deklarierte IDs](../declared-ids.md) , um beim Übergeben authentifizierter Kunden-IDs Ihre Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode werden von Audience Manager in Ihrem Namen nur Ihre Hash-E-Mail-Adressen von Benutzern Zielgruppe, die sich online authentifiziert haben. Die E-Mail-Adressen, die auf benutzerbasierte Kanal abzielen, sind nur die Adressen in den deklarierten ID-Ereignis-Aufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit aktiviert.

## 6. Profil Merge Rule for Segmentation verwenden {#use-profile-merge-rules}

Je nach Anwendungsfall (siehe [1). Definieren des Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case)) gibt es zwei Möglichkeiten, die für die Segmentierung verwendet werden [!DNL Profile Merge Rules] können.

**A) Vorhandene verwenden[!DNL Profile Merge Rules]**. Diese Option gilt für den ersten Anwendungsfall (Audience Targeting auf der Grundlage der kombinierten Online- und Offline-Aktivität). In diesem Szenario verfügen Sie über eine bestehende Kundenbindung in Audience Manager und haben bereits mindestens eine Profil Merge Rule definiert, die Sie bei der Segmentierung verwendet haben. In diesem Fall müssen Sie keine neuen erstellen[!DNL Profile Merge Rules].

**B) Erstellen Sie eine neue[!DNL All Cross-Device Profiles]Merge-Regel**. Diese Option gilt für den zweiten Anwendungsfall (Audience-Targeting, das ausschließlich auf der Offline-Aktivität basiert). In diesem Fall bringen Sie Ihre Offline-Kundendaten von Ihrem [!DNL CRM] in den Audience Manager und möchten aus diesen Daten Segmente erstellen. Dazu führt [!DNL People-Based Destinations] eine neue, vierte Profil Merge Rule mit dem Namen **[!DNL All Cross-Device Profiles]** ein. Diese Regel müssen Sie bei der Segmentierung von reinen Offlinedaten verwenden.

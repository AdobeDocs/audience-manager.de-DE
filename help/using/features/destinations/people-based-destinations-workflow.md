---
description: Personalisierte Ziele bieten mehrere Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für benutzerbasierte Ziele ausführen müssen.
seo-description: 'Personalisierte Ziele bieten mehrere Implementierungsstrategien, je nachdem, wie Ihre Kundendaten strukturiert sind. In diesem Artikel erhalten Sie einen Überblick über die Implementierungsschritte, die Sie je nach Szenario für benutzerbasierte Ziele ausführen müssen.  '
seo-title: Implementierungsleitlinien für benutzerspezifische Ziele
solution: Audience Manager
title: Durchführungsleitlinien
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

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

Bevor Sie mit der Implementierung beginnen, müssen Sie [!DNL People-Based Destinations]den Anwendungsfall, für den Sie diese Funktion verwenden werden, klar definieren. Sie können Zielgruppen auf zwei Arten und basierend auf der Zielgruppenaktivität [!DNL People-Based Destinations] als Ziel auswählen:

**A) Zielgruppen-Targeting auf Basis Ihrer kombinierten Online- und Offline-Benutzeraktivität**. In diesem Szenario möchten Sie vorhandene Zielgruppendaten aus Audience Manager mit Daten aus Ihrem internen [!DNL CRM] System kombinieren und die resultierenden Zielgruppensegmente an [!DNL People-Based Destinations]senden. Hier ist ein Beispiel, das dieses Szenario illustriert:

Ihr Unternehmen, eine Fluggesellschaft, hat verschiedene Kundenstufen (Bronze, Silver und Gold) und Sie möchten jeder dieser Stufen personalisierte Angebote über soziale Plattformen bereitstellen. Mit Audience Manager können Sie die Kundenaktivität auf Ihrer Website analysieren. Nicht alle Kunden verwenden jedoch die mobile App der Fluggesellschaft, und einige von ihnen haben sich noch nicht bei der Website des Unternehmens angemeldet. Ihre Kundendaten sind meist auf Mitgliedschafts-IDs und E-Mail-Adressen beschränkt.

Um sie über soziale Medien und ähnliche benutzerbasierte Kanäle hinweg als Ziel festzulegen, können Sie Ihre [Hash-E-Mail-Adressen](people-based-destinations-prerequisites.md) in Audience Manager einbinden und sie mit Ihren bestehenden Online-Aktivitätseigenschaften kombinieren, um neue Zielgruppensegmente zu erstellen. Als Nächstes können Sie diese Segmente verwenden, um Ihre Zielgruppe zielgerichtet zu gestalten [!DNL People-Based Destinations].

**B) Zielgruppen-Targeting, das ausschließlich auf Ihrer Offline-Benutzeraktivität** basiert. In diesem Szenario enthält Ihr [!DNL CRM] System Ihre E-Mail-Adressen und andere Kundenattribute Ihrer Kunden. Kunden haben jedoch noch gar nicht mit Ihrer Website interagiert, sodass Sie keine Kundenaktivität in Audience Manager haben. Here's an example that illustrates this scenario:

Ihr Unternehmen, ein Anbieter von Telekommunikationsdiensten, speichert Kundendaten wie E-Mail-Adressen und erworbene Telekommunikationspläne in einem internen [!DNL CRM]Bereich. You want to target existing customers in social platforms to offer them upgrade packages based on their existing subscriptions. To do this, you can ingest your hashed customer email addresses into Audience Manager, and create segments based on the existing customer subscriptions. Then, you can send these segments to  to target your customers with personalized offers.[!DNL People-Based Destinations]

## 2. Define the Type of Targeted Email Addresses {#define-target-email}

The second step in defining your implementation strategy is deciding what type of customer email addresses you want to target.

**A) Audience targeting based on your authenticated email addresses**. In this scenario, your users have multiple accounts associated with multiple email addresses, and you want to target them with personalized offers, based only on the email address that they authenticate on your website, in real time.

**B) Zielgruppen-Targeting auf Basis all Ihrer zugehörigen E-Mail-Adressen**. In this scenario, your users have multiple accounts associated with multiple email addresses, and you want to target them across all of their associated email addresses, regardless of authenticated activity.

## 3. Identify the Type of Customer IDs (CRM IDs) That You Have {#identify-customer-id}

Targeting audiences in [!DNL People-Based Destinations] requires you to send [SHA256 hashed](people-based-destinations-prerequisites.md) versions of your customer email addresses. Depending on your existing Audience Manager configuration, you may find yourself in one of the following two scenarios:

**A) Your Audience Manager customer IDs ([DPUUIDs](../../reference/ids-in-aam.md)) are already lowercase, hashed email addresses**. In this scenario, you can use these existing IDs to target your audiences in .[!DNL People-Based Destinations]

**B) Your Audience Manager customer IDs (DPUUIDs) are not lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)** In diesem Szenario können Ihre vorhandenen Kunden-IDs nicht an gesendet werden [!DNL People-Based Destinations]. Zur Verwendung [!DNL People-Based Destinations]müssen Sie eine ID-Synchronisierung zwischen Ihren bestehenden Kunden-IDs und den Kleinbuchstaben- und Hash-Versionen Ihrer E-Mail-Adressen Ihrer Kunden durchführen. Dazu verwenden Sie entweder die [dateibasierte ID-Synchronisierung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) oder [deklarierte IDs](../declared-ids.md).

## 4. Qualifikation der Eigenschaften {#trait-qualification}

Um Ihr Zielpublikum genau auszurichten, [!DNL People-Based Destinations]müssen Ihre Benutzer sich je nach Zielgruppen-Targeting, die Sie durchführen möchten, für regelbasierte oder Onboarded-Eigenschaften qualifizieren.

**A) Qualifizieren Sie Ihre Kunden-IDs und Geräte-IDs in Echtzeit für regelbasierte Eigenschaften**. Diese Option gilt für den Anwendungsfall A von [1. Definieren des Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case). Wenn Ihr Ziel auf Zielgruppen basierend auf Online- und Offline-Aktivitäten ausgerichtet werden soll, qualifizieren Sie Ihre Zielgruppe höchstwahrscheinlich bereits für [regelbasierte Eigenschaften](../traits/trait-qualification-reference.md).

**B) Integrierte Eigenschaften für Ihre Kunden-IDs über eingehende Datendateien**. Diese Option gilt für den Anwendungsfall B von [1. Definieren des Anwendungsfalls](people-based-destinations-workflow.md#defining-your-use-case). Beim Targeting Ihrer Zielgruppe auf der Grundlage rein Offline-Aktivität müssen Sie Kunden-IDs für integrierte Eigenschaften durch [eingehende Datendateien](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)qualifizieren.

## 5. Erstellen oder Beschriften von Datenquellen und integrierten Hash-E-Mail-Adressen {#create-label-data-sources}

Abhängig vom Typ der Kunden-IDs, die Sie in Audience Manager haben (siehe [3). Identifizieren Sie den Typ der Kunden-IDs (CRM-IDs), die Sie haben](people-based-destinations-workflow.md#identify-customer-id), und Sie finden sich in einem der folgenden Szenarien:

**A) Beschriften einer vorhandenen Datenquelle**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) bereits in Kleinbuchstaben mit Hash-E-Mail-Adressen versehen sind. In diesem Fall müssen Sie Ihre Datenquelle beschriften, in der Sie die IDs als [!DNL PII] Datenquelle speichern. Einzelheiten zu den Einstellungen für die Datenquelle finden Sie unter [Datenquelleneinstellungen](../datasources-list-and-settings.md) . Sie müssen sicherstellen, dass die Option "An personenbezogene Daten nicht gebunden werden können"nicht aktiviert ist.

**B) Erstellen Sie eine neue Datenquelle**. Diese Option gilt für das Szenario, in dem Ihre Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) keine Hash-E-Mail-Adressen sind. In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen und Ihre Hash-E-Mail-Adressen mit einbeziehen. Sie können dies auf zwei Arten tun:

* Verwenden Sie die dateibasierte ID-Synchronisierung. Einzelheiten dazu, wie ID-Synchronisierungsdateien aussehen sollten, finden Sie unter [Name und Inhaltsanforderungen für ID-Synchronisierungsdateien](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) . Bei Verwendung dieser Methode können Sie alle Ihre Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank als Ziel auswählen.
* Verwenden Sie [deklarierte IDs](../declared-ids.md) , um beim Übergeben authentifizierter Kunden-IDs Ihre Hash-E-Mail-Adressen zu deklarieren. When using this method, Audience Manager, on your behalf, only targets your hashed email addresses from users who have authenticated online. Die E-Mail-Adressen, die auf benutzerbasierte Kanäle abzielen, sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Other email addresses associated with the customer ID are not activated in real-time.

## 6. Use a Profile Merge Rule for Segmentation {#use-profile-merge-rules}

Depending on your use case (see 1. [ Defining Your Use Case), there are two ways to use  for segmentation.](people-based-destinations-workflow.md#defining-your-use-case)[!DNL Profile Merge Rules]

**A) Use existing .[!DNL Profile Merge Rules]** This option applies to the first use case (audience targeting based on combined online and offline user activity). In this scenario, you have existing customer activity in Audience Manager and you have already defined at least one Profile Merge Rule that you have used in segmentation. In this case, you don't need to create any new .[!DNL Profile Merge Rules]

**B) Create a new,  Merge Rule.[!DNL All Cross-Device Profiles]** This option applies to the second use case (audience targeting based exclusively on offline user activity). In this scenario you are bringing your offline customer data from your  into Audience Manager, and want to create segments from that data. [!DNL CRM] To do this,  introduces a new, fourth Profile Merge Rule, called . [!DNL People-Based Destinations]**[!DNL All Cross-Device Profiles]** This is the rule that you need to use when segmenting purely offline data.

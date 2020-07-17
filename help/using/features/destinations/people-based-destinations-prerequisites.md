---
description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-title: Voraussetzungen und Erwägungen für benutzerspezifische Ziele
solution: Audience Manager
title: Voraussetzungen und Überlegungen
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 4%

---


# Voraussetzungen und Überlegungen {#prerequisites-considerations}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Nachfolgend finden Sie einen Überblick über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für [!UICONTROL People-Based Destinations]die Anmeldung anmelden.

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

## Anmelden für [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] ist eine Premium-Funktion, mit der Sie Ihre Audience Manager besser ansprechen können, indem Sie Erstanbieter-Audiencen in personalisierten Umgebung aktivieren, Ihre Audience auf benutzerdefinierte Angebot in sozialen Netzwerken oder über E-Mail-Marketing ausrichten können.

Wenden Sie sich an Ihren Adobe-Kundenbetreuer, um diese Premium-Funktion nutzen zu können.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook]

Bevor Sie Ihre Erstanbieter-Audience [!UICONTROL People-Based Destinations] an [!UICONTROL segments] [!DNL Facebook]senden können, stellen Sie sicher, dass folgende Voraussetzungen erfüllt sind:

1. Für Ihr [!DNL Facebook] Benutzerkonto muss die Berechtigung &quot;Kampagnen **** verwalten&quot;für das Anzeigenkonto aktiviert sein, das Sie verwenden möchten.
2. Add the **Adobe Experience Cloud** business account as an advertising partner in your [!DNL Facebook Ad Account]. Verwenden Sie `business ID=206617933627973`. See [Add Partners to Your Business Manager](https://www.facebook.com/business/help/1717412048538897) for details.
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the **Manage campaigns** permission. Dies ist für die Integration von [!UICONTROL People-Based Destinations] erforderlich.
3. Lesen und unterzeichnen Sie die [!DNL Facebook Custom Audiences] Nutzungsbedingungen. Gehen Sie dazu zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wobei `accountID` Ihre [!DNL Facebook Ad Account ID] ist.

### [!DNL LinkedIn]

Bevor Sie Ihre Erstanbieter-Audiencen [!UICONTROL People-Based Destinations] an senden können, stellen Sie sicher, dass Ihr [!DNL LinkedIn]Konto über die [!DNL LinkedIn Campaign Manager] [!DNL Creative Manager] oder höhere Berechtigungsstufe verfügt.

Weitere Informationen zum Bearbeiten Ihrer [!DNL LinkedIn Campaign Manager] Benutzerberechtigungen finden Sie unter [Hinzufügen, Bearbeiten und Entfernen von Benutzerberechtigungen für Werbekonten](https://www.linkedin.com/help/lms/answer/5753) in der LinkedIn-Dokumentation.

Videoanweisungen finden Sie unter [Das benutzerspezifische Ziel](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) von LinkedIn verstehen und konfigurieren.

## Datenintegration {#data-onboarding}

Die Datenerfassung für [!UICONTROL People-Based Destinations] derzeit unterstützt bis zu 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID ([!DNL CRM ID]) pro Batch-Übertragung verknüpft sind. Durch das Hochladen von mehr als 10 mit einer Kunden-ID verknüpften Hash-E-Mail-Adressen werden 10 davon von Audience Manager in beliebiger Reihenfolge aufgenommen.

Beim Hochladen von mehr als 10 mit einer Kunden-ID verknüpften Hash-E-Mail-Adressen in mehreren Batch-Übertragungen behält der Audience Manager die letzten 10 hinzugefügten E-Mail-Adressen bei.

## Datenschutz {#data-privacy}

Obwohl [!UICONTROL People-Based Destinations] Sie die Zielgruppe von Audiencen auf der Grundlage von von Ihnen hochgeladenen Hash-E-Mail-Adressen ermöglichen, ist es Ihnen weiterhin verboten, direkt identifizierbare Besucher-Informationen in Audience Manager hochzuladen. In der Phase der Dateneingabe müssen Sie sicherstellen, dass die zu verwendenden E-Mail-Adressen mit dem [!DNL SHA256] Algorithmus verschlüsselt werden. Andernfalls können Sie sie nicht in verwenden [!UICONTROL People-Based Destinations].

## Daten-Hashing im Vergleich zur Verschlüsselung {#data-hashing-encryption}

Verschlüsselung ist eine Zweiwegefunktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Das Verschlüsseln von Daten im Zusammenhang mit Audience Managern stellt eine ernsthafte Gefahr dar, da jede verschlüsselte Form von personenbezogenen Daten auch entschlüsselt werden kann. Im Gegensatz zur Verschlüsselung [!UICONTROL People-Based Destinations] sind sie stattdessen für die Verwendung mit Hashdaten konzipiert.

Hashing ist eine Einwegfunktion, die die Eingabe verwirft, um ein einzigartiges Ergebnis zu erzielen. Durch den Einsatz geeigneter Hashing-Algorithmen wie [!DNL SHA256]z. B. gibt es keine Möglichkeit, die Hashing-Funktion umzukehren und die nicht verschachtelten Informationen offen zu legen. Die E-Mail-Adressen, die Sie an Audience Manager senden, müssen mit dem [!DNL SHA256] Algorithmus verschlüsselt werden. Auf diese Weise können Sie sicherstellen, dass keine entsperrten E-Mail-Adressen Audience Manager erreichen.

## Hashanforderungen {#hashing-requirements}

Achten Sie beim Hashing der E-Mail-Adressen auf die Einhaltung der folgenden Anforderungen:

* Entfernen Sie alle führenden und nachfolgenden Leerzeichen aus der E-Mail-Zeichenfolge. example: `johndoe@example.com`, nicht `<space>johndoe@example.com<space>`;
* Achten Sie beim Hashing der E-Mail-Zeichenfolgen darauf, die Zeichenfolge in Kleinbuchstaben mit Hash zu versehen.
   * Beispiel: `example@email.com`, nicht `EXAMPLE@EMAIL.COM`;
* Stellen Sie sicher, dass die Hash-Zeichenfolge nur in Kleinbuchstaben angegeben wird
   * Beispiel: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, nicht `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Salt die Zeichenfolge nicht.

Sehen Sie sich das folgende Video an, um die Hashing-Anforderungen von [!UICONTROL People-Based Destinations]zu verstehen.

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Mit Adobe Experience Cloud haben Sie die Möglichkeit, Kunden-IDs über die [!DNL Adobe Experience Platform Identity Service (ECID)]. Detaillierte Informationen zur Verwendung von ECID zum Hash von Kunden-IDs finden Sie unter [SHA256-Hashing-Support für setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Abrufen der Benutzerberechtigung {#obtaining-user-permission}

Da Sie [!UICONTROL People-Based Destinations] bei der Aktivierung von Erstanbieter-Audiencen in personalisierten Kanälen unterstützen, ist es Ihre Verantwortung, Ihre Kunden darüber zu informieren und die erforderlichen Einwilligungen zu erhalten, wie Sie diese Daten für Werbezwecke oder andere Zwecke verwenden werden.

Bevor Sie sich für anmelden, [!UICONTROL People-Based Destinations]müssen Sie die Zustimmung Ihrer Kunden einholen, bevor Sie ihre Informationen für Werbezwecke verwenden.

Falls Ihre Kunden die Kampagnen für Werbung ausschließen möchten, finden Sie unter [Ausschluss-Verwaltung](../../overview/data-security-and-privacy/data-privacy-requests.md) weitere Informationen dazu, wie Audience Manager daran gehindert werden können, Daten zu erfassen.

## Aktivierung von Erstanbieter-Daten erzwingen {#enforcing-first-party-activation}

Bei der Verwendung [!UICONTROL People-Based Destinations]können Sie Erstanbieter-Daten nur verwenden, um Audiencen in benutzerbasierten Kanälen zu aktivieren. Sie können keine Daten von Drittanbietern zur Aktivierung der Audience in benutzerbasierten Kanälen verwenden.

Verwenden Sie bei der Verwendung [!UICONTROL People-Based Destinations]die [Datenexportkontrolle](../data-export-controls.md) , um Ihre [!UICONTROL data sources] und [!UICONTROL destinations] gemäß den Richtlinien und Anforderungen von Zielplattformen und Datenanbietern zu kennzeichnen.

## Integriertes authentifiziertes Hash-IDs mit deklariertem ID-Targeting {#onboard-authenticated-declared-id}

Es gibt zwei Möglichkeiten, Ihre Offline-Daten für [!UICONTROL People-Based Destinations] in Audience Manager zu laden.

* [Senden Sie Stapeldaten](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an Audience Manager, um Hash-E-Mail-Adressen zu erfassen. Bei dieser Methode können Sie die Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank in verwenden [!UICONTROL People-Based Destinations]. Bei Verwendung dieser Methode können Sie außerdem die Hash-E-Mail-Adressen für [Onboarded-Eigenschaften](../traits/trait-and-segment-qualification-reference.md)qualifizieren.
* Use [Declared IDs](../declared-ids.md) to declare hashed email addresses when passing in authenticated customer IDs. When using this method, Audience Manager, on your behalf, only sends to [!UICONTROL People-Based Destinations] the hashed email addresses from users who have authenticated online. Die E-Mail-Adressen, die über benutzerbasierte Kanal aktiviert werden, sind nur die Adressen in den deklarierten ID-Ereignis-Aufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit gesendet.

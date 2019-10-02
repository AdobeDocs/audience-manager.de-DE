---
description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Voraussetzungen und Erwägungen
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# Prerequisites and Considerations {#prerequisites-considerations}

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nothing contained herein is legal advice. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Read below for an overview of customer requirements that you need to meet before signing up for [!DNL People-Based Destinations].

>[!IMPORTANT]
> Read through this article carefully before moving on to the implementation phase.

## Anmelden für benutzerspezifische Ziele {#signing-up}

[!DNL People-Based Destinations] is a premium capability that enhances your Audience Manager experience by allowing you to activate your first-party audience segments in people-based environments, by targeting your audience with customized offers on social networks or through email marketing.

Wenden Sie sich an Ihren Adobe-Kundenbetreuer, um diese Premium-Funktion nutzen zu können.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook]

Bevor Sie Ihre Erstanbieter-Zielgruppensegmente [!DNL People-Based Destinations] [!DNL Facebook]an senden können, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Für Ihr [!DNL Facebook] Benutzerkonto muss die Berechtigung "Kampagnen **** verwalten"für das Anzeigenkonto aktiviert sein, das Sie verwenden möchten.
1. Fügen Sie das **Adobe Experience Cloud** -Geschäftskonto als Werbepartner zu Ihrem [!DNL Facebook Ad Account]Konto hinzu. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter Partner zu Ihrem Business Manager [hinzufügen](https://www.facebook.com/business/help/708679622611131) .
   >[!IMPORTANT]
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung "Kampagnen **verwalten** "aktivieren. Dies ist für die [!DNL People-Based Destinations] Integration erforderlich.
1. Lesen und unterzeichnen Sie die [!DNL Facebook Custom Audiences] Nutzungsbedingungen. Um das zu tun, gehen Sie zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wo `accountID` ist Ihr [!DNL Facebook Ad Account ID].

## Daten bei der Einschiffung {#data-onboarding}

Die Datenerfassung für [!DNL People-Based Destinations] derzeit unterstützt bis zu 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID ([!DNL CRM ID]) pro Batch-Übertragung verknüpft sind. Durch das Hochladen von mehr als 10 mit einer Kunden-ID verknüpften Hash-E-Mail-Adressen erhält Audience Manager 10 davon in beliebiger Reihenfolge.

Durch das Hochladen von mehr als 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID verknüpft sind, in mehreren Batch-Übertragungen behält Audience Manager die letzten 10 hinzugefügten E-Mail-Adressen bei.

## Datenschutz{#data-privacy}

Obwohl Sie Zielgruppen auf Basis von von von Ihnen hochgeladenen Hash-E-Mail-Adressen ansprechen [!DNL People-Based Destinations] können, ist es Ihnen weiterhin verboten, direkt identifizierbare Besucherinformationen in Audience Manager hochzuladen. In der Phase der Dateneingabe müssen Sie sicherstellen, dass die zu verwendenden E-Mail-Adressen mit dem [!DNL SHA256] Algorithmus verschlüsselt werden. Andernfalls können Sie sie nicht in verwenden [!DNL People-Based Destinations].

## Daten-Hashing gegen Verschlüsselung {#data-hashing-encryption}

Verschlüsselung ist eine Zweiwegefunktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Das Verschlüsseln von Daten im Zusammenhang mit Audience Manager stellt eine ernste Gefahr dar, da jede verschlüsselte Form von personenbezogenen Daten auch entschlüsselt werden kann. Im Gegensatz zur Verschlüsselung [!DNL People-Based Destinations] sind sie stattdessen für die Verwendung mit Hashdaten konzipiert.

Hashing ist eine Einwegfunktion, die die Eingabe verwirft, um ein einzigartiges Ergebnis zu erzielen. By using proper hashing algorithms, like , there is no way to reverse the hashing function and reveal the unscrambled information. [!DNL SHA256] Die E-Mail-Adressen, die Sie an Audience Manager senden, müssen mit dem [!DNL SHA256] Algorithmus in Hashing gesetzt werden. This way, you can ensure that no unhashed email addresses reach Audience Manager.

## Hashanforderungen {#hashing-requirements}

Achten Sie beim Hashing der E-Mail-Adressen auf die folgenden Anforderungen:

* Entfernen Sie alle führenden und nachfolgenden Leerzeichen aus der E-Mail-Zeichenfolge. example: `johndoe@example.com`, nicht `<space>johndoe@example.com<space>`;
* Achten Sie beim Hashing der E-Mail-Zeichenfolgen darauf, die Zeichenfolge in Kleinbuchstaben zu hash;
   * Beispiel: `example@email.com`, nicht `EXAMPLE@EMAIL.COM`;
* Stellen Sie sicher, dass die Hash-Zeichenfolge nur in Kleinbuchstaben angegeben wird
   * Beispiel: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, nicht `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Salt die Zeichenfolge nicht.

Mit Adobe Experience Cloud haben Sie die Möglichkeit, Kunden-IDs über den Experience Cloud ID-Dienst zu hash. Detaillierte Informationen zur Verwendung von ECID zum Hash von Kunden-IDs finden Sie unter [SHA256-Hashing-Support für setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Abrufen der Benutzerberechtigung {#obtaining-user-permission}

Da [!DNL People-Based Destinations] Sie die Aktivierung von Erstanbieter-Zielgruppendaten in personalisierten Kanälen unterstützen, ist es Ihre Verantwortung, die notwendigen Einwilligungen Ihrer Kunden darüber zu erhalten, wie Sie ihre Daten für Werbung oder andere Zwecke verwenden werden.

Bevor Sie sich für anmelden, [!DNL People-Based Destinations]müssen Sie die Zustimmung Ihrer Kunden einholen, bevor Sie ihre Informationen für Werbezwecke verwenden.

Falls Ihre Kunden Werbekampagnen ausschließen möchten, finden Sie unter [Opt-out-Verwaltung](../../overview/data-security-and-privacy/opt-out-management.md) weitere Informationen dazu, wie Sie Audience Manager daran hindern können, Daten weiter zu erfassen.

## Enforcing First-Party Data Activation {#enforcing-first-party-activation}

When using , you can only use first-party data to activate audience segments in people-based channels. [!DNL People-Based Destinations] You cannot use any second- or third-party data for audience activation in people-based channels.

## Onboard Authenticated Hashed IDs through Declared ID Targeting {#onboard-authenticated-declared-id}

There are two ways you can bring your offline data to Audience Manager for .[!DNL People-Based Destinations]

* [Send batch data to Audience Manager to ingest hashed email addresses. ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) With this method, you can choose to use the hashed email addresses from your  database in . [!DNL CRM][!DNL People-Based Destinations] Bei Verwendung dieser Methode können Sie außerdem die Hash-E-Mail-Adressen für [Onboarded-Eigenschaften](../traits/trait-qualification-reference.md)qualifizieren.
* Verwenden Sie [deklarierte IDs](../declared-ids.md) , um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Wenn Sie diese Methode verwenden, sendet Audience Manager in Ihrem Namen nur von Benutzern, die sich online authentifiziert haben, an [!DNL People-Based Destinations] die Hash-E-Mail-Adressen. Die E-Mail-Adressen, die über benutzerbasierte Kanäle aktiviert werden, sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit gesendet.

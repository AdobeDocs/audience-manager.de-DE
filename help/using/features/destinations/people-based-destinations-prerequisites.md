---
description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-title: Voraussetzungen und Erwägungen für benutzerspezifische Ziele
solution: Audience Manager
title: Voraussetzungen und Erwägungen
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Voraussetzungen und Erwägungen {#prerequisites-considerations}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Read below for an overview of customer requirements that you need to meet before signing up for .[!DNL People-Based Destinations]

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

## Anmelden für benutzerspezifische Ziele {#signing-up}

[!DNL People-Based Destinations] ist eine Premium-Funktion, die Ihr Audience Manager-Erlebnis verbessert, indem Sie Ihre Erstanbieter-Zielgruppensegmente in benutzerbasierten Umgebungen aktivieren können, indem Sie Ihre Zielgruppe mit benutzerdefinierten Angeboten in sozialen Netzwerken oder per E-Mail-Marketing ansprechen.

Please contact your Adobe representative to take advantage of this premium feature.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook]

Before you can use  to send your first-party audience segments to , make sure you meet the following requirements:[!DNL People-Based Destinations][!DNL Facebook]

1. Your [!DNL Facebook] user account must have the **Manage campaigns** permission enabled for the Ad account that you plan to use.
1. Add the Adobe Experience Cloud business account as an advertising partner in your . ****[!DNL Facebook Ad Account] Verwenden Sie `business ID=206617933627973`. See Add Partners to Your Business Manager for details.[](https://www.facebook.com/business/help/708679622611131)
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the Manage campaigns permission. **** Dies ist für die [!DNL People-Based Destinations] Integration erforderlich.
1. Read and sign the  Terms of Service. [!DNL Facebook Custom Audiences] Um das zu tun, gehen Sie zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wo `accountID` ist Ihr [!DNL Facebook Ad Account ID].

## Data Onboarding {#data-onboarding}

Data ingestion for  currently supports up to 10 hashed email addresses linked to one customer ID (), per batch transfer. [!DNL People-Based Destinations][!DNL CRM ID] Uploading more than 10 hashed email addresses linked to one customer ID causes Audience Manager to ingest 10 of them, in no specific order.

Uploading more than 10 hashed email addresses linked to one customer ID in multiple batch transfers causes Audience Manager to retain the most recent 10 email addresses added.

## Datenschutz{#data-privacy}

Although [!DNL People-Based Destinations] allow you to target audiences based on hashed email addresses uploaded by you, you remain prohibited from uploading any directly identifiable visitor information into Audience Manager. In the data onboarding phase, you must ensure that the email addresses you plan to use are hashed with the  algorithm. [!DNL SHA256] Andernfalls können Sie sie nicht in verwenden [!DNL People-Based Destinations].

## Daten-Hashing gegen Verschlüsselung {#data-hashing-encryption}

Verschlüsselung ist eine Zweiwegefunktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Das Verschlüsseln von Daten im Zusammenhang mit Audience Manager stellt eine ernste Gefahr dar, da jede verschlüsselte Form von personenbezogenen Daten auch entschlüsselt werden kann. As opposed to encryption,  are designed to work with hashed data instead.[!DNL People-Based Destinations]

Hashing ist eine Einwegfunktion, die die Eingabe verwirft, um ein einzigartiges Ergebnis zu erzielen. Durch den Einsatz geeigneter Hashing-Algorithmen wie [!DNL SHA256]z. B. gibt es keine Möglichkeit, die Hashing-Funktion umzukehren und die nicht verschachtelten Informationen offen zu legen. Die E-Mail-Adressen, die Sie an Audience Manager senden, müssen mit dem [!DNL SHA256] Algorithmus in Hashing gesetzt werden. Auf diese Weise können Sie sicherstellen, dass keine entsperrten E-Mail-Adressen zu Audience Manager gelangen.

## Hashanforderungen {#hashing-requirements}

Achten Sie beim Hashing der E-Mail-Adressen auf die folgenden Anforderungen:

* Entfernen Sie alle führenden und nachfolgenden Leerzeichen aus der E-Mail-Zeichenfolge. example: `johndoe@example.com`, nicht `<space>johndoe@example.com<space>`;
* Achten Sie beim Hashing der E-Mail-Zeichenfolgen darauf, die Zeichenfolge in Kleinbuchstaben zu hash;
   * Beispiel: `example@email.com`, nicht `EXAMPLE@EMAIL.COM`;
* Stellen Sie sicher, dass die Hash-Zeichenfolge nur in Kleinbuchstaben angegeben wird
   * Beispiel: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, nicht `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Salt die Zeichenfolge nicht.

Sehen Sie sich das folgende Video an, um die Hashing-Anforderungen von [!UICONTROL People-Based Destinations]zu verstehen.

>[!VIDEO](https://video.tv.adobe.com/v/29003/?captions=ger)

Mit Adobe Experience Cloud haben Sie die Möglichkeit, Kunden-IDs über den Experience Cloud ID-Dienst zu hash. Detaillierte Informationen zur Verwendung von ECID zum Hash von Kunden-IDs finden Sie unter [SHA256-Hashing-Support für setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Abrufen der Benutzerberechtigung {#obtaining-user-permission}

Da [!DNL People-Based Destinations] Sie die Aktivierung von Erstanbieter-Zielgruppendaten in personalisierten Kanälen unterstützen, ist es Ihre Verantwortung, die notwendigen Einwilligungen Ihrer Kunden darüber zu erhalten, wie Sie ihre Daten für Werbung oder andere Zwecke verwenden werden.

Bevor Sie sich für anmelden, [!DNL People-Based Destinations]müssen Sie die Zustimmung Ihrer Kunden einholen, bevor Sie ihre Informationen für Werbezwecke verwenden.

Falls Ihre Kunden Werbekampagnen ausschließen möchten, finden Sie unter [Opt-out-Verwaltung](../../overview/data-security-and-privacy/opt-out-management.md) weitere Informationen dazu, wie Sie Audience Manager daran hindern können, Daten weiter zu erfassen.

## Erstanbieter-Datenaktivierung forcieren {#enforcing-first-party-activation}

Bei der Verwendung [!DNL People-Based Destinations]können Sie Erstanbieter-Daten nur verwenden, um Zielgruppensegmente in benutzerbasierten Kanälen zu aktivieren. You cannot use any second- or third-party data for audience activation in people-based channels.

## Integriertes authentifiziertes Hash-IDs mit deklariertem ID-Targeting {#onboard-authenticated-declared-id}

Es gibt zwei Möglichkeiten, Ihre Offlinedaten in Audience Manager zu laden [!DNL People-Based Destinations].

* [Send batch data to Audience Manager to ingest hashed email addresses. ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) With this method, you can choose to use the hashed email addresses from your  database in . [!DNL CRM][!DNL People-Based Destinations] Additionally, when using this method, you can also qualify the hashed email addresses for onboarded traits.[](../traits/trait-qualification-reference.md)
* Use Declared IDs to declare hashed email addresses when passing in authenticated customer IDs. [](../declared-ids.md) When using this method, Audience Manager, on your behalf, only sends to  the hashed email addresses from users who have authenticated online. [!DNL People-Based Destinations] The email addresses activated through people-based channels are only the ones in the declared ID event calls. Other email addresses associated with the customer ID are not sent in real-time.

---
description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-title: Voraussetzungen und Erwägungen für benutzerspezifische Ziele
solution: Audience Manager
title: Voraussetzungen und Erwägungen
translation-type: tm+mt
source-git-commit: f3fe6abe913d98549ae6c090a2d5f721485308c2

---


# Voraussetzungen und Erwägungen {#prerequisites-considerations}

Nachfolgend finden Sie einen Überblick über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für [!DNL People-Based Destinations]die Anmeldung anmelden.

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

## Anmelden für benutzerspezifische Ziele {#signing-up}

[!DNL People-Based Destinations] ist eine Premium-Funktion, die Ihr Audience Manager-Erlebnis verbessert, indem Sie Erstanbieter-Zielgruppensegmente in benutzerbasierten Umgebungen aktivieren können, indem Sie Ihre Zielgruppe mit benutzerdefinierten Angeboten in sozialen Netzwerken oder per E-Mail-Marketing ansprechen.

Wenden Sie sich an Ihren Adobe-Kundenbetreuer, um diese Premium-Funktion nutzen zu können.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook]

Bevor Sie Zielgruppensegmente [!DNL People-Based Destinations] [!DNL Facebook]an senden können, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Für Ihr [!DNL Facebook] Benutzerkonto muss die Berechtigung "Kampagnen **** verwalten"für das Anzeigenkonto aktiviert sein, das Sie verwenden möchten.
1. Fügen Sie das **Adobe Experience Cloud** -Geschäftskonto als Werbepartner zu Ihrem [!DNL Facebook Ad Account]Konto hinzu. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter Partner zu Ihrem Business Manager [hinzufügen](https://www.facebook.com/business/help/708679622611131) .
   >[!IMPORTANT]
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung "Kampagnen **verwalten** "aktivieren. Dies ist für die [!DNL People-Based Destinations] Integration erforderlich.
1. Lesen und unterzeichnen Sie die [!DNL Facebook Custom Audiences] Nutzungsbedingungen. Um das zu tun, gehen Sie zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wo `accountID` ist Ihr [!DNL Facebook Ad Account ID].

## Daten bei der Einschiffung {#data-onboarding}

Die Datenerfassung für [!DNL People-Based Destinations] derzeit unterstützt bis zu 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID ([!DNL CRM ID]) pro Batch-Übertragung verknüpft sind. Durch das Hochladen von mehr als 10 mit einer Kunden-ID verknüpften Hash-E-Mail-Adressen erhält Audience Manager 10 davon in beliebiger Reihenfolge.

Durch das Hochladen von mehr als 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID verknüpft sind, in mehreren Batch-Übertragungen behält Audience Manager die letzten 10 hinzugefügten E-Mail-Adressen bei.

## Datenschutz{#data-privacy}

Obwohl Sie Zielgruppen auf Basis von E-Mail-Adressen ansprechen [!DNL People-Based Destinations] können, erreichen keine direkt identifizierbaren Besucherinformationen jemals Audience Manager. In der Phase der Dateneingabe müssen Sie sicherstellen, dass die zu verwendenden E-Mail-Adressen mit dem [!DNL SHA256] Algorithmus verschlüsselt werden. Andernfalls können Sie sie nicht in verwenden [!DNL People-Based Destinations].

## Daten-Hashing gegen Verschlüsselung {#data-hashing-encryption}

Verschlüsselung ist eine Zweiwegefunktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Das Verschlüsseln von Daten im Zusammenhang mit Audience Manager stellt ein ernsthaftes Datenschutzrisiko dar, da jede verschlüsselte Form von personenbezogenen Daten auch entschlüsselt werden kann und vertrauliche Kundendaten offen gelegt werden. Im Gegensatz zur Verschlüsselung [!DNL People-Based Destinations] sind diese so konzipiert, dass sie stattdessen mit Hashdaten arbeiten und die Kundendaten schützen, die Sie für das Targeting verwenden.

Hashing ist eine Einwegfunktion, die die Eingabe verwirft, um ein einzigartiges Ergebnis zu erzielen. Durch den Einsatz geeigneter Hashing-Algorithmen wie [!DNL SHA256]z. B. gibt es keine Möglichkeit, die Hashing-Funktion umzukehren und die nicht verschachtelten Informationen offen zu legen. Die E-Mail-Adressen, die Sie an Audience Manager senden, müssen mit dem [!DNL SHA256] Algorithmus in Hashing gesetzt werden. Auf diese Weise erreichen Sie Audience Manager nie persönlich identifizierbare Informationen, sodass Ihre Kundendaten sicher bleiben.

## Hashanforderungen {#hashing-requirements}

Achten Sie beim Hashing der E-Mail-Adressen auf die folgenden Anforderungen:

* Entfernen Sie alle führenden und nachfolgenden Leerzeichen aus der E-Mail-Zeichenfolge. example: `johndoe@example.com`, nicht `<space>johndoe@example.com<space>`;
* Stellen Sie sicher, dass die Hash-Zeichenfolge Kleinbuchstaben hat. example: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, nicht `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Salt die Zeichenfolge nicht.

Mit Adobe Experience Cloud haben Sie die Möglichkeit, Kunden-IDs über den Experience Cloud ID-Dienst zu hash. Detaillierte Informationen zur Verwendung von ECID zum Hash von Kunden-IDs finden Sie unter [SHA256-Hashing-Support für setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Abrufen der Benutzerberechtigung {#obtaining-user-permission}

Da [!DNL People-Based Destinations] Sie die Aktivierung von Erstanbieter-Zielgruppendaten in personalisierten Kanälen unterstützen, ist es Ihre Verantwortung, Ihre Kunden darüber zu informieren, wie Sie ihre Daten für Werbezwecke verwenden werden.

Bevor Sie sich für anmelden, [!DNL People-Based Destinations]müssen Sie die Zustimmung Ihrer Kunden einholen, bevor Sie ihre Informationen für Werbezwecke verwenden.

Falls Ihre Kunden Werbekampagnen ausschließen möchten, finden Sie unter [Opt-out-Verwaltung](../../overview/data-security-and-privacy/opt-out-management.md) weitere Informationen dazu, wie Sie Audience Manager daran hindern können, Daten weiter zu erfassen.

## Erstanbieter-Datenaktivierung forcieren {#enforcing-first-party-activation}

Bei der Verwendung [!DNL People-Based Destinations]können Sie Erstanbieter-Daten nur verwenden, um Zielgruppensegmente in benutzerbasierten Kanälen zu aktivieren. Sie können keine Daten von Drittanbietern zur Aktivierung der Zielgruppe in benutzerbasierten Kanälen verwenden.

## Integriertes authentifiziertes Hash-IDs mit deklariertem ID-Targeting {#onboard-authenticated-declared-id}

Es gibt zwei Möglichkeiten, Ihre Offlinedaten in Audience Manager zu laden [!DNL People-Based Destinations].

* [Senden Sie Stapeldaten](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an Audience Manager, um Hash-E-Mail-Adressen zu erfassen. Mit dieser Methode können Sie alle Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank in verwenden [!DNL People-Based Destinations]. Bei Verwendung dieser Methode können Sie außerdem die Hash-E-Mail-Adressen für [Onboarded-Eigenschaften](../traits/trait-qualification-reference.md)qualifizieren.
* Verwenden Sie [deklarierte IDs](../declared-ids.md) , um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode sendet Audience Manager nur an [!DNL People-Based Destinations] die Hash-E-Mail-Adressen von Benutzern, die sich online authentifiziert haben. Die über Facebook aktivierten E-Mail-Adressen sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit gesendet.

---
description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-title: Voraussetzungen und Erwägungen für benutzerspezifische Ziele
solution: Audience Manager
title: Voraussetzungen und Erwägungen
translation-type: tm+mt
source-git-commit: c605e04489ad444193e1e884ee6a3b05f437b9f2

---


# Voraussetzungen und Erwägungen {#prerequisites-considerations}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Nachfolgend finden Sie einen Überblick über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für [!DNL People-Based Destinations]die Anmeldung anmelden.

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

## Anmelden für benutzerspezifische Ziele {#signing-up}

[!DNL People-Based Destinations] ist eine Premium-Funktion, mit der Sie Ihre Audience Manager-Erfahrung verbessern können, indem Sie Erstanbieter-Audiencen in personalisierten Umgebung aktivieren, Ihre Audience mit angepassten Angeboten in sozialen Netzwerken oder per E-Mail-Marketing ausrichten können.

Wenden Sie sich an Ihren Adobe-Kundenbetreuer, um diese Premium-Funktion nutzen zu können.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook]

Bevor Sie Ihre Erstanbieter-Audiencen [!DNL People-Based Destinations] [!DNL Facebook]an senden können, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. Für Ihr [!DNL Facebook] Benutzerkonto muss die Berechtigung &quot;Campaign **** verwalten&quot;für das Anzeigenkonto aktiviert sein, das Sie verwenden möchten.
2. Hinzufügen Sie das **Adobe Experience Cloud** -Geschäftskonto als Werbepartner in Ihrem [!DNL Facebook Ad Account]. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter [Hinzufügen Partner zu Ihrem Business Manager](https://www.facebook.com/business/help/1717412048538897) .
   >[!IMPORTANT]
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung &quot;Campaign **verwalten** &quot;aktivieren. Dies ist für die [!DNL People-Based Destinations] Integration erforderlich.
3. Lesen und unterzeichnen Sie die [!DNL Facebook Custom Audiences] Nutzungsbedingungen. Um das zu tun, gehen Sie zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wo `accountID` ist Ihr [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn]

>[!IMPORTANT]
>
> Die [!DNL People-Based Destinations] Integration mit [!DNL LinkedIn] befindet sich derzeit in der Beta-Testphase und steht nur einer begrenzten Anzahl von Kunden zur Verfügung.
> 
> Nach Abschluss des Beta-Tests steht diese Integration allen Audience Manager-Kunden zur Verfügung, die sich angemeldet haben [!DNL People-Based Destinations].

Bevor Sie Ihre Erstanbieter-Audiencen [!DNL People-Based Destinations] an senden können, stellen Sie sicher, dass Ihr [!DNL LinkedIn]Konto über die [!DNL LinkedIn Campaign Manager] [!DNL Creative Manager] oder höhere Berechtigungsstufe verfügt.

Informationen zum Bearbeiten Ihrer [!DNL LinkedIn Campaign Manager] Benutzerberechtigungen finden Sie unter [Hinzufügen, Bearbeiten und Entfernen von Benutzerberechtigungen in Werbekonten](https://www.linkedin.com/help/lms/answer/5753)

## Daten bei der Einschiffung {#data-onboarding}

Die Datenerfassung für [!DNL People-Based Destinations] derzeit unterstützt bis zu 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID ([!DNL CRM ID]) pro Batch-Übertragung verknüpft sind. Wenn Sie mehr als 10 mit einer Kunden-ID verknüpfte Hash-E-Mail-Adressen hochladen, erhält Audience Manager 10 davon in beliebiger Reihenfolge.

Beim Hochladen von mehr als 10 mit einer Kunden-ID verknüpften Hash-E-Mail-Adressen in mehreren Batch-Übertragungen behält Audience Manager die letzten 10 hinzugefügten E-Mail-Adressen bei.

## Datenschutz{#data-privacy}

Obwohl [!DNL People-Based Destinations] Sie die Zielgruppe von Audiencen auf der Grundlage von von Ihnen hochgeladenen Hash-E-Mail-Adressen ermöglichen, ist es Ihnen nach wie vor nicht möglich, direkt identifizierbare Besucher in Audience Manager hochzuladen. In der Phase der Dateneingabe müssen Sie sicherstellen, dass die zu verwendenden E-Mail-Adressen mit dem [!DNL SHA256] Algorithmus verschlüsselt werden. Andernfalls können Sie sie nicht in verwenden [!DNL People-Based Destinations].

## Daten-Hashing im Vergleich zur Verschlüsselung {#data-hashing-encryption}

Verschlüsselung ist eine Zweiwegefunktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Das Verschlüsseln von Daten im Kontext von Audience Manager stellt eine ernsthafte Gefahr dar, da jede verschlüsselte Form von personenbezogenen Daten auch entschlüsselt werden kann. Im Gegensatz zur Verschlüsselung [!DNL People-Based Destinations] sind sie stattdessen für die Verwendung mit Hashdaten konzipiert.

Hashing ist eine Einwegfunktion, die die Eingabe verwirft, um ein einzigartiges Ergebnis zu erzielen. Durch den Einsatz geeigneter Hashing-Algorithmen wie [!DNL SHA256]z. B. gibt es keine Möglichkeit, die Hashing-Funktion umzukehren und die nicht verschachtelten Informationen offen zu legen. Die E-Mail-Adressen, die Sie an Audience Manager senden, müssen mit dem [!DNL SHA256] Algorithmus verknüpft werden. Auf diese Weise können Sie sicherstellen, dass keine entsperrten E-Mail-Adressen den Audience Manager erreichen.

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

Adobe Experience Cloud bietet Ihnen die Möglichkeit, Kunden-IDs über den Identitätsdienst für Adobe Experience Platform zu hash. Detaillierte Informationen zur Verwendung von ECID zum Hash von Kunden-IDs finden Sie unter [SHA256-Hashing-Support für setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Abrufen der Benutzerberechtigung {#obtaining-user-permission}

Da Sie [!DNL People-Based Destinations] bei der Aktivierung von Erstanbieter-Audiencen in personalisierten Kanälen unterstützen, ist es Ihre Verantwortung, Ihre Kunden darüber zu informieren und die erforderlichen Einwilligungen zu erhalten, wie Sie diese Daten für Werbezwecke oder andere Zwecke verwenden werden.

Bevor Sie sich für anmelden, [!DNL People-Based Destinations]müssen Sie die Zustimmung Ihrer Kunden einholen, bevor Sie ihre Informationen für Werbezwecke verwenden.

Falls Ihre Kunden Werbemaßnahmen ablehnen möchten, finden Sie unter [Opt-out-Verwaltung](../../overview/data-security-and-privacy/data-privacy-requests.md) weitere Informationen dazu, wie Sie Audience Manager daran hindern können, Daten weiter zu erfassen.

## Aktivierung von Erstanbieter-Daten erzwingen {#enforcing-first-party-activation}

Bei der Verwendung [!DNL People-Based Destinations]können Sie Erstanbieter-Daten nur verwenden, um Audiencen in benutzerbasierten Kanälen zu aktivieren. Sie können keine Daten von Drittanbietern zur Aktivierung der Audience in benutzerbasierten Kanälen verwenden.

Verwenden Sie bei der Verwendung [!UICONTROL People-Based Destinations]die [Data Export Controls](../data-export-controls.md) , um Ihre Datenquellen und Ziele gemäß den Richtlinien und Anforderungen von Zielplattformen und Datenanbietern zu kennzeichnen.

## Integriertes authentifiziertes Hash-IDs mit deklariertem ID-Targeting {#onboard-authenticated-declared-id}

Es gibt zwei Möglichkeiten, Ihre Offlinedaten in Audience Manager zu laden [!DNL People-Based Destinations].

* [Senden Sie Stapeldaten](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an Audience Manager, um Hash-E-Mail-Adressen zu erfassen. Bei dieser Methode können Sie die Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank in verwenden [!DNL People-Based Destinations]. Bei Verwendung dieser Methode können Sie außerdem die Hash-E-Mail-Adressen für [Onboarded-Eigenschaften](../traits/trait-qualification-reference.md)qualifizieren.
* Verwenden Sie [deklarierte IDs](../declared-ids.md) , um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Wenn Sie diese Methode verwenden, sendet Audience Manager in Ihrem Namen nur an [!DNL People-Based Destinations] die Hash-E-Mail-Adressen von Benutzern, die sich online authentifiziert haben. Die E-Mail-Adressen, die über benutzerbasierte Kanal aktiviert werden, sind nur die Adressen in den deklarierten ID-Ereignis-Aufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit gesendet.

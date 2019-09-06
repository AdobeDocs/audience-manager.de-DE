---
description: 'Lesen Sie unten, um einen Überblick über die Kundenanforderungen zu erhalten, die Sie erfüllen müssen, bevor Sie sich für benutzerbasierte Ziele registrieren.  '
seo-description: 'Lesen Sie unten, um einen Überblick über die Kundenanforderungen zu erhalten, die Sie erfüllen müssen, bevor Sie sich für benutzerbasierte Ziele registrieren.  '
seo-title: Voraussetzungen und Überlegungen zu benutzerbasierten Zielen
solution: Audience Manager
title: Voraussetzungen und Überlegungen
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Voraussetzungen und Überlegungen {#prerequisites-considerations}

Lesen Sie unten einen Überblick über die Kundenanforderungen, die Sie erfüllen müssen, bevor [!DNL People-Based Destinations]Sie sich registrieren.

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie zur Implementierungsphase wechseln.

## Registrierung für benutzerbasierte Ziele {#signing-up}

[!DNL People-Based Destinations] ist eine Premium-Funktion, die Ihr Audience Manager-Erlebnis verbessert, indem Sie es Ihnen ermöglichen, Zielgruppensegmente von Erstanbietern in personenbasierten Umgebungen zu aktivieren, indem Sie Ihre Zielgruppe mit angepassten Angeboten in sozialen Netzwerken oder per E-Email-Marketing auswählen.

Weitere Informationen zur Anmeldung erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter [!DNL People-Based Destinations].

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook]

Bevor Sie Zielgruppensegmente [!DNL People-Based Destinations] senden können, [!DNL Facebook]müssen Sie die folgenden Anforderungen erfüllen:

1. Für Ihr [!DNL Facebook] Benutzerkonto muss die Berechtigung **Kampagnen** verwalten für das Anzeigenkonto aktiviert sein, das Sie verwenden möchten.
1. Fügen Sie das **Adobe Experience Cloud** -Geschäftskonto als Werbepartner in Ihrem [!DNL Facebook Ad Account]Unternehmen hinzu. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter [Partner zu Ihrem Business Manager](https://www.facebook.com/business/help/708679622611131) hinzufügen.
   >[!IMPORTANT]
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung **Kampagnen** verwalten aktivieren. Dies ist für die [!DNL People-Based Destinations] Integration erforderlich.
1. Lesen und signieren Sie die [!DNL Facebook Custom Audiences] Servicebedingungen. Gehen Sie dazu zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wo `accountID` ist Ihre [!DNL Facebook Ad Account ID].

## Datenonboarding {#data-onboarding}

Die Datenerfassung unterstützt derzeit [!DNL People-Based Destinations] bis zu 10 Hash-E-Email-Adressen, die mit einer Kunden-ID ([!DNL CRM ID]) verknüpft sind, pro Batch-Übertragung. Wenn Sie mehr als 10 Hash-E-Email-Adressen hochladen, die mit einer Kunden-ID verknüpft sind, werden 10 davon in Audience Manager (ohne spezifische Reihenfolge) übernommen.

Wenn Sie mehr als 10 Hash-E-Email-Adressen hochladen, die mit einer Kunden-ID in mehreren Batch-Übertragungen verknüpft sind, werden die letzten 10 E-Email-Adressen von Audience Manager beibehalten.

## Datenschutz{#data-privacy}

Obwohl [!DNL People-Based Destinations] Sie Zielgruppen auf Basis von E-Email-Adressen erreichen können, erreichen keine direkt identifizierbaren Besucherinformationen jemals den Audience Manager. In der Dateneinstiegsphase müssen Sie sicherstellen, dass die E-Mail-Adressen, die Sie verwenden möchten, mit dem [!DNL SHA256] Algorithmus verschlüsselt werden. Andernfalls können Sie sie [!DNL People-Based Destinations]nicht mehr verwenden.

## Datenhashing Versus Verschlüsselung {#data-hashing-encryption}

Verschlüsselung ist eine bidirektionale Funktion. Verschlüsselte Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Die Verschlüsselung von Daten im Kontext von Audience Manager stellt ein ernsthaftes Datenschutzrisiko dar, da jede verschlüsselte Form von persönlichen Informationen auch entschlüsselt und sensible Kundendaten offen gelegt werden kann. Im Gegensatz zur Verschlüsselung [!DNL People-Based Destinations] können Sie stattdessen mit Hash-Daten arbeiten und die für das Targeting verwendeten Kundendaten schützen.

Hashing ist eine Unidirektionalität, die die Eingabe verwirft, um ein eindeutiges Ergebnis zu erzeugen. Durch die Verwendung von richtigen Hash-Algorithmen gibt [!DNL SHA256]es keine Möglichkeit, die Hashfunktion umzukehren und die unscrageschnittenen Informationen anzuzeigen. Die E-Email-Adressen, die Sie in Audience Manager aufrufen werden, müssen mit dem [!DNL SHA256] Algorithmus Hashing werden. Auf diese Weise erreichen keine personenbezogenen Informationen jemals den Audience Manager, sodass Ihre Kundendaten sicher sind.

## Hashanforderungen {#hashing-requirements}

Achten Sie beim Hashing der E-Mail-Adressen darauf, die folgenden Anforderungen zu erfüllen:

* Entfernen Sie alle führenden und nachfolgenden Leerzeichen aus der E-Email-Zeichenfolge. Beispiel: `johndoe@example.com`, nicht `<space>johndoe@example.com<space>`;
* Stellen Sie sicher, dass die Hash-Zeichenfolge kleinschreibung ist. Beispiel: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, nicht `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Führen Sie die Zeichenfolge nicht durch.

Adobe Experience Cloud gibt Ihnen die Möglichkeit, Kunden-IDs über den Experience Cloud ID-Dienst zu hash. Ausführliche Informationen zur Verwendung von ECID für Hash-Kunden-IDs finden Sie unter [SHA 256 Hashing Support für setcustomerids](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Abrufen von Benutzerberechtigungen {#obtaining-user-permission}

Da Sie [!DNL People-Based Destinations] die Daten der Erstanbieter-Zielgruppe in benutzerbasierten Kanälen aktivieren, sollten Sie Ihre Kunden darüber informieren, wie Sie ihre Daten für Werbezwecke verwenden.

Bevor Sie sich registrieren, [!DNL People-Based Destinations]sollten Sie die Zustimmung Ihrer Kunden einholen, bevor Sie Ihre Informationen zu Werbezwecken verwenden.

Wenn Ihre Kunden Werbekampagnen ausschließen möchten, finden [Sie weitere Informationen](../../overview/data-security-and-privacy/opt-out-management.md) dazu, wie Sie mit Audience Manager keine Daten mehr erfassen können.

## Erzwingen der Erstanbieter-Datenaktivierung {#enforcing-first-party-activation}

Bei der Verwendung [!DNL People-Based Destinations]können Sie nur Erstanbieterdaten verwenden, um Zielgruppensegmente in benutzerbasierten Kanälen zu aktivieren. Sie können keine Drittanbieter- oder Drittanbieterdaten für die Zielgruppenaktivierung in benutzerbasierten Kanälen verwenden.

## Onboard-Authentifizierte Hash-IDs über deklarierte ID-Targeting {#onboard-authenticated-declared-id}

Sie können Ihre Offline-Daten auf zweierlei Weise in Audience Manager übernehmen.[!DNL People-Based Destinations]

* [Senden Sie Stapeldaten](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an Audience Manager, um Hash-E-Email-Adressen zu erfassen. Mit dieser Methode können Sie alle Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank verwenden. [!DNL People-Based Destinations] Wenn Sie diese Methode verwenden, können Sie außerdem die Hash-E-Mail-Adressen für [onboardierte Eigenschaften qualifizieren](../traits/trait-qualification-reference.md).
* Verwenden [Sie deklarierte IDs](../declared-ids.md) , um Hash-E-Email-Adressen beim Übermitteln authentifizierter Kunden-IDs zu deklarieren. Bei Verwendung dieser Methode sendet Audience Manager nur [!DNL People-Based Destinations] den Hash-E-Email-Adressen von Benutzern, die online authentifiziert wurden. Die per Facebook aktivierten E-Email-Adressen sind nur diejenigen in den deklarierten ID-Ereignisaufrufen. Andere E-Email-Adressen, die mit der Kunden-ID verknüpft sind, werden nicht in Echtzeit gesendet.

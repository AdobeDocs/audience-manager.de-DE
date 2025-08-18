---
description: Lesen Sie unten für einen Überblick über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für People-Based Destinations anmelden.
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Voraussetzungen und Überlegungen
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: 2b823855994f394261a66e896ef7de7bb7a5450f
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 2%

---


# Voraussetzungen und Überlegungen {#prerequisites-considerations}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Verwendung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um Rechtsberatung zu erhalten.

Lesen Sie unten für einen Überblick über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für [!UICONTROL People-Based Destinations] anmelden.

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie mit der Implementierungsphase fortfahren.

## Für [!UICONTROL People-Based Destinations] anmelden {#signing-up}

[!UICONTROL People-Based Destinations] ist eine Premium-Funktion, mit der Sie Ihr Audience Manager-Erlebnis verbessern können, indem Sie Erstanbieter-Zielgruppensegmente in personenbasierten Umgebungen aktivieren, indem Sie Ihre Zielgruppe mit benutzerdefinierten Angeboten in sozialen Netzwerken oder per E-Mail-Marketing ansprechen.

Wenden Sie sich an Ihren Adobe-Support-Mitarbeiter, um diese Premium-Funktion nutzen zu können.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Ihre First-Party-[!UICONTROL segments] an [!DNL Facebook] zu senden, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Für Ihr [!DNL Facebook]-Benutzerkonto muss die Berechtigung **Kampagnen verwalten** für das Werbekonto aktiviert sein, das Sie verwenden möchten.
2. Adobe Experience Cloud Fügen Sie das Geschäftskonto **** als Werbepartner zu Ihrer [!DNL Facebook Ad Account] hinzu. Verwenden Sie `business ID=206617933627973`. Weitere [ finden Sie unter „Hinzufügen von Partnern ](https://www.facebook.com/business/help/1717412048538897) Ihrem Business Manager“.

   >[!IMPORTANT]
   >Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung **Kampagnen verwalten** aktivieren. Dies ist für die Integration von [!UICONTROL People-Based Destinations] erforderlich.

3. Lesen und unterzeichnen Sie die [!DNL Facebook Custom Audiences] Nutzungsbedingungen. Gehen Sie dazu zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wobei `accountID` Ihre [!DNL Facebook Ad Account ID] ist.

### [!DNL LinkedIn] {#linkedin}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Ihre Erstanbieter-Zielgruppensegmente an [!DNL LinkedIn] zu senden, stellen Sie sicher, dass Ihr [!DNL LinkedIn Campaign Manager]-Konto über die Berechtigungsstufe [!DNL Creative Manager] oder höher verfügt.

Informationen zum Bearbeiten Ihrer [!DNL LinkedIn Campaign Manager]-Benutzerberechtigungen finden Sie unter [Hinzufügen, Bearbeiten und Entfernen von Benutzerberechtigungen für Advertising-Konten](https://www.linkedin.com/help/lms/answer/5753) in der LinkedIn-Dokumentation.

Videoanweisungen [ Sie unter „Grundlagen und Konfigurieren des personenbasierten LinkedIn](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html)Ziels .

### [!DNL Google Customer Match] {#gcm}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Ihre Erstanbieter-Zielgruppensegmente an ein [!DNL Google Customer Match]-Ziel zu senden, stellen Sie sicher, dass Sie die Richtlinie von Google zur Verwendung von [!DNL Customer Match] lesen und einhalten, wie in der [Dokumentation zum Google-Support beschrieben](https://support.google.com/google-ads/answer/6299717).

Stellen Sie als Nächstes sicher, dass Ihr [!DNL Google]-Konto für eine [!DNL Standard] oder höhere Berechtigungsstufe konfiguriert ist. Weitere Informationen finden Sie in der Dokumentation zu {[}Google Ads .](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&rd=1)

Kunden mit konformen Konten werden automatisch von Google auf die Zulassungsliste gesetzt.

## Daten-Onboarding {#data-onboarding}

>[!IMPORTANT]
>
>Alle Audience Manager-Kunden können Hash-E-Mails aufnehmen, ohne sich für [!UICONTROL People-Based Destinations] anzumelden.

Die Datenaufnahme für [!UICONTROL People-Based Destinations] unterstützt derzeit bis zu 10 gehashte E-Mail-Adressen, die pro Batch-Übertragung mit einer Kunden-ID ([!DNL CRM ID]) verknüpft sind.

Beim Hochladen von mehr als 10 gehashten E-Mail-Adressen, die bei mehreren Batch-Übertragungen mit einer Kunden-ID verknüpft sind, behält Audience Manager die letzten 10 hinzugefügten E-Mail-Adressen bei.

Um Hash-Kennungen aufzunehmen, erstellen [ eine geräteübergreifende Datenquelle für Hash-Kennungen ](../create-data-source-hashed-emails.md) aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations and/or hashed email workflows]** .

![Bild der Audience Manager-Benutzeroberfläche, das die Option zum Freigeben zugehöriger geräteübergreifender IDs in personenbasierten Zielen und/oder Hash-E-Mail-Workflows zeigt](assets/data-source-share-ids.png)

## Datenschutz {#data-privacy}

Obwohl [!UICONTROL People-Based Destinations] es Ihnen ermöglichen, Zielgruppen auf der Grundlage von gehashten E-Mail-Adressen, die Sie hochgeladen haben, anzusprechen, ist es Ihnen weiterhin untersagt, direkt identifizierbare Besucherinformationen in Audience Manager hochzuladen. In der Onboarding-Phase für Daten müssen Sie sicherstellen, dass die E-Mail-Adressen, die Sie verwenden möchten, mit dem [!DNL SHA256]-Algorithmus gehasht werden. Andernfalls können Sie sie nicht in [!UICONTROL People-Based Destinations] verwenden.

## Daten-Hashing versus Verschlüsselung {#data-hashing-encryption}

Die Verschlüsselung ist eine bidirektionale Funktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Die Verschlüsselung von Daten im Zusammenhang mit Audience Manager stellt ein ernsthaftes Risiko dar, da auch jede verschlüsselte Form von persönlich identifizierbaren Informationen entschlüsselt werden kann. Im Gegensatz zur Verschlüsselung sind [!UICONTROL People-Based Destinations] dafür konzipiert, stattdessen mit Hash-Daten zu arbeiten.

Hashing ist eine unidirektionale Funktion, mit der die Eingabe verschlüsselt wird, um ein eindeutiges Ergebnis zu erzielen. Durch die Verwendung geeigneter Hash-Algorithmen wie [!DNL SHA256] gibt es keine Möglichkeit, die Hash-Funktion umzukehren und die entschlüsselten Informationen offenzulegen. Die E-Mail-Adressen, die Sie in Audience Manager integrieren werden, müssen mit dem [!DNL SHA256] gehasht werden. Auf diese Weise können Sie sicherstellen, dass keine ungehashten E-Mail-Adressen Audience Manager erreichen.

## Hash-Anforderungen {#hashing-requirements}

Achten Sie beim Hashing der E-Mail-Adressen auf die Einhaltung der folgenden Anforderungen:

* Alle führenden und nachfolgenden Leerzeichen aus der E-Mail-Zeichenfolge kürzen; Beispiel: `johndoe@example.com`, nicht `<space>johndoe@example.com<space>`;
* Achten Sie beim Hashing der E-Mail-Zeichenfolgen darauf, die Zeichenfolge in Kleinbuchstaben zu hashen.
   * Beispiel: `example@email.com`, nicht `EXAMPLE@EMAIL.COM`;
* Stellen Sie sicher, dass die Hash-Zeichenfolge vollständig in Kleinbuchstaben geschrieben ist
   * Beispiel: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, nicht `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Die Schnur nicht salzen.

Sehen Sie sich das folgende Video an, um die Hash-Anforderungen von [!UICONTROL People-Based Destinations] zu verstehen.

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud bietet Ihnen die Möglichkeit, Kunden-IDs über die [!DNL Adobe Experience Platform Identity Service (ECID)] zu hashen. Siehe [SHA256 Hashing Support for setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) für detaillierte Informationen zur Verwendung von ECID zum Hashing von Kunden-IDs.

## Abrufen der Benutzerberechtigung {#obtaining-user-permission}

Da [!UICONTROL People-Based Destinations] Ihnen bei der Aktivierung von First-Party-Zielgruppendaten in personenbasierten Kanälen hilft, sind Sie dafür verantwortlich, Ihre Kunden darüber zu informieren und die erforderlichen Einverständnisse von ihnen einzuholen, wie Sie ihre Daten für Werbe- oder andere Zwecke verwenden werden.

Bevor Sie sich für [!UICONTROL People-Based Destinations] anmelden, sollten Sie die Zustimmung Ihrer Kunden einholen, bevor Sie deren Informationen für Werbezwecke verwenden.

Wenn Ihre Kundinnen und Kunden Werbekampagnen deaktivieren möchten, finden Sie unter [Opt-out-Verwaltung](../../overview/data-security-and-privacy/data-privacy-requests.md) weitere Informationen dazu, wie Sie Audience Manager daran hindern können, Daten zu erfassen.

## Erzwingen der First-Party-Datenaktivierung {#enforcing-first-party-activation}

Bei Verwendung von [!UICONTROL People-Based Destinations] können Sie nur First-Party-Daten verwenden, um Zielgruppensegmente in personenbasierten Kanälen zu aktivieren. Sie können keine Zweit- oder Drittanbieterdaten für die Zielgruppenaktivierung in personenbasierten Kanälen verwenden.

Verwenden Sie bei der Verwendung von [!UICONTROL People-Based Destinations] [Datenexportsteuerelemente](../data-export-controls.md) um Ihre [!UICONTROL data sources] und [!UICONTROL destinations] gemäß den Richtlinien und Anforderungen von Zielplattformen und Datenanbietern zu kennzeichnen.

## Integrieren von authentifizierten Hash-IDs durch Targeting mit deklarierter ID {#onboard-authenticated-declared-id}

Es gibt zwei Möglichkeiten, Ihre Offline-Daten für [!UICONTROL People-Based Destinations] in Audience Manager zu laden.

* [Senden von Batch-Daten](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an Audience Manager zum Aufnehmen von Hash-E-Mail-Adressen. Mit dieser Methode können Sie die gehashten E-Mail-Adressen aus Ihrer [!DNL CRM] in [!UICONTROL People-Based Destinations] verwenden. Darüber hinaus können Sie bei Verwendung dieser Methode die gehashten E-Mail-Adressen auch für &quot;[ Eigenschaften“ ](../traits/trait-and-segment-qualification-reference.md).
* Verwenden Sie [Declared IDs](../declared-ids.md), um Hash-E-Mail-Adressen zu deklarieren, wenn authentifizierte Kunden-IDs übergeben werden. Bei Verwendung dieser Methode sendet Audience Manager in Ihrem Auftrag nur an [!UICONTROL People-Based Destinations] die gehashten E-Mail-Adressen von Benutzern, die sich online authentifiziert haben. Die über personenbasierte Kanäle aktivierten E-Mail-Adressen sind nur diejenigen, die in den deklarierten ID-Ereignisaufrufen enthalten sind. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit gesendet.

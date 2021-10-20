---
description: 'Unten finden Sie eine Übersicht über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für personenbasierte Ziele registrieren.  '
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Voraussetzungen und Überlegungen
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# Voraussetzungen und Überlegungen {#prerequisites-considerations}

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

Unten finden Sie eine Übersicht über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

## Anmelden für [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] ist eine Premium-Funktion, mit der Sie Ihr Kundenerlebnis verbessern können, indem Sie Ihre Erstanbieter-Zielgruppensegmente in benutzerbezogenen Umgebungen aktivieren, indem Sie Ihre Zielgruppe mit benutzerdefinierten Angeboten in sozialen Netzwerken oder per E-Mail-Marketing ansprechen.

Wenden Sie sich an Ihren Kundenbetreuer, um von dieser Premium-Funktion profitieren zu können.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Bevor Sie [!UICONTROL People-Based Destinations] , um Ihre Erstanbieterzielgruppe zu senden [!UICONTROL segments] nach [!DNL Facebook]müssen Sie sicherstellen, dass Sie die folgenden Anforderungen erfüllen:

1. Ihre [!DNL Facebook] Das Benutzerkonto muss über Folgendes verfügen: **Verwalten von Kampagnen** -Berechtigung für das Werbekonto aktiviert wurde, das Sie verwenden möchten.
2. Fügen Sie die **Adobe Experience Cloud** Geschäftskonto als Werbepartner in Ihrem [!DNL Facebook Ad Account]. Verwenden Sie `business ID=206617933627973`. Siehe [Partner zu Ihrem Business Manager hinzufügen](https://www.facebook.com/business/help/1717412048538897) für Details.
   >[!IMPORTANT]
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die **Verwalten von Kampagnen** Berechtigung. Dies ist für die Integration von [!UICONTROL People-Based Destinations] erforderlich.
3. Lesen und unterschreiben Sie die [!DNL Facebook Custom Audiences] Nutzungsbedingungen. Gehen Sie dazu zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wobei `accountID` Ihre [!DNL Facebook Ad Account ID] ist.

### [!DNL LinkedIn] {#linkedin}

Bevor Sie [!UICONTROL People-Based Destinations] , um Ihre Erstanbieter-Zielgruppensegmente an zu senden. [!DNL LinkedIn], stellen Sie sicher, dass [!DNL LinkedIn Campaign Manager] -Konto hat [!DNL Creative Manager] oder einer höheren Berechtigungsebene.

Informationen zum Bearbeiten Ihrer [!DNL LinkedIn Campaign Manager] Benutzerberechtigungen, siehe [Hinzufügen, Bearbeiten und Entfernen von Benutzerberechtigungen für Werbekonten](https://www.linkedin.com/help/lms/answer/5753) in der LinkedIn-Dokumentation.

Siehe [Verstehen und Konfigurieren des personenbasierten Ziels von LinkedIn](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) für Videoanleitungen.

### [!DNL Google Customer Match] {#gcm}

Bevor Sie [!UICONTROL People-Based Destinations] , um Ihre Erstanbieter-Zielgruppensegmente an eine [!DNL Google Customer Match] Ziel, achten Sie darauf, die Google-Richtlinie zur Verwendung von [!DNL Customer Match], die im Abschnitt [Dokumentation zur Google-Unterstützung](https://support.google.com/google-ads/answer/6299717).

Stellen Sie als Nächstes sicher, dass Ihre [!DNL Google] -Konto für eine [!DNL Standard] oder einer höheren Berechtigungsebene. Siehe [Dokumentation zu Google Ads](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) für Details.

Kunden mit kompatiblen Konten werden von Google automatisch auf die Zulassungsliste gesetzt.

## Datenintegration {#data-onboarding}

Datenerfassung für [!UICONTROL People-Based Destinations] unterstützt derzeit bis zu 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID verknüpft sind ([!DNL CRM ID]), pro Batch-Übertragung. Das Hochladen von mehr als 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID verknüpft sind, führt dazu, dass der Audience Manager 10 davon in beliebiger Reihenfolge aufnimmt.

Durch das Hochladen von mehr als 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID verknüpft sind, bei mehreren Batch-Übertragungen behält der Audience Manager die letzten 10 hinzugefügten E-Mail-Adressen bei.

## Datenschutz {#data-privacy}

Obwohl [!UICONTROL People-Based Destinations] ermöglichen es Ihnen, Zielgruppen auf der Basis von von Ihnen hochgeladenen Hash-E-Mail-Adressen auszuwählen. Sie dürfen weiterhin keine direkt identifizierbaren Besucherinformationen in Audience Manager hochladen. In der Phase des Daten-Onboarding müssen Sie sicherstellen, dass die E-Mail-Adressen, die Sie verwenden möchten, mit dem Hash der [!DNL SHA256] -Algorithmus. Andernfalls können Sie sie nicht in [!UICONTROL People-Based Destinations].

## Daten-Hashing im Vergleich zur Verschlüsselung {#data-hashing-encryption}

Die Verschlüsselung ist eine bidirektionale Funktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Die Verschlüsselung von Daten im Kontext des Audience Managers birgt ernsthafte Risiken, da jede verschlüsselte Form von personenbezogenen Daten auch entschlüsselt werden kann. Im Gegensatz zur Verschlüsselung [!UICONTROL People-Based Destinations] werden stattdessen für Hash-Daten entwickelt.

Hashing ist eine unidirektionale Funktion, die die Eingabe verwirft, um ein eindeutiges Ergebnis zu erzielen. Durch Verwendung geeigneter Hashing-Algorithmen, wie [!DNL SHA256]gibt es keine Möglichkeit, die Hashing-Funktion umzukehren und die nicht verschachtelten Informationen anzuzeigen. Die E-Mail-Adressen, die Sie an Audience Manager senden, müssen mit dem Hash-Wert für [!DNL SHA256] -Algorithmus. Auf diese Weise können Sie sicherstellen, dass keine ungehashten E-Mail-Adressen Audience Manager erreichen.

## Hashanforderungen {#hashing-requirements}

Achten Sie beim Hashing der E-Mail-Adressen auf die folgenden Anforderungen:

* Entfernen Sie alle Leerzeichen am Anfang und am Ende der E-Mail-Zeichenfolge. Beispiel: `johndoe@example.com`, nicht `<space>johndoe@example.com<space>`;
* Achten Sie beim Hashing der E-Mail-Zeichenfolgen darauf, die Zeichenfolge in Kleinbuchstaben zu hash;
   * Beispiel: `example@email.com`, nicht `EXAMPLE@EMAIL.COM`;
* Stellen Sie sicher, dass der Hash-String nur in Kleinbuchstaben geschrieben wird.
   * Beispiel: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, nicht `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Salz die Zeichenfolge nicht.

Sehen Sie sich das folgende Video an, um die Hash-Anforderungen von [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud bietet Ihnen die Möglichkeit, Kunden-IDs über die [!DNL Adobe Experience Platform Identity Service (ECID)]. Siehe [SHA-256-Hashing-Unterstützung für setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) für detaillierte Informationen zur Verwendung von ECID zum Hash von Kunden-IDs.

## Abrufen von Benutzerberechtigungen {#obtaining-user-permission}

Seit [!UICONTROL People-Based Destinations] hilft Ihnen, Erstanbieter-Zielgruppendaten in personenbasierten Kanälen zu aktivieren, ist es Ihre Verantwortung, Ihre Kunden darüber zu informieren und die nötige Zustimmung dazu zu erhalten, wie Sie ihre Daten für Werbung oder andere Zwecke verwenden werden.

Bevor Sie sich für [!UICONTROL People-Based Destinations]müssen Sie die Einwilligung Ihrer Kunden einholen, bevor Sie deren Informationen zu Werbezwecken nutzen.

Falls Ihre Kunden Werbekampagnen abwählen möchten, lesen Sie [Opt-out-Verwaltung](../../overview/data-security-and-privacy/data-privacy-requests.md) Einzelheiten dazu, wie verhindert werden kann, dass der Audience Manager Daten erfasst.

## Erstanbieterdatenaktivierung forcieren {#enforcing-first-party-activation}

Bei Verwendung von [!UICONTROL People-Based Destinations]können Sie Erstanbieterdaten nur verwenden, um Zielgruppensegmente in benutzerbezogenen Kanälen zu aktivieren. Sie können keine Zweit- oder Drittanbieterdaten für die Aktivierung von Zielgruppen in benutzerbezogenen Kanälen verwenden.

Bei Verwendung von [!UICONTROL People-Based Destinations], verwenden [Datenexportkontrollen](../data-export-controls.md) um [!UICONTROL data sources] und [!UICONTROL destinations] gemäß den Richtlinien und Anforderungen von Zielplattformen und Datenanbietern.

## Integrierte authentifizierte Hash-IDs über deklariertes ID-Targeting {#onboard-authenticated-declared-id}

Es gibt zwei Möglichkeiten, Ihre Offline-Daten für [!UICONTROL People-Based Destinations] in Audience Manager zu laden.

* [Senden von Batch-Daten](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) zum Audience Manager, um Hash-E-Mail-Adressen zu erfassen. Bei dieser Methode können Sie die Hash-E-Mail-Adressen Ihrer [!DNL CRM] Datenbank in [!UICONTROL People-Based Destinations]. Bei Verwendung dieser Methode können Sie außerdem die Hash-E-Mail-Adressen für [integrierte Eigenschaften](../traits/trait-and-segment-qualification-reference.md).
* Verwendung [Declared IDs](../declared-ids.md) um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode sendet Audience Manager in Ihrem Namen nur an [!UICONTROL People-Based Destinations] die Hash-E-Mail-Adressen von Benutzern, die sich online authentifiziert haben. Die E-Mail-Adressen, die über benutzerbasierte Kanäle aktiviert werden, sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit gesendet.

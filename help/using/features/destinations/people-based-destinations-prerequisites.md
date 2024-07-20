---
description: Unten finden Sie eine Übersicht über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für personenbasierte Ziele registrieren.
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
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

Unten finden Sie eine Übersicht über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für [!UICONTROL People-Based Destinations] registrieren.

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

## Anmelden für [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] ist eine Premium-Funktion, die Ihr Audience Manager-Erlebnis verbessert, indem Sie Ihre Erstanbieter-Zielgruppensegmente in benutzerbezogenen Umgebungen aktivieren können, indem Sie Ihre Zielgruppe mit benutzerdefinierten Angeboten in sozialen Netzwerken oder per E-Mail-Marketing auswählen.

Wenden Sie sich an Ihren Adobe-Support-Mitarbeiter, um diese Premium-Funktion nutzen zu können.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Ihre Erstanbieter-Audience [!UICONTROL segments] an [!DNL Facebook] zu senden, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Für Ihr [!DNL Facebook] -Benutzerkonto muss die Berechtigung **Kampagnen verwalten** für das Werbekonto aktiviert sein, das Sie verwenden möchten.
2. Fügen Sie das Geschäftskonto **Adobe Experience Cloud** als Werbepartner in Ihre [!DNL Facebook Ad Account] ein. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter [Partner zu Ihrem Business Manager hinzufügen](https://www.facebook.com/business/help/1717412048538897) .

   >[!IMPORTANT]
   >Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung **Kampagnen verwalten** aktivieren. Dies ist für die Integration von [!UICONTROL People-Based Destinations] erforderlich.

3. Lesen und unterschreiben Sie die [!DNL Facebook Custom Audiences] -Nutzungsbedingungen. Gehen Sie dazu zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wobei `accountID` Ihre [!DNL Facebook Ad Account ID] ist.

### [!DNL LinkedIn] {#linkedin}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Ihre Erstanbieter-Zielgruppensegmente an [!DNL LinkedIn] zu senden, stellen Sie sicher, dass Ihr [!DNL LinkedIn Campaign Manager]-Konto über die Berechtigungsebene [!DNL Creative Manager] oder höher verfügt.

Informationen zum Bearbeiten Ihrer [!DNL LinkedIn Campaign Manager] -Benutzerberechtigungen finden Sie unter [Hinzufügen, Bearbeiten und Entfernen von Benutzerberechtigungen für Advertising-Konten](https://www.linkedin.com/help/lms/answer/5753) in der LinkedIn-Dokumentation.

Videoanweisungen finden Sie unter [Grundlegendes zum personenbasierten Ziel von LinkedIn](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) und Konfigurieren .

### [!DNL Google Customer Match] {#gcm}

Bevor Sie mit [!UICONTROL People-Based Destinations] Ihre Erstanbieter-Zielgruppensegmente an ein [!DNL Google Customer Match]-Ziel senden können, sollten Sie die Google-Richtlinie zur Verwendung von [!DNL Customer Match] lesen und einhalten, wie in der [Google-Support-Dokumentation](https://support.google.com/google-ads/answer/6299717) beschrieben.

Stellen Sie als Nächstes sicher, dass Ihr [!DNL Google]-Konto für eine Berechtigungsebene von [!DNL Standard] oder höher konfiguriert ist. Weitere Informationen finden Sie in der Dokumentation zu Google Ads](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) .[

Kunden mit kompatiblen Konten werden von Google automatisch auf die Zulassungsliste gesetzt.

## Datenintegration {#data-onboarding}

>[!IMPORTANT]
>
>Alle Audience Manager können Hash-E-Mails erfassen, ohne sich für [!UICONTROL People-Based Destinations] anzumelden.

Die Datenerfassung für [!UICONTROL People-Based Destinations] unterstützt derzeit bis zu 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID ([!DNL CRM ID]) verknüpft sind, pro Batch-Übertragung.

Durch das Hochladen von mehr als 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID verknüpft sind, bei mehreren Batch-Übertragungen behält der Audience Manager die letzten zehn hinzugefügten E-Mail-Adressen bei.

Um Hash-IDs zu erfassen, erstellen Sie [ eine geräteübergreifende Datenquelle für Hash-Kennungen](../create-data-source-hashed-emails.md) und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations and/or hashed email workflows]** .

![Audience Manager-UI-Bild, das die Option zum Freigeben verknüpfter geräteübergreifender IDs in benutzerbezogenen Zielen und/oder Hash-E-Mail-Workflows anzeigt](assets/data-source-share-ids.png)

## Datenschutz {#data-privacy}

Obwohl Sie mit [!UICONTROL People-Based Destinations] Zielgruppen auf der Basis von von Ihnen hochgeladenen Hash-E-Mail-Adressen ansprechen können, ist es Ihnen auch weiterhin untersagt, direkt identifizierbare Besucherinformationen in Audience Manager hochzuladen. In der Phase des Daten-Onboarding müssen Sie sicherstellen, dass die E-Mail-Adressen, die Sie verwenden möchten, mit dem [!DNL SHA256] -Algorithmus gehasht werden. Andernfalls können Sie sie nicht in [!UICONTROL People-Based Destinations] verwenden.

## Daten-Hashing im Vergleich zur Verschlüsselung {#data-hashing-encryption}

Die Verschlüsselung ist eine bidirektionale Funktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Die Verschlüsselung von Daten im Kontext des Audience Managers birgt ernsthafte Risiken, da jede verschlüsselte Form von personenbezogenen Daten auch entschlüsselt werden kann. Im Gegensatz zur Verschlüsselung sind [!UICONTROL People-Based Destinations] stattdessen für die Verwendung mit Hash-Daten konzipiert.

Hashing ist eine unidirektionale Funktion, die die Eingabe verwirft, um ein eindeutiges Ergebnis zu erzielen. Durch die Verwendung richtiger Hashing-Algorithmen wie [!DNL SHA256] gibt es keine Möglichkeit, die Hashing-Funktion umzukehren und die nicht verschachtelten Informationen anzuzeigen. Die E-Mail-Adressen, die Sie an Audience Manager senden, müssen mit dem Algorithmus [!DNL SHA256] gehasht werden. Auf diese Weise können Sie sicherstellen, dass keine ungehashten E-Mail-Adressen Audience Manager erreichen.

## Hashanforderungen {#hashing-requirements}

Achten Sie beim Hashing der E-Mail-Adressen auf die folgenden Anforderungen:

* Entfernen Sie alle Leerzeichen am Anfang und am Ende der E-Mail-Zeichenfolge. Beispiel: `johndoe@example.com`, nicht `<space>johndoe@example.com<space>`;
* Achten Sie beim Hashing der E-Mail-Zeichenfolgen darauf, die Zeichenfolge in Kleinbuchstaben zu hash;
   * Beispiel: `example@email.com`, nicht `EXAMPLE@EMAIL.COM`;
* Stellen Sie sicher, dass der Hash-String nur in Kleinbuchstaben geschrieben wird.
   * Beispiel: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, nicht `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Salz die Zeichenfolge nicht.

Sehen Sie sich das folgende Video an, um die Hashing-Anforderungen von [!UICONTROL People-Based Destinations] zu verstehen.

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud bietet Ihnen die Möglichkeit, Kunden-IDs über die [!DNL Adobe Experience Platform Identity Service (ECID)] zu hash. Detaillierte Informationen zur Verwendung von ECID zum Hash von Kunden-IDs finden Sie unter [SHA256-Hashing-Unterstützung für setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) .

## Abrufen von Benutzerberechtigungen {#obtaining-user-permission}

Da [!UICONTROL People-Based Destinations] Ihnen dabei hilft, Erstanbieter-Zielgruppendaten in personenbasierten Kanälen zu aktivieren, ist es Ihre Verantwortung, Ihre Kunden über die Verwendung ihrer Daten für Werbung oder andere Zwecke zu informieren und die nötigen Einverständnisse zu erhalten.

Bevor Sie sich für [!UICONTROL People-Based Destinations] registrieren, müssen Sie die Zustimmung Ihrer Kunden einholen, bevor Sie deren Informationen für Werbezwecke verwenden.

Falls Ihre Kunden Werbekampagnen abwählen möchten, finden Sie unter [Opt-out-Verwaltung](../../overview/data-security-and-privacy/data-privacy-requests.md) weitere Informationen dazu, wie Sie verhindern können, dass Audience Manager Daten weiter erfassen.

## Erstanbieterdatenaktivierung forcieren {#enforcing-first-party-activation}

Bei Verwendung von [!UICONTROL People-Based Destinations] können Sie Erstanbieterdaten nur verwenden, um Zielgruppensegmente in benutzerbezogenen Kanälen zu aktivieren. Sie können keine Zweit- oder Drittanbieterdaten für die Aktivierung von Zielgruppen in benutzerbezogenen Kanälen verwenden.

Verwenden Sie bei Verwendung von [!UICONTROL People-Based Destinations] [Datenexportkontrollen](../data-export-controls.md) , um Ihre [!UICONTROL data sources] und [!UICONTROL destinations] gemäß den Richtlinien und Anforderungen von Zielplattformen und Datenanbietern zu beschriften.

## Integrierte authentifizierte Hash-IDs über deklariertes ID-Targeting {#onboard-authenticated-declared-id}

Es gibt zwei Möglichkeiten, Ihre Offline-Daten für [!UICONTROL People-Based Destinations] in Audience Manager zu laden.

* [ Batch-Daten senden](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an Audience Manager, um Hash-E-Mail-Adressen zu erfassen. Bei dieser Methode können Sie die Hash-E-Mail-Adressen aus Ihrer [!DNL CRM]-Datenbank in [!UICONTROL People-Based Destinations] verwenden. Bei Verwendung dieser Methode können Sie außerdem die Hash-E-Mail-Adressen für [integrierte Eigenschaften](../traits/trait-and-segment-qualification-reference.md) qualifizieren.
* Verwenden Sie [Declared IDs](../declared-ids.md) , um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode sendet Audience Manager in Ihrem Namen nur die Hash-E-Mail-Adressen von Benutzern, die sich online authentifiziert haben, an [!UICONTROL People-Based Destinations]. Die E-Mail-Adressen, die über benutzerbasierte Kanäle aktiviert werden, sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit gesendet.

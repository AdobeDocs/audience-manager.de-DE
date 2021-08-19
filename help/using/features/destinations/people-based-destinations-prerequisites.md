---
description: 'Unten finden Sie eine Übersicht über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für personenbasierte Ziele registrieren.  '
seo-description: 'Unten finden Sie eine Übersicht über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für personenbasierte Ziele registrieren.  '
seo-title: Voraussetzungen und Überlegungen für benutzerbasierte Ziele
solution: Audience Manager
title: Voraussetzungen und Überlegungen
feature: Benutzerbasierte Ziele
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1013'
ht-degree: 3%

---

# Voraussetzungen und Überlegungen {#prerequisites-considerations}

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

Unten finden Sie eine Übersicht über die Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für [!UICONTROL People-Based Destinations] registrieren.

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

## Anmeldung für [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] ist eine Premium-Funktion, mit der Sie Ihr Kundenerlebnis verbessern können, indem Sie Ihre Erstanbieter-Zielgruppensegmente in benutzerbezogenen Umgebungen aktivieren, indem Sie Ihre Zielgruppe mit benutzerdefinierten Angeboten in sozialen Netzwerken oder per E-Mail-Marketing ansprechen.

Wenden Sie sich an Ihren Kundenbetreuer, um von dieser Premium-Funktion profitieren zu können.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Ihre Erstanbieter-Audience [!UICONTROL segments] an [!DNL Facebook] zu senden, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Für Ihr [!DNL Facebook]-Benutzerkonto muss die Berechtigung **Kampagnen verwalten** für das Werbekonto aktiviert sein, das Sie verwenden möchten.
2. Fügen Sie das Geschäftskonto **Adobe Experience Cloud** als Werbepartner in Ihrem [!DNL Facebook Ad Account] hinzu. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter [Partner zu Ihrem Business Manager hinzufügen](https://www.facebook.com/business/help/1717412048538897) .
   >[!IMPORTANT]
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung **Kampagnen verwalten** aktivieren. Dies ist für die Integration von [!UICONTROL People-Based Destinations] erforderlich.
3. Lesen und unterschreiben Sie die [!DNL Facebook Custom Audiences]-Nutzungsbedingungen. Gehen Sie dazu zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wobei `accountID` Ihre [!DNL Facebook Ad Account ID] ist.

### [!DNL LinkedIn] {#linkedin}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Ihre Erstanbieter-Zielgruppensegmente an [!DNL LinkedIn] zu senden, stellen Sie sicher, dass Ihr [!DNL LinkedIn Campaign Manager]-Konto über die Berechtigungsebene [!DNL Creative Manager] oder höher verfügt.

Informationen zum Bearbeiten Ihrer [!DNL LinkedIn Campaign Manager]-Benutzerberechtigungen finden Sie unter [Hinzufügen, Bearbeiten und Entfernen von Benutzerberechtigungen für Werbekonten](https://www.linkedin.com/help/lms/answer/5753) in der LinkedIn-Dokumentation.

Videoanleitungen finden Sie unter [Grundlegendes zum und Konfigurieren des personenbasierten LinkedIn-Ziels](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html).

### [!DNL Google Customer Match] {#gcm}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Ihre Erstanbieter-Zielgruppensegmente an ein [!DNL Google Customer Match]-Ziel zu senden, müssen Sie [!DNL Google] zur Zulassungsliste hinzufügen.

Wenden Sie sich an Ihren [!DNL Google]-Support-Mitarbeiter und befolgen Sie die Anweisungen zur Zulassungsliste, die in der [Verwenden Sie Partner für Kundenabgleich, um Ihre Daten hochzuladen](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google] -Dokumentation beschrieben sind.

Nach Abschluss dieses Vorgangs können Sie [!UICONTROL People-Based Destination] erstellen.

## Datenintegration {#data-onboarding}

Die Datenerfassung für [!UICONTROL People-Based Destinations] unterstützt derzeit bis zu 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID ([!DNL CRM ID]) verknüpft sind, pro Batch-Übertragung. Das Hochladen von mehr als 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID verknüpft sind, führt dazu, dass der Audience Manager 10 davon in beliebiger Reihenfolge aufnimmt.

Durch das Hochladen von mehr als 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID verknüpft sind, bei mehreren Batch-Übertragungen behält der Audience Manager die letzten 10 hinzugefügten E-Mail-Adressen bei.

## Datenschutz {#data-privacy}

Obwohl Sie mit [!UICONTROL People-Based Destinations] Zielgruppen auf der Basis von von Ihnen hochgeladenen Hash-E-Mail-Adressen ansprechen können, ist es Ihnen auch weiterhin untersagt, direkt identifizierbare Besucherinformationen in Audience Manager hochzuladen. In der Phase des Daten-Onboarding müssen Sie sicherstellen, dass die E-Mail-Adressen, die Sie verwenden möchten, mit dem [!DNL SHA256]-Algorithmus gehasht werden. Andernfalls können Sie sie nicht in [!UICONTROL People-Based Destinations] verwenden.

## Daten-Hashing im Vergleich zur Verschlüsselung {#data-hashing-encryption}

Die Verschlüsselung ist eine bidirektionale Funktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Die Verschlüsselung von Daten im Kontext des Audience Managers birgt ernsthafte Risiken, da jede verschlüsselte Form von personenbezogenen Daten auch entschlüsselt werden kann. Im Gegensatz zur Verschlüsselung sind [!UICONTROL People-Based Destinations] stattdessen für die Verwendung mit Hash-Daten konzipiert.

Hashing ist eine unidirektionale Funktion, die die Eingabe verwirft, um ein eindeutiges Ergebnis zu erzielen. Wenn Sie geeignete Hashing-Algorithmen wie [!DNL SHA256] verwenden, gibt es keine Möglichkeit, die Hashing-Funktion umzukehren und die nicht verschachtelten Informationen anzuzeigen. Die E-Mail-Adressen, die Sie an Audience Manager senden, müssen mit dem [!DNL SHA256]-Algorithmus gehasht werden. Auf diese Weise können Sie sicherstellen, dass keine ungehashten E-Mail-Adressen Audience Manager erreichen.

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

Adobe Experience Cloud bietet Ihnen die Möglichkeit, Kunden-IDs über [!DNL Adobe Experience Platform Identity Service (ECID)] zu hash. Detaillierte Informationen zur Verwendung von ECID zum Hash von Kunden-IDs finden Sie unter [SHA256-Hashing-Unterstützung für setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) .

## Abrufen von Benutzerberechtigungen {#obtaining-user-permission}

Da [!UICONTROL People-Based Destinations] Ihnen dabei hilft, Erstanbieter-Zielgruppendaten in personenbasierten Kanälen zu aktivieren, ist es in Ihrer Verantwortung, Ihre Kunden über die Verwendung ihrer Daten zu Werbezwecken oder zu anderen Zwecken zu informieren und die nötigen Einverständnisse zu erhalten.

Bevor Sie sich für [!UICONTROL People-Based Destinations] registrieren, vergewissern Sie sich, dass Sie die Zustimmung Ihrer Kunden einholen, bevor Sie deren Informationen für Werbezwecke verwenden.

Falls Ihre Kunden Werbekampagnen abwählen möchten, finden Sie unter [Opt-out-Verwaltung](../../overview/data-security-and-privacy/data-privacy-requests.md) weitere Informationen dazu, wie Sie verhindern können, dass Audience Manager Daten erfassen.

## Erstanbieterdatenaktivierung forcieren {#enforcing-first-party-activation}

Bei Verwendung von [!UICONTROL People-Based Destinations] können Sie Erstanbieterdaten nur verwenden, um Zielgruppensegmente in benutzerbezogenen Kanälen zu aktivieren. Sie können keine Zweit- oder Drittanbieterdaten für die Aktivierung von Zielgruppen in benutzerbezogenen Kanälen verwenden.

Verwenden Sie bei Verwendung von [!UICONTROL People-Based Destinations] [Datenexportkontrollen](../data-export-controls.md), um Ihre [!UICONTROL data sources] und [!UICONTROL destinations] gemäß den Richtlinien und Anforderungen von Zielplattformen und Datenanbietern zu beschriften.

## Integrierte authentifizierte Hash-IDs über deklariertes ID-Targeting {#onboard-authenticated-declared-id}

Es gibt zwei Möglichkeiten, Ihre Offline-Daten für [!UICONTROL People-Based Destinations] in Audience Manager zu laden.

* [Senden Sie Batch-](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Daten an den Audience Manager, um Hash-E-Mail-Adressen zu erfassen. Bei dieser Methode können Sie die Hash-E-Mail-Adressen aus Ihrer [!DNL CRM]-Datenbank in [!UICONTROL People-Based Destinations] verwenden. Bei Verwendung dieser Methode können Sie außerdem die Hash-E-Mail-Adressen für [integrierte Eigenschaften](../traits/trait-and-segment-qualification-reference.md) qualifizieren.
* Verwenden Sie [Declared IDs](../declared-ids.md), um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode sendet der Audience Manager in Ihrem Namen nur an [!UICONTROL People-Based Destinations] die Hash-E-Mail-Adressen von Benutzern, die sich online authentifiziert haben. Die E-Mail-Adressen, die über benutzerbasierte Kanäle aktiviert werden, sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit gesendet.

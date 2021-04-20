---
description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-description: 'Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für "People-Based Destination"registrieren.  '
seo-title: Voraussetzungen und Erwägungen für benutzerspezifische Ziele
solution: Audience Manager
title: Voraussetzungen und Überlegungen
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 3%

---

# Voraussetzungen und Überlegungen {#prerequisites-considerations}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Nachfolgend finden Sie eine Übersicht der Kundenanforderungen, die Sie erfüllen müssen, bevor Sie sich für [!UICONTROL People-Based Destinations] registrieren.

>[!IMPORTANT]
> Lesen Sie diesen Artikel sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

## Anmelden für [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] ist eine Premium-Funktion, mit der Sie Ihre Audience Manager besser ansprechen können, indem Sie Erstanbieter-Audiencen in personalisierten Umgebung aktivieren, Ihre Audience auf benutzerdefinierte Angebot in sozialen Netzwerken oder über E-Mail-Marketing ausrichten können.

Wenden Sie sich an Ihren Kundenbetreuer, um diese Premium-Funktion nutzen zu können.

## Partnerspezifische Voraussetzungen {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Ihre Erstanbieter-Audience [!UICONTROL segments] an [!DNL Facebook] zu senden, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Für Ihr [!DNL Facebook]-Benutzerkonto muss die Berechtigung **Kampagnen verwalten** für das Anzeigenkonto aktiviert sein, das Sie verwenden möchten.
2. hinzufügen Sie das Geschäftskonto **Adobe Experience Cloud** als Werbepartner in Ihrem [!DNL Facebook Ad Account]. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter [Hinzufügen Partner in Ihrem Business Manager](https://www.facebook.com/business/help/1717412048538897).
   >[!IMPORTANT]
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung **Kampagnen verwalten** aktivieren. Dies ist für die Integration von [!UICONTROL People-Based Destinations] erforderlich.
3. Lesen und unterzeichnen Sie die [!DNL Facebook Custom Audiences]-Nutzungsbedingungen. Gehen Sie dazu zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wobei `accountID` Ihre [!DNL Facebook Ad Account ID] ist.

### [!DNL LinkedIn] {#linkedin}

Bevor Sie [!UICONTROL People-Based Destinations] verwenden können, um Erstanbieter-Audiencen an [!DNL LinkedIn] zu senden, stellen Sie sicher, dass Ihr [!DNL LinkedIn Campaign Manager]-Konto die [!DNL Creative Manager]- oder eine höhere Berechtigungsstufe aufweist.

Informationen zum Bearbeiten Ihrer [!DNL LinkedIn Campaign Manager]-Benutzerberechtigungen finden Sie unter [Hinzufügen, Bearbeiten und Entfernen von Benutzerberechtigungen für Werbekonten](https://www.linkedin.com/help/lms/answer/5753) in der LinkedIn-Dokumentation.

Videoanweisungen finden Sie unter [Das benutzerbasierte LinkedIn-Ziel](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) verstehen und konfigurieren.

### [!DNL Google Customer Match] {#gcm}

Bevor Sie mit [!UICONTROL People-Based Destinations] Erstanbieter-Audiencen an ein [!DNL Google Customer Match]-Ziel senden können, müssen Sie [!DNL Google] zur Zulassungsliste hinzufügen.

Wenden Sie sich an Ihren [!DNL Google]-Kundenbetreuer und befolgen Sie die Anweisungen zur Zulassungsliste, die Sie in der [Benutzen Sie Kunden-Match-Partner, um Ihre Daten](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google] hochzuladen.

Nach Abschluss dieses Prozesses können Sie [!UICONTROL People-Based Destination] erstellen.

## Datenintegration {#data-onboarding}

Die Datenerfassung für [!UICONTROL People-Based Destinations] unterstützt derzeit bis zu 10 Hash-E-Mail-Adressen, die mit einer Kunden-ID ([!DNL CRM ID]) pro Batch-Übertragung verknüpft sind. Durch das Hochladen von mehr als 10 mit einer Kunden-ID verknüpften Hash-E-Mail-Adressen werden 10 davon von Audience Manager in beliebiger Reihenfolge aufgenommen.

Beim Hochladen von mehr als 10 mit einer Kunden-ID verknüpften Hash-E-Mail-Adressen in mehreren Batch-Übertragungen behält der Audience Manager die letzten 10 hinzugefügten E-Mail-Adressen bei.

## Datenschutz {#data-privacy}

Auch wenn [!UICONTROL People-Based Destinations] Ihnen die Zielgruppe von Audiencen auf der Grundlage von von Ihnen hochgeladenen Hash-E-Mail-Adressen erlaubt, ist es Ihnen weiterhin untersagt, direkt identifizierbare Besucher-Informationen in Audience Manager hochzuladen. In der Phase der Dateneingabe müssen Sie sicherstellen, dass die zu verwendenden E-Mail-Adressen mit dem Algorithmus [!DNL SHA256] gehasht werden. Andernfalls können Sie sie nicht in [!UICONTROL People-Based Destinations] verwenden.

## Daten-Hashing im Vergleich zur Verschlüsselung {#data-hashing-encryption}

Verschlüsselung ist eine Zweiwegefunktion. Alle verschlüsselten Informationen können auch mit dem richtigen Entschlüsselungsschlüssel entschlüsselt werden. Das Verschlüsseln von Daten im Zusammenhang mit Audience Managern stellt eine ernsthafte Gefahr dar, da jede verschlüsselte Form von personenbezogenen Daten auch entschlüsselt werden kann. Im Gegensatz zur Verschlüsselung sind [!UICONTROL People-Based Destinations] für die Verwendung mit Hashdaten konzipiert.

Hashing ist eine Einwegfunktion, die die Eingabe verwirft, um ein einzigartiges Ergebnis zu erzielen. Wenn Sie geeignete Hashing-Algorithmen wie [!DNL SHA256] verwenden, gibt es keine Möglichkeit, die Hashing-Funktion umzukehren und die nicht verschachtelten Informationen anzuzeigen. Die E-Mail-Adressen, die Sie an Audience Manager binden, müssen mit dem [!DNL SHA256]-Algorithmus Hashing durchgeführt werden. Auf diese Weise können Sie sicherstellen, dass keine entsperrten E-Mail-Adressen Audience Manager erreichen.

## Hashanforderungen {#hashing-requirements}

Achten Sie beim Hashing der E-Mail-Adressen auf die Einhaltung der folgenden Anforderungen:

* Entfernen Sie alle führenden und nachfolgenden Leerzeichen aus der E-Mail-Zeichenfolge. example: `johndoe@example.com`, nicht `<space>johndoe@example.com<space>`;
* Achten Sie beim Hashing der E-Mail-Zeichenfolgen darauf, die Zeichenfolge in Kleinbuchstaben mit Hash zu versehen.
   * Beispiel: `example@email.com`, nicht `EXAMPLE@EMAIL.COM`;
* Stellen Sie sicher, dass die Hash-Zeichenfolge nur in Kleinbuchstaben angegeben wird
   * Beispiel: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, nicht `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Salt die Zeichenfolge nicht.

Sehen Sie sich das folgende Video an, um die Hashing-Anforderungen von [!UICONTROL People-Based Destinations] zu verstehen.

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud bietet Ihnen die Möglichkeit, Kunden-IDs über das [!DNL Adobe Experience Platform Identity Service (ECID)] zu hash. Detaillierte Informationen zur Verwendung von ECID zum Hash von Kunden-IDs finden Sie unter [SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html).

## Abrufen der Benutzerberechtigung {#obtaining-user-permission}

Da [!UICONTROL People-Based Destinations] Ihnen bei der Aktivierung von Erstanbieter-Audience-Daten in personalisierten Kanälen hilft, ist es Ihre Verantwortung, Ihre Kunden darüber zu informieren und die erforderlichen Einwilligungen zu erhalten, wie Sie ihre Daten für Werbezwecke oder andere Zwecke verwenden werden.

Bevor Sie sich für [!UICONTROL People-Based Destinations] registrieren, müssen Sie die Zustimmung Ihrer Kunden einholen, bevor Sie deren Informationen für Werbezwecke verwenden.

Wenn Ihre Kunden Werbemaßnahmen ablehnen möchten, finden Sie unter [Opt-out-Kampagne](../../overview/data-security-and-privacy/data-privacy-requests.md) weitere Informationen dazu, wie Audience Manager daran gehindert werden können, Daten zu erfassen.

## Aktivierung von Erstanbieter-Daten {#enforcing-first-party-activation} erzwingen

Bei Verwendung von [!UICONTROL People-Based Destinations] können Sie Erstanbieterdaten nur verwenden, um Audiencen in benutzerbasierten Kanälen zu aktivieren. Sie können keine Daten von Drittanbietern zur Aktivierung der Audience in benutzerbasierten Kanälen verwenden.

Verwenden Sie bei Verwendung von [!UICONTROL People-Based Destinations] [Datenexportsteuerelemente](../data-export-controls.md), um Ihre [!UICONTROL data sources] und [!UICONTROL destinations] gemäß den Richtlinien und Anforderungen von Zielplattformen und Datenanbietern zu kennzeichnen.

## Integrierte authentifizierte Hash-IDs mit deklariertem ID-Targeting {#onboard-authenticated-declared-id}

Es gibt zwei Möglichkeiten, Ihre Offline-Daten für [!UICONTROL People-Based Destinations] in Audience Manager zu laden.

* [Senden Sie ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) den Batch-Datato-Audience Manager an die Erfassung von Hash-E-Mail-Adressen. Bei dieser Methode können Sie die Hash-E-Mail-Adressen aus Ihrer [!DNL CRM]-Datenbank in [!UICONTROL People-Based Destinations] verwenden. Bei Verwendung dieser Methode können Sie außerdem die Hash-E-Mail-Adressen für [onboarded-Eigenschaften](../traits/trait-and-segment-qualification-reference.md) qualifizieren.
* Verwenden Sie [Deklarierte IDs](../declared-ids.md), um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode sendet Audience Manager in Ihrem Namen nur an [!UICONTROL People-Based Destinations] die Hash-E-Mail-Adressen von Benutzern, die sich online authentifiziert haben. Die E-Mail-Adressen, die über benutzerbasierte Kanal aktiviert werden, sind nur die Adressen in den deklarierten ID-Ereignis-Aufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit gesendet.

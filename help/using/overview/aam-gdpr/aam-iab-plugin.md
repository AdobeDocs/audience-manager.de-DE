---
description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-title: Audience Manager Plug-In für IAB TCF
solution: Audience Manager
title: Audience Manager Plug-In für IAB TCF
translation-type: tm+mt
source-git-commit: 0e32fcaee617e7f18ce4223ffacc39708fb32786

---


# Audience Manager Plug-In für IAB TCF {#aam-iab-plugin}

## Überblick

Ein wichtiger Aspekt der Datenschutzverpflichtungen, die Sie gegenüber Ihren Anwendern haben, ist die Akquise und Übermittlung von Benutzerentscheidungen darüber, wie ihre personenbezogenen Daten verwendet werden dürfen (d. h. „Zwecke“) und von wem (d. h. „Unternehmen“).

Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die [Opt-in-Funktion](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) und die Unterstützung des [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) zu verwalten und zu übermitteln.

Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren. Audience Manager wird in der IAB-TCF mit der Anbieter-ID 565 registriert.

The Audience Manager Plug-in for IAB TCF utilizes the [Opt-in functionality](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), which is, in turn, part of the Adobe [Experience Cloud ID Service (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) library.

## Scope and Limitations {#scope-and-limitations}

Als Herausgeber oder Advertiser, die mit Audience Manager arbeiten, können Sie Benutzerentscheidungen nach IAB TCF an Audience Manager senden. Auf diese Weise erhalten Sie eine einfache und konsistente Möglichkeit, Benutzerentscheidungen an alle Partner zu senden, mit denen Sie arbeiten, und Audience Manager kann Ihnen dabei helfen, die Datenschutzentscheidungen Ihrer Benutzer zu respektieren.

Die in diesem Artikel beschriebene IAB-TCF-Unterstützung stellt die erste Phase in der geplanten Unterstützung des Audience Manager für das IAB-Framework dar. Audience Manager unterstützt derzeit nicht:

* Arbeitsabläufe für Mobilgeräte;
* Geräteübergreifende Genehmigungsverwaltung;
* Appending consent to URLs sent to [URL destinations](/help/using/features/destinations/manage-destinations.md#configure-url-destination);
* Anhängen der Zustimmung zu Segmenten.

## Voraussetzungen {#prerequisites}

Sie müssen die folgenden Voraussetzungen erfüllen, um das IAB-TCF mit Audience Manager zu verwenden:

1. Sie müssen die Experience Cloud ID-Dienst-Version 4.1 oder höher verwenden. [Laden Sie](https://github.com/Adobe-Marketing-Cloud/id-service/releases) unsere aktuelle ECID-Version herunter.
2. 
   1. You must be using Audience Manager Data Integration Library (DIL) version 9.0 or newer, downloadable from [here](https://github.com/Adobe-Marketing-Cloud/dil/releases). Read about [DIL in the Audience Manager documentation](/help/using/dil/dil-overview.md).
   2. Wenn Sie die Daten mit serverseitiger Weiterleitung (SSF) in Audience Manager importieren, müssen Sie auch auf die neueste Version von appmeasurement aktualisieren. Download AppMeasurement using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
3. Sie müssen eine CMP (Approval Management Platform) verwenden, entweder kommerzielle oder eigene, die IAB unterstützt und bei der IAB-TCF registriert ist. See the list of [CMPs registered within the IAB framework](https://advertisingconsent.eu/cmp-list/).

## Recommendations and how to implement {#recommendations}

To enable the IAB TCF support in Audience Manager, read our documentation on [how to set up IAB with Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

This is easiest done by using [Adobe Launch](https://docs.adobelaunch.com/) to instrument ECID Opt-in on your properties. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## User choice workflow when using the IAB framework {#user-choice-workflow}

Wenn Sie eine Webeigenschaft besuchen, können Ihre Benutzer ihre Wahl darüber bereitstellen, wie ihre Daten vom Herausgeber und von den Drittanbietern, mit denen der Herausgeber arbeitet, verwendet werden. Users provide their choices in the form of *standard purposes* and permissions to *third-party vendors* registered in the global vendor list. Die unten stehende Abbildung stellt ein Beispiel eines CMP-Dialogs dar, der einem erstmaligen Besucher einer Website angezeigt wird. Beachten Sie, dass dieser Dialog aufgrund der Kundenimplementierung sehr unterschiedlich aussehen kann.

![CMP-Dialog](/help/using/overview/aam-gdpr/assets/cmp.png)

Die Standardziele im IAB-Framework sind:

* Informationsspeicherung und -zugriff
* Personalisierung
* Anzeigenauswahl, Auslieferung und Berichterstellung
* Inhaltsauswahl, Bereitstellung und Berichterstellung
* Videoinformationen

Refer to the [IAB framework specification page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) for a description of the five standard purposes.

Benutzer können ihre Zustimmung für eine Kombination aus Standardzielen und Anbietern erteilen. Beispielsweise können Benutzer ihre Zustimmung zu Speicher, Personalisierung und Messung erteilen und ihre Zustimmung für alle Drittanbieter, die von CMP angezeigt werden, genehmigen. In einem anderen Beispiel könnten sie ihre Zustimmung zu allen fünf Standardzwecken erteilen, aber nur einigen der durch CMP angezeigten Anbieter zustimmen.

Sobald der Benutzer seine Datenschutzoptionen auswählt, werden die Auswahlmöglichkeiten der Benutzer in der IAB-TCF-Genehmigungszeichenfolge aufgezeichnet. The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the [IAB page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) for more information). Jeder im IAB registrierte Anbieter wertet die IAB-TCF-Genehmigungszeichenfolge aus und trifft Entscheidungen auf der Grundlage der Datenschutzeinstellungen der Benutzer. Denken Sie daran, dass die Datenschutzeinstellungen der Benutzer für alle zugelassenen Anbieter gültig sind.

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

Audience Manager bewertet die in der IAB-TFC-Zeichenfolge gespeicherten Optionen für Folgendes:

* Information storage and access (purpose ID 1 in the [global vendor list](https://vendorlist.consensu.org/vendorlist.json))
* Personalisierung (Zweck-ID 2)
* Messung (Zweck-ID 5)
* Audience Manager-Anbieter zur Speicherung, Verarbeitung oder Aktivierung von Daten für einen Herausgeber.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

Audience Manager funktioniert unterschiedlich, je nachdem, ob Audience Manager in der IAB-Genehmigungszeichenfolge erkennt, dass der Benutzer die Zustimmung zu den drei Zwecken (Speicherung, Personalisierung, Messung) angegeben hat.

| When your user *provides consent*, Audience Manager: | When your user *declines* consent, Audience Manager: |
|---|---|
| <ul><li>Führt alle von Ihnen angeforderten Anwendungsfälle von Audience Manager aus.</li><li>Überträgt die Zustimmung zu Dritten in ID-Synchronisierungen (indem gdpr = 1 und die Bestätigungszeichenfolge als gdpr_ consent bei ID-Synchronisationsaufrufen übergeben werden).</li><li>Wertet die Zustimmung aus, die von den Anzeigenserverpixeln übergeben wurde, und berücksichtigt diese.</li><li>Berücksichtigt die von Partnern initiierten ID-Synchronisierungen.</li></ul> | <ul><li>Speichert keine neuen Benutzerdaten in Ihrer Instanz. Dazu gehören Partner-IDs, Signale, Eigenschaften oder Pixeldaten.</li><li>Startet keine Drittanbieter-ID-Synchronisierung.</li><li>Die vom Partner initiierten ID-Synchronisierungen werden nicht berücksichtigt.</li></ul> |



## Publisher Use Case {#publisher-use-case}

Durch die Implementierung des TCF sind Sie nicht verpflichtet, benutzerdefinierten Code für die Genehmigungsverwaltung in Ihren Webeigenschaften über einen anderen Mechanismus mit Adobe oder anderen Drittanbietern zu verwalten. Der Verwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginnen Sie links vom Bild:

1. Ein Benutzer besucht eine Ihrer Webeigenschaften. As long as you are using the latest versions of the ECID and DIL libraries (see [Prerequisites](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), the opt-in flow is triggered.
2. Audience Manager checks whether the IAB flow applies (`isIabContext=true`). See [Recommendations and how to implement](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager checks whether GDPR applies (`gdpr = 1`) and whether there is a CMP, registered with IAB, on your web property. Dies würde beispielsweise für Benutzer gelten, die aus dem Bereich der europäischen Union besuchen. Beachten Sie, dass Sie als Herausgeber das GDPR-Flag festlegen.
4. If GDPR applies, Audience Manager checks the IAB TCF consent string, passed in the parameter `gdpr_consent`, for the needed permissions. Audience Manager benötigt Berechtigungen für Speicher, Personalisierung, Messung, einschließlich der Zustimmung des Audience Manager-Anbieters, um Daten zu speichern, zu verarbeiten oder zu aktivieren.
5. If the IAB TCF consent string is present and it contains the required permissions, Audience Manager passes the IAB TCF consent string on to our [data collection servers](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager responds by setting a [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) on the browser. Audience Manager initiiert und berücksichtigt auch die Synchronisierung von Drittanbieter-Ids.
7. Wenn die in Schritt 5 übergebene IAB-TCF-Zeichenfolge nicht alle erforderlichen Berechtigungen enthält, erfasst Audience Manager keine Daten, verarbeitet oder aktivieren keine Daten und ignoriert oder startet keine ID-Synchronisierungen.

![Verwendungsfall für Herausgeber](assets/publisher-use-case.png)

## Advertiser Use Case {#advertiser-use-case}

Audience Manager evaluates and honors consent passed in [pixel calls](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), in accordance with the IAB TCF.

Pixel werden im Allgemeinen von Audience Manager-Kunden auf ihren Partnerseiten platziert oder sie werden in Anzeigenservern platziert, um sie in die Werbeantwort einzuschließen. Im ersten Fall muss Ihr Partner den Parameter zur Bestätigung programmatisch abrufen und ihn vor dem Auslösen dem Pixel hinzufügen. Im zweiten Fall, der häufiger und im Folgenden detailliert beschrieben wird, hängen Anzeigenserver die Zustimmungsparameter an, die sie von den angebotsseitigen Plattformen (SSP) oder den Anzeigen-Servern für alle Pixel empfangen.

Audience Manager verwendet zwei Parameter, um die Benutzerzustimmung in Pixelaufrufe zu übergeben:

* `gdpr` kann 0 (GDPR nicht angewendet) oder 1 (GDPR angewendet) sein;
* `gdpr_consent` ist die URL-sichere Base 64-kodierte GDPR-Zeichenfolge (siehe [Spezifikation](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Ein Beispielaufruf für ein Impression-Pixel, wobei die beiden Parameter wie folgt aussehen könnten:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Der Verwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginnen Sie links vom Bild:

1. Ihr Benutzer wird über einen Anzeigenserver impressionen. Dies erfolgt in einen Pixelaufruf an unsere Data Collection Server (DCS).
1. Audience Manager überprüft, ob das GDPR-Flag angewendet wird. Wenn dies nicht der Fall ist, speichert Audience Manager die in den Makrovariablen übergebenen Daten in Pixelaufrufen.
1. Wenn die Genehmigungszeichenfolge vorhanden ist und die erforderlichen Berechtigungen enthält, speichert Audience Manager die in den Makrovariablen übergebenen Daten in Pixelaufrufen.
1. Wenn die Genehmigungszeichenfolge fehlt oder die erforderlichen Berechtigungen fehlt, legt Audience Manager die Daten ab, die in Pixelaufrufen in den Makrovariablen übergeben wurden.

![Verwendungsfall für Advertiser](assets/advertiser-use-case.png)

## Activation partners that support IAB TCF {#aam-activation-partners}

Mit dem Audience Manager-Plugin für IAB können Sie die IAB-TCF-Genehmigungszeichenfolge an Aktivierungspartner weiterleiten und die Datenschutzmöglichkeiten der Benutzer einhalten. For information on which activation partners support IAB TCF (accurate as of July 7th, 2019), refer to our **[Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**.

## Test your IAB implementation {#test-iab-implementation}

To test that you have correctly implemented the Audience Manager Plug-in for IAB TCF, read [Use Case 4 in Validation Methods for Opt-in and IAB implementation](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## IAB und Opt-out in Audience Manager. Order of precedence. {#iab-and-optout}

Eine weitere Datenschutzoption für den Benutzer ist die Möglichkeit, die Datenerfassung auszuschließen. Adobe provides users with the means to do so within the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page.

Audience Manager addresses opt-out management in a [separate article in our documentation](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Reihenfolge der Priorität** : Wenn der Benutzer die Datenerfassung mithilfe eines globalen Abmeldungswerkzeugs abmeldet, wie im obigen Link beschrieben, hat dies Vorrang vor den Überprüfungen für Teilnahme und IAB.

## Zusätzliche Ressourcen {#additional-resources}

* [Experience Cloud ID-Dienst-Teilnahme](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR Transparency and Approval Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Technische Spezifikationen für IAB Europe GDPR Transparency and Approval Framework](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-Plugin - Videodemonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
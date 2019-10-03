---
description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-title: Audience Manager Plug-In für IAB TCF
solution: Audience Manager
title: Audience Manager Plug-In für IAB TCF
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# Audience Manager Plug-In für IAB TCF {#aam-iab-plugin}

## Überblick

Ein wichtiger Aspekt der Datenschutzverpflichtungen, die Sie gegenüber Ihren Anwendern haben, ist die Akquise und Übermittlung von Benutzerentscheidungen darüber, wie ihre personenbezogenen Daten verwendet werden dürfen (d. h. „Zwecke“) und von wem (d. h. „Unternehmen“).

Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die [Opt-in-Funktion](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) und die Unterstützung des [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) zu verwalten und zu übermitteln.

Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren. Audience Manager is registered in the IAB TCF with the vendor ID 565.

The Audience Manager Plug-in for IAB TCF utilizes the Opt-in functionality, which is, in turn, part of the Adobe Experience Cloud ID Service (ECID) library.[](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)[](https://marketing.adobe.com/resources/help/en_US/mcvid/)

## Scope and Limitations {#scope-and-limitations}

As a Publisher or Advertiser working with Audience Manager, you are able to convey user choices to Audience Manager as per IAB TCF. Dadurch erhalten Sie eine einfache und konsistente Möglichkeit, allen Partnern, mit denen Sie arbeiten, Benutzeroptionen mitzuteilen. Audience Manager kann Ihnen dabei helfen, die Datenschutzentscheidungen Ihrer Benutzer zu respektieren.

Die in diesem Artikel beschriebene Unterstützung der IAB-TCF stellt die erste Phase der geplanten Unterstützung des IAB-Rahmens durch Audience Manager dar. Derzeit unterstützt Audience Manager nicht:

* Arbeitsabläufe für Mobilgeräte
* geräteübergreifende Verwaltung der Zustimmung;
* Beifügen der Zustimmung zu URLs, die an [URL-Ziele](/help/using/features/destinations/create-url-destination.md)gesendet werden;
* An Segmente anhängen.

## Voraussetzungen {#prerequisites}

Sie müssen die folgenden Voraussetzungen erfüllen, um die IAB-TCF mit Audience Manager verwenden zu können:

1. Sie müssen Experience Cloud ID-Dienst (ECID) Version 4.1 oder höher verwenden. [Laden Sie](https://github.com/Adobe-Marketing-Cloud/id-service/releases) unsere neueste ECID-Version herunter.
2. 
   1. Sie müssen Audience Manager Data Integration Library (DIL) Version 9.0 oder neuer verwenden, die [hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)heruntergeladen werden kann. Lesen Sie mehr über [DIL in der Audience Manager-Dokumentation](/help/using/dil/dil-overview.md).
   2. Wenn Sie zum Importieren von Daten in Audience Manager Server-Side Forwarding (SSF) verwenden, müssen Sie auch auf die neueste Version von AppMeasurement aktualisieren. Laden Sie AppMeasurement mit dem [Analytics-Code-Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)herunter.
3. Sie müssen entweder eine kommerzielle oder eigene Consent Management Platform (CMP) verwenden, die IAB unterstützt und bei der IAB TCF registriert ist. Siehe Liste der [CMP, die im Rahmen](https://advertisingconsent.eu/cmp-list/)der IAB registriert sind.

## Empfehlungen und Implementierungen {#recommendations}

Um die IAB TCF-Unterstützung in Audience Manager zu aktivieren, lesen Sie unsere Dokumentation [wie Sie IAB mit Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)einrichten.

Dies ist am einfachsten, wenn Sie die ECID-Teilnahme mit [Adobe Launch](https://docs.adobelaunch.com/) in Ihren Eigenschaften instrumentieren. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Arbeitsablauf für die Benutzerauswahl bei Verwendung des IAB-Frameworks {#user-choice-workflow}

Wenn Sie eine Webeigenschaft besuchen, können Ihre Benutzer festlegen, wie ihre Daten vom Herausgeber und von Drittanbietern, mit denen der Herausgeber arbeitet, verwendet werden sollen. Benutzer bieten ihre Auswahl in Form von *Standardzwecken* und Berechtigungen an *Drittanbieter* , die in der globalen Händlerliste registriert sind. Die folgende Abbildung zeigt ein Beispiel eines CMP-Dialogfelds, das einem erstmaligen Besucher einer Website angezeigt wird. Beachten Sie, dass dieser Dialog je nach Kundenimplementierung sehr unterschiedlich aussehen kann.

![CMP-Dialogfeld](/help/using/overview/aam-gdpr/assets/cmp.png)

Die IAB-Rahmenvorschriften verfolgen folgende Standardziele:

* Informationsspeicherung und -zugriff
* Personalisierung
* Auswahl, Bereitstellung und Berichterstellung von Anzeigen
* Inhaltsauswahl, Bereitstellung und Berichterstellung
* Videoinformationen

Refer to the IAB framework specification page for a description of the five standard purposes.[](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features)

Benutzer können ihre Einwilligung für eine Kombination aus Standardzwecken und Anbietern erteilen. For example, users could grant their consent for storage, personalization, and measurement and grant their consent to all third-party vendors displayed by the CMP. Or, in another example, they could grant their consent for all five standard purposes but only grant consent to a few of the vendors displayed by the CMP.

Once the user selects their privacy choices, the user choice(s) are recorded in the IAB TCF consent string. The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the IAB page for more information). [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) Every vendor registered in the IAB TCF evaluates the IAB TCF consent string and makes decisions based on the users' privacy choices. Keep in mind that the users' privacy choices are valid across all approved vendors.

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

Audience Manager bewertet die in der IAB TFC-Zustimmungszeichenfolge gespeicherten Benutzerentscheidungen für:

* Information storage and access (purpose ID 1 in the global vendor list)[](https://vendorlist.consensu.org/vendorlist.json)
* Personalization (purpose ID 2)
* Measurement (purpose ID 5)
* Audience Manager vendor consent to store, process, or activate on data for a publisher.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

Audience Manager works differently depending on whether Audience Manager detects in the IAB TCF consent string that the user has provided consent for the three purposes (storage, personalization, measurement) or not.

| When your user provides consent, Audience Manager:** | Wenn Ihr Benutzer die Zustimmung *ablehnt* , dann Audience Manager: |
|---|---|
| <ul><li>Führt alle von Ihnen angeforderten Fälle von Audience Manager aus.</li><li>Sendet Zustimmung an Dritte in ID-Syncs (durch Übergabe von gdpr = 1 und der Zustimmungszeichenfolge als gdpr_approval bei ID-Synchronisierungsaufrufen).</li><li>Wertet die von Anzeigenserverpixeln weitergegebene Zustimmung aus und berücksichtigt sie.</li><li>Bezeichnet von Partnern initiierte ID-Synchronisierungen.</li></ul> | <ul><li>Speichert keine neuen Benutzerdaten in Ihrer Instanz. Dazu gehören Partner-IDs, Signale, Eigenschaften oder Pixeldaten.</li><li>Initiiert keine Synchronisierung der Drittanbieter-IDs.</li><li>Die ID-Synchronisierungen, die vom Partner initiiert wurden, werden nicht berücksichtigt.</li></ul> |



## Verwendungsfall für Herausgeber {#publisher-use-case}

Durch die Implementierung der IAB-TCF müssen Sie keinen benutzerdefinierten Code für die Verwaltung der Zustimmung in Ihren Webeigenschaften über einen anderen Mechanismus mit Adobe oder anderen Drittanbietern verwalten. Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Von links im Bild beginnen:

1. Ein Benutzer besucht eine Ihrer Webeigenschaften. Solange Sie die neuesten Versionen der ECID- und DIL-Bibliotheken verwenden (siehe [Voraussetzungen](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), wird der Abmeldevorgang ausgelöst.
2. Audience Manager überprüft, ob der IAB-Fluss angewendet wird (`isIabContext=true`). Siehe [Recommendations und Implementierungen](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager prüft, ob GDPR angewendet wird (`gdpr = 1`) und ob eine CMP, die bei IAB registriert ist, in Ihrer Webeigenschaft vorhanden ist. Dies würde beispielsweise für Benutzer gelten, die aus dem Gebiet der Europäischen Union kommen. Beachten Sie, dass es Ihre Verantwortung als Herausgeber ist, das GDPR-Flag festzulegen.
4. Wenn GDPR angewendet wird, prüft Audience Manager die IAB-TCF-Zustimmungszeichenfolge, die im Parameter übergeben `gdpr_consent`wird, auf die erforderlichen Berechtigungen. Audience Manager benötigt Berechtigungen für Speicherung, Personalisierung, Messung und die Zustimmung des Audience Manager-Anbieters, um Daten zu speichern, zu verarbeiten oder zu aktivieren.
5. Wenn die IAB-TCF-Genehmigungszeichenfolge vorhanden ist und die erforderlichen Berechtigungen enthält, übergibt Audience Manager die IAB-TCF-Genehmigungszeichenfolge an unsere [Datenerfassungsserver](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager reagiert, indem ein [demdex-Cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) im Browser gesetzt wird. Audience Manager initiiert und honoriert auch ID-Synchronisierungen von Drittanbietern.
7. Wenn die in Schritt 5 übergebene IAB-TCF-Genehmigungszeichenfolge nicht alle erforderlichen Berechtigungen enthält, erfasst, verarbeitet oder aktiviert Audience Manager keine Daten und berücksichtigt keine ID-Synchronisierungen oder initiiert sie nicht.

![Verwendungsfall für Herausgeber](assets/publisher-use-case.png)

## Advertiser Use Case {#advertiser-use-case}

Audience Manager bewertet und berücksichtigt die in [Pixelaufrufen](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)weitergegebene Zustimmung gemäß der IAB-TCF.

Pixel werden von Audience Manager-Kunden in der Regel auf ihren Partnerseiten platziert oder in Werbeseiten platziert, um sie in die Anzeigenantwort einzubeziehen. In the first case, your partner must programmatically retrieve the consent parameter and add it to the pixel before firing. In the second case, which is more common and is described in detail below, ad servers append the consent parameters they receive from the Supply-Side Platform (SSP) or publisher ad servers to all pixels.

Audience Manager uses two parameters to pass user consent in pixel calls:

* `gdpr` can be 0 (GDPR does not apply) or 1 (GDPR applies);
* `gdpr_consent` is the URL-safe base64-encoded GDPR consent string (see specification). [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications) A sample call for an impression pixel, with the two parameters could look like below:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Von links im Bild beginnen:

1. Ihr Benutzer erhält eine Impression über einen Werbeserver. Dies führt zu einem Pixelaufruf an unsere Datenerfassungsserver (Data Collection Servers, DCS).
1. Audience Manager überprüft, ob das GDPR-Flag angewendet wird. Andernfalls speichert Audience Manager die in Makrovariablen übergebenen Daten in Pixelaufrufen.
1. Wenn die Zeichenfolge für die Zustimmung vorhanden ist und die erforderlichen Berechtigungen enthält, speichert Audience Manager die in Makrovariablen übergebenen Daten in Pixelaufrufen.
1. Wenn die Zustimmungszeichenfolge fehlt oder die erforderlichen Berechtigungen fehlen, legt Audience Manager die in Makrovariablen übergebenen Daten in Pixelaufrufen ab.

![Anwendungsfall für Advertiser](assets/advertiser-use-case.png)

## Aktivierungspartner, die die IAB-TCF unterstützen {#aam-activation-partners}

Mit dem Audience Manager-Plug-in für die IAB-TCF können Sie die IAB-TCF-Zustimmungszeichenfolge an Aktivierungspartner weiterleiten und dabei die Datenschutzeinstellungen der Benutzer beachten. Informationen darüber, welche Aktivierungspartner die IAB-TCF unterstützen (genau ab 7. Juli 2019), finden Sie in unserem **[Partner Excel-Blatt](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx)**.

## IAB-Implementierung testen {#test-iab-implementation}

Um zu testen, ob Sie das Audience Manager-Plug-in für IAB TCF korrekt implementiert haben, lesen Sie [Verwendungsfall 4 in Validierungsmethoden für Ausschluss- und IAB-Implementierung](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## IAB und Ausschluss in Audience Manager. Rangfolge. {#iab-and-optout}

Eine weitere Datenschutzoption, die Ihren Benutzern zur Verfügung steht, ist die Möglichkeit, die Datenerfassung auszuschließen. Adobe stellt Benutzern auf der Seite " [Datenschutzoptionen](https://www.adobe.com/privacy/opt-out.html#customeruse) "die entsprechenden Mittel zur Verfügung.

Audience Manager befasst sich mit der Abmeldeverwaltung in einem [separaten Artikel in unserer Dokumentation](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Reihenfolge der Rangfolge** - Wenn Ihr Benutzer die Datenerfassung mit einem globalen Ausschluss-Tool ablehnt, wie im obigen Link beschrieben, hat dies Vorrang vor der Teilnahme- und IAB-Überprüfung.

## Zusätzliche Ressourcen {#additional-resources}

* [Teilnahme am Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR - Transparenz und Zustimmung](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR - Transparenz und Zustimmung - Rahmen Technische Spezifikationen](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-Plugin - Videodemonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
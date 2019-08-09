---
description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-title: Audience Manager Plug-In für IAB TCF
solution: Audience Manager
title: Audience Manager Plug-In für IAB TCF
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Audience Manager Plug-In für IAB TCF {#aam-iab-plugin}

## Überblick

Ein wichtiger Aspekt der Datenschutzverpflichtungen, die Sie gegenüber Ihren Anwendern haben, ist die Akquise und Übermittlung von Benutzerentscheidungen darüber, wie ihre personenbezogenen Daten verwendet werden dürfen (d. h. „Zwecke“) und von wem (d. h. „Unternehmen“).

Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die [Opt-in-Funktion](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) und die Unterstützung des [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) zu verwalten und zu übermitteln.

Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren. Audience Manager wird in der IAB-TCF mit der Anbieter-ID 565 registriert.

Das Audience Manager-Plug-In für IAB nutzt die [Opt-in-Funktion](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), die wiederum Teil der Adobe [Experience Cloud ID-Dienst (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) -Bibliothek ist.

## Umfang und Einschränkungen {#scope-and-limitations}

Als Herausgeber oder Advertiser, die mit Audience Manager arbeiten, können Sie Benutzerentscheidungen nach IAB TCF an Audience Manager senden. Auf diese Weise erhalten Sie eine einfache und konsistente Möglichkeit, Benutzerentscheidungen an alle Partner zu senden, mit denen Sie arbeiten, und Audience Manager kann Ihnen dabei helfen, die Datenschutzentscheidungen Ihrer Benutzer zu respektieren.

Die in diesem Artikel beschriebene IAB-TCF-Unterstützung stellt die erste Phase in der geplanten Unterstützung des Audience Manager für das IAB-Framework dar. Audience Manager unterstützt derzeit nicht:

* Arbeitsabläufe für Mobilgeräte;
* Geräteübergreifende Genehmigungsverwaltung;
* Anhängen der Zustimmung zu urls, die an [URL-Ziele gesendet](/help/using/features/destinations/create-url-destination.md)werden;
* Anhängen der Zustimmung zu Segmenten.

## Voraussetzungen {#prerequisites}

Sie müssen die folgenden Voraussetzungen erfüllen, um das IAB-TCF mit Audience Manager zu verwenden:

1. Sie müssen die Experience Cloud ID-Dienst-Version 4.1 oder höher verwenden. [Laden Sie](https://github.com/Adobe-Marketing-Cloud/id-service/releases) unsere aktuelle ECID-Version herunter.
2. 
   1. Sie müssen die Audience Manager Data Integration Library (DIL) Version 9.0 oder neuer verwenden, die von [hier heruntergeladen](https://github.com/Adobe-Marketing-Cloud/dil/releases)werden kann. Lesen Sie [DIL in der Audience Manager-Dokumentation](/help/using/dil/dil-overview.md).
   2. Wenn Sie die Daten mit serverseitiger Weiterleitung (SSF) in Audience Manager importieren, müssen Sie auch auf die neueste Version von appmeasurement aktualisieren. Laden Sie appmeasurement mit dem [Analytics Code-Manager herunter](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
3. Sie müssen eine CMP (Approval Management Platform) verwenden, entweder kommerzielle oder eigene, die IAB unterstützt und bei der IAB-TCF registriert ist. Siehe Liste der [cmps, die innerhalb des IAB-Frameworks registriert](https://advertisingconsent.eu/cmp-list/)sind.

## Empfehlungen und Implementierung {#recommendations}

Um die IAB-TCF-Unterstützung in Audience Manager zu aktivieren, lesen Sie unsere Dokumentation zur [Einrichtung von IAB mit der Teilnahme an der Anmeldung](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Dies ist am einfachsten durch Verwendung von [Adobe Launch](https://docs.adobelaunch.com/) für die ECID-Teilnahme an Ihren Eigenschaften. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Benutzerauswahlarbeitsablauf bei Verwendung des IAB-Frameworks {#user-choice-workflow}

Wenn Sie eine Webeigenschaft besuchen, können Ihre Benutzer ihre Wahl darüber bereitstellen, wie ihre Daten vom Herausgeber und von den Drittanbietern, mit denen der Herausgeber arbeitet, verwendet werden. Benutzer treffen ihre Auswahlmöglichkeiten in Form von *Standardzwecken* und Berechtigungen für *Drittanbieter,* die in der Liste der globalen Anbieter registriert sind. Die unten stehende Abbildung stellt ein Beispiel eines CMP-Dialogs dar, der einem erstmaligen Besucher einer Website angezeigt wird. Beachten Sie, dass dieser Dialog aufgrund der Kundenimplementierung sehr unterschiedlich aussehen kann.

![CMP-Dialog](/help/using/overview/aam-gdpr/assets/cmp.png)

Die Standardziele im IAB-Framework sind:

* Informationsspeicherung und -zugriff
* Personalisierung
* Anzeigenauswahl, Auslieferung und Berichterstellung
* Inhaltsauswahl, Bereitstellung und Berichterstellung
* Videoinformationen

Eine Beschreibung der fünf Standardzwecke finden Sie auf der [IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) -Framework-Spezifikation.

Benutzer können ihre Zustimmung für eine Kombination aus Standardzielen und Anbietern erteilen. Beispielsweise können Benutzer ihre Zustimmung zu Speicher, Personalisierung und Messung erteilen und ihre Zustimmung für alle Drittanbieter, die von CMP angezeigt werden, genehmigen. In einem anderen Beispiel könnten sie ihre Zustimmung zu allen fünf Standardzwecken erteilen, aber nur einigen der durch CMP angezeigten Anbieter zustimmen.

Sobald der Benutzer seine Datenschutzoptionen auswählt, werden die Auswahlmöglichkeiten der Benutzer in der IAB-TCF-Genehmigungszeichenfolge aufgezeichnet. Die IAB-TCF-Bestätigungszeichenfolge speichert die Kombination aus genehmigten Zielen und Anbietern zusammen mit anderen Metadateninformationen (weitere Informationen finden Sie auf der [IAB-Seite](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) ). Jeder im IAB registrierte Anbieter wertet die IAB-TCF-Genehmigungszeichenfolge aus und trifft Entscheidungen auf der Grundlage der Datenschutzeinstellungen der Benutzer. Denken Sie daran, dass die Datenschutzeinstellungen der Benutzer für alle zugelassenen Anbieter gültig sind.

## Von Audience Manager benötigte Standardziele {#aam-standard-purposes}

Audience Manager bewertet die in der IAB-TFC-Zeichenfolge gespeicherten Optionen für Folgendes:

* Informationsspeicher und Zugriff (Zweck-ID 1 in der [globalen Anbieterliste](https://vendorlist.consensu.org/vendorlist.json))
* Personalisierung (Zweck-ID 2)
* Messung (Zweck-ID 5)
* Audience Manager-Anbieter zur Speicherung, Verarbeitung oder Aktivierung von Daten für einen Herausgeber.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Das Verhalten von Audience Manager hängt davon ab, ob der Benutzer die Zustimmung gewährt. {#aam-behavior-consent}

Audience Manager funktioniert unterschiedlich, je nachdem, ob Audience Manager in der IAB-Genehmigungszeichenfolge erkennt, dass der Benutzer die Zustimmung zu den drei Zwecken (Speicherung, Personalisierung, Messung) angegeben hat.

| Wenn Ihr Benutzer *die Zustimmung bereitstellt*, wird Audience Manager: | Wenn der Benutzer *die Zustimmung abbricht* , wird Audience Manager: |
|---|---|
| <ul><li>Führt alle von Ihnen angeforderten Anwendungsfälle von Audience Manager aus.</li><li>Überträgt die Zustimmung zu Dritten in ID-Synchronisierungen (indem gdpr = 1 und die Bestätigungszeichenfolge als gdpr_ consent bei ID-Synchronisationsaufrufen übergeben werden).</li><li>Wertet die Zustimmung aus, die von den Anzeigenserverpixeln übergeben wurde, und berücksichtigt diese.</li><li>Berücksichtigt die von Partnern initiierten ID-Synchronisierungen.</li></ul> | <ul><li>Speichert keine neuen Benutzerdaten in Ihrer Instanz. Dazu gehören Partner-IDs, Signale, Eigenschaften oder Pixeldaten.</li><li>Startet keine Drittanbieter-ID-Synchronisierung.</li><li>Die vom Partner initiierten ID-Synchronisierungen werden nicht berücksichtigt.</li></ul> |



## Verwendungsfall für Herausgeber {#publisher-use-case}

Durch die Implementierung des TCF sind Sie nicht verpflichtet, benutzerdefinierten Code für die Genehmigungsverwaltung in Ihren Webeigenschaften über einen anderen Mechanismus mit Adobe oder anderen Drittanbietern zu verwalten. Der Verwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginnen Sie links vom Bild:

1. Ein Benutzer besucht eine Ihrer Webeigenschaften. Solange Sie die neuesten Versionen der ECID- und DIL-Bibliotheken verwenden (siehe [Voraussetzungen](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), wird der Ablauf für die Anmeldung ausgelöst.
2. Audience Manager überprüft, ob der IAB-Fluss angewendet wird (`isIabContext=true`). Siehe [Empfehlungen und Implementierung](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager prüft, ob GDPR (`gdpr = 1`) angewendet wird und ob ein CMP (registriert mit IAB) in Ihrer Webeigenschaft vorhanden ist. Dies würde beispielsweise für Benutzer gelten, die aus dem Bereich der europäischen Union besuchen. Beachten Sie, dass Sie als Herausgeber das GDPR-Flag festlegen.
4. Wenn GDPR angewendet wird, prüft Audience Manager die IAB-TCF-Genehmigungszeichenfolge, die im Parameter `gdpr_consent`für die erforderlichen Berechtigungen übergeben wird. Audience Manager benötigt Berechtigungen für Speicher, Personalisierung, Messung, einschließlich der Zustimmung des Audience Manager-Anbieters, um Daten zu speichern, zu verarbeiten oder zu aktivieren.
5. Wenn die IAB-TCF-Bestätigungszeichenfolge vorhanden ist und sie die erforderlichen Berechtigungen enthält, übergibt Audience Manager die IAB-TCF-Genehmigungszeichenfolge an unsere [Datenerfassungsserver](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager reagiert durch Festlegen eines [demdex-Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) im Browser. Audience Manager initiiert und berücksichtigt auch die Synchronisierung von Drittanbieter-Ids.
7. Wenn die in Schritt 5 übergebene IAB-TCF-Zeichenfolge nicht alle erforderlichen Berechtigungen enthält, erfasst Audience Manager keine Daten, verarbeitet oder aktivieren keine Daten und ignoriert oder startet keine ID-Synchronisierungen.

![Verwendungsfall für Herausgeber](assets/publisher-use-case.png)

## Verwendungsfall für Advertiser {#advertiser-use-case}

Audience Manager bewertet und berücksichtigt die Einwilligung, die in [Pixelaufrufen](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)übermittelt wird, gemäß dem IAB-TCF.

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

## Aktivierungspartner, die IAB-TCF unterstützen {#aam-activation-partners}

Mit dem Audience Manager-Plugin für IAB können Sie die IAB-TCF-Genehmigungszeichenfolge an Aktivierungspartner weiterleiten und die Datenschutzmöglichkeiten der Benutzer einhalten. Informationen darüber, welche Aktivierungspartner IAB TCF unterstützen (genau ab dem 7. Juli 2019), finden Sie in unserem **[Partner Excel Sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**.

## Testen der IAB-Implementierung {#test-iab-implementation}

Um zu testen, ob Sie das Audience Manager-Plug-In für IAB-TCF richtig implementiert haben, lesen Sie [in den Validierungsmethoden für die Implementierung und die IAB-Implementierung die Option "Anwendungsfall 4 verwenden](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)«.

## IAB und Opt-out in Audience Manager. Rangfolge. {#iab-and-optout}

Eine weitere Datenschutzoption für den Benutzer ist die Möglichkeit, die Datenerfassung auszuschließen. Adobe stellt den Benutzern auf der Seite ["Datenschutzeinstellungen"](https://www.adobe.com/privacy/opt-out.html#customeruse) die entsprechenden Möglichkeiten zur Verfügung.

Audience Manager behandelt die Ausschluss-Verwaltung in einem [separaten Artikel in unserer Dokumentation](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Reihenfolge der Priorität** : Wenn der Benutzer die Datenerfassung mithilfe eines globalen Abmeldungswerkzeugs abmeldet, wie im obigen Link beschrieben, hat dies Vorrang vor den Überprüfungen für Teilnahme und IAB.

## Zusätzliche Ressourcen {#additional-resources}

* [Experience Cloud ID-Dienst-Teilnahme](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR Transparency and Approval Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Technische Spezifikationen für IAB Europe GDPR Transparency and Approval Framework](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-Plugin - Videodemonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
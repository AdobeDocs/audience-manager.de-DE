---
description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-title: Audience Manager Plug-In für IAB TCF
solution: Audience Manager
title: Audience Manager Plug-In für IAB TCF
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Audience Manager Plug-In für IAB TCF {#aam-iab-plugin}

## Überblick

Ein wichtiger Aspekt der Datenschutzverpflichtungen, die Sie gegenüber Ihren Anwendern haben, ist die Akquise und Übermittlung von Benutzerentscheidungen darüber, wie ihre personenbezogenen Daten verwendet werden dürfen (d. h. „Zwecke“) und von wem (d. h. „Unternehmen“).

Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die [Opt-in-Funktion](hhttps://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) und die Unterstützung des [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) zu verwalten und zu übermitteln.

Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren. Audience Manager ist bei der IAB-TCF mit der Anbieter-ID 565 registriert.

Das Audience Manager-Plug-in für die IAB-TCF verwendet die [Opt-in-Funktion](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html), die wiederum Teil der Adobe [Experience Platform Identity Service (ECID)](https://docs.adobe.com/content/help/en/id-service/using/home.html) -Bibliothek ist.

## Anwendungsbereich und Beschränkungen {#scope-and-limitations}

Als Herausgeber oder Advertiser, der mit Audience Manager arbeitet, können Sie gemäß IAB-TCF Benutzeroptionen an Audience Manager weiterleiten. Dadurch erhalten Sie eine einfache und konsistente Möglichkeit, allen Partnern, mit denen Sie arbeiten, Benutzerentscheidungen mitzuteilen, und Audience Manager kann Ihnen dabei helfen, die Datenschutzentscheidungen Ihrer Benutzer zu respektieren.

Die in diesem Artikel beschriebene Unterstützung der IAB-TCF stellt die erste Phase der geplanten Audience-Manager-Unterstützung für den IAB-Rahmen dar. Derzeit unterstützt Audience Manager nicht:

* Workflows von Mobilgeräten;
* geräteübergreifende Verwaltung der Zustimmung;
* Beifügen der Zustimmung zu URLs, die an [URL-Ziele](../../features/destinations/create-url-destination.md)gesendet werden;
* An Segmente anhängen.

## Voraussetzungen {#prerequisites}

Sie müssen die folgenden Voraussetzungen erfüllen, um die IAB-TCF mit Audience Manager zu verwenden:

1. Sie müssen Adobe Experience Platform Identity Service (ECID) Version 4.1 oder höher verwenden. [Laden Sie](https://github.com/Adobe-Marketing-Cloud/id-service/releases) unsere neueste ECID-Version herunter.
1. Sie müssen die Audience Manager Data Integration Library (DIL) Version 9.0 oder neuer verwenden, die [hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)heruntergeladen werden kann. Lesen Sie mehr über [DIL in der Audience Manager-Dokumentation](../..//dil/dil-overview.md).
1. Wenn Sie zum Importieren von Daten in Audience Manager die serverseitige Weiterleitung (SSF) verwenden, müssen Sie auch auf die neueste Version von AppMeasurement aktualisieren. Laden Sie AppMeasurement mit dem [Analytics-Code-Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)herunter.
1. Sie müssen entweder eine kommerzielle oder eigene Consent Management Platform (CMP) verwenden, die die IAB TCF unterstützt und bei der IAB TCF registriert ist. Siehe die Liste der im Rahmen des IAB registrierten [CMPs](https://advertisingconsent.eu/cmp-list/).

## Empfehlungen und Implementierungen {#recommendations}

Um die IAB TCF-Unterstützung im Audience Manager zu aktivieren, lesen Sie unsere Dokumentation [wie Sie IAB mit Opt-in](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)einrichten.

Dies ist am einfachsten mit dem [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) , um die ECID-Teilnahme an Ihren Eigenschaften zu instrumentieren. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Arbeitsablauf für die Benutzerauswahl bei Verwendung des IAB-Frameworks {#user-choice-workflow}

Wenn Sie eine Webeigenschaft besuchen, können Ihre Benutzer festlegen, wie ihre Daten vom Herausgeber und von Drittanbietern, mit denen der Herausgeber arbeitet, verwendet werden sollen. Die Benutzer bieten ihre Auswahl in Form von *Standardzwecken* und Berechtigungen an *Drittanbieter* , die in der Liste des globalen Anbieters registriert sind. Die folgende Abbildung zeigt ein Beispiel für ein CMP-Dialogfeld, das einem erstmaligen Besucher einer Website angezeigt wird. Beachten Sie, dass dieser Dialog je nach Kundenimplementierung sehr unterschiedlich aussehen kann.

![CMP-Dialogfeld](assets/cmp.png)

Die IAB-Rahmenvorschriften verfolgen folgende Standardziele:

* Datenspeicherung und Zugang von Informationen
* Personalisierung
* Anzeigenauswahl, Versand und Berichte
* Inhaltsauswahl, Versand und Berichte
* Videoinformationen

Eine Beschreibung der fünf Standardzwecke finden Sie auf der Seite [der](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) IAB-Rahmenspezifikation.

Benutzer können ihre Einwilligung für eine Kombination aus Standardzwecken und Anbietern erteilen. So könnten die Nutzer beispielsweise ihre Einwilligung zur Datenspeicherung, Personalisierung und Messung erteilen und allen vom CMP dargestellten Drittanbietern ihre Einwilligung erteilen. Oder in einem anderen Beispiel könnten sie ihre Zustimmung für alle fünf Standardzwecke erteilen, aber nur einigen Anbietern, die vom CMP gezeigt werden, ihre Zustimmung erteilen.

Sobald der Benutzer seine Datenschutzeinstellungen ausgewählt hat, werden die Benutzerauswahl(en) in der IAB-TCF-Genehmigungszeichenfolge aufgezeichnet. Die IAB-TCF-Genehmigungszeichenfolge speichert die Kombination von genehmigten Zwecken und Anbietern zusammen mit anderen Metadateninformationen (weitere Informationen finden Sie auf der [IAB-Seite](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) ). Jeder in der IAB TCF registrierte Anbieter bewertet die IAB-TCF-Zustimmungszeichenfolge und trifft Entscheidungen auf der Grundlage der Datenschutzentscheidungen der Nutzer. Beachten Sie, dass die Datenschutzeinstellungen der Benutzer für alle zugelassenen Anbieter gültig sind.

## Standardaufgaben von Audience Manager {#aam-standard-purposes}

Audience Manager bewertet die in der IAB TFC-Zustimmungszeichenfolge gespeicherten Benutzerentscheidungen für:

* Datenspeicherung und Zugriff von Informationen (Zweck-ID 1 in der [Liste](https://vendorlist.consensu.org/vendorlist.json)globaler Anbieter)
* Personalisierung (Ziel-ID 2)
* Messung (Zweck-ID 5)
* Audience Manager-Anbieter stimmen zu, Daten für Herausgeber zu speichern, zu verarbeiten oder zu aktivieren.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Das Verhalten von Audience Manager hängt davon ab, ob der Benutzer seine Zustimmung erteilt {#aam-behavior-consent}

Audience Manager funktioniert unterschiedlich, je nachdem, ob Audience Manager in der IAB-TCF-Genehmigungszeichenfolge erkennt, dass der Benutzer seine Zustimmung zu den drei Zwecken (Datenspeicherung, Personalisierung, Messung) erteilt hat oder nicht.

| Wenn Ihr Benutzer seine Zustimmung *erteilt*, dann Audience Manager: | Wenn Ihr Benutzer die Zustimmung *ablehnt* , dann Audience Manager: |
|---|---|
| <ul><li>Führt alle von Ihnen angeforderten Anwendungsfälle von Audience Manager aus.</li><li>Sendet Zustimmung an Dritte in ID-Syncs (durch Übergabe von gdpr = 1 und der Zustimmungszeichenfolge als gdpr_approval bei ID-Synchronisierungsaufrufen).</li><li>Wertet die von Anzeigenserverpixeln übergebene Zustimmung aus und berücksichtigt sie.</li><li>Bezeichnet von Partnern initiierte ID-Synchronisierungen.</li></ul> | <ul><li>Speichert keine neuen Benutzerdaten in Ihrer Instanz. Dazu gehören Partner-IDs, Signale, Eigenschaften oder Pixeldaten.</li><li>Initiiert keine Synchronisierung der Drittanbieter-IDs.</li><li>Die ID-Synchronisierungen, die vom Partner initiiert wurden, werden nicht berücksichtigt.</li></ul> |

## Verwendungsfall für Herausgeber {#publisher-use-case}

Durch die Implementierung der IAB-TCF müssen Sie keinen benutzerdefinierten Code für die Verwaltung der Zustimmung in Ihren Webeigenschaften über einen anderen Mechanismus mit Adobe oder anderen Drittanbietern verwalten. Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginn links neben dem Bild:

1. Ein Benutzer besucht eine Ihrer Webeigenschaften. Solange Sie die neuesten Versionen der ECID- und DIL-Bibliotheken verwenden (siehe [Voraussetzungen](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), wird der Abmeldevorgang ausgelöst.
2. Audience Manager überprüft, ob der IAB-Fluss angewendet wird (`isIabContext=true`). Siehe [Recommendations und Implementierungen](aam-iab-plugin.md#recommendations).
3. Audience Manager prüft, ob GDPR angewendet wird (`gdpr = 1`) und ob eine CMP, die bei IAB registriert ist, in Ihrer Webeigenschaft vorhanden ist. Dies würde beispielsweise für Nutzer gelten, die aus dem Bereich der europäischen Vereinigung besuchen. Beachten Sie, dass es Ihre Verantwortung als Herausgeber ist, das GDPR-Flag festzulegen.
4. Wenn GDPR angewendet wird, prüft Audience Manager die IAB-TCF-Zustimmungszeichenfolge, die im Parameter übergeben `gdpr_consent`wird, auf die erforderlichen Berechtigungen. Audience Manager benötigt Berechtigungen zur Datenspeicherung, Personalisierung, Messung und Audience Manager-Anbietergenehmigung, um Daten zu speichern, zu verarbeiten oder zu aktivieren.
5. Wenn die IAB-TCF-Genehmigungszeichenfolge vorhanden ist und die erforderlichen Berechtigungen enthält, übergibt Audience Manager die IAB-TCF-Genehmigungszeichenfolge an unsere [Datenerfassungsserver](../../reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager reagiert, indem ein [demdex-Cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) im Browser gesetzt wird. Audience Manager initiiert und honoriert auch ID-Synchronisierungen von Drittanbietern.
7. Wenn die in Schritt 5 übergebene IAB-TCF-Genehmigungszeichenfolge nicht alle erforderlichen Berechtigungen enthält, erfasst, verarbeitet oder aktiviert Audience Manager keine Daten und berücksichtigt keine ID-Synchronisierungen oder initiiert sie nicht.

![Verwendungsfall für Herausgeber](assets/publisher-use-case.png)

## Anwendungsfall für Advertiser {#advertiser-use-case}

Audience Manager bewertet und honoriert die in [Pixelaufrufen](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)übergebene Zustimmung gemäß der IAB-TCF.

Pixel werden von Audience Manager-Kunden in der Regel auf ihren Partnerseiten platziert oder in Werbeseiten platziert, um sie in die Anzeigenantwort einzubeziehen. Im ersten Fall muss Ihr Partner den Parameter &quot;approval&quot;programmgesteuert abrufen und ihn dem Pixel hinzufügen, bevor er ausgelöst wird. Im zweiten Fall, der häufiger vorkommt und unten detailliert beschrieben wird, hängen Anzeigenserver die von der Supply-Side Platform (SSP) oder dem Herausgeber-Anzeigenserver erhaltenen Parameter an alle Pixel an.

Audience Manager verwendet zwei Parameter, um die Benutzereinwilligung in Pixelaufrufen weiterzugeben:

* `gdpr` kann 0 (GDPR gilt nicht) oder 1 (GDPR gilt) betragen;
* `gdpr_consent` ist die URL-sichere base64-kodierte GDPR-Zustimmungszeichenfolge (siehe [Spezifikation](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Ein Beispielaufruf für ein Impressions-Pixel mit den beiden Parametern könnte wie folgt aussehen:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginn links neben dem Bild:

1. Ihr Benutzer erhält eine Impression über einen Werbeserver. Dies führt zu einem Pixelaufruf an unsere Datenerfassungsserver (Data Collection Servers, DCS).
2. Audience Manager überprüft, ob das GDPR-Flag angewendet wird. Andernfalls speichert Audience Manager die in Makrovariablen übergebenen Daten in Pixelaufrufen.
3. Wenn die Zeichenfolge für die Zustimmung vorhanden ist und die erforderlichen Berechtigungen enthält, speichert Audience Manager die in Makrovariablen übergebenen Daten in Pixelaufrufen.
4. Wenn die Zustimmungszeichenfolge fehlt oder die erforderlichen Berechtigungen fehlen, legt Audience Manager die in Makrovariablen übergebenen Daten in Pixelaufrufen ab.

![Anwendungsfall für Advertiser](assets/advertiser-use-case.png)

## Aktivierungen-Partner, die die IAB-TCF unterstützen {#aam-activation-partners}

Mit dem Audience Manager-Plug-in für IAB TCF können Sie die IAB TCF-Zustimmungszeichenfolge an Aktivierungen-Partner weiterleiten, wobei die Datenschutzeinstellungen der Nutzer zu beachten sind. Informationen darüber, welche Aktivierung-Partner die IAB TCF unterstützen, finden Sie in unserer [Liste der gerätebasierten Ziele](/help/using/features/destinations/device-based-destinations-list.md).

## IAB-Implementierung testen {#test-iab-implementation}

Um zu testen, ob Sie das Audience Manager-Plug-in für IAB TCF korrekt implementiert haben, lesen Sie [Verwendungsfall 4 in Validierungsmethoden für Opt-in- und IAB-Implementierung](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB und Opt-out in Audience Manager. Rangfolge. {#iab-and-optout}

Eine weitere Datenschutzoption, die Ihren Benutzern zur Verfügung steht, ist die Möglichkeit, die gesamte Datenerfassung zu Opt-out. Adobe stellt Benutzern auf der Seite &quot; [Ihre Datenschutzoptionen](https://www.adobe.com/privacy/opt-out.html#customeruse) &quot;die entsprechenden Mittel zur Verfügung.

Audience Manager behandelt Abmeldeanforderungen in einem [separaten Artikel in unserer Dokumentation](data-privacy-requests.md).

>[!NOTE]
>
>**Reihenfolge der Rangfolge** - Wenn Ihr Benutzer die Datenerfassung mit einem globalen Ausschluss-Tool ablehnt, wie im obigen Link beschrieben, hat dies Vorrang vor der Teilnahme- und IAB-Überprüfung.

## Zusätzliche Ressourcen {#additional-resources}

* [Adobe Experience Platform Identity Service-Teilnahme](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB Europe GDPR - Transparenz und Zustimmung](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR - Transparenz und Zustimmung - Rahmen Technische Spezifikationen](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-Plugin - Videodemonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
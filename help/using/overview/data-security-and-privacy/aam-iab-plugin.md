---
description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-title: Audience Manager-Plug-In für IAB TCF
solution: Audience Manager
title: Audience Manager-Plug-In für IAB TCF
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: ff592184ba1785e3448aa449745d0e66ecba955b
workflow-type: tm+mt
source-wordcount: '2449'
ht-degree: 39%

---


# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Überblick

Ein wichtiger Aspekt bei den Datenschutzverpflichtungen, die Sie gegenüber Ihren Nutzern haben, ist der Erwerb und die Übertragung von Benutzerentscheidungen darüber, wie ihre personenbezogenen Daten verwendet werden dürfen (d.h. &quot;Zwecke&quot;) und von wem (d.h. &quot;Firmen&quot;).

Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die [Opt-in-Funktion](https://docs.adobe.com/content/help/de-DE/id-service/using/implementation/opt-in-service/optin-overview.html) und die Unterstützung des [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) zu verwalten und zu übermitteln.

Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.

>[!IMPORTANT]
>
>Audience Manager is registered in the [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) with the vendor ID 565.

Das Audience Manager-Plug-in für IAB TCF verwendet die [Opt-in-Funktion](https://docs.adobe.com/content/help/de-DE/id-service/using/implementation/opt-in-service/iab.html), die wiederum Teil der [ Experience Platform Identity Service (ECID)](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html)-Bibliothek von Adobe ist.

## Umfang und Beschränkungen {#scope-and-limitations}

Als Publisher oder Advertiser, der mit Audience Manager arbeitet, können Sie gemäß IAB-TCF Benutzerentscheidungen an Audience Manager weiterleiten.

>[!IMPORTANT]
>
>Die IAB-TCF-Vorschriften gelten nur für Besucher im Europäischen Wirtschaftsraum.

Audience Manager hilft Ihnen, die Datenschutzentscheidungen Ihrer Benutzer zu respektieren und bietet Ihnen eine einfache Möglichkeit, diese Auswahlmöglichkeiten allen Partnern, mit denen Sie arbeiten, mitzuteilen.

Derzeit bietet Audience Manager für Folgendes keine Unterstützung:

* Workflows für Mobilgeräte;
* An Segmentierung von Exporten angehängte Zustimmung.

## Auf [!DNL IAB TCF v2.0] {#upgrading}

Kunden, die ihre [!DNL Audience Manager Plug-in for IAB TCF] Implementierung von [!DNL IAB TCF] v1.1 auf [!DNL IAB TCF] v2.0 aktualisieren oder [!DNL IAB TCF] v2.0 zum ersten Mal aktivieren, sollten dieselben Richtlinien zu Voraussetzungen und Implementierung befolgen, wie nachfolgend beschrieben.

## Voraussetzungen {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager unterstützt IAB TCF v2.0.
>
>Die Unterstützung für IAB TCF v1.1 endet am 15. August 2020.
>
> Kunden, die das Audience Manager-Plug-in für die IAB-TCF für die Verwaltung der Zustimmung weiterhin verwenden möchten, sollten zur weiteren Unterstützung auf die neueste Version der [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) aktualisieren.
>
> Nach der Aktualisierung auf die neueste [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) -Version werden die IAB TCF v1.1-Zustimmungszeichenfolgen nicht mehr unterstützt. Achten Sie daher darauf, Ihre CMP zu aktualisieren, bevor Sie auf die neueste ECID-Version aktualisieren.

Sie müssen die folgenden Voraussetzungen erfüllen, um das Audience Manager-Plug-in für IAB TCF mit Audience Manager zu verwenden:

1. Sie müssen Adobe Experience Platform Identity Service (ECID) Version 5 (oder neuer) verwenden. [Laden](https://github.com/Adobe-Marketing-Cloud/id-service/releases) Sie unsere neueste ECID-Version herunter.
2. You must be using Audience Manager [!DNL Data Integration Library] (DIL) version 9.0 or newer, downloadable from [here](https://github.com/Adobe-Marketing-Cloud/dil/releases). Weitere Informationen zur DIL finden Sie [in der Dokumentation zu Audience Manager](../..//dil/dil-overview.md). Es wird empfohlen, [Adobe Launch](https://docs.adobe.com/content/help/de-DE/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) für die einfachste DIL-Implementierung für Audience Manager zu verwenden.
3. Alternatively, if you use [!DNL Server-Side Forwarding] (SSF) to import data into Audience Manager, you must upgrade to the latest version of AppMeasurement. Laden Sie AppMeasurement mit dem [Analytics-Code-Manager](https://docs.adobe.com/content/help/de-DE/analytics/admin/admin-tools/code-manager-admin.html) herunter.
4. Sie müssen entweder eine kommerzielle oder eigene Consent Management Platform (CMP) verwenden, die mit IAB TCF v2.0 integriert ist und bei der IAB TCF registriert ist. Siehe dazu die Liste der [beim IAB-Framework registrieren CMPs](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Wenn Sie eine Consent Management Platform (CMP) verwenden, die IAB TCF v.2.0 nicht unterstützt, sendet Audience Manager den `gdpr=0` Parameter automatisch in ID-Syncs, auch wenn sich Ihre Besucher in der europäischen Vereinigung befinden. Um festzustellen, ob Ihre GDPR-Validierung aktiv ist, sollten Sie mit Ihrer Consent Management Platform (CMP) bestätigen, dass sie IAB TCF v2.0 unterstützen.

## Empfehlungen und Implementierung {#recommendations}

Um die IAB TCF-Unterstützung in Audience Manager zu aktivieren, lesen Sie unsere Dokumentation [zum Einrichten von IAB mit Opt-in-Funktion](https://docs.adobe.com/content/help/de-DE/id-service/using/implementation/opt-in-service/iab.html).

Am einfachsten können Sie dies tun, indem Sie [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) verwenden, um [!DNL ECID Opt-in] Ihre Eigenschaften hinzuzufügen. Informationen zur Einrichtung der Launch-Erweiterung finden Sie in der Dokumentation zur [ECID-Opt-in-Erweiterung](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html).

## Workflow für Benutzerentscheidungen bei Verwendung des IAB-Framework {#user-choice-workflow}

Beim Besuch einer Web-Eigenschaft können Ihre Benutzer festlegen, wie ihre Daten vom Publisher und von den Drittanbietern, mit denen der Publisher zusammenarbeitet, verwendet werden sollen.

Die Nutzer stellen ihre Auswahl in Form der *Zustimmung* und des *berechtigten Interesses* an der IAB gegenüber *Drittanbietern* bereit, die in der Liste des Anbieters registriert sind.

Das folgende Bild zeigt ein Beispiel für ein CMP-Dialogfeld, das einem erstmaligen Besucher einer Website angezeigt wird. Beachten Sie, dass dieser Dialog je nach Kundenimplementierung sehr unterschiedlich aussehen kann.

![CMP-Dialogfeld](assets/cmp-example.png)

Einzelheiten zu den verschiedenen Zwecken und Berechtigungen, die in der IAB TCF v2.0 enthalten sind, finden Sie in den Richtlinien des [IAB Europe Transparency &amp; Consent Framework](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Benutzer können ihre Einwilligung oder ihr berechtigtes Interesse (sofern verfügbar) für eine Kombination von Zwecken und Lieferanten gewähren. Beispielsweise könnten Benutzer ihre Zustimmung zur Speicherung von Informationen auf einem Gerät, zur Entwicklung und Verbesserung von Produkten und zur Erteilung ihrer Zustimmung an alle vom CMP angezeigten Drittanbieter erteilen.

Oder in einem anderen Beispiel könnten sie ihre Zustimmung oder ihr berechtigtes Interesse für alle Zwecke erteilen, aber nur einigen Anbietern, die vom CMP gezeigt werden, Einwilligung oder berechtigtes Interesse erteilen.

Sobald der Benutzer seine Datenschutzeinstellungen ausgewählt hat, werden die Benutzerauswahl(en) in der IAB-TC-Zeichenfolge aufgezeichnet. The IAB TC string stores the combination of approved purposes and vendors, along with other metadata information (see the [IAB page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) for more information).

Jeder im IAB TCF registrierte Anbieter bewertet die IAB TC-Zeichenfolge und trifft Entscheidungen auf der Grundlage der Datenschutzentscheidungen der Benutzer. Beachten Sie, dass die Datenschutzeinstellungen der Benutzer für alle Anbieter gültig sind, die bei IAB TCF registriert sind.

## Von Audience Manager erforderliche Ziele {#aam-standard-purposes}

Audience Manager bewertet die in der IAB-TC-Zeichenfolge gespeicherten Benutzerentscheidungen für die folgenden Zwecke, die in den Richtlinien des [IAB Europe Transparency &amp; Consent Framework](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)definiert sind. Darüber hinaus finden Sie die Ziele auch in der [Liste](https://vendorlist.consensu.org/vendorlist.json)globaler Anbieter.

* **Zweck 1**: Speichern und/oder Zugreifen auf einem Gerät;
* **Zweck 10**: Entwicklung und Verbesserung der Produkte;
* **Sonderzweck 1**: Sicherstellen der Sicherheit, Vermeiden von Betrug und Debuggen.

>[!IMPORTANT]
>
>Audience Manager benötigen die Zustimmung zu Zweck 1 und Zweck 10 sowie die Zustimmung des Anbieters, um Cookies bereitzustellen und ID-Syncs zu initiieren oder zu berücksichtigen.
>
>Gemäß den [IAB-Bestimmungen](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)wird der Sonderzweck 1 (Sicherheit, Verhinderung von Betrug und Debugging) immer akzeptiert und die Benutzer können keine Einwände dagegen erheben.

## Das Verhalten von Audience Manager hängt davon ab, ob der Benutzer seine Zustimmung erteilt {#aam-behavior-consent}

Audience Manager funktioniert unterschiedlich, je nachdem, ob die IAB-TC-Zeichenfolge die Benutzereinwilligung für die beiden Zwecke enthält (Speicherung und/oder Zugriff auf Informationen auf einem Gerät und Entwicklung und Verbesserung von Produkten) oder nicht.

Wir überprüfen auch die Benutzereinwilligung für alle Ziele, mit denen Sie in Audience Manager arbeiten, solange diese Ziele bei IAB TCF registriert sind.

| When your user *provides* consent, Audience Manager: | Wenn Ihr Benutzer seine *Zustimmung nicht erteilt*, wird Audience Manager: |
|---|---|
| <ul><li>alle von Ihnen angeforderten Audience Manager-Anwendungsfälle ausführen.</li><li>Conveys consent to third parties in ID syncs (by passing `gdpr = 1` and the consent string as `gdpr_consent` on ID sync calls).</li><li>die von Adserver-Pixeln übergebene Zustimmung auswerten und berücksichtigen.</li><li>von Partnern initiierte ID-Synchronisierungen berücksichtigen.</li></ul> | <ul><li>keine neuen Benutzerdaten in Ihrer Instanz speichern. Dazu gehören Partner-IDs, Signale, Eigenschaften oder Pixeldaten.</li><li>keine Synchronisierung der Drittanbieter-IDs initiieren.</li><li>von Partnern initiierte ID-Synchronisierungen nicht berücksichtigen.</li><li>Der Benutzer wird von der weiteren Datenerfassung ausgeschlossen.</li></ul> |

## Anwendungsfall: Publisher {#publisher-use-case}

Durch die Implementierung des Audience Manager-Plug-ins für die IAB-TCF müssen Sie keinen benutzerdefinierten Code für die Verwaltung der Zustimmung in Ihren Webeigenschaften über einen anderen Mechanismus mit Adobe oder anderen Drittanbietern verwalten. Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginnen Sie links im Bild:

1. Ein Benutzer besucht eine Ihrer Web-Eigenschaften. Solange Sie die neuesten Versionen der ECID- und DIL-Bibliotheken verwenden (siehe [Voraussetzungen](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), wird der Opt-in-Fluss ausgelöst.
2. Audience Manager überprüft, ob der IAB-Fluss zutrifft (`isIabContext=true`). Siehe [Empfehlungen und Implementierung](aam-iab-plugin.md#recommendations).
3. Audience Manager checks whether GDPR applies (`gdpr = 1`) and whether there is a CMP, registered with IAB TCF, on your web property. Dies würde beispielsweise für Benutzer gelten, die von der europäischen Vereinigung aus besuchen. Beachten Sie, dass es Ihre Verantwortung als Herausgeber ist, das GDPR-Flag festzulegen.
4. If GDPR applies, Audience Manager checks the IAB TC string, passed in the `gdpr_consent` parameter, for the required consent. Audience Manager benötigen die Zustimmung zur Speicherung und/oder zum Zugriff auf Informationen auf einem Gerät ([IAB TCF-Zweck 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), zur Entwicklung und Verbesserung von Produkten ([IAB-TCF-Zweck 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)) sowie die Zustimmung des Anbieters zum Speichern, Verarbeiten oder Aktivieren von Daten.
5. If the IAB TC string is present and it contains the required consent, Audience Manager passes the IAB TC string on to our [data collection servers](../../reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager antwortet, indem er im Browser ein [demdex-Cookie](https://docs.adobe.com/content/help/de-DE/core-services/interface/ec-cookies/cookies-am.html) setzt und ID-Synchronisierungen von Drittanbietern initiiert und berücksichtigt.
7. Wenn die in Schritt 4 übergebene IAB-TC-Zeichenfolge nicht alle erforderlichen Berechtigungen enthält, erfasst, verarbeitet oder aktiviert Audience Manager keine Benutzerdaten und berücksichtigt keine ID-Synchronisierungen oder initiiert sie nicht. Außerdem wird der Benutzer von den Zielen, mit denen Sie arbeiten, ausgeschlossen.

>[!IMPORTANT]
>
>Wenn Sie mit Audience Manager-Zielpartnern arbeiten, die IAB-TCF-Parameter benötigen, aber keinen CMP haben, der die IAB-TCF auf Ihrer Website unterstützt, sendet Audience Manager ID-Synchronisierungen `gdpr=0` . Dies bedeutet, dass GDPR nicht für diese Benutzer gilt.
>
> Falls dies nicht gewünscht wird, sollten Sie die IAB-TCF-Funktion in Audience Manager aktivieren, um die entsprechenden IAB-TC-Zeichenfolgen an die Zielpartner zu senden.



![Anwendungsfall: Publisher ](assets/publisher-use-case.png)

## Anwendungsfall: Advertiser {#advertiser-use-case}

Audience Manager bewertet und berücksichtigt die in [Pixelaufrufen](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md) übergebene Zustimmung gemäß des IAB TCF.

Pixel können von Audience Manager auf ihren Partnerseiten platziert werden oder sie werden auf den Anzeigen-Servern platziert, um sie in die Anzeigenantwort einzubeziehen. Im ersten Fall muss Ihr Partner den Zustimmungsparameter programmgesteuert abrufen und dem Pixel vor dem Auslösen hinzufügen. Im zweiten Fall, der häufiger vorkommt und im Folgenden ausführlich beschrieben wird, hängen Adserver die Zustimmungsparameter, die sie von der SSP (Supply-Side Platform) oder von Adservern des Publishers erhalten, an alle Pixel an.

Audience Manager verwendet zwei Parameter, um die Benutzerzustimmung in Pixelaufrufen weiterzugeben:

* `gdpr` kann 0 (DSGVO trifft nicht zu) oder 1 (DSGVO trifft zu) betragen;
* `gdpr_consent` ist die URL-sichere base64-kodierte DSGVO-Zustimmungszeichenfolge (siehe [Spezifikation](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Ein Beispielaufruf für ein Impressionspixel mit den beiden Parametern könnte wie folgt aussehen:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginnen Sie links im Bild:

1. Ihr Benutzer erhält eine Impression über einen Adserver. This translates into a [pixel call](../../integration/media-data-integration/impression-data-pixels.md) to our Data Collection Servers (DCS).
2. Audience Manager überprüft, ob die DSGVO-Markierung gesetzt ist. If it doesn&#39;t, Audience Manager stores the data passed in the `gdpr` and `gdpr_consent` variables in pixel calls.
3. If the IAB TC string is present and it contains the required permissions, Audience Manager stores the data passed in the `gdpr` and `gdpr_consent` variables in pixel calls.
4. If the IAB TC string is missing or lacks the required permissions, Audience Manager drops the data passed in the `gdpr` and `gdpr_consent` variables in pixel calls.

![Anwendungsfall: Advertiser ](assets/advertiser-use-case.png)

## Aktivierungspartner, die das IAB TCF unterstützen {#aam-activation-partners}

Mit dem Audience Manager-Plug-in für IAB TCF können Sie die IAB TC-Zeichenfolge an Aktivierungen-Partner weiterleiten und dabei die Datenschutzentscheidungen der Nutzer beachten. Informationen darüber, welche Aktivierungspartner das IAB TCF unterstützen, finden Sie in unserer [Liste gerätebasierter Ziele](/help/using/features/destinations/device-based-destinations-list.md).

## Anhängen der Zustimmung zu URLs, die an URL-Ziele gesendet werden

Die Audience Manager-Integration mit IAB TCF v2.0 unterstützt das Anhängen der Zustimmung zu Informationen, die an [URL-Ziele](../../features/destinations/create-url-destination.md) gesendet werden, die in IAB TCF v2.0 integriert sind. Dieser Vorgang wird jedoch nicht automatisch von Audience Manager ausgeführt, um zu vermeiden, dass bestimmte URL-Formate umgangen werden.

Kunden, die die Zustimmung zu den an gesendeten Daten anhängen möchten, [!DNL URL destinations] müssen die URL-Dateien `${GDPR}` und die `${GDPR_CONSENT_XXXX}` -Makros manuell hinzufügen und `XXXX` durch die Ziel-Partner-ID ersetzen.

Beispiel: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Weitere Informationen zu den unterstützten Zielmakros finden Sie unter [Zielmakros definiert](../../features/destinations/destination-macros.md) .

## Geräteübergreifende Verwaltung der Zustimmung

Das Audience Manager-Plug-in für die IAB-TCF meldet die bei einer Anforderung vorhandenen IDs automatisch ab, wenn Ihre Site-Besucher nicht über die entsprechenden Berechtigungen verfügen. Wenn die Anforderung eine [geräteübergreifende ID (CRM-ID)](../../reference/ids-in-aam.md)enthält, wählt der Audience Manager die ID zusammen mit dem letzten mit dieser [geräteübergreifenden ID (CRM-ID)](../../reference/ids-in-aam.md)verknüpften Gerät aus.

## Testen der IAB-Implementierung {#test-iab-implementation}

To test that you have correctly implemented the Audience Manager Plug-in for IAB TCF, read [Use Case 4 in Validating Opt-in Service](https://docs.adobe.com/content/help/de-DE/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB und Opt-out in Audience Manager. Prioritätsfolge. {#iab-and-optout}

Eine weitere Datenschutzoption, die Ihren Benutzern zur Verfügung steht, ist die Möglichkeit, sich gegen jegliche Datenerfassung zu entscheiden. Adobe stellt Benutzern auf der Seite [Ihre Datenschutzoptionen](https://www.adobe.com/de/privacy/opt-out.html#customeruse) die entsprechenden Mittel zur Verfügung.

Audience Manager behandelt Opt-out-Anfragen in einem [separaten Artikel in unserer Dokumentation](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Benutzer, die sich aus der Datenerfassung ausgeschlossen haben, nachdem sie die Zustimmung abgelehnt haben, können nicht wieder aufgenommen werden.

>[!NOTE]
>
>**Prioritätsfolge** – Wenn Ihr Benutzer die Datenerfassung mit Hilfe eines globalen Opt-out-Tools, wie im obigen Link beschrieben, ablehnt, hat dies Vorrang vor den Opt-in- und IAB-Überprüfungen.

## Zusätzliche Ressourcen {#additional-resources}

* [Adobe Experience Platform Identity Service-Opt-in](https://docs.adobe.com/content/help/de-DE/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB Europe DSGVO Transparency and Consent Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe DSGVO Transparency and Consent Framework, Technische Spezifikationen](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-Plugin – Videodemonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
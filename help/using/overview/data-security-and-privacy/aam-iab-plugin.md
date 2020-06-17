---
description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-title: Audience Manager Plug-In für IAB TCF
solution: Audience Manager
title: Audience Manager Plug-In für IAB TCF
translation-type: tm+mt
source-git-commit: 1fb8ee6c229418e48fcaa412a8ea0f1ab5f00331
workflow-type: tm+mt
source-wordcount: '2423'
ht-degree: 7%

---


# Audience Manager Plug-In für IAB TCF {#aam-iab-plugin}

## Überblick

Ein wichtiger Aspekt bei den Datenschutzverpflichtungen, die Sie gegenüber Ihren Nutzern haben, ist der Erwerb und die Übertragung von Benutzerentscheidungen darüber, wie ihre personenbezogenen Daten verwendet werden dürfen (d.h. &quot;Zwecke&quot;) und von wem (d.h. &quot;Firmen&quot;).

Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die [Opt-in-Funktion](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) und die Unterstützung des [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) zu verwalten und zu übermitteln.

Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.

>[!IMPORTANT]
>
>Audience Manager ist im [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) mit der Anbieter-ID 565 registriert.

Das Audience Manager-Plug-in für IAB TCF verwendet die [Opt-in-Funktion](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html), die wiederum Teil der ECID-Bibliothek ( [Adobe Experience Platform Identity Service)](https://docs.adobe.com/content/help/en/id-service/using/home.html) ist.

## Anwendungsbereich und Beschränkungen {#scope-and-limitations}

Als Publisher oder Advertiser, der mit Audience Manager arbeitet, können Sie Benutzeroptionen gemäß IAB TCF an Audience Manager weiterleiten.

>[!IMPORTANT]
>
>Die IAB-TCF-Vorschriften gelten nur für Besucher im Europäischen Wirtschaftsraum.

Audience Manager hilft Ihnen, die Datenschutzentscheidungen Ihrer Benutzer zu respektieren und bietet Ihnen eine einfache Möglichkeit, diese Auswahlmöglichkeiten allen Partnern, mit denen Sie arbeiten, mitzuteilen.

Derzeit unterstützt Audience Manager nicht:

* Workflows von Mobilgeräten;
* An Segmentierung von Exporten angehängte Zustimmung.

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

1. Sie müssen Adobe Experience Platform Identity Service (ECID) Version 5 oder höher verwenden. [Laden Sie](https://github.com/Adobe-Marketing-Cloud/id-service/releases) unsere neueste ECID-Version herunter.
2. Sie müssen Audience Manager [!DNL Data Integration Library] (DIL) Version 9.0 oder neuer verwenden, die [hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)heruntergeladen werden kann. Lesen Sie mehr über [DIL in der Dokumentation](../..//dil/dil-overview.md)des Audience Managers. Es wird empfohlen, [Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) für die einfachste DIL-Implementierung für Audience Manager zu verwenden.
3. Wenn Sie Daten in Audience Manager importieren, müssen Sie auch auf die neueste Version von AppMeasurement aktualisieren, wenn Sie [!DNL Server-Side Forwarding] (SSF) verwenden. Laden Sie AppMeasurement mit dem [Analytics Code-Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)herunter.
4. Sie müssen eine Consent Management Platform (CMP) verwenden, entweder kommerziell oder eigens, die mit IAB TCF v2.0 integriert ist und bei der IAB TCF registriert ist. Siehe die Liste der im Rahmen des IAB registrierten [CMPs](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Wenn Sie eine Consent Management Platform (CMP) verwenden, die IAB TCF v.2.0 nicht unterstützt, sendet Audience Manager den `gdpr=0` Parameter automatisch in ID-Syncs, auch wenn sich Ihre Besucher in der europäischen Vereinigung befinden. Um festzustellen, ob Ihre GDPR-Validierung aktiv ist, sollten Sie mit Ihrer Platform für die Consent Management (CMP) bestätigen, dass sie IAB TCF v2.0 unterstützen.

## Empfehlungen und Implementierungen {#recommendations}

Um die IAB TCF-Unterstützung in Audience Manager zu aktivieren, lesen Sie unsere Dokumentation [wie Sie IAB mit Opt-in](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)einrichten.

Am einfachsten können Sie dies tun, indem Sie [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) verwenden, um [!DNL ECID Opt-in] Ihre Eigenschaften hinzuzufügen. Read the documentation for the [ECID Opt-in extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) to learn how to set up the Launch extension.

## Arbeitsablauf für die Benutzerauswahl bei Verwendung des IAB-Frameworks {#user-choice-workflow}

Wenn Sie eine Webeigenschaft besuchen, können Ihre Benutzer festlegen, wie ihre Daten vom Herausgeber und von Drittanbietern, mit denen der Herausgeber arbeitet, verwendet werden sollen.

Die Nutzer stellen ihre Auswahl in Form der *Zustimmung* und des *berechtigten Interesses* an der IAB gegenüber *Drittanbietern* bereit, die in der Liste des Anbieters registriert sind.

Die folgende Abbildung zeigt ein Beispiel für ein CMP-Dialogfeld, das einem erstmaligen Besucher einer Website angezeigt wird. Beachten Sie, dass dieser Dialog je nach Kundenimplementierung sehr unterschiedlich aussehen kann.

![CMP-Dialogfeld](assets/cmp-example.png)

Einzelheiten zu den verschiedenen Zwecken und Berechtigungen, die in der IAB TCF v2.0 enthalten sind, finden Sie in den Richtlinien des [IAB Europe Transparency &amp; Consent Framework](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Benutzer können ihre Einwilligung oder ihr berechtigtes Interesse (sofern verfügbar) für eine Kombination von Zwecken und Lieferanten gewähren. Beispielsweise könnten Benutzer ihre Zustimmung zur Speicherung von Informationen auf einem Gerät, zur Entwicklung und Verbesserung von Produkten und zur Erteilung ihrer Zustimmung an alle vom CMP angezeigten Drittanbieter erteilen.

Oder in einem anderen Beispiel könnten sie ihre Zustimmung oder ihr berechtigtes Interesse für alle Zwecke erteilen, aber nur einigen Anbietern, die vom CMP gezeigt werden, Einwilligung oder berechtigtes Interesse erteilen.

Sobald der Benutzer seine Datenschutzeinstellungen ausgewählt hat, werden die Benutzerauswahl(en) in der IAB-TC-Zeichenfolge aufgezeichnet. Die IAB-TC-Zeichenfolge speichert die Kombination von genehmigten Zwecken und Anbietern zusammen mit anderen Metadaten (weitere Informationen finden Sie auf der [IAB-Seite](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) ).

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

## Das Verhalten des Audience Managers hängt davon ab, ob der Benutzer seine Zustimmung erteilt {#aam-behavior-consent}

Audience Manager funktioniert unterschiedlich, je nachdem, ob die IAB-TC-Zeichenfolge die Benutzereinwilligung für die beiden Zwecke enthält (Speicherung und/oder Zugriff auf Informationen auf einem Gerät und Entwicklung und Verbesserung von Produkten) oder nicht.

Wir überprüfen auch die Benutzereinwilligung für alle Ziele, mit denen Sie in Audience Manager arbeiten, solange diese Ziele bei IAB TCF registriert sind.

| Wenn Ihr Benutzer seine *Einwilligung* erteilt, Audience Manager: | Wenn Ihr Benutzer seine Zustimmung *ablehnt* , Audience Manager: |
|---|---|
| <ul><li>Führt alle von Ihnen angeforderten Anwendungsfälle des Audience Managers aus.</li><li>Übergibt die Zustimmung an Dritte in ID-Syncs (durch Übergabe `gdpr = 1` und die Zustimmungszeichenfolge wie `gdpr_consent` bei ID-Synchronisierungsaufrufen).</li><li>Wertet die von Anzeigenserverpixeln übergebene Zustimmung aus und berücksichtigt sie.</li><li>Bezeichnet von Partnern initiierte ID-Synchronisierungen.</li></ul> | <ul><li>Speichert keine neuen Benutzerdaten in Ihrer Instanz. Dazu gehören Partner-IDs, Signale, Eigenschaften oder Pixeldaten.</li><li>Initiiert keine Synchronisierung der Drittanbieter-IDs.</li><li>Die ID-Synchronisierungen, die vom Partner initiiert wurden, werden nicht berücksichtigt.</li><li>Der Benutzer wird von der weiteren Datenerfassung ausgeschlossen.</li></ul> |

## Verwendungsfall für Herausgeber {#publisher-use-case}

Durch die Implementierung des Audience Manager-Plug-ins für die IAB-TCF müssen Sie keinen benutzerdefinierten Code für die Verwaltung der Zustimmung in Ihren Webeigenschaften über einen anderen Mechanismus mit Adobe oder anderen Drittanbietern verwalten. Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginn links neben dem Bild:

1. Ein Benutzer besucht eine Ihrer Webeigenschaften. Solange Sie die neuesten Versionen der ECID- und DIL-Bibliotheken verwenden (siehe [Voraussetzungen](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), wird der Abmeldevorgang ausgelöst.
2. Audience Manager prüft, ob der IAB-Durchfluss angewendet wird (`isIabContext=true`). Siehe [Recommendations und Implementierungen](aam-iab-plugin.md#recommendations).
3. Audience Manager prüft, ob GDPR angewendet wird (`gdpr = 1`) und ob eine CMP, die bei IAB TCF registriert ist, in Ihrer Webeigenschaft vorhanden ist. Dies würde beispielsweise für Benutzer gelten, die von der europäischen Vereinigung aus besuchen. Beachten Sie, dass es Ihre Verantwortung als Herausgeber ist, das GDPR-Flag festzulegen.
4. Wenn GDPR angewendet wird, prüft Audience Manager die IAB-TC-Zeichenfolge, die im `gdpr_consent` Parameter übergeben wird, auf die erforderliche Zustimmung. Audience Manager benötigen die Zustimmung zur Speicherung und/oder zum Zugriff auf Informationen auf einem Gerät ([IAB TCF-Zweck 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), zur Entwicklung und Verbesserung von Produkten ([IAB-TCF-Zweck 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)) sowie die Zustimmung des Anbieters zum Speichern, Verarbeiten oder Aktivieren von Daten.
5. Wenn die IAB-TC-Zeichenfolge vorhanden ist und die erforderliche Zustimmung enthält, übergibt Audience Manager die IAB-TC-Zeichenfolge an unsere [Datenerfassungsserver](../../reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager antwortet, indem er im Browser ein [demdex-Cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) setzt und ID-Synchronisierungen von Drittanbietern initiiert und berücksichtigt.
7. Wenn die in Schritt 4 übergebene IAB-TC-Zeichenfolge nicht alle erforderlichen Berechtigungen enthält, erfasst, verarbeitet oder aktiviert Audience Manager keine Benutzerdaten und berücksichtigt keine ID-Synchronisierungen oder initiiert sie nicht. Außerdem wird der Benutzer von den Zielen, mit denen Sie arbeiten, ausgeschlossen.

>[!IMPORTANT]
>
>Wenn Sie mit Audience Manager-Zielpartnern arbeiten, die IAB-TCF-Parameter benötigen, aber keinen CMP haben, der die IAB-TCF auf Ihrer Website unterstützt, sendet Audience Manager ID-Synchronisierungen `gdpr=0` . Dies bedeutet, dass GDPR nicht für diese Benutzer gilt.
>
> Falls dies nicht gewünscht wird, sollten Sie die IAB-TCF-Funktion in Audience Manager aktivieren, um die entsprechenden IAB-TC-Zeichenfolgen an die Zielpartner zu senden.



![Verwendungsfall für Herausgeber](assets/publisher-use-case.png)

## Anwendungsfall für Advertiser {#advertiser-use-case}

Audience Manager bewertet und berücksichtigt die in [Pixelaufrufen](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)übergebene Zustimmung gemäß der IAB-TCF.

Pixel können von Audience Manager auf ihren Partnerseiten platziert werden oder sie werden auf den Anzeigen-Servern platziert, um sie in die Anzeigenantwort einzubeziehen. Im ersten Fall muss Ihr Partner den Parameter &quot;approval&quot;programmgesteuert abrufen und ihn dem Pixel hinzufügen, bevor er ausgelöst wird. Im zweiten Fall, der häufiger vorkommt und unten detailliert beschrieben wird, hängen Anzeigenserver die von der Supply-Side-Platform (SSP) oder dem Herausgeber-Anzeigenserver erhaltenen Zustimmungsparameter an alle Pixel an.

Audience Manager verwendet zwei Parameter, um die Benutzereinwilligung in Pixelaufrufen weiterzugeben:

* `gdpr` kann 0 (GDPR gilt nicht) oder 1 (GDPR gilt) betragen;
* `gdpr_consent` ist die URL-sichere base64-kodierte GDPR-Zustimmungszeichenfolge (siehe [Spezifikation](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Ein Beispielaufruf für ein Impressions-Pixel mit den beiden Parametern könnte wie folgt aussehen:

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginn links neben dem Bild:

1. Ihr Benutzer erhält eine Impression über einen Werbeserver. Dies bedeutet einen [Pixelaufruf](../../integration/media-data-integration/impression-data-pixels.md) an unsere Datenerfassungsserver (Data Collection Servers, DCS).
2. Audience Manager prüft, ob das GDPR-Flag zutrifft. Ist dies nicht der Fall, speichert Audience Manager die in den `gdpr` Variablen und `gdpr_consent` Variablen übergebenen Daten in Pixelaufrufen.
3. Wenn die IAB-TC-Zeichenfolge vorhanden ist und die erforderlichen Berechtigungen enthält, speichert Audience Manager die in den Variablen `gdpr` und übergebenen Daten in Pixelaufrufen `gdpr_consent` .
4. Wenn die IAB-TC-Zeichenfolge fehlt oder die erforderlichen Berechtigungen fehlen, legt der Audience Manager die Daten, die an die Variablen `gdpr` und `gdpr_consent` die Variablen übergeben werden, in Pixelaufrufen ab.

![Anwendungsfall für Advertiser](assets/advertiser-use-case.png)

## Aktivierungen-Partner, die die IAB-TCF unterstützen {#aam-activation-partners}

Mit dem Audience Manager-Plug-in für IAB TCF können Sie die IAB TC-Zeichenfolge an Aktivierungen-Partner weiterleiten und dabei die Datenschutzentscheidungen der Nutzer beachten. Informationen darüber, welche Aktivierung-Partner die IAB TCF unterstützen, finden Sie in unserer [Liste der gerätebasierten Ziele](/help/using/features/destinations/device-based-destinations-list.md).

## Anhängen der Zustimmung zu URLs, die an URL-Ziele gesendet werden

Die Audience Manager-Integration mit IAB TCF v2.0 unterstützt das Anhängen der Zustimmung zu Informationen, die an [URL-Ziele](../../features/destinations/create-url-destination.md) gesendet werden, die in IAB TCF v2.0 integriert sind. Dieser Vorgang wird jedoch nicht automatisch von Audience Manager ausgeführt, um zu vermeiden, dass bestimmte URL-Formate umgangen werden.

Kunden, die die Zustimmung zu den an gesendeten Daten anhängen möchten, [!DNL URL destinations] müssen die URL-Dateien `${GDPR}` und die `${GDPR_CONSENT_XXXX}` -Makros manuell hinzufügen und `XXXX` durch die Ziel-Partner-ID ersetzen.

Beispiel: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Weitere Informationen zu den unterstützten Zielmakros finden Sie unter [Zielmakros definiert](../../features/destinations/destination-macros.md) .

## Geräteübergreifende Verwaltung der Zustimmung

Das Audience Manager-Plug-in für die IAB-TCF meldet die IDs, die bei einer Anforderung vorhanden sind, automatisch ab, wenn Ihre Site-Besucher nicht über die entsprechenden Berechtigungen verfügen. Wenn die Anforderung eine [geräteübergreifende ID (CRM-ID)](../../reference/ids-in-aam.md)enthält, wählt der Audience Manager die ID zusammen mit dem letzten mit dieser [geräteübergreifenden ID (CRM-ID)](../../reference/ids-in-aam.md)verknüpften Gerät aus.

## IAB-Implementierung testen {#test-iab-implementation}

Um zu testen, ob Sie das Audience Manager-Plug-in für die IAB-TCF korrekt implementiert haben, lesen Sie [Verwendungsfall 4 unter Validation Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB und Opt-out in Audience Manager. Rangfolge. {#iab-and-optout}

Eine weitere Datenschutzoption, die Ihren Benutzern zur Verfügung steht, ist die Möglichkeit, die gesamte Datenerfassung zu Opt-out. Adobe stellt Benutzern auf der Seite &quot; [Ihre Datenschutzoptionen](https://www.adobe.com/privacy/opt-out.html#customeruse) &quot;die entsprechenden Mittel zur Verfügung.

Audience Manager behandelt Abmeldeanfragen in einem [separaten Artikel in unserer Dokumentation](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Benutzer, die sich aus der Datenerfassung ausgeschlossen haben, nachdem sie die Zustimmung abgelehnt haben, können nicht wieder aufgenommen werden.

>[!NOTE]
>
>**Reihenfolge der Rangfolge** - Wenn Ihr Benutzer die Datenerfassung mit einem globalen Ausschluss-Tool ablehnt, wie im obigen Link beschrieben, hat dies Vorrang vor der Teilnahme- und IAB-Überprüfung.

## Zusätzliche Ressourcen {#additional-resources}

* [Adobe Experience Platform Identity Service-Teilnahme](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB Europe GDPR - Transparenz und Zustimmung](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR - Transparenz und Zustimmung - Rahmen Technische Spezifikationen](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-Plugin - Videodemonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
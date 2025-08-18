---
description: Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die Opt-in-Funktion und die Unterstützung des IAB Transparency and Consent Framework (TCF) zu verwalten und zu übermitteln. Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: Audience Manager-Plug-In für IAB TCF
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: 8b370a64d80b40124abee91351cbef09711243d4
workflow-type: tm+mt
source-wordcount: '2173'
ht-degree: 29%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Überblick

Ein wichtiger Aspekt in den Datenschutzverpflichtungen, die Sie Ihren Benutzern gegenüber haben können, ist der Erwerb und die Weitergabe von Benutzerentscheidungen darüber, wie ihre personenbezogenen Daten verwendet werden dürfen (d. h. „Zwecke„) und von wem (d. h. „Unternehmen„).

Adobe bietet Ihnen die Möglichkeit, die Datenschutzoptionen Ihrer Benutzer über die [Opt-in-Funktion](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=de) und die Unterstützung des [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) zu verwalten und zu übermitteln.

Dieser Artikel beschreibt die Audience Manager-Anwendungsfälle, die das IAB TCF unterstützen, und wie Sie die IAB TCF-Unterstützung in Audience Manager implementieren.

>[!IMPORTANT]
>
>Audience Manager ist im [IAB TCF) ](https://iabeurope.eu/tcf-for-vendors/) Anbieter-ID 565 registriert.

Das Audience Manager-Plug-in für IAB TCF nutzt die [Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html?lang=de)-Funktion, die wiederum Teil der [Bibliothek des Adobe Experience Platform Identity Services (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=de) ist.

## Umfang und Einschränkungen {#scope-and-limitations}

Als Publisher oder Advertiser, der mit Audience Manager arbeitet, können Sie Audience Manager Benutzeroptionen gemäß IAB TCF vermitteln.

>[!IMPORTANT]
>
>Die IAB TCF-Vorschriften gelten nur für Besucher, die sich im Europäischen Wirtschaftsraum befinden.

Audience Manager hilft Ihnen, die Datenschutzentscheidungen Ihrer Benutzer zu respektieren, und bietet Ihnen eine einfache Möglichkeit, diese Entscheidungen allen Partnern mitzuteilen, mit denen Sie arbeiten.

Derzeit bietet Audience Manager für Folgendes keine Unterstützung:

* Workflows für Mobilgeräte;
* Anhängen des Einverständnisses an Segmentexporte.

## Aktualisieren auf [!DNL IAB TCF v2.2] {#upgrading}

Kunden, die ein Upgrade ihrer [!DNL Audience Manager Plug-in for IAB TCF]-Implementierung von [!DNL IAB TCF] v1.1 auf [!DNL IAB TCF] v2.2 durchführen oder [!DNL IAB TCF] v2.2 zum ersten Mal aktivieren, sollten alle die gleichen Richtlinien zu Voraussetzungen und Implementierung wie unten beschrieben befolgen.

## Voraussetzungen {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager unterstützt IAB TCF v2.2.
>
>Die Unterstützung für IAB TCF v1.1 endet am 15. August 2020.
>
> Kunden, die das Audience Manager-Plug-in für IAB TCF weiterhin für die Einverständnisverwaltung verwenden möchten, sollten zur Fortsetzung des Supports auf die neueste Version [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) aktualisieren.
>
> Nach der Aktualisierung auf die neueste [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)-Version werden die Einverständniszeichenfolgen für IAB TCF v1.1 nicht mehr unterstützt. Aktualisieren Sie daher Ihre CMP, bevor Sie auf die neueste ECID-Version aktualisieren.

Sie müssen die folgenden Voraussetzungen erfüllen, um das Audience Manager-Plug-in für IAB TCF mit Audience Manager verwenden zu können:

1. Sie müssen Adobe Experience Platform Identity Service (ECID) Version 5 (oder neuer) verwenden. [Laden](https://github.com/Adobe-Marketing-Cloud/id-service/releases) Sie unsere neueste ECID-Version herunter.
2. Sie müssen Audience Manager [!DNL Data Integration Library] (DIL) Version 9.0 oder neuer verwenden, die von (hier[ heruntergeladen werden ](https://github.com/Adobe-Marketing-Cloud/dil/releases). Mehr über [DIL erfahren Sie in der Dokumentation zu Audience Manager](../../dil/dil-overview.md). Es wird empfohlen, die Tag-Erweiterung [Adobe Audience Manager zu verwenden](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=de) um die einfachste DIL-Implementierung von Audience Manager zu ermöglichen.
3. Wenn Sie [!DNL Server-Side Forwarding] (SSF) zum Importieren von Daten in Audience Manager verwenden, müssen Sie ein Upgrade auf die neueste Version von AppMeasurement durchführen. Laden Sie AppMeasurement mit dem [Analytics-Code-Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=de) herunter.
4. Sie müssen eine kommerzielle oder eigene Consent Management Platform (CMP) verwenden, die in IAB TCF v2.2 integriert und beim IAB TCF registriert ist. Siehe dazu die Liste der [beim IAB-Framework registrieren CMPs](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Wenn Sie eine Consent Management Platform (CMP) verwenden, die IAB TCF v2.2 nicht unterstützt, sendet Audience Manager den `gdpr=0` Parameter automatisch bei der ID-Synchronisierung, auch wenn sich Ihre Besucher in der Europäischen Union befinden. Um festzustellen, ob Ihre DSGVO-Validierung aktiv ist, empfehlen wir Ihnen, sich mit Ihrer Consent Management Platform (CMP) zu vergewissern, dass sie IAB TCF v2.2 unterstützt.

## Empfehlungen und Implementierungsverfahren {#recommendations}

Um die IAB TCF-Unterstützung in Audience Manager zu aktivieren, lesen Sie unsere Dokumentation [zum Einrichten von IAB mit Opt-in-Funktion](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html?lang=de).

Am einfachsten geht dies, wenn Sie [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=de) verwenden, um [!DNL ECID Opt-in] zu Ihren Eigenschaften hinzuzufügen. Lesen Sie die Dokumentation für die [ECID-Opt-in](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=de)-Erweiterung, um zu erfahren, wie Sie die Tags-Erweiterung einrichten.

## Workflow zur Benutzerauswahl bei Verwendung des IAB-Frameworks {#user-choice-workflow}

Beim Besuch einer Web-Eigenschaft können Ihre Benutzer angeben, wie ihre Daten vom Herausgeber und von den Drittanbietern verwendet werden sollen, mit denen der Herausgeber zusammenarbeitet.

Die Benutzer stellen ihre Auswahl in Form eines *Einverständnisses* für IAB-Zwecke *(Drittanbieter* bereit, die in der globalen Anbieterliste registriert sind.

Das folgende Bild zeigt ein Beispiel für ein CMP-Dialogfeld, das einem erstmaligen Besucher einer Website angezeigt wird. Beachten Sie, dass dieser Dialog je nach Kundenimplementierung sehr unterschiedlich aussehen kann.

![CMP-Dialogfeld](assets/cmp-example.png)

Einzelheiten zu den verschiedenen Zwecken und Berechtigungen in IAB TCF v2.2 finden Sie in den [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Benutzer können ihre Zustimmung für eine Kombination von Zwecken und Anbietern erteilen. Beispielsweise könnten Benutzer ihre Zustimmung zur Speicherung von Informationen auf einem Gerät, zur Entwicklung und Verbesserung von Produkten erteilen und ihre Zustimmung allen Drittanbietern erteilen, die von der CMP angezeigt werden.

Oder in einem anderen Beispiel könnten sie ihre Zustimmung für alle Zwecke erteilen, aber nur einigen wenigen der von der CMP angezeigten Anbieter.

Sobald der Benutzer seine Datenschutzoptionen auswählt, werden diese in der IAB TC-Zeichenfolge aufgezeichnet. Die IAB-TC-Zeichenfolge speichert die Kombination von genehmigten Zwecken und Anbietern zusammen mit anderen Metadateninformationen (weitere Informationen finden Sie [ Seite ](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) IAB).

Jeder im IAB TCF registrierte Anbieter bewertet die IAB TC-Zeichenfolge und trifft Entscheidungen auf der Grundlage der Datenschutzentscheidungen der Benutzer. Beachten Sie, dass die Datenschutzoptionen der Benutzer für alle Anbieter gelten, die bei IAB TCF registriert sind.

## Von Audience Manager benötigte Zwecke {#aam-standard-purposes}

Audience Manager bewertet die in der IAB-TC-Zeichenfolge gespeicherten Benutzeroptionen für die folgenden Zwecke, die in den [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions) definiert sind.

* **Zweck 1** Speicherung und/oder Zugriff auf Informationen auf einem Gerät;
* **Zweck 10**: Entwicklung und Verbesserung von Produkten;
* **Sonderzweck 1**: Gewährleistung der Sicherheit, Verhinderung von Betrug und Fehlerbehebung.

>[!IMPORTANT]
>
>Audience Manager benötigt das Einverständnis für Zweck 1 und Zweck 10 sowie das Einverständnis des Anbieters, um Cookies bereitzustellen und ID-Synchronisierungen zu initiieren oder zu berücksichtigen.
>
>Gemäß [ IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)Vorschriften wird Special Purpose 1 (Gewährleistung der Sicherheit, Verhinderung von Betrug und Debugging) immer zugestimmt, und Benutzer können keine Einwände dagegen erheben.

## Das Verhalten von Audience Manager hängt davon ab, ob der Benutzer sein Einverständnis erteilt {#aam-behavior-consent}

Audience Manager funktioniert unterschiedlich, je nachdem, ob die IAB-TC-Zeichenfolge das Benutzereinverständnis für die beiden Zwecke (Speichern und/oder Zugreifen auf Informationen auf einem Gerät, Entwicklung und Verbesserung von Produkten) enthält oder nicht.

Wir prüfen auch das Benutzereinverständnis für alle Ziele, mit denen Sie in Audience Manager arbeiten, sofern diese Ziele bei IAB TCF registriert sind.

| Wenn Ihr Benutzer seine *Zustimmung erteilt*, wird Audience Manager: | Wenn Ihr Benutzer seine *Zustimmung nicht erteilt*, wird Audience Manager: |
|---|---|
| <ul><li>alle von Ihnen angeforderten Audience Manager-Anwendungsfälle ausführen.</li><li>Übermittelt Einverständnis an Dritte bei ID-Synchronisierungen (durch Übergabe von `gdpr = 1` und der Einverständniszeichenfolge wie bei ID-Synchronisierungsaufrufen `gdpr_consent`).</li><li>die von Adserver-Pixeln übergebene Zustimmung auswerten und berücksichtigen.</li><li>von Partnern initiierte ID-Synchronisierungen berücksichtigen.</li></ul> | <ul><li>keine neuen Benutzerdaten in Ihrer Instanz speichern. Dazu gehören Partner-IDs, Signale, Eigenschaften oder Pixeldaten.</li><li>keine Synchronisierung der Drittanbieter-IDs initiieren.</li><li>von Partnern initiierte ID-Synchronisierungen nicht berücksichtigen.</li><li>Opt den Benutzer von der weiteren Datenerfassung aus.</li></ul> |

## Anwendungsfall für Publisher {#publisher-use-case}

Durch die Implementierung des Audience Manager-Plug-ins für IAB TCF müssen Sie keinen benutzerdefinierten Code für die Einverständnisverwaltung in Ihren Web-Eigenschaften über einen anderen Mechanismus mit Adobe oder anderen Drittanbietern verwalten. Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginnen Sie links im Bild:

1. Ein Benutzer besucht eine Ihrer Web-Eigenschaften. Solange Sie die neuesten Versionen der ECID- und DIL-Bibliotheken verwenden (siehe [Voraussetzungen](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), wird der Opt-in-Fluss ausgelöst.
2. Audience Manager überprüft, ob der IAB-Fluss zutrifft (`isIabContext=true`). Siehe [Empfehlungen und Implementierung](aam-iab-plugin.md#recommendations).
3. Audience Manager prüft, ob die DSGVO (`gdpr = 1`) gilt und ob in Ihrer Web-Eigenschaft eine beim IAB TCF registrierte CMP vorhanden ist. Dies würde beispielsweise für Nutzer gelten, die aus der Europäischen Union kommen. Beachten Sie, dass Sie als Publisher dafür verantwortlich sind, das DSGVO-Flag zu setzen.
4. Wenn die DSGVO gilt, prüft Audience Manager die im `gdpr_consent` übergebene IAB-TC-Zeichenfolge auf die erforderliche Zustimmung. Audience Manager benötigt die Einwilligung zum Speichern und/oder Zugreifen auf Informationen auf einem Gerät ([IAB TCF Purpose 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), Entwickeln und Verbessern von Produkten ([IAB TCF Purpose 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)) sowie die Einwilligung des Audience Manager-Anbieters zum Speichern, Verarbeiten oder Aktivieren von Daten.
5. Wenn die IAB TC-Zeichenfolge vorhanden ist und sie die erforderliche Einwilligung enthält, gibt Audience Manager die IAB TC-Zeichenfolge an unsere [Datenerfassungs-Server](../../reference/system-components/components-data-collection.md) (DCS) weiter.
6. Audience Manager reagiert, indem [demdex-Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=de) im Browser gesetzt wird, und initiiert und berücksichtigt ID-Synchronisierungen von Drittanbietern.
7. Wenn die in Schritt 4 übergebene IAB-TC-Zeichenfolge nicht alle erforderlichen Berechtigungen enthält, erfasst, verarbeitet oder aktiviert Audience Manager keine Benutzerdaten und berücksichtigt keine ID-Synchronisierungen und initiiert keine ID-Synchronisierungen. Außerdem wird der Benutzer von den Zielen, mit denen Sie arbeiten, abgemeldet.

>[!IMPORTANT]
>
>Wenn Sie mit Audience Manager-Zielpartnern arbeiten, die IAB TCF-Parameter benötigen, aber keine CMP haben, die IAB TCF auf Ihrer Website unterstützt, sendet Audience Manager `gdpr=0` bei der ID-Synchronisierung. Dies bedeutet, dass die DSGVO nicht für diese Benutzenden gilt.
>
> Wenn dies nicht gewünscht ist, sollten Sie die IAB TCF-Funktion in Audience Manager aktivieren, um die entsprechenden IAB TC-Zeichenfolgen an die Zielpartner zu senden.



![Anwendungsfall: Publisher ](assets/publisher-use-case.png)

## Anwendungsfall für Advertiser {#advertiser-use-case}

Audience Manager bewertet und berücksichtigt die in [Pixelaufrufen](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md) übergebene Zustimmung gemäß des IAB TCF.

Pixel können von Audience Manager-Kunden auf ihren Partnerseiten platziert werden oder sie werden auf Anzeigen-Servern platziert, die in die Anzeigenantwort aufgenommen werden sollen. Im ersten Fall muss Ihr Partner den Zustimmungsparameter programmgesteuert abrufen und dem Pixel vor dem Auslösen hinzufügen. Im zweiten Fall, der häufiger vorkommt und im Folgenden ausführlich beschrieben wird, hängen Adserver die Zustimmungsparameter, die sie von der SSP (Supply-Side Platform) oder von Adservern des Publishers erhalten, an alle Pixel an.

Audience Manager verwendet zwei Parameter, um die Benutzerzustimmung in Pixelaufrufen weiterzugeben:

* `gdpr` kann 0 (DSGVO trifft nicht zu) oder 1 (DSGVO trifft zu) betragen;
* `gdpr_consent` ist die URL-sichere base64-kodierte DSGVO-Zustimmungszeichenfolge (siehe [Spezifikation](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Ein Beispielaufruf für ein Impressionspixel mit den beiden Parametern könnte wie folgt aussehen:

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Der Anwendungsfall wird im Bild und in den unten stehenden Schritten beschrieben. Beginnen Sie links im Bild:

1. Ihr Benutzer erhält eine Impression über einen Adserver. Dies führt zu einem [Pixel-Aufruf](../../integration/media-data-integration/impression-data-pixels.md) an unsere Datenerfassungs-Server (DCS).
2. Audience Manager überprüft, ob die DSGVO-Markierung gesetzt ist. Ist dies nicht der Fall, speichert Audience Manager die in den `gdpr` übergebenen Daten und `gdpr_consent` Variablen in Pixel-Aufrufen.
3. Wenn die IAB-TC-Zeichenfolge vorhanden ist und sie die erforderlichen Berechtigungen enthält, speichert Audience Manager die in den `gdpr` übergebenen Daten und `gdpr_consent` Variablen in Pixelaufrufen.
4. Wenn die IAB-TC-Zeichenfolge fehlt oder die erforderlichen Berechtigungen fehlen, lässt Audience Manager die in der `gdpr` übergebenen Daten und `gdpr_consent` Variablen in Pixel-Aufrufen fallen.

![Anwendungsfall: Advertiser ](assets/advertiser-use-case.png)

## Aktivierungspartner, die IAB TCF unterstützen {#aam-activation-partners}

Mit dem Audience Manager Plug-in für IAB TCF können Sie die IAB TC-Zeichenfolge an Aktivierungspartner weiterleiten, wobei die Datenschutzentscheidungen der Benutzer respektiert werden. Informationen darüber, welche Aktivierungspartner das IAB TCF unterstützen, finden Sie in unserer [Liste gerätebasierter Ziele](/help/using/features/destinations/device-based-destinations-list.md).

## Anhängen des Einverständnisses an URLs, die an URL-Ziele gesendet werden

Die Audience Manager-Integration mit IAB TCF v2.2 unterstützt das Anhängen des Einverständnisses an Informationen, die an [URL-Ziele](../../features/destinations/create-url-destination.md) gesendet werden, die in IAB TCF v2.2 integriert sind. Dieser Vorgang wird jedoch nicht automatisch von Audience Manager ausgeführt, um zu vermeiden, dass bestimmte URL-Formate beschädigt werden.

Kunden, die ihr Einverständnis zu an [!DNL URL destinations] gesendeten Daten anhängen möchten, müssen die `${GDPR}`- und `${GDPR_CONSENT_XXXX}`-Makros manuell zu ihrem URL-Format hinzufügen und `XXXX` durch die Zielpartner-ID ersetzen.

Beispiel: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Weitere [ zu den unterstützten Zielmakros finden ](../../features/destinations/destination-macros.md) unter „Zielmakros definiert“.

## Geräteübergreifende Einverständnisverwaltung

Das Audience Manager-Plug-in für IAB TCF schließt IDs, die in einer Anfrage vorhanden sind, automatisch aus, wenn Ihre Site-Besucherinnen und -Besucher nicht die entsprechenden Berechtigungen bereitstellen. Wenn die Anfrage eine [geräteübergreifende ID (CRM-ID)](../../reference/ids-in-aam.md) enthält, widerruft Audience Manager die ID sowie das letzte mit dieser verknüpfte Gerät [geräteübergreifende ID (CRM-ID)](../../reference/ids-in-aam.md).

## Testen der IAB-Implementierung {#test-iab-implementation}

Um zu testen, ob Sie das Audience Manager-Plug-in für IAB TCF korrekt implementiert haben, lesen Sie [Anwendungsfall 4 unter Validieren des Opt-in-Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html?lang=de#section-64331998954d4892960dcecd744a6d88).

## IAB und Opt-out in Audience Manager. Rangfolge der Priorität. {#iab-and-optout}

Eine weitere Datenschutzoption, die Ihren Benutzern zur Verfügung steht, ist die Möglichkeit, sich gegen jegliche Datenerfassung zu entscheiden. Adobe stellt Benutzern auf der Seite [Ihre Datenschutzoptionen](https://www.adobe.com/de/privacy/opt-out.html#customeruse) die entsprechenden Mittel zur Verfügung.

Audience Manager behandelt Opt-out-Anfragen in einem [separaten Artikel in unserer Dokumentation](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Benutzende, die von der gesamten Datenerfassung abgemeldet werden, nachdem sie ihre Zustimmung abgelehnt haben, können nicht wieder angemeldet werden.

>[!NOTE]
>
>**Prioritätsfolge** – Wenn Ihr Benutzer die Datenerfassung mit Hilfe eines globalen Opt-out-Tools, wie im obigen Link beschrieben, ablehnt, hat dies Vorrang vor den Opt-in- und IAB-Überprüfungen.

## Zusätzliche Ressourcen {#additional-resources}

* [Adobe Experience Platform Identity Service-Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=de)
* [IAB Europe DSGVO Transparency and Consent Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe DSGVO Transparency and Consent Framework, Technische Spezifikationen](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-Plugin – Videodemonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)

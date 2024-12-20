---
description: Beschreibt die Integration von Audience Manager und die Einhaltung allgemein anerkannter Best Practices in Bezug auf Verbraucherschutz und Opt-out-Verfahren.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: Datenschutz – Überblick
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 52%

---

# Datenschutz – Überblick {#data-privacy}

## Überblick

Die Dokumentation zum Datenschutz beschreibt [!DNL Audience Manager] Integration und die Einhaltung allgemein anerkannter Best Practices im Zusammenhang mit dem Datenschutz und Opt-out von Kundinnen und Kunden.

[!DNL Audience Manager] erkennt die Bedeutung der Beziehung zwischen den Verbrauchern und den Online-Marken, mit denen sie interagieren. Beide Parteien profitieren vom transparenten Austausch pseudonymer Datenelemente:

* Verbraucher erhalten personalisierte Inhalte, vergünstigte Produktangebote und optimierte Benutzererlebnisse.
* Marken erhalten wichtige Umsatzströme, die mehrere Online-Geschäftsmodelle unterstützen.

Im Rahmen unserer kontinuierlichen Unterstützung dieses Modells engagiert sich [!DNL Audience Manager] weiterhin dafür, Ihnen die Tools zur Verfügung zu stellen, die Sie dabei unterstützen, Ihren Kunden Transparenz und Kontrolle zu bieten und gleichzeitig personalisierte Anzeigen gemäß den Selbstregulierungsgrundsätzen von [Online Behavioral Advertising (OBA)](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/) bereitzustellen.

## [!DNL GDPR] {#gdpr}

Mit der [Datenschutz-Grundverordnung (DSGVO)](https://gdpr.eu/data-privacy/) wurden mehrere neue Datenschutzrechte für Mitglieder der Europäischen Union eingeführt, darunter das **Recht auf Zugriff** und das **Recht auf Vergessenwerden**. Das bedeutet, dass jeder [!DNL EU] Bürger, dessen personenbezogene Daten von Ihrem Unternehmen erfasst wurden, jederzeit Auskunft über seine Daten erhalten oder diese löschen kann. Die Nichtbeachtung dieser Anforderungen kann für Ihr Unternehmen Geldstrafen in Millionenhöhe nach sich ziehen.

Um [!DNL GDPR] zu erfüllen, unterstützt [!DNL Audience Manager] Datenzugriffs- und [Anfragen](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

Das [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), das am 1. Januar 2020 in Kraft trat, gewährt den Einwohnern Kaliforniens neue Rechte in Bezug auf ihre personenbezogenen Daten und legt bestimmten Unternehmen, die in Kalifornien geschäftlich tätig sind, Datenschutzpflichten auf.

[!DNL CCPA] bietet neue Datenschutzrechte, mit denen Verbraucher beispielsweise ihre personenbezogenen Daten einsehen und löschen oder herausfinden können, ob (und an wen) ihre Daten verkauft oder weitergegeben wurden. Um [!DNL CCPA] zu erfüllen, unterstützt [!DNL Audience Manager] [!DNL CCPA] Zugriffs- und [Anfragen](data-privacy-requests.md).

Weitere Informationen finden Sie im [Adobe Privacy Center](https://www.adobe.com/de/privacy/opt-out.html).

## Einhaltung von Vorschriften {#compliance}

[!DNL Audience Manager] hilft Ihnen bei der Einhaltung Ihrer Verpflichtungen aus bestimmten Datenschutzbestimmungen mithilfe von Datenschutztools wie dem [Adobe Experience Platform Privacy Service ](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) für Datenzugriffs- und Löschanfragen.

Dieser Dienst bietet eine [!DNL RESTful API] und eine Benutzeroberfläche, die Sie bei der Verwaltung von Datenanfragen von Verbrauchern unterstützen. Mithilfe des [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) können Sie auf Anfrage eines einzelnen Verbrauchers Anfragen zum Zugriff auf und zum Löschen personenbezogener Daten senden, um diesen Teil Ihrer Compliance-Verpflichtungen zu automatisieren.

Während Datenzugriffs- und Löschanfragen über den Privacy Service verarbeitet werden, werden [Opt-out](data-privacy-requests.md#opt-out-requests)Anfragen derzeit über die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) unterstützt. Weitere Informationen finden Sie unter [Datenschutzanfragen](data-privacy-requests.md).

## Verwandte Konzepte {#related-concepts}

* [Datenschutzanfragen](data-privacy-requests.md)
* [Zustimmungsverwaltung](data-privacy-consent.md)
* [Audience Manager-Plug-In für IAB TCF](aam-iab-plugin.md)
* [Audience Manager-IDs](data-privacy-ids.md)
* [CCPA-Glossar](aam-ccpa-glossary.md)
* [DSGVO-Glossar](aam-gdpr-glossary.md)
* [DSGVO-Überlegungen für Ziele](aam-gdpr-partners.md)
* [DSGVO-Bereitschaftsleitfaden für Audience Manager-Kunden](aam-gdpr-readiness.md)
* [Data Governance](data-governance.md)
* [Häufig gestellte Fragen zu Datenschutz und Datenaufbewahrung](../../faq/faq-privacy.md)

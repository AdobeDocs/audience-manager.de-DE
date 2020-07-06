---
description: Beschreibt die Integration von Audience Manager und die Einhaltung allgemein anerkannter Best Practices in Bezug auf Verbraucherschutz und Opt-out-Verfahren.
seo-description: Beschreibt die Integration von Audience Manager und die Einhaltung allgemein anerkannter Best Practices in Bezug auf Verbraucherschutz und Opt-out-Verfahren.
seo-title: Datenschutz – Überblick
solution: Audience Manager
title: Datenschutz – Überblick
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Datenschutz – Überblick {#data-privacy}

## Überblick

The Data Privacy documentation describes [!DNL Audience Manager] integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

[!DNL Audience Manager] erkennt die Bedeutung der Beziehung zwischen Verbrauchern und den Online-Marken, mit denen sie interagieren. Beide Parteien profitieren vom transparenten Austausch pseudonymer Datenelemente:

* Verbraucher erhalten personalisierte Inhalte, vergünstigte Produktangebote und optimierte Benutzererlebnisse.
* Marken erhalten wichtige Umsatzströme, die mehrere Online-Geschäftsmodelle unterstützen.

In our continuing support of this model, [!DNL Audience Manager] remains committed to providing you with the tools to help support your ability to provide  transparency and control to your consumers, while delivering personalized ads subject to the [Online Behavioral Advertising (OBA) Self-Regulatory Principles](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

Mit der [Datenschutz-Grundverordnung (DSGVO)](https://eugdpr.org/) wurden mehrere neue Datenschutzrechte für Mitglieder der Europäischen Union eingeführt, darunter das **Recht auf Zugriff** und das **Recht auf Vergessenwerden**. This means that any [!DNL EU] citizen whose personal data has been collected by your business can request to access or delete their data at any time. Die Nichtbeachtung dieser Anforderungen kann für Ihr Unternehmen Geldstrafen in Millionenhöhe nach sich ziehen.

To comply with [!DNL GDPR], [!DNL Audience Manager] supports data access and delete [requests](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

Das [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), das am 1. Januar 2020 in Kraft trat, gewährt den Einwohnern Kaliforniens neue Rechte in Bezug auf ihre personenbezogenen Daten und legt bestimmten Unternehmen, die in Kalifornien geschäftlich tätig sind, Datenschutzpflichten auf.

[!DNL CCPA]Das bietet Einwohnern Kaliforniens neue Datenschutzrechte, einschließlich des Rechts, auf ihre personenbezogenen Daten zuzugreifen und diese zu löschen und zu erfahren, ob ihre persönlichen Daten verkauft oder weitergegeben werden (und an wen). Zur Einhaltung [!DNL CCPA]der Anforderungen [!DNL Audience Manager] unterstützt [!DNL CCPA] den Zugriff und das Löschen von [Anforderungen](data-privacy-requests.md).

Weitere Informationen finden Sie im [Adobe Privacy Center](https://www.adobe.com/de/privacy/opt-out.html).

## Einhaltung von Vorschriften {#compliance}

[!DNL Audience Manager]Mit können Sie Ihre Verpflichtungen aus bestimmten Datenschutzbestimmungen durch Datenschutz-Tools wie den [Adobe Experience Platform Privacy Service](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html) für Datenzugriffs- und Löschanfragen erfüllen.

Dieser Dienst bietet eine [!DNL RESTful API] und eine Benutzeroberfläche, die Sie bei der Verwaltung von Datenanfragen von Verbrauchern unterstützen. Mithilfe des [Privacy Service](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html) können Sie auf Anfrage eines einzelnen Verbrauchers Anfragen zum Zugriff auf und zum Löschen personenbezogener Daten senden, um diesen Teil Ihrer Compliance-Verpflichtungen zu automatisieren.

Während Datenzugriffs- und Löschanfragen über den [Privacy Service](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html) verarbeitet werden, werden [Opt-out-Anfragen](data-privacy-requests.md#opt-out-requests) derzeit über die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) unterstützt. Weitere Informationen finden Sie unter [Datenschutzanfragen](data-privacy-requests.md).

## Verwandte Konzepte {#related-concepts}

* [Datenschutzanfragen](data-privacy-requests.md)
* [Zustimmungsverwaltung](data-privacy-consent.md)
* [Audience Manager-Plug-In für IAB TCF](aam-iab-plugin.md)
* [Audience Manager-IDs](data-privacy-ids.md)
* [CCPA-Glossar](aam-ccpa-glossary.md)
* [DSGVO-Glossar](aam-gdpr-glossary.md)
* [DSGVO-Überlegungen für Ziele](aam-gdpr-partners.md)
* [DSGVO-Bereitschaftsleitfaden für Audience Manager-Kunden](aam-gdpr-readiness.md)
* [Data Governance](data-governance.md)
* [Häufig gestellte Fragen zu Datenschutz und Datenhaltung](../../faq/faq-privacy.md)
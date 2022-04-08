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
source-wordcount: '460'
ht-degree: 68%

---

# Datenschutz – Überblick {#data-privacy}

## Überblick

Die Datenschutzdokumentation beschreibt [!DNL Audience Manager] Integration und Einhaltung allgemein anerkannter Best Practices in Bezug auf Privatsphäre und Opt-out-Verfahren der Verbraucher.

[!DNL Audience Manager] erkennt die Bedeutung der Beziehung zwischen Verbrauchern und den Online-Marken, mit denen sie interagieren. Beide Parteien profitieren vom transparenten Austausch pseudonymer Datenelemente:

* Verbraucher erhalten personalisierte Inhalte, vergünstigte Produktangebote und optimierte Benutzererlebnisse.
* Marken erhalten wichtige Umsatzströme, die mehrere Online-Geschäftsmodelle unterstützen.

In unserer kontinuierlichen Unterstützung dieses Modells [!DNL Audience Manager] wird Ihnen weiterhin die Tools zur Verfügung stellen, mit denen Sie Ihre Fähigkeit unterstützen, Ihren Kunden Transparenz und Kontrolle zu bieten, während Sie personalisierte Anzeigen bereitstellen, die dem [Selbstregulierungsgrundsätze für Online-Verhaltenswerbung (OBA)](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

Mit der [Datenschutz-Grundverordnung (DSGVO)](https://gdpr.eu/data-privacy/) wurden mehrere neue Datenschutzrechte für Mitglieder der Europäischen Union eingeführt, darunter das **Recht auf Zugriff** und das **Recht auf Vergessenwerden**. Dies bedeutet, dass [!DNL EU] Bürger, deren personenbezogene Daten von Ihrem Unternehmen erfasst wurden, können jederzeit den Zugriff auf oder die Löschung ihrer Daten anfordern. Die Nichtbeachtung dieser Anforderungen kann für Ihr Unternehmen Geldstrafen in Millionenhöhe nach sich ziehen.

Einhaltung von [!DNL GDPR], [!DNL Audience Manager] unterstützt Datenzugriff und -löschung [requests](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

Das [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), das am 1. Januar 2020 in Kraft trat, gewährt den Einwohnern Kaliforniens neue Rechte in Bezug auf ihre personenbezogenen Daten und legt bestimmten Unternehmen, die in Kalifornien geschäftlich tätig sind, Datenschutzpflichten auf.

[!DNL CCPA]Das bietet Einwohnern Kaliforniens neue Datenschutzrechte, einschließlich des Rechts, auf ihre personenbezogenen Daten zuzugreifen und diese zu löschen und zu erfahren, ob ihre persönlichen Daten verkauft oder weitergegeben werden (und an wen). Einhaltung von [!DNL CCPA], [!DNL Audience Manager] unterstützt [!DNL CCPA] Zugriff und Löschen [requests](data-privacy-requests.md).

Weitere Informationen finden Sie im [Adobe Privacy Center](https://www.adobe.com/de/privacy/opt-out.html).

## Einhaltung von Vorschriften {#compliance}

[!DNL Audience Manager]Mit können Sie Ihre Verpflichtungen aus bestimmten Datenschutzbestimmungen durch Datenschutz-Tools wie den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) für Datenzugriffs- und Löschanfragen erfüllen.

Dieser Dienst bietet eine [!DNL RESTful API] und eine Benutzeroberfläche, die Sie bei der Verwaltung von Datenanfragen von Verbrauchern unterstützen. Mithilfe des [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) können Sie auf Anfrage eines einzelnen Verbrauchers Anfragen zum Zugriff auf und zum Löschen personenbezogener Daten senden, um diesen Teil Ihrer Compliance-Verpflichtungen zu automatisieren.

Während Datenzugriffs- und Löschanfragen über den Privacy Service verarbeitet werden, [Opt-out-Anfragen](data-privacy-requests.md#opt-out-requests) werden derzeit über die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Weitere Informationen finden Sie unter [Datenschutzanfragen](data-privacy-requests.md).

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
* [Häufig gestellte Fragen zu Datenschutz und Datenaufbewahrung](../../faq/faq-privacy.md)

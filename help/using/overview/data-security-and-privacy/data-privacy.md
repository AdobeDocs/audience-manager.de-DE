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
source-wordcount: '485'
ht-degree: 78%

---


# Datenschutz – Überblick {#data-privacy}

## Überblick

In der Datenschutzdokumentation werden die [!DNL Audience Manager]-Integration und die Einhaltung allgemein anerkannter Best Practices zum Schutz der Privatsphäre von Verbrauchern und Ausschluss-Verfahren beschrieben.

[!DNL Audience Manager] erkennt die Bedeutung der Beziehung zwischen Verbrauchern und den Online-Marken, mit denen sie interagieren. Beide Parteien profitieren vom transparenten Austausch pseudonymer Datenelemente:

* Verbraucher erhalten personalisierte Inhalte, vergünstigte Produktangebote und optimierte Benutzererlebnisse.
* Marken erhalten wichtige Umsatzströme, die mehrere Online-Geschäftsmodelle unterstützen.

[!DNL Audience Manager] wird dieses Modell auch weiterhin unterstützen und Sie mit den Werkzeugen unterstützen, die Sie bei der Transparenz und Kontrolle Ihrer Kunden unterstützen. Gleichzeitig bieten wir Ihnen personalisierte Anzeigen an, die den Selbstregulierungsgrundsätzen der [Online-verhaltensbasierten Werbung (OBA) unterliegen.](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/)

## [!DNL GDPR] {#gdpr}

Mit der [Datenschutz-Grundverordnung (DSGVO)](https://eugdpr.org/) wurden mehrere neue Datenschutzrechte für Mitglieder der Europäischen Union eingeführt, darunter das **Recht auf Zugriff** und das **Recht auf Vergessenwerden**. Das bedeutet, dass jeder [!DNL EU]-Bürger, dessen personenbezogene Daten von Ihrem Unternehmen gesammelt wurden, jederzeit den Zugriff auf seine Daten oder deren Löschung anfordern kann. Die Nichtbeachtung dieser Anforderungen kann für Ihr Unternehmen Geldstrafen in Millionenhöhe nach sich ziehen.

Um [!DNL GDPR] einzuhalten, unterstützt [!DNL Audience Manager] den Datenzugriff und das Löschen von [Anforderungen](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

Das [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), das am 1. Januar 2020 in Kraft trat, gewährt den Einwohnern Kaliforniens neue Rechte in Bezug auf ihre personenbezogenen Daten und legt bestimmten Unternehmen, die in Kalifornien geschäftlich tätig sind, Datenschutzpflichten auf.

[!DNL CCPA]Das bietet Einwohnern Kaliforniens neue Datenschutzrechte, einschließlich des Rechts, auf ihre personenbezogenen Daten zuzugreifen und diese zu löschen und zu erfahren, ob ihre persönlichen Daten verkauft oder weitergegeben werden (und an wen). Um [!DNL CCPA] einzuhalten, unterstützt [!DNL Audience Manager] den Zugriff und Löschung [Anforderungen](data-privacy-requests.md).[!DNL CCPA]

Weitere Informationen finden Sie im [Adobe Privacy Center](https://www.adobe.com/de/privacy/opt-out.html).

## Einhaltung von Vorschriften {#compliance}

[!DNL Audience Manager]Mit können Sie Ihre Verpflichtungen aus bestimmten Datenschutzbestimmungen durch Datenschutz-Tools wie den [Adobe Experience Platform Privacy Service](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html) für Datenzugriffs- und Löschanfragen erfüllen.

Dieser Dienst bietet eine [!DNL RESTful API] und eine Benutzeroberfläche, die Sie bei der Verwaltung von Datenanfragen von Verbrauchern unterstützen. Mithilfe des [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) können Sie auf Anfrage eines einzelnen Verbrauchers Anfragen zum Zugriff auf und zum Löschen personenbezogener Daten senden, um diesen Teil Ihrer Compliance-Verpflichtungen zu automatisieren.

Während Datenzugriffs- und Löschanfragen über den [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) verarbeitet werden, werden [Opt-out-Anfragen](data-privacy-requests.md#opt-out-requests) derzeit über die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) unterstützt. Weitere Informationen finden Sie unter [Datenschutzanfragen](data-privacy-requests.md).

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
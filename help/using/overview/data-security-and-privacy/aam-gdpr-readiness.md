---
description: DSGVO-Bereitschaftsleitfaden für Audience Manager-Kunden
seo-description: GDPR Readiness Guidance for Audience Manager Customers
seo-title: GDPR Readiness Guidance for Audience Manager Customers
solution: Audience Manager
title: DSGVO-Bereitschaftsleitfaden für Audience Manager-Kunden
feature: Data Governance & Privacy
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
TQID: https://experienceleague.adobe.com/K72pQ8Q6yILWexkG38Hc5W1roYObFvhLE5A0GSCyhYE
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cbid: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 98%

---

# Handbuch zur DSGVO-Bereitschaft für Audience Manager-Kunden (Datenverantwortliche) {#gdpr-readiness-guidance}

Audience Manager empfiehlt, im Bereich der Data Governance und der Organisationsbereitschaft proaktiv zu sein. Auf diese Weise können Sie sicherstellen, dass Ihre Verbraucherdaten für Prozesse im Zusammenhang mit Zugriffs- oder Löschanfragen organisiert werden, Ihre Teams in die Lage versetzt werden, diese Anfragen zu verwalten, und dass Ihre Verbraucher (betroffene Personen) ein positives, differenziertes Erlebnis mit Ihrer Marke haben.

Als Ihr Datenverarbeiter kann Adobe keine Rechtsberatung zu den DSGVO-Anforderungen und dem Verfahren zur Einholung der Einwilligung Ihrer betroffenen Personen anbieten. Bitte wenden Sie sich an Ihren Rechtsberater, um Ratschläge zur DSGVO-Konformität Ihrer Organisation zu erhalten.

## Data Governance: Machen Sie sich Gedanken darüber, wie Ihre Verbraucherdaten in Ihrer in Audience Manager-Instanz verwaltet werden.

* Überprüfen Sie die verschiedenen Kunden-IDs, die Ihre Marketing-Teams verwenden, um Benutzer in Audience Manager zu identifizieren, sowie die Datenquellen, in denen sie gespeichert sind. Dadurch wird der Prozess für Anfragen (wie Löschen oder Zugriff) rationalisiert, da bestimmte Datentypen von Ihren Teams vor der Aufnahme in Audience Manager gehasht werden.
* IDFA-/GAID-IDs für mobile Geräte werden in Audience Manager für mehrere Anwendungsfälle verwendet. Wenn Sie das Adobe Mobile SDK verwenden, stellen Sie sicher, dass Sie die Experience Cloud ID (MID) zusammen mit IDFA/GAID senden, um sicherzustellen, dass die DSGVO-Antworten vollständig sind.
* Da die Definition personenbezogener Daten immer umfassender wird, können IP-Adressen als personenbezogene Daten in Ihrer Region betrachtet werden. Wenden Sie sich proaktiv an Adobe Consulting, um das letzte Oktett zu verschleiern.
* Legen Sie eine Validierungs-/Authentifizierungsrichtlinie und einen Prozess zur Bestätigung der Identität einer betroffenen Person fest, wenn diese eine DSGVO-Anfrage übermittelt.
* Erwägen Sie die Verwendung von [Datenexportkontrollen](../../features/data-export-controls.md), um die Aktivierung von Zielgruppen für Technologien zu blockieren, in denen personenbezogene Daten gespeichert sind. Segmente mit Drittanbieterdaten sollten beispielsweise nicht E-Mail-Dienstleistern zur Verfügung gestellt werden. Legen Sie eine [!UICONTROL Data Export Control] fest, um sicherzustellen, dass diese Daten nicht versehentlich aktiviert werden können.
* Verwenden Sie zunächst [rollenbasierte Zugriffskontrollen](../../features/administration/administration-overview.md), um sicherzustellen, dass die richtigen Teams Zugriff auf die gewünschten Daten haben.
* Erwägen Sie geeignete [Aufbewahrungsfristen](../../faq/faq-privacy.md#data-retention-faq) für die Daten.
* Überprüfen Sie die Richtlinien zur Identitätsverknüpfung und zum Datenschutz sowie die gesetzlichen Anforderungen, um festzustellen, wann und wo es angebracht ist, Identitätssätze miteinander zu verknüpfen. Stellen Sie die angemessene Verwendung über die [Profilzusammenführungsrichtlinien](../../features/profile-merge-rules/merge-rules-overview.md) von Audience Manager sicher.

## Organisationsbereitschaft: Einrichten eines Geschäftsprozesses

* Identifizieren Sie einen Prozess zum Empfangen / Beantworten von Anfragen betroffener Personen. Erwägen Sie die Erstellung eines automatisierten Tools zum Senden von Anfragen an Audience Manager.
* Ernennen Sie einen Datenschutzbeauftragen in Ihrem DMP-Kompetenzzentrum. Verbinden Sie den Datenschutzbeauftragten Ihres Unternehmens mit Ihrem Audience Manager-Produktnutzungsteam, um zu erfahren, wie Sie Ihre Anforderungen an die Eingabe-ID verwalten können.
* Führen Sie vor der Weitergabe an die betroffene Person eine Datenüberprüfung durch. Dokumentieren Sie die Schritte, die Sie unternommen haben, um die Verantwortlichkeit zu ermitteln.

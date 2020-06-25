---
description: GDPR-Bereitschaftsleitlinie für Audience Manager
seo-description: GDPR-Bereitschaftsleitlinie für Audience Manager
seo-title: GDPR-Bereitschaftsleitlinie für Audience Manager
solution: Audience Manager
title: GDPR-Bereitschaftsleitlinie für Audience Manager
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# GDPR Readiness Guidance for Audience Manager Customers (Data Controllers) {#gdpr-readiness-guidance}

Der Audience Manager empfiehlt, im Bereich der Datenverwaltung und der organisatorischen Vorbereitung proaktiv zu sein. Auf diese Weise können Sie sicherstellen, dass Ihre Verbraucherdaten für Prozesse organisiert werden, die mit dem Zugriff oder Löschen von Anforderungen zusammenhängen. Ihre Teams werden in die Lage versetzt und in die Lage versetzt, diese Anforderungen zu verwalten, und Ihre Verbraucher (Datensubjekte) verfügen über eine positive, differenzierte Erfahrung mit Ihrer Marke.

Als Datenprozessor kann Adobe keine Rechtsberatung zu GDPR-Anforderungen und zum Verfahren zur Einholung der Einwilligung Ihrer Datensubjekte erteilen. Bitte konsultieren Sie Ihren Rechtsbeistand, um Anleitungen zur Einhaltung der GDPR für Ihre Einrichtung zu erhalten.

## Datenverwaltung: Beginn, die sich Gedanken darüber machen, wie Ihre Verbraucherdaten in Ihrer Audience Manager-Instanz verwaltet werden

* Überprüfen Sie die verschiedenen Kunden-IDs, die Ihre Marketingteams verwenden, um Benutzer in Audience Manager zu identifizieren, sowie die Datenquellen, in denen sie gespeichert sind. Auf diese Weise wird der Prozess für Anforderungen (z. B. Löschen oder Zugriff) vereinfacht, da bestimmte Datentypen von Ihren Teams vor der Erfassung in Audience Manager mit Hashing gesendet werden.
* IDFA-/GAID-Mobilgeräte-IDs werden in Audience Managern für mehrere Anwendungsfälle verwendet. Wenn Sie Adobe Mobile SDK verwenden, müssen Sie die Experience Cloud-ID (MID) zusammen mit IDFA/GAID übermitteln, um sicherzustellen, dass die GDPR-Antworten vollständig sind.
* Da die Definition personenbezogener Daten immer umfassender wird, können IP-Adressen als personenbezogene Daten in Ihrer Region betrachtet werden. Wenden Sie sich proaktiv an Adobe Consulting, um das letzte Oktett zu verschleiern.
* Legen Sie eine Validierungs-/Authentifizierungsrichtlinie und einen Prozess zur Bestätigung der Identität eines Datenbetreibers fest, wenn dieser eine GDPR-Anforderung abgibt.
* Erwägen Sie die Verwendung von [Datenexportkontrollen](../../features/data-export-controls.md) , um die Aktivierung der Audience mit Technologien zu blockieren, in denen personenbezogene Daten gespeichert sind. Segmente mit Drittanbieterdaten sollten beispielsweise nicht mit E-Mail-Dienstleistern synchronisiert werden. Stellen Sie eine [!UICONTROL Data Export Control] ein, um sicherzustellen, dass diese Daten nicht versehentlich aktiviert werden können.
* Verwenden Sie zunächst [rollenbasierte Zugriffskontrollen](../../features/administration/administration-overview.md) , um sicherzustellen, dass die richtigen Teams Zugriff auf die gewünschten Daten haben.
* Erwägen Sie geeignete [Aufbewahrungszeiträume](../../faq/faq-privacy.md#data-retention-faq) für die Daten.
* Überprüfung der Identitätsverknüpfung und der Datenschutzrichtlinien und der rechtlichen Anforderungen, um festzustellen, wann und wo Identitätsgruppen miteinander verknüpft werden sollten; verwenden Sie die [Profil Merge Rules](../../features/profile-merge-rules/merge-rules-overview.md)des Audience Managers entsprechend.

## Organisationsbereitschaft: Geschäftsprozess einrichten

* Identifizieren Sie einen Prozess zum Empfangen/Antworten auf Datenfach-Anfragen. Sie sollten ein automatisiertes Tool erstellen, um Anforderungen an Audience Manager zu senden.
* Benennen Sie einen Ansprechpartner für die Privatsphäre in Ihrem DMP-Kompetenzzentrum. Verbinden Sie den Datenschutzbeauftragten Ihres Unternehmens mit dem Produktverwendungsteam Ihres Audience Managers, um zu verstehen, wie Sie Ihre Eingabe-ID-Anforderungen verwalten können.
* Führen Sie vor der Freigabe für das Datenfach eine Datenprüfung durch. Dokument der von Ihnen eingerichteten Schritte zur Feststellung der Verantwortlichkeit.

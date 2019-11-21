---
description: GDPR-Versionshinweise für Audience Manager-Kunden
seo-description: GDPR-Versionshinweise für Audience Manager-Kunden
seo-title: GDPR-Versionshinweise für Audience Manager-Kunden
solution: Audience Manager
title: GDPR-Versionshinweise für Audience Manager-Kunden
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# GDPR Readiness Guidance for Audience Manager Customers (Data Controllers) {#gdpr-readiness-guidance}

Audience Manager empfiehlt, in den Bereichen Datenverwaltung und Organisationsbereitschaft proaktiv zu sein. Auf diese Weise können Sie sicherstellen, dass Ihre Verbraucherdaten für Prozesse organisiert werden, die mit dem Zugriff oder Löschen von Anforderungen zusammenhängen. Ihre Teams werden in die Lage versetzt und in die Lage versetzt, diese Anforderungen zu verwalten, und Ihre Verbraucher (Datensubjekte) verfügen über eine positive, differenzierte Erfahrung mit Ihrer Marke.

Als Datenprozessor kann Adobe keine Rechtsberatung zu GDPR-Anforderungen und zum Verfahren zur Einholung der Einwilligung Ihrer Datensubjekte erteilen. Bitte konsultieren Sie Ihren Rechtsbeistand, um Anleitungen zur Einhaltung der GDPR für Ihre Einrichtung zu erhalten.

## Datenverwaltung: Denken Sie darüber nach, wie Ihre Verbraucherdaten in Ihrer Audience Manager-Instanz verwaltet werden

* Überprüfen Sie die verschiedenen Kunden-IDs, die Ihre Marketingteams zur Identifizierung von Benutzern in Audience Manager verwenden, zusammen mit den Datenquellen, in denen sie gespeichert sind. Dadurch wird der Prozess für Anforderungen (z. B. Löschen oder Zugriff) optimiert, da bestimmte Datentypen von Ihren Teams vor der Erfassung in Audience Manager gehasht werden.
* IDFA/GAID-Mobilgeräte-IDs werden in Audience Manager für mehrere Anwendungsfälle verwendet. Wenn Sie Adobe Mobile SDK verwenden, stellen Sie sicher, dass Sie die Experience Cloud ID (MID) zusammen mit IDFA/GAID übermitteln, um sicherzustellen, dass die GDPR-Antworten vollständig sind.
* Da die Definition personenbezogener Daten immer umfassender wird, können IP-Adressen als personenbezogene Daten in Ihrer Region betrachtet werden. Wenden Sie sich proaktiv an Adobe Consulting, um das letzte Oktett zu verschleiern.
* Legen Sie eine Validierungs-/Authentifizierungsrichtlinie und einen Prozess zur Bestätigung der Identität eines Datenbetreibers fest, wenn dieser eine GDPR-Anforderung abgibt.
* Erwägen Sie die Verwendung von [Datenexportsteuerelementen](../../features/data-export-controls.md) , um die Aktivierung der Zielgruppe für Technologien zu blockieren, in denen personenbezogene Daten gespeichert sind. Segmente mit Drittanbieterdaten sollten beispielsweise nicht mit E-Mail-Dienstanbietern synchronisiert werden. Stellen Sie eine [!UICONTROL Data Export Control] ein, um sicherzustellen, dass diese Daten nicht versehentlich aktiviert werden können.
* Verwenden Sie zunächst [rollenbasierte Zugriffssteuerungselemente](../../features/administration/administration-overview.md) , um sicherzustellen, dass die richtigen Teams Zugriff auf die gewünschten Daten haben.
* Erwägen Sie geeignete [Aufbewahrungszeiträume](../../faq/faq-privacy.md#data-retention-faq) für die Daten.
* Überprüfung der Identitätsverknüpfung und der Datenschutzrichtlinien und der rechtlichen Anforderungen, um festzustellen, wann und wo Identitätsgruppen miteinander verknüpft werden sollten; Verwenden Sie die [Profilzusammenführungsregeln](../../features/profile-merge-rules/merge-rules-overview.md)von Audience Manager entsprechend.

## Organisationsbereitschaft: Geschäftsprozess einrichten

* Identifizieren Sie einen Prozess zum Empfangen/Antworten auf Datenfach-Anfragen. Sie sollten ein automatisiertes Tool erstellen, um Anforderungen an Audience Manager zu senden.
* Benennen Sie einen Ansprechpartner für die Privatsphäre in Ihrem DMP-Kompetenzzentrum. Verbinden Sie den Datenschutzbeauftragten Ihres Unternehmens mit Ihrem Audience Manager-Produktnutzungsteam, um zu verstehen, wie Sie Ihre Eingabe-ID-Anforderungen verwalten können.
* Führen Sie vor der Freigabe für das Datenfach eine Datenprüfung durch. Dokumentieren Sie die Schritte, die Sie eingerichtet haben, um Ihnen bei der Feststellung der Verantwortlichkeit behilflich zu sein.

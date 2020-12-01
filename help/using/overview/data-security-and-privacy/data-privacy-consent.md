---
description: In diesem Dokument wird erläutert, wie die Zustimmungsverwaltung in Audience Manager funktioniert.
seo-description: In diesem Dokument wird erläutert, wie die Zustimmungsverwaltung in Audience Manager funktioniert.
seo-title: Zustimmungsverwaltung
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Zustimmungsverwaltung
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 100%

---


# Zustimmungsverwaltung

## Überblick {#overview}

In Fällen, in denen die Zustimmung für bestimmte Marketing-Aktivitäten erforderlich ist, müssen Audience Manager-Kunden den Umfang und die Notwendigkeit festlegen, ob bestimmter Zustimmungen aktualisiert werden müssen, um die Daten in Zukunft weiterhin nutzen zu können.

Audience Manager bietet Ihnen Tools, mit denen Sie die erforderlichen Benutzerzustimmungen einholen können, damit Sie ihnen kanalübergreifend personalisierte Erlebnisse bieten können. 

>[!IMPORTANT]
>
> Die Inhalte dieses Dokuments ersetzen keine rechtliche Beratung.
>
> Als Ihr Datenverarbeiter kann Adobe keine rechtliche Beratung zum Erhalt der Zustimmung erteilen. Möglicherweise möchten Sie auch mit einem Anbieter von Lösungen für die Zustimmungsverwaltung wie [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) oder [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) zusammenarbeiten und sich bei der Einrichtung Ihrer Opt-in-Implementierung an die Rechtsabteilung Ihres Unternehmens wenden, um Ratschläge zu Zustimmungen und Praktiken zu erhalten.

## Opt-in-Dienst für Experience Cloud

Mit dem [Opt-in-Dienst für Experience Cloud](https://docs.adobe.com/content/help/de-DE/id-service/using/implementation/opt-in-service/optin-overview.html) können Sie Protokolle für den Besucher einrichten, um zu bestimmen, ob Sie ein Cookie auf dem Gerät oder im Browser des Benutzers setzen können, wenn dieser Ihre Site besucht.

Dies eine Erweiterung von [!DNL Experience Cloud ID (ECID) Service] und ermöglicht Ihnen zu steuern, ob und welche Experience Cloud-Lösungen Cookies auf Webseiten für Besucher setzen können, bevor die Besucher zugestimmt haben.

Mit dem [Opt-in-Dienst für Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) können Sie außerdem Protokolle zur Integration in Ihre Consent Management Platform (CMP) und vorhandene Systeme als Teil Ihres umfassenderen Designs festlegen.

## Verwalten der Opt-in-Funktion/Einholen der Zustimmung

Audience Manager-Kunden können die Benutzerzustimmung für verschiedene Anwendungsfälle wie Werbung oder Personalisierung als Eigenschaften in Audience Manager zu speichern. Segmente, die Sie mit diesen Eigenschaften erstellen, umfassen dann nur Benutzer, die die entsprechende Zustimmung für jeden dieser Anwendungsfälle erteilen. Beachten Sie, dass die Verwendung dieses Ansatzes die Datenerfassung nicht stoppt, sondern sich nur auf die Datennutzung auswirkt, wenn Sie Segmente zur Aktivierung senden. Wenn Benutzer ihre Einwilligung widerrufen, können Sie diese Eigenschaften mithilfe des [eingehenden Batch-Prozesses](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) von Audience Manager oder des Opt-out-Prozesses von Audience Manager (siehe unten) aus dem Benutzerprofil entfernen.

## Verwalten der Opt-out-Funktion/Widerrufen der Zustimmung

Die Opt-out-Funktion kann für Adobe Experience Cloud über die Seite [Ihre Datenschutzoptionen](https://www.adobe.com/de/privacy/opt-out.html#customeruse) verwaltet werden. Mit 1-Klick-Funktionen können Ihre Endbenutzer die Datenerfassung durch die Adobe Experience Cloud-Werbelösungen (einschließlich Audience Manager) steuern und deaktivieren. Weitere Informationen finden Sie im Abschnitt hinsichtlich [ Geschäftskunden](https://www.adobe.com/privacy/opt-out.html#customeruse) auf der Seite „Ihre Datenschutzoptionen“. Informationen zu Browsern, die keine Drittanbieter-Cookies unterstützen, finden Sie unter [Deklariertes ID-Targeting](../../features/declared-ids.md#declared-id-targeting). Rufen Sie für mobile Geräte die entsprechenden Audience Manager-IDs ab und rufen Sie die Audience Manager-Abmelde-APIs auf, wie in den [Beispielen für Opt-out-Verfahren mit deklarierten IDs](../../features/declared-ids.md#opt-out-examples) angegeben. Danach können Sie die Datenerfassung für Benutzer mit den Abmelde-APIs des Mobile SDK einstellen – siehe [Android-Geräte](https://docs.adobe.com/content/help/de-DE/mobile-services/android/gdpr-privacy-android/privacy.html) und [iOS-Geräte](https://docs.adobe.com/content/help/de-DE/mobile-services/ios/privacy-gdpr-ios/privacy.html). Weitere Informationen zum Opt-out-Verfahren finden Sie in der [Dokumentation zu Datenschutzanfragen](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Verwalten der Zustimmung für Zweitpartner

Zweitpartner sind in der Regel auch Datenverantwortliche und Eigentümer des Verfahrens, um die erforderliche Zustimmung der betroffenen Personen einzuholen, um Daten mit ihren Zweitdatenpartnern zu teilen. Es liegt in Ihrer Verantwortung als Audience Manager-Kunde festzustellen, ob der Zweitpartner die erforderliche Zustimmung für Ihren Anwendungsfall eingeholt hat. Weitere Einzelheiten zur Einholung der Zustimmung werden oben behandelt.

## Verwalten der Zustimmung für Audience Marketplace-Drittpartner

Audience Marketplace-Drittpartner sind auch Datenverantwortliche und Eigentümer ihres Verfahrens zur Einholung von Zustimmung und Verwaltung von Zugriffs-/Lösch-/Korrekturanfragen. Adobe fordert Audience Marketplace-Drittpartner proaktiv auf, ihre Firmenprofilinformationen in [Adobe Audience Finder](https://www.adobe-audience-finder.com/) mit zusätzlichen Informationen zur Benutzerdatenerfassung zu aktualisieren. Die Informationen werden von Audience Marketplace-Drittpartner bezogen und regelmäßig aktualisiert. Es liegt jedoch an jedem Audience Manager-Kunden, festzustellen, ob der Audience Marketplace-Drittpartner die erforderliche Zustimmung für den Anwendungsfall dieses Kunden eingeholt hat. Adobe macht keine Zusicherungen über den Umfang oder die Gültigkeit der Zustimmung, die ein Audience Marketplace-Drittpartner für einen bestimmten Anwendungsfall eingeholt oder gemeldet hat.

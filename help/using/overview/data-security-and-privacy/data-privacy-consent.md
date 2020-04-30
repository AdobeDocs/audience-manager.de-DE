---
description: In diesem Dokument wird erläutert, wie die Verwaltung von Genehmigungen in Audience Manager funktioniert.
seo-description: In diesem Dokument wird erläutert, wie die Verwaltung von Genehmigungen in Audience Manager funktioniert.
seo-title: Genehmigungsverwaltung
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Genehmigungsverwaltung
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Genehmigungsverwaltung

## Überblick {#overview}

In Fällen, in denen die Zustimmung für bestimmte Marketing-Aktivitäten erforderlich ist, müssen Audience Manager-Kunden den Umfang und die Notwendigkeit bestimmter Zustimmungen festlegen, um die Daten in Zukunft weiter nutzen zu können.

Audience Manager bietet Ihnen Angebote, mit denen Sie die erforderlichen Benutzerzustimmungen abrufen können, damit Sie personalisierte Erlebnisse für alle Kanal bereitstellen können.

>[!IMPORTANT]
>
> Die Inhalte dieses Dokuments sind keine Rechtsberatung und sollen nicht die Rechtsberatung ersetzen.
>
> Als Ihr Datenverarbeiter kann Adobe keine rechtliche Beratung zum Erhalt der Zustimmung erteilen. Sie können auch erwägen, mit einem Anbieter von Lösungen für die Genehmigungsverwaltung wie [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) oder [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/)zusammenzuarbeiten und sich bei der Einrichtung Ihrer Opt-in-Implementierung an die Rechtsabteilung Ihrer Firma zu wenden, um Beratung hinsichtlich der Zustimmung und der Vorgehensweise zu erhalten.

## Experience Cloud-Dienst für Teilnahme

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) lets you set up protocols for the visitor to assist you in determining if you can set a cookie on the individual&#39;s device or browser when visiting your site.

This is an extension of the [!DNL Experience Cloud ID (ECID) Service], designed to let you control whether and which Experience Cloud solutions can place cookies on web pages for visitors prior to user consent.

Mit dem [Experience Cloud-Einstiegsdienst](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) können Sie außerdem Protokolle zur Integration in Ihre Consent Management Platform (CMP) und vorhandene Systeme als Teil Ihres größeren Designs festlegen.

## Verwalten der Teilnahme/Einholung der Zustimmung

Audience Manager-Kunden haben die Möglichkeit, die Benutzereinwilligung für verschiedene Anwendungsfälle wie Werbung oder Personalisierung als Eigenschaften in Audience Manager zu speichern. Segmente, die Sie mit diesen Eigenschaften erstellen, umfassen dann nur Benutzer, die die entsprechende Zustimmung für jeden dieser Anwendungsfälle erteilen. Beachten Sie, dass die Datenerfassung mit diesem Ansatz nicht gestoppt wird, sondern sich nur auf die Datenverwendung auswirkt, wenn Sie Segmente zur Aktivierung senden. Wenn Benutzer ihre Einwilligung widerrufen, können Sie diese Eigenschaften mithilfe des Audience Manager- [Ausstiegsvorgangs](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) oder des Audience Manager-Abmeldeprozesses wie unten beschrieben aus dem Profil entfernen.

## Verwalten der Abmeldung/Widerruf der Zustimmung

Die Abmeldung kann für die Adobe Experience Cloud über die Seite [Ihre Datenschutzoptionen](https://www.adobe.com/privacy/opt-out.html#customeruse) verwaltet werden. Mit 1-Klick-Funktionen können Endbenutzer die Datenerfassung über die Adobe Experience Cloud-Werbesysteme (einschließlich Audience Manager) steuern und abwählen. Weitere Informationen finden Sie im Abschnitt [Geschäftskunden](https://www.adobe.com/privacy/opt-out.html#customeruse) auf der Seite &quot;Datenschutzoptionen&quot;. Informationen zu Browsern, die keine Drittanbieter-Cookies unterstützen, finden Sie unter [Deklariertes ID-Targeting](../../features/declared-ids.md#declared-id-targeting). Rufen Sie bei Mobilgeräten die entsprechenden Audience Manager-IDs ab und rufen Sie die Audience Manager-Ausschluss-APIs auf, wie in den [erklärten ID-Abmeldebeispielen](../../features/declared-ids.md#opt-out-examples)beschrieben. Danach können Sie die Datenerfassung für Benutzer mit den Opt-out-APIs des Mobile SDK einstellen - siehe [Android-Geräte](https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html) und [iOS-Geräte](https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html). Weitere Informationen zum Ausschluss finden Sie in der Dokumentation zu [Datenschutzanfragen](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Verwalten der Zustimmung für Zweitanbieter-Partner

Zweitparteien-Partner sind in der Regel auch Datenkontrolleure und Eigentümer des Verfahrens, um die erforderliche Zustimmung der betroffenen Daten zu erhalten, um Daten mit ihren Zweitanbieter-Datenpartnern zu teilen. Es liegt in Ihrer Verantwortung, als Audience Manager-Kunde festzustellen, ob der Zweitpartei-Partner die erforderliche Zustimmung für Ihren Verwendungsfall erhalten hat. Weitere Einzelheiten zur Einholung der Zustimmung werden oben behandelt.

## Verwalten der Zustimmung für Audience Marketplace-Drittanbieter

Audience Marketplace Drittanbieter sind auch Datenkontrolleure und Eigentümer ihres Verfahrens zur Einholung von Einwilligung und Verwaltung von Zugriffs-/Löschungs-/Korrekturanforderungen. Adobe fordert Audience Marketplace-Drittanbieter-Partner proaktiv auf, ihre Firma-Profil-Informationen in [Adobe Audience Finder](https://www.adobe-audience-finder.com/) mit zusätzlichen Informationen zur Benutzerdatenerfassung zu aktualisieren. Die Informationen werden vom Audience Marketplace Drittanbieter bezogen und regelmäßig aktualisiert. Es obliegt jedoch jedem Kundenbetreuer, festzustellen, ob der Drittanbieter-Audience-Partner die erforderliche Zustimmung für den Verwendungsfall des Audience-Managers erhalten hat. Adobe gibt keine Erklärungen zum Umfang oder zur Gültigkeit der von einem Drittanbieter-Partner von Audience Marketplace für einen bestimmten Anwendungsfall erhaltenen oder gemeldeten Zustimmung ab.

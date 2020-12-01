---
description: Verwenden Sie globale Datenquellen, um Anzeigen-IDs für Geräte zu importieren.
seo-description: Verwenden Sie globale Datenquellen, um Anzeigen-IDs für Geräte zu importieren.
seo-title: Globale Data Sources
solution: Audience Manager
title: Globale Data Sources
feature: Data Sources
translation-type: tm+mt
source-git-commit: cb84f95d52c2e851cb0c016cb25f408f2d79d01b
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 6%

---


# Globale Data Sources {#global-data-sources}

## Überblick

Globale Datenquellen sind für alle Audience Manager zugänglich und enthalten Anzeigen-IDs von Geräteherstellern wie [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] und [!DNL Android] Geräteherstellern. Diese IDs werden von den Herstellern für Werbezwecke bereitgestellt. Audience Manager können globale Datenquellen verwenden, um Geräte-IDs zu synchronisieren und Daten zu importieren oder zu exportieren, die aus diesen Zuordnungen herausgefiltert wurden.

Die folgende Tabelle beschreibt die von Audience Manager unterstützten globalen Datenquellen.

| Datenquellen-ID | Beschreibung |
|---|---|
| 2014 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** IDs stellen Geräte dar, auf denen das  [!DNL Android] Betriebssystem ausgeführt wird. |
| 2015 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** IDs stellen Geräte dar, auf denen das  [!DNL iOS] Betriebssystem ausgeführt wird. |
| 121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** IDs stellen  [!DNL Roku] Streaming-Geräte dar. |
| 389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** IDs stellen Geräte dar, auf denen das  [!DNL Windows 10] Betriebssystem ausgeführt wird. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** IDs stellen  [!DNL Samsung] Smart-TVs dar. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** Geräte darstellen, die  [!DNL Amazon Fire OS] |

## Importieren von Daten aus globalen Datenquellen

Sie können Geräte-IDs aus globalen Datenquellen sowohl über [Echtzeit-Datenübertragung](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) als auch über [Stapeldatenübertragung](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) importieren.

>[!IMPORTANT]
>
>Stellen Sie beim Senden von Daten an Audience Manager mit einer globalen Geräte-ID sicher, dass Sie die entsprechende Datenquelle für die betreffende Geräte-ID verwenden. Beispiel: zum Importieren von Daten für [!DNL Apple IDFA] verwenden Sie die Datenquellen-ID 20915.

## Einschränkungen

Auf Geräten mit den Betriebssystemen [!DNL iOS] und [!DNL Android] können nur native Anwendungen Geräte-Anzeigen-IDs ([!UICONTROL DAID]s) abrufen und verwenden. Webanwendungen, die in mobilen Browsern ausgeführt werden, haben keinen Zugriff auf IDs für Gerätewerbung.

## Validierung der globalen Geräte-ID

Audience Manager überprüft die von Kunden importierten Anzeigen-IDs ([!UICONTROL DAID]) anhand ihres Formats, um sicherzustellen, dass sie dem von Geräteherstellern angegebenen Standardformat entsprechen. Eine detaillierte Zuordnung von Anzeigen-IDs zu globalen Datenquellen und das richtige Format für jede ID finden Sie unter [IDs in Audience Manager](../reference/ids-in-aam.md). Achten Sie darauf, dass Sie Geräte-IDs im korrekten Format importieren, je nach Gerätetyp. Audience Manager lehnt Geräte-IDs ab, die nicht dem richtigen Format entsprechen, und gibt eine Fehlermeldung zurück, die darauf hinweist, dass die ID abgelehnt wurde.

* Fehlermeldungen für Batch-Datenübertragungen werden hier beschrieben: [Begriffe und Definitionen im Bericht &quot;Onboarding-Status&quot;](../reporting/onboarding-status-report.md#report-terms-conditions)
* Fehlermeldungen bei Datenübertragungen in Echtzeit werden hier beschrieben: [DCS-Fehlercodes, Meldungen und Beispiele](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Richtlinie zum Ablauf der Geräte-ID

Audience Manager verwirft Geräte-Anzeigen-IDs nach 120 Tagen Inaktivität automatisch, ähnlich wie [AAM UUID](../faq/faq-privacy.md)s.

## Neue globale Datenquellen anfordern

Wenden Sie sich an den Kundendienst von Adobe Consulting oder Adobe und geben Sie detaillierte Informationen zu den erforderlichen Datenquellen an, um neue globale Datenquellen anzufordern, die dem Audience Manager hinzugefügt werden sollen:

* Name der angeforderten Plattform (z. B. [!UICONTROL Apple IDFA]);
* Der Name der Firma/Organisation, die die Plattform verwaltet (z. B. [!UICONTROL Apple Inc.]);
* Links zu den technischen Spezifikationen für den Namensraum der Anzeigen-ID des Geräts (z. B. [AdSupport-Dokumentation](https://developer.apple.com/documentation/adsupport)).
---
description: Verwenden Sie globale Data Sources, um Geräte-Werbe-IDs zu importieren.
seo-description: Verwenden Sie globale Data Sources, um Geräte-Werbe-IDs zu importieren.
seo-title: Globale Data Sources
solution: Audience Manager
title: Globale Data Sources
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 6%

---

# Globale Data Sources {#global-data-sources}

## Überblick

Globale Datenquellen sind für alle Audience Manager zugänglich und enthalten Geräte-Werbe-IDs von Geräteherstellern wie [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] und [!DNL Android] Geräteherstellern. Diese IDs werden von den Herstellern für Werbezwecke bereitgestellt. Audience Manager können globale Datenquellen verwenden, um Geräte-IDs zu synchronisieren und Daten zu importieren oder zu exportieren, die von diesen Zuordnungen abgeleitet wurden.

In der folgenden Tabelle werden die vom Audience Manager unterstützten globalen Datenquellen beschrieben.

| Datenquellen-ID | Beschreibung |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** IDs stellen Geräte dar, auf denen das  [!DNL Android] Betriebssystem ausgeführt wird. |
| 20915 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** IDs stellen Geräte dar, auf denen das  [!DNL iOS] Betriebssystem ausgeführt wird. |
| 121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** IDs stellen  [!DNL Roku] Streaming-Geräte dar. |
| 389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** IDs stellen Geräte dar, auf denen das  [!DNL Windows 10] Betriebssystem ausgeführt wird. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** IDs stellen  [!DNL Samsung] Smart-TVs dar. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** Geräte darstellen, die ausgeführt werden  [!DNL Amazon Fire OS] |

## Importieren von Daten aus globalen Data Sources

Sie können Geräte-IDs aus globalen Datenquellen sowohl über [Echtzeit-Datenübertragung](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) als auch über [Batch-Datenübertragung](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) importieren.

>[!IMPORTANT]
>
>Stellen Sie beim Senden von Daten an Audience Manager mithilfe einer globalen Geräte-ID sicher, dass Sie die entsprechende Datenquelle für die betreffende Geräte-ID verwenden. Beispiel: zum Importieren von Daten für [!DNL Apple IDFA] verwenden Sie die Datenquellen-ID 20915.

## Einschränkungen

Auf Geräten mit den Betriebssystemen [!DNL iOS] und [!DNL Android] können nur native Anwendungen Geräte Werbe-IDs ([!UICONTROL DAID]s) abrufen und verwenden. Webanwendungen, die in mobilen Browsern ausgeführt werden, haben keinen Zugriff auf Geräte-Werbe-IDs.

## Validierung der globalen Geräte-ID

Audience Manager validiert die von Kunden importierten Geräte-Werbe-IDs ([!UICONTROL DAID]) anhand ihres Formats, um sicherzustellen, dass sie dem von Geräteherstellern angegebenen Standardformat entsprechen. Eine detaillierte Zuordnung der Werbe-IDs zu globalen Datenquellen und das richtige Format für jede ID finden Sie unter [Index of IDs in Audience Manager](../reference/ids-in-aam.md). Stellen Sie sicher, dass Sie Geräte-IDs basierend auf dem Gerätetyp im richtigen Format importieren. Audience Manager lehnt Geräte-IDs ab, die nicht dem richtigen Format entsprechen, und gibt eine Fehlermeldung zurück, die angibt, dass die ID zurückgewiesen wurde.

* Fehlermeldungen für Batch-Datenübertragungen werden hier beschrieben: [Begriffe und Definitionen des Onboarding-Statusberichts](../reporting/onboarding-status-report.md#report-terms-conditions).
* Fehlernachrichten für Echtzeit-Datenübertragungen werden hier beschrieben: [DCS-Fehlercodes, Meldungen und Beispiele](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Richtlinie zum Ablauf der Geräte-ID

Audience Manager verwirft Geräte-Werbe-IDs nach 120 Tagen Inaktivität automatisch, ähnlich wie [AAM UUID](../faq/faq-privacy.md)s.

## Anfordern neuer globaler Datenquellen

Um neue globale Datenquellen anzufordern, die dem Audience Manager hinzugefügt werden sollen, wenden Sie sich an die Kundenunterstützung von Adobe Consulting oder Adobe und geben Sie detaillierte Informationen zu den erforderlichen Datenquellen an:

* Name der angeforderten Plattform (z. B. [!UICONTROL Apple IDFA]);
* Name des Unternehmens/der Organisation, das/die die Plattform verwaltet (z. B. [!UICONTROL Apple Inc.]);
* Links zu den technischen Spezifikationen für den Namespace der Geräte-Werbe-ID (z. B. [AdSupport-Dokumentation](https://developer.apple.com/documentation/adsupport)).

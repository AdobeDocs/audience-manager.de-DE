---
description: Verwenden Sie globale Datenquellen, um Geräte-Werbe-IDs zu importieren.
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: Globale Datenquellen
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
TQID: https://experienceleague.adobe.com/ypEVWQ9WTVzEAluf8a7PqkWvatH-G9JH82WkjmhwWEM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 447
ht-degree: 4%

---

# Globale Datenquellen {#global-data-sources}

## Überblick

Globale Datenquellen stehen allen Audience Manager-Kunden zur Verfügung und enthalten Gerätewerbe-IDs, die von Geräteherstellern wie [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] und [!DNL Android] Geräteherstellern generiert wurden. Diese IDs werden von den Herstellern für Werbezwecke bereitgestellt. Audience Manager-Kunden können globale Datenquellen verwenden, um Geräte-IDs zu synchronisieren und Daten, die von diesen Zuordnungen abgeleitet wurden, zu importieren oder zu exportieren.

In der folgenden Tabelle werden die von Audience Manager unterstützten globalen Datenquellen beschrieben.

| Data Source ID | Beschreibung |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]**-IDs stellen Geräte dar, auf denen das [!DNL Android] Betriebssystem ausgeführt wird. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]**-IDs stellen Geräte dar, auf denen das [!DNL iOS] Betriebssystem ausgeführt wird. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]**-IDs stellen [!DNL Roku] Streaming-Geräte dar. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]**-IDs stellen Geräte dar, auf denen das [!DNL Windows 10] Betriebssystem ausgeführt wird. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** IDs stellen [!DNL Samsung] Smart-TVs dar. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** stellen Geräte dar, die [!DNL Amazon Fire OS] ausgeführt werden |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** stellen Geräte dar, auf denen das [!DNL LG webOS] Betriebssystem ausgeführt wird. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** stellen Geräte dar, auf denen die Betriebssysteme Vizio Smart TV ausgeführt werden. |

## Importieren von Daten aus globalen Datenquellen

Sie können Geräte-IDs aus globalen Datenquellen sowohl durch [Echtzeit-Datenübertragung](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) als auch [Batch-Datenübertragung](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) importieren.

>[!IMPORTANT]
>
>Wenn Sie Daten mit einer globalen Geräte-ID an Audience Manager senden, stellen Sie sicher, dass Sie die entsprechende Datenquelle für die jeweilige Geräte-ID verwenden. Beispiel: Um Daten für [!DNL Apple IDFA] zu importieren, verwenden Sie die Datenquellen-ID 20915.

## Einschränkungen

Auf Geräten, auf denen [!DNL iOS] und [!DNL Android] Betriebssysteme ausgeführt werden, können nur native Programme Gerätewerbe-IDs ([!UICONTROL DAID]) abrufen und verwenden. Web-Anwendungen, die in mobilen Browsern ausgeführt werden, haben keinen Zugriff auf Geräte-Werbe-IDs.

## Validierung der globalen Geräte-ID

Audience Manager validiert die von Kunden importierten Gerätewerbe-IDs ([!UICONTROL DAID]) anhand ihres Formats, um sicherzustellen, dass sie dem von Geräteherstellern beschriebenen Standardformat entsprechen. Siehe [ID-Index in Audience Manager](../reference/ids-in-aam.md) für eine detaillierte Zuordnung von Gerätewerbe-IDs zu globalen Datenquellen und das richtige Format für jede ID. Stellen Sie sicher, dass Sie Geräte-IDs je nach Gerätetyp im richtigen Format importieren. Audience Manager lehnt Geräte-IDs ab, die nicht das richtige Format aufweisen, und gibt eine Fehlermeldung zurück, die angibt, dass die ID abgelehnt wurde.

* Fehlermeldungen für Batch-Datenübertragungen sind hier beschrieben: [Bedingungen und Definitionen für Onboarding-](../reporting/onboarding-status-report.md#report-terms-conditions).
* Fehlermeldungen für Echtzeit-Datenübertragungen werden hier beschrieben: [DCS-Fehlercodes, Meldungen und Beispiele](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Ablaufrichtlinie für Geräte-IDs

Audience Manager verwirft Gerätewerbe-IDs automatisch nach 120 Tagen Inaktivität, ähnlich wie [AAM UUID](../faq/faq-privacy.md).

## Neue globale Datenquellen werden angefordert

Um neue globale Datenquellen anzufordern, die zu Audience Manager hinzugefügt werden sollen, wenden Sie sich an die Adobe Consulting- oder Adobe-Kundenunterstützung und geben Sie detaillierte Informationen zu den erforderlichen Datenquellen an:

* Name der angeforderten Plattform (z. B. [!UICONTROL Apple IDFA]);
* Der Name des Unternehmens/der Organisation, das/die die Plattform verwaltet (z. B. [!UICONTROL Apple Inc.]);
* Links zu den technischen Spezifikationen für den Namespace der Geräteanzeige (z. B. [AdSupport-Dokumentation](https://developer.apple.com/documentation/adsupport)).

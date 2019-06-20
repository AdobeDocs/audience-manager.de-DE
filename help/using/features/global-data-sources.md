---
description: Verwenden Sie globale Datenquellen, um Geräte-ids für Geräte zu importieren.
seo-description: Verwenden Sie globale Datenquellen, um Geräte-ids für Geräte zu importieren.
seo-title: Globale Data Sources
solution: Audience Manager
title: Globale Data Sources
uuid: null
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Globale Data Sources {#global-data-sources}

## Überblick

Globale Datenquellen stehen allen Audience Manager-Kunden zur Verfügung und enthalten Geräte-IDs, die von Geräteherstellern wie [!DNL Apple][!DNL Samsung][!DNL Microsoft], [!DNL Roku]und [!DNL Android] Geräteherstellern generiert wurden. Diese IDs werden von den Herstellern für Werbezwecke bereitgestellt. Audience Manager-Kunden können globale Datenquellen verwenden, um Geräte-IDs zu synchronisieren und Daten, die aus diesen Zuordnungen stammen, zu importieren oder zu exportieren.

Die folgende Tabelle beschreibt die globalen Datenquellen, die von Audience Manager unterstützt werden.

| Datenquellen-ID | Beschreibung |
|---|---|
| 20914 | **Google Advertising ID** - **ghilfen** stellen Geräte dar, die das Android-Betriebssystem ausführen. |
| 20915 | **Apple-ID für Werbung** - **idfas** stellen Geräte dar, die das ios-Betriebssystem ausführen. |
| 121963 | **Roku-ID für Werbung** - **ridas** stellt Roku-Streaming-Geräte dar. |
| 389146 | **Microsoft Advertising ID** - **maids** stellen Geräte dar, die das Windows 10-Betriebssystem ausführen. |
| 404660 | **Samsung duids** stellen Samsung-Smart-Fernseher dar. |

## Importieren von Daten aus globalen Datenquellen

Geräte-IDs können sowohl über [Echtzeit-Datenübertragungen](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) als auch [über Batch-Datenübertragungen aus globalen Datenquellen importiert](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)werden.

>[!IMPORTANT]
>
>Wenn Sie Daten mit einer globalen Geräte-ID an Audience Manager senden, müssen Sie die entsprechende Datenquelle für die betreffende Geräte-ID verwenden. Beispiel: verwenden, um Daten zu [!DNL Apple IDFA]importieren, verwenden Sie die Datenquellen-ID 20915.

## Einschränkungen

Auf Geräten, auf denen Betriebssysteme ausgeführt werden [!DNL iOS] , [!DNL Android] können nur native Anwendungen Geräte-IDs (s) abrufen und verwenden[!UICONTROL DAID]. Webanwendungen, die in mobilen Browsern ausgeführt werden, haben keinen Zugriff auf Geräte-ids für Geräte.

## Globale Geräte-ID-Validierung

Audience Manager überprüft die von Kunden importierten Geräte-ids ([!UICONTROL DAID]) anhand ihres Formats, um sicherzustellen, dass sie dem von Geräteherstellern angegebenen Standardformat entsprechen. Eine detaillierte Zuordnung von Geräteanzeigen-IDs zu globalen Datenquellen und das richtige Format für jede ID finden Sie unter [Index von IDs in Audience Manager](../reference/ids-in-aam.md) . Stellen Sie sicher, dass Sie Geräte-IDs im korrekten Format importieren, basierend auf dem Gerätetyp. Audience Manager lehnt Geräte-IDs ab, die das richtige Format nicht erfüllen, und gibt eine Fehlermeldung zurück, um anzugeben, dass die ID abgelehnt wurde.

* Fehlermeldungen für Batch-Datenübertragungen finden Sie hier: [Begriffe und Definitionen des Onboarding-Status](../reporting/onboarding-status-report.md#report-terms-conditions).
* Fehlermeldungen für Echtzeit-Datenübertragungen werden hier beschrieben: [DCS-Fehlercodes, Nachrichten und Beispiele](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Ablaufrichtlinie für Geräte-Ids

Audience Manager verwirft Geräte-Advertising-IDs nach 120 Tagen inaktivität automatisch, ähnlich [wie AAM uuids](../faq/faq-privacy.md).

## Anfordern neuer globaler Datenquellen

Um neue globale Datenquellen anzufordern, die dem Audience Manager hinzugefügt werden sollen, wenden Sie sich an Adobe Consulting oder den Adobe-Kundendienst und geben Sie detaillierte Informationen zu den erforderlichen Datenquellen an:

* Der Name der angeforderten Plattform (z. [!UICONTROL Apple IDFA]B.);
* Name des Unternehmens/Unternehmens, das die Plattform verwaltet (z. [!UICONTROL Apple Inc.]B.);
* Links zu den technischen Spezifikationen für den Namespace des Geräte-ids (z. B. [adsupport-Dokumentation](https://developer.apple.com/documentation/adsupport)).
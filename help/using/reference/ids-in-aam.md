---
description: In diesem Dokument finden Sie die vollständige Liste der Adobe Audience Manager-IDs.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuuid, uuuid
seo-description: In diesem Dokument finden Sie die vollständige Liste der Adobe Audience Manager-IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Index of IDs in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: reference
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 5%

---


# Index der IDs in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Überblick {#overview}

[!DNL Audience Manager] verwendet mehrere IDs, um die Daten zu identifizieren und zu verwalten, die Sie an sie senden. In diesem Artikel finden Sie die vollständige Liste der [!DNL Audience Manager]-IDs sowie Beispiele der Präfixe, mit denen Sie sie verwenden sollten.

## ID-Präfix {#prefixing}

Die meisten dieser IDs sind zwar mit eigenständigen Namen gekennzeichnet, die meisten sind jedoch für die Verwendung mit verschiedenen Präfixen vorgesehen, wenn Daten über [!DNL DCS]-Aufrufe weitergegeben werden. Einige dieser IDs werden von [!DNL Audience Manager] verwendet, ohne dass sie Benutzern zur Verfügung stehen, während andere auch in der Benutzeroberfläche sichtbar sind.

Informationen zu den in den folgenden Beispielen verwendeten Präfixen finden Sie unter [Unterstützte Attribute für DCS API-Aufrufe](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] ID-Liste {#id-list}

| ID | Name und Beschreibung | Nutzung und Beispiele | Benutzeroberflächenposition |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], auch bekannt als  [!UICONTROL Device ID]. Eine numerische, 38-stellige Geräte-ID, die [!DNL Audience Manager] jedem Gerät zugeordnet wird, mit dem sie interagiert. Denken Sie an diese ID, wenn Sie in der Benutzeroberfläche [!DNL Audience Manager] eine Erwähnung von Unique Users sehen. Audience Manager speichert diese ID als [!DNL cookie] in der Drittanbieterdomäne `demdex.net`. | Bei Aufrufen von [!DNL DCS] wird `uuid` das Präfix `d_` vorangestellt. <br>Beispiel: `d_uuid = 07955261652886032950143702505894272138` | Sie können [!DNL traits] nach [!UICONTROL Device ID] filtern, wenn Sie [Look-Alike Models](../features/algorithmic-models/create-model.md) und [Segmentaufbausegmente](../features/segments/segment-builder.md) erstellen. Sie können die Ergebnisse auch nach [!UICONTROL Device ID] filtern, wenn [Allgemeine Berichte für Eigenschaften](../reporting/general-reports.md) und [Trendberichte für Eigenschaften](../reporting/trend-reports.md) ausgeführt werden. |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Dies ist die ID, die eine Firma bei der Anmeldung für ein [!DNL Experience Cloud]-Konto bereitstellt. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Nicht sichtbar in der [!DNL Audience Manager]-Benutzeroberfläche. Um zu erfahren, wie Sie die [!DNL Organization ID] Ihrer Firma finden können, lesen Sie [Ihre Organisations-ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255) suchen. |
| [!DNL PID] | [!DNL Partner ID]. [!DNL PID] ist eine Firmen-ID in [!DNL Audience Manager]. Audience Manager verknüpft ein [!DNL imsOrgId] mit einem [!DNL PID]. | `1352` | Nicht sichtbar in der [!DNL Audience Manager]-Benutzeroberfläche. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. Die [!DNL Experience Cloud]-ID ([!DNL ECID], veraltete Abkürzungen [!DNL MID] oder [!DNL MCID]) wird mathematisch von Ihren [!DNL Organization ID] und dem [!DNL Audience Manager] [!UICONTROL Unique User ID] abgeleitet. Solange diese IDs konstant bleiben, stellt die Generierung des richtigen [!DNL ECID] für einen bestimmten Benutzer einfach ein mathematisches Problem dar. Mit dem gleichen [!DNL Organization ID] und [!DNL Audience Manager] [!DNL UUID] erhalten Sie jedes Mal denselben [!DNL ECID]-Wert. Weitere Informationen zu [!DNL ECID] finden Sie in der Dokumentation [Cookies und Experience Cloud-ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17). | `mid = 08382830887934830189014177072406221371` | Nicht sichtbar in der [!DNL Audience Manager]-Benutzeroberfläche. |
| [!DNL SID] | [!UICONTROL Trait ID]. [!UICONTROL Trait ID] identifiziert [!DNL traits] in der [!DNL Audience Manager]-Umgebung eindeutig. | Bei Aufrufen von [!DNL DCS] wird `SID` das Präfix `d_` vorangestellt. <br>Beispiel `d_sid=289983`. | Jedem [!DNL trait] wird ein [!UICONTROL Trait ID]-Zeichen zugewiesen und in der Benutzeroberfläche auf der Seite [Eigenschaften](../features/traits/trait-details-page.md) angezeigt. |
| [!DNL SID] | [!UICONTROL Segment ID]. [!UICONTROL Segment ID] identifiziert [!DNL segments] in der [!DNL Audience Manager]-Umgebung eindeutig. | Bei Aufrufen von [!DNL DCS] wird `SID` das Präfix `d_` vorangestellt. <br>Beispiel `d_sid=4798574`. | Jedem [!DNL segment] wird ein [!UICONTROL Segment ID]-Zeichen zugewiesen und in der Benutzeroberfläche auf der Seite [Segmente](../features/segments/segment-summary-view.md) angezeigt. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Diese ID identifiziert eindeutig Segmente in der Umgebung [!DNL Audience Manager]. | `741232` | Jedem Segment wird ein [!UICONTROL Legacy Segment ID] zugewiesen und in der Benutzeroberfläche auf der Seite [Segmente](../features/segments/segment-summary-view.md) angezeigt. |
| [!DNL destID] | [!UICONTROL Destination ID]. [!UICONTROL Destination ID] identifiziert [!DNL destinations] in der [!DNL Audience Manager]-Umgebung eindeutig. Jedem [!DNL destination] in der Benutzeroberfläche wird eine ID zugewiesen. | `2523` | Jedem [!DNL destination] wird ein [!UICONTROL Destination ID] zugewiesen und in der Benutzeroberfläche auf der Seite [Ziele](../features/destinations/destinations-home.md) angezeigt. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (auch als  [!UICONTROL Data Provider ID]). [!UICONTROL Data Source ID] ist ein Namensraum für IDs oder [!DNL traits]. Jedem [!DNL data source] (Datenanbieter) in der Benutzeroberfläche wird eine ID zugewiesen. | Bei Aufrufen von [!DNL DCS] wird `dpid` das Präfix `d_` vorangestellt. <br>Beispiel: `d_dpid=39217`. | Jedem [!DNL data source] wird ein [!UICONTROL Data Provider ID]-Element zugewiesen und in der Benutzeroberfläche auf der Seite [Datenquellen](../features/datasources-list-and-settings.md) angezeigt. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], auch als  [!DNL CRM ID] oder bezeichnet  [!UICONTROL Cross-Device ID]. Eine Drittanbieter-ID. Dies ist die ID, mit der Sie Endbenutzer in Ihrem eigenen [!DNL CRM]-System identifizieren können. Sie können [!DNL DPUUIDs] mit [!DNL Audience Manager] [!DNL UUIDs] synchronisieren und [!DNL DPUUIDs] aus den verschiedenen [!UICONTROL Data Sources] ([!DNL DPIDs]) im ID-Synchronisierungsprozess synchronisieren. | Bei [!DNL DCS]-Aufrufen ist `dpuuid` das Präfix `d_` vorangestellt. <br> Beispiel `d_dpuuid=2132-3423vn-343fds-3432r`. | Sie können [!DNL traits] nach [!UICONTROL Cross-Device ID] filtern, wenn Sie [Look-Alike Models](../features/algorithmic-models/create-model.md) und [Segmentaufbausegmente](../features/segments/segment-builder.md) erstellen. Sie können die Ergebnisse auch nach [!UICONTROL Cross-Device ID] filtern, wenn [Allgemeine Berichte für Eigenschaften](../reporting/general-reports.md) und [Trendberichte für Eigenschaften](../reporting/trend-reports.md) ausgeführt werden. |
| [!DNL CRM ID] | Siehe `DPUUID`. | Siehe `DPUUID`. | Siehe `DPUUID`. |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Die Schlüssel-Wert-Paare [!DNL CID] und [!DNL CID_IC] ersetzen [!DNL DPID] und [!DNL DPUUID]. Sie bieten dieselben Funktionen wie [!DNL DPID] und [!DNL DPUUID], sind jedoch effizienter, da sie die Datenanbieter-ID und die Benutzer-ID (oder den Integrationscode) in einem einzelnen Schlüssel-Wert-Paar enthalten. | Bei Aufrufen von [!DNL DCS] wird diesen IDs das Präfix `d_` vorangestellt. <br>Beispiel: `d_cid_ic=39217_myIntegrationCode`. | Siehe `DPID` und `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Eine ID, die für jedes Hardwaregerät eindeutig ist und für Werbezwecke verwendet wird. In der Regel vom Hersteller des Geräts oder Betriebssystems bereitgestellt. | Siehe [Globale Geräte-IDs](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Globale Geräte-IDs sind Anzeigen-IDs für Geräte, die für jedes Gerät einzeln vom Gerätehersteller oder vom Betriebssystem bereitgestellt werden. In der folgenden Tabelle werden die IDs und ihr Format erläutert. Weitere Informationen zu globalen Geräte-IDs und deren Verwendung in [!DNL Audience Manager] finden Sie unter [Globale Datenquellen](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Name und Beschreibung | Beispiel |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 2015 | [!DNL Identifier for Advertisers] IDs sind vom Gerätehersteller bereitgestellte Identifikatoren für Mobilgeräte. Diese IDs stellen Geräte dar, auf denen das Betriebssystem [!DNL iOS] ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Großbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen.<br> Beispiel: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 2014 | [!DNL Google Advertising ID]s sind Mobilgerätekennungen, die von Android-Geräteherstellern bereitgestellt werden. Diese IDs stellen Geräte dar, auf denen das Betriebssystem [!DNL Android] ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen. <br>Beispiel: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] repräsentieren  [!DNL Roku] Streaming-Geräte. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen. <br>Beispiel: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sind Geräte-IDs, die von  [!DNL Windows 10] pro Gerät und pro Benutzer generiert werden. | [!DNL MAID]s werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] sind Geräte-IDs, die von  [!DNL Samsung] Smart-TVs bereitgestellt werden. | [!DNL Samsung] [!DNL TIFA] IDs werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Geräte-IDs, die Geräte darstellen, auf denen das Betriebssystem [!DNL Fire OS] ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen. <br>Beispiel: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
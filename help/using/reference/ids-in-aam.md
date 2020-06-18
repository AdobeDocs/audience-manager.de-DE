---
description: In diesem Dokument finden Sie die vollständige Liste der Adobe Audience Manager-IDs.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: In diesem Dokument finden Sie die vollständige Liste der Adobe Audience Manager-IDs.
seo-title: Index der IDs in Audience Manager
solution: Audience Manager
title: Index der IDs in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 3%

---


# Index der IDs in Audience Manager {#index-of-ids-in-audience-manager}

## Überblick {#overview}

[!DNL Audience Manager] verwendet mehrere IDs, um die Daten zu identifizieren und zu verwalten, die Sie an sie senden. In diesem Artikel finden Sie eine vollständige Liste der [!DNL Audience Manager] IDs sowie Beispiele der Präfixe, mit denen Sie sie verwenden sollten.

## ID-Vorgabe {#prefixing}

Die meisten dieser IDs sind zwar mit eigenständigen Namen gekennzeichnet, die meisten sind jedoch für die Verwendung mit verschiedenen Präfixen vorgesehen, wenn Daten über [!DNL DCS] Aufrufe weitergegeben werden. Einige dieser IDs werden von Audience Manager verwendet, ohne dass sie Benutzern zur Verfügung stehen, während andere auch in der Benutzeroberfläche angezeigt werden.

Informationen zu den in den folgenden Beispielen verwendeten Präfixen finden Sie unter [Unterstützte Attribute für DCS-API-Aufrufe](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## Audience Manager-Liste von IDs {#id-list}

| ID | Name und Beschreibung | Nutzung und Beispiele | UI-Position |
|---|---|---|---|
| [!DNL AAM UUID] | Eindeutige Adobe Audience Manager-ID, auch bekannt als [!UICONTROL Device ID]. Eine numerische, 38-stellige Geräte-ID, die jedem Gerät, mit dem sie interagiert, [!DNL Audience Manager] zugeordnet wird. Denken Sie an diese ID, wenn Sie in der [!DNL Audience Manager] Benutzeroberfläche eine Erwähnung von Unique Users sehen. Audience Manager speichert diese ID als Cookie in der `demdex.net` Drittanbieterdomäne. | Bei [!DNL DCS] Aufrufen `uuid` wird das `d_` Präfix vorangestellt. <br>Beispiel: `d_uuid = 07955261652886032950143702505894272138` | Sie können Eigenschaften filtern, [!UICONTROL Device ID] wenn Sie [Look-Alike-Modelle](../features/algorithmic-models/create-model.md)erstellen und Segmente [erstellen](../features/segments/segment-builder.md). Sie können die Ergebnisse auch filtern, [!UICONTROL Device ID] wenn Sie [Allgemeine Berichte für Eigenschaften](../reporting/general-reports.md) und [Trendberichte für Eigenschaften](../reporting/trend-reports.md)ausführen. |
| [!DNL ImsOrgId] | Organisations-ID. Dies ist die ID, die eine Firma bei der Anmeldung für ein [!DNL Experience Cloud] Konto bereitstellt. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Nicht in der Benutzeroberfläche des Audience Managers sichtbar. Weitere Informationen zum Auffinden der Firma finden Sie unter [!DNL Organization ID]Organisations-ID [](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | Partner-ID. Die [!DNL PID] ID einer Firma in [!DNL Audience Manager]. Audience Manager verknüpft eine [!DNL imsOrgId] mit einer [!DNL PID]. | `1352` | Nicht in der Benutzeroberfläche des Audience Managers sichtbar. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. Die [!DNL Experience Cloud] ID ([!DNL ECID], veraltete Abkürzungen [!DNL MID] oder [!DNL MCID]) wird mathematisch aus Ihrer Organisations-ID und dem [!DNL Audience Manager][!UICONTROL Unique User ID]abgeleitet. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and [!DNL Audience Manager] [!DNL UUID] you get the same [!DNL ECID] value every time. Weitere Informationen zum Thema finden Sie [!DNL ECID] in der Dokumentation zu [Cookies und Experience Cloud-ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Nicht sichtbar im [!DNL Audience Manager][!DNL UI]. |
| [!DNL SID] | [!UICONTROL Trait ID]. Die [!UICONTROL Trait ID] Eigenschaften in der [!DNL Audience Manager] Umgebung werden eindeutig identifiziert. | Bei [!DNL DCS] Aufrufen `SID` wird das `d_` Präfix vorangestellt. <br>Beispiel `d_sid=289983`. | Jedem Merkmal [!UICONTROL Trait ID] wird ein Wert zugewiesen und auf der Seite &quot; [Eigenschaften](../features/traits/trait-details-page.md) &quot;in der Benutzeroberfläche angezeigt. |
| [!DNL SID] | [!UICONTROL Segment ID]. Die [!UICONTROL Segment ID] eindeutige Identifizierung von Segmenten in der [!DNL Audience Manager] Umgebung. | Bei [!DNL DCS] Aufrufen `SID` wird das `d_` Präfix vorangestellt. <br>Beispiel `d_sid=4798574`. | Jedem Segment [!UICONTROL Segment ID] wird ein Segment zugewiesen und auf der Seite &quot; [Segmente](../features/segments/segment-summary-view.md) &quot;in der Benutzeroberfläche angezeigt. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Diese ID identifiziert Segmente in der [!DNL Audience Manager] Umgebung eindeutig. | `741232` | Jedem Segment [!UICONTROL Legacy Segment ID] wird ein Segment zugewiesen und auf der Seite &quot; [Segmente](../features/segments/segment-summary-view.md) &quot;in der Benutzeroberfläche angezeigt. |
| [!DNL destID] | [!UICONTROL Destination ID]. Die [!UICONTROL Destination ID] eindeutige Identifizierung der Ziele in der [!DNL Audience Manager] Umgebung. Jedem Ziel in der Benutzeroberfläche wird eine ID zugewiesen. | `2523` | Jedem Ziel [!UICONTROL Destination ID] wird eine ID zugewiesen, die in der Benutzeroberfläche auf der Seite &quot; [Ziele](../features/destinations/destinations-home.md) &quot;angezeigt wird. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (auch als [!UICONTROL Data Provider ID]). Der Namensraum [!UICONTROL Data Source ID] dient zur Kennzeichnung von IDs oder Eigenschaften. Jeder Datenquelle (Datenanbieter) in der Benutzeroberfläche wird eine ID zugewiesen. | Bei [!DNL DCS] Aufrufen `dpid` wird das `d_` Präfix vorangestellt. <br>Beispiel: `d_dpid=39217`. | Jeder Datenquelle [!UICONTROL Data Provider ID] wird eine ID zugewiesen, die auf der Seite &quot; [Datenquellen](../features/datasources-list-and-settings.md) &quot;in der Benutzeroberfläche angezeigt wird. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], auch als [!DNL CRM ID] oder bezeichnet [!UICONTROL Cross-Device ID]. Eine Drittanbieter-ID. Mit dieser ID können Sie Endbenutzer in Ihrem eigenen [!DNL CRM] System identifizieren. Sie können [!DNL DPUUIDs] mit synchronisieren [!DNL Audience Manager] und [!DNL UUIDs] im ID-Synchronisierungsprozess von einem anderen [!DNL DPUUIDs] ( [!UICONTROL Data Sources][!DNL DPIDs]) aus synchronisieren. | Bei [!DNL DCS] Aufrufen `dpuuid` wird das `d_` Präfix vorangestellt. <br> Beispiel `d_dpuuid=2132-3423vn-343fds-3432r`. | Sie können Eigenschaften filtern, [!UICONTROL Cross-Device ID] wenn Sie [Look-Alike-Modelle](../features/algorithmic-models/create-model.md)erstellen und Segmente [erstellen](../features/segments/segment-builder.md). Sie können die Ergebnisse auch filtern, [!UICONTROL Cross-Device ID] wenn Sie [Allgemeine Berichte für Eigenschaften](../reporting/general-reports.md) und [Trendberichte für Eigenschaften](../reporting/trend-reports.md)ausführen. |
| [!DNL CRM ID] | Siehe `DPUUID`. | Siehe `DPUUID`. | Siehe `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Die Paare [!DNL CID] und [!DNL CID_IC] Schlüssel-Wert ersetzen [!DNL DPID] und [!DNL DPUUID]. Sie bieten die gleichen Funktionen wie die [!DNL DPID] und [!DNL DPUUID]sind jedoch effizienter, da sie die Datenanbieter-ID und die Benutzer-ID (oder den Integrationscode) in einem einzelnen Schlüssel-Wert-Paar enthalten. | Bei [!DNL DCS] Aufrufen wird diesen IDs das `d_` Präfix vorangestellt. <br>Beispiel: `d_cid_ic=39217_myIntegrationCode`. | Siehe `DPID` und `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Eine ID, die für jedes Hardwaregerät eindeutig ist und für Werbezwecke verwendet wird. In der Regel vom Hersteller des Geräts oder Betriebssystems bereitgestellt. | Siehe [Globale Geräte-IDs](#global-device-ids). |  |

## Globale Geräte-IDs {#global-device-ids}

Globale Geräte-IDs sind Anzeigen-IDs für Geräte, die für jedes Gerät einzeln vom Gerätehersteller oder vom Betriebssystem bereitgestellt werden. In der folgenden Tabelle werden die IDs und ihr Format erläutert. Weitere Informationen zu globalen Geräte-IDs und deren Verwendung finden Sie unter [!DNL Audience Manager][Globale Datenquellen](/help/using/features/global-data-sources.md).

| ID | Globale Datenquelle-ID | Name und Beschreibung | Beispiel  |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] IDs sind vom Gerätehersteller bereitgestellte Identifikatoren für Mobilgeräte. Diese IDs stellen Geräte dar, auf denen das iOS-Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Großbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen.<br> Beispiel: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sind Mobilgerätekennungen, die von Android-Geräteherstellern bereitgestellt werden. Diese IDs stellen Geräte dar, auf denen das [!DNL Android] Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen. <br>Beispiel: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] repräsentieren [!DNL Roku] Streaming-Geräte. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen. <br>Beispiel: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sind Geräte-IDs, die von [!DNL Windows 10] pro Gerät und pro Benutzer generiert werden. | [!DNL MAID]s werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s sind Geräte-IDs, die von [!DNL Samsung] Smart-TVs bereitgestellt werden. | [!DNL Samsung] [!DNL DUID]s werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Geräte-IDs, die Geräte darstellen, auf denen das [!DNL Fire OS] Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen. <br>Beispiel: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |


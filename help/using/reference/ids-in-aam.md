---
description: Eine vollständige Liste der Adobe Audience Manager IDs finden Sie in diesem Dokument .
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuuid, uuuid, uuuuuid.
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Index der IDs in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '1001'
ht-degree: 2%

---

# Index der IDs in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Überblick {#overview}

[!DNL Audience Manager] verwendet mehrere IDs, um die an sie gesendeten Daten zu identifizieren und zu verwalten. In diesem Artikel finden Sie eine vollständige Liste der [!DNL Audience Manager] IDs sowie Beispiele für die Präfixe, mit denen Sie sie verwenden sollten.

## ID-Präfix {#prefixing}

Die meisten dieser IDs können zwar anhand ihrer eigenständigen Namen referenziert werden, die meisten sind jedoch für die Verwendung mit verschiedenen Präfixen vorgesehen, wenn Daten über [!DNL DCS] -Aufrufe übergeben werden. Einige dieser IDs werden von [!DNL Audience Manager] verwendet, ohne für Benutzer verfügbar zu sein, während andere auch in der Benutzeroberfläche sichtbar sind.

Informationen zu den in den folgenden Beispielen verwendeten Präfixen finden Sie unter [Unterstützte Attribute für DCS-API-Aufrufe](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Liste der IDs {#id-list}

| ID | Name und Beschreibung | Nutzung und Beispiele | Standort der Benutzeroberfläche |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], auch als [!UICONTROL Device ID] bezeichnet. Eine numerische, 38-stellige Geräte-ID, die [!DNL Audience Manager] jedem Gerät zuordnet, mit dem sie interagiert. Denken Sie an diese ID, wenn Sie in der Benutzeroberfläche von [!DNL Audience Manager] eine Erwähnung von Unique Users sehen. Audience Manager speichert diese ID als [!DNL cookie] in der Drittanbieterdomäne `demdex.net`. | Bei [!DNL DCS] -Aufrufen wird `uuid` das Präfix `d_` vorangestellt. <br>Beispiel: `d_uuid = 07955261652886032950143702505894272138` | Sie können [!DNL traits] nach [!UICONTROL Device ID] filtern, wenn Sie [Look-alike-Modelle](../features/algorithmic-models/create-model.md) und [Segmente erstellen](../features/segments/segment-builder.md). Sie können die Ergebnisse auch nach [!UICONTROL Device ID] filtern, wenn [Allgemeine Berichte für Eigenschaften](../reporting/general-reports.md) und [Trendberichte für Eigenschaften](../reporting/trend-reports.md) ausgeführt werden. |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Dies ist die ID, die ein Unternehmen erhält, wenn es sich für ein [!DNL Experience Cloud] -Konto anmeldet. | `5DC5123F5245B1D20A490D46@AdobeOrg` | In der Benutzeroberfläche von [!DNL Audience Manager] nicht sichtbar. Um zu erfahren, wie Sie die [!DNL Organization ID] Ihres Unternehmens finden können, lesen Sie [Organisations-ID ermitteln](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. Die [!DNL PID] ist die Kennung eines Unternehmens in [!DNL Audience Manager]. Audience Manager ordnet einer [!DNL imsOrgId] eine [!DNL PID] zu. | `1352` | In der Benutzeroberfläche von [!DNL Audience Manager] nicht sichtbar. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. Die [!DNL Experience Cloud] ID ([!DNL ECID], veraltete Abkürzungen [!DNL MID] oder [!DNL MCID]) wird mathematisch aus Ihren [!DNL Organization ID] und den [!DNL Audience Manager] [!UICONTROL Unique User ID] abgeleitet. Solange diese IDs konstant bleiben, ist das Generieren des richtigen [!DNL ECID] für einen bestimmten Benutzer einfach ein mathematisches Problem. Mit denselben [!DNL Organization ID] und [!DNL Audience Manager] [!DNL UUID] erhalten Sie immer denselben [!DNL ECID] Wert. Weitere Informationen zu [!DNL ECID] finden Sie in der Dokumentation zu [Cookies und Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | In der Benutzeroberfläche von [!DNL Audience Manager] nicht sichtbar. |
| [!DNL SID] | [!UICONTROL Trait ID]. Der [!UICONTROL Trait ID] identifiziert [!DNL traits] eindeutig in der [!DNL Audience Manager] -Umgebung. | Bei [!DNL DCS] -Aufrufen wird `SID` das Präfix `d_` vorangestellt. <br>Beispiel `d_sid=289983`. | Jedem [!DNL trait] wird ein [!UICONTROL Trait ID] zugewiesen und auf der Seite [Eigenschaften](../features/traits/trait-details-page.md) in der Benutzeroberfläche angezeigt. |
| [!DNL SID] | [!UICONTROL Segment ID]. Der [!UICONTROL Segment ID] identifiziert [!DNL segments] eindeutig in der [!DNL Audience Manager] -Umgebung. | Bei [!DNL DCS] -Aufrufen wird `SID` das Präfix `d_` vorangestellt. <br>Beispiel `d_sid=4798574`. | Jedem [!DNL segment] wird ein [!UICONTROL Segment ID] zugewiesen und in der Benutzeroberfläche auf der Seite [Segmente](../features/segments/segment-summary-view.md) angezeigt. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Mit dieser ID werden Segmente in der [!DNL Audience Manager] -Umgebung eindeutig identifiziert. | `741232` | Jedem Segment wird ein [!UICONTROL Legacy Segment ID] zugewiesen und in der Benutzeroberfläche auf der Seite [Segmente](../features/segments/segment-summary-view.md) angezeigt. |
| [!DNL destID] | [!UICONTROL Destination ID]. Der [!UICONTROL Destination ID] identifiziert [!DNL destinations] eindeutig in der [!DNL Audience Manager] -Umgebung. Jeder [!DNL destination] in der Benutzeroberfläche wird eine ID zugewiesen. | `2523` | Jedem [!DNL destination] wird ein [!UICONTROL Destination ID] zugewiesen und auf der Seite [Ziele](../features/destinations/destinations-home.md) in der Benutzeroberfläche angezeigt. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (auch als [!UICONTROL Data Provider ID] bezeichnet). Die [!UICONTROL Data Source ID] ist ein Namespace für IDs oder [!DNL traits]. Jedem [!DNL data source] (Datenanbieter) in der Benutzeroberfläche wird eine ID zugewiesen. | Bei [!DNL DCS] -Aufrufen wird `dpid` das Präfix `d_` vorangestellt. <br>Beispiel: `d_dpid=39217`. | Jedem [!DNL data source] wird ein [!UICONTROL Data Provider ID] zugewiesen und in der Benutzeroberfläche auf der Seite [Datenquellen](../features/datasources-list-and-settings.md) angezeigt. |
| [!DNL DPUUID] | 0, auch als [!DNL CRM ID] oder [!UICONTROL Cross-Device ID] bezeichnet. [!UICONTROL Data Provider Unique User ID] Eine Drittanbieter-ID. Dies ist die ID, mit der Sie Endbenutzer in Ihrem eigenen [!DNL CRM]-System identifizieren. Sie können [!DNL DPUUIDs] mit [!DNL Audience Manager] [!DNL UUIDs] synchronisieren und [!DNL DPUUIDs] von Ihren verschiedenen [!UICONTROL Data Sources] ([!DNL DPIDs]) im ID-Synchronisierungsprozess synchronisieren. | Bei [!DNL DCS] -Aufrufen wird `dpuuid` das Präfix `d_` vorangestellt. <br> Beispiel `d_dpuuid=2132-3423vn-343fds-3432r`. | Sie können [!DNL traits] nach [!UICONTROL Cross-Device ID] filtern, wenn Sie [Look-alike-Modelle](../features/algorithmic-models/create-model.md) und [Segmente erstellen](../features/segments/segment-builder.md). Sie können die Ergebnisse auch nach [!UICONTROL Cross-Device ID] filtern, wenn [Allgemeine Berichte für Eigenschaften](../reporting/general-reports.md) und [Trendberichte für Eigenschaften](../reporting/trend-reports.md) ausgeführt werden. |
| [!DNL CRM ID] | Siehe `DPUUID`. | Siehe `DPUUID`. | Siehe `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code] Die Schlüssel-Wert-Paare [!DNL CID] und [!DNL CID_IC] ersetzen [!DNL DPID] und [!DNL DPUUID]. Sie bieten dieselben Funktionen wie die [!DNL DPID] und [!DNL DPUUID], sind jedoch effizienter, da sie die Datenanbieter-ID und die Benutzer-ID (oder den Integrationscode) in einem einzigen Schlüssel-Wert-Paar enthalten. | Bei [!DNL DCS] -Aufrufen wird diesen IDs das Präfix `d_` vorangestellt. <br>Beispiel: `d_cid_ic=39217_myIntegrationCode`. | Siehe `DPID` und `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Eine ID, die für jedes Hardwaregerät eindeutig ist und für Werbezwecke verwendet wird. Wird normalerweise vom Hersteller des Geräts oder Betriebssystems des Geräts bereitgestellt. | Siehe [Globale Geräte-IDs](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Globale Geräte-IDs sind Geräte-Werbe-IDs, die für jedes Gerät eindeutig sind und vom Gerätehersteller oder vom Betriebssystem bereitgestellt werden. In der folgenden Tabelle werden diese IDs und ihr Format erläutert. Weitere Informationen zu globalen Geräte-IDs und deren Verwendung in [!DNL Audience Manager] finden Sie unter [Globale Data Sources](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Name und Beschreibung | Beispiel |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] IDs sind vom Gerätehersteller bereitgestellte IDs für Mobilgeräte. Diese IDs stellen Geräte dar, auf denen das Betriebssystem [!DNL iOS] ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Großbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit einer Gesamtanzahl von 36 Zeichen.Beispiel: `AEBE52E7-03EE-455A-B3C4-E57283966239`.<br> |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sind Mobilgerätekennungen, die von Android-Geräteherstellern bereitgestellt werden. Diese IDs stellen Geräte dar, auf denen das Betriebssystem [!DNL Android] ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit einer Gesamtanzahl von 36 Zeichen. <br>Beispiel: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] steht für [!DNL Roku] Streaming-Geräte. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit einer Gesamtanzahl von 36 Zeichen. <br>Beispiel: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sind Gerätekennungen, die von [!DNL Windows 10] pro Gerät und Benutzer generiert werden. | [!DNL MAID]s werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] sind Geräte-IDs, die von [!DNL Samsung] Smart TVs bereitgestellt werden. | [!DNL Samsung] [!DNL TIFA] IDs werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Geräte-IDs, die Geräte darstellen, die das Betriebssystem [!DNL Fire OS] ausführen. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit einer Gesamtanzahl von 36 Zeichen. <br>Beispiel: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | Geräte-IDs, die Geräte darstellen, die das Betriebssystem [!DNL LG webOS] ausführen. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit einer Gesamtanzahl von 36 Zeichen. <br>Beispiel: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Geräte-IDs, die Geräte darstellen, auf denen das Video Smart TV-Betriebssystem ausgeführt wird. | [!DNL Vizio IFA] IDs werden als alphanumerische Zeichenfolgen formatiert. <br>Beispiel: `7XCBNROQJQPYW`. |

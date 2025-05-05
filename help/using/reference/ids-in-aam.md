---
description: Die vollständige Liste der Adobe Audience Manager-IDs finden Sie in diesem Dokument .
keywords: DPID; DPUUID; CID; UUID; uuid; uuuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: ID-Index im Audience Manager
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

[!DNL Audience Manager] verwendet mehrere IDs, um die an sie gesendeten Daten zu identifizieren und zu verwalten. In diesem Artikel finden Sie die vollständige Liste der [!DNL Audience Manager]-IDs zusammen mit Beispielen für die Präfixe, mit denen Sie sie verwenden sollten.

## ID-Präfix {#prefixing}

Die meisten dieser IDs können Sie anhand ihrer eigenständigen Namen referenzieren. Die meisten sind jedoch für die Verwendung mit verschiedenen Präfixen vorgesehen, wenn Daten über [!DNL DCS]-Aufrufe übergeben werden. Einige dieser IDs werden von [!DNL Audience Manager] verwendet, ohne dass sie Benutzenden angezeigt werden, während andere ebenfalls in der Benutzeroberfläche (UI) sichtbar sind.

Informationen zu den in den folgenden Beispielen verwendeten Präfixen finden Sie unter &quot;[ Attribute für DCS-API-Aufrufe](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## Liste der IDs [!DNL Audience Manager] {#id-list}

| ID | Name und Beschreibung | Verwendung und Beispiele | Speicherort der Benutzeroberfläche |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], auch bekannt als [!UICONTROL Device ID]. Eine numerische, 38-stellige Geräte-ID, die [!DNL Audience Manager] jedem Gerät zuordnet, mit dem es interagiert. Denken Sie immer dann an diese ID, wenn in der [!DNL Audience Manager]-Benutzeroberfläche eindeutige Benutzer erwähnt werden. Audience Manager speichert diese ID als [!DNL cookie] in der Domain `demdex.net` Drittanbieters. | In [!DNL DCS] Aufrufen wird `uuid` das Präfix `d_` vorangestellt. <br>Beispiel: `d_uuid = 07955261652886032950143702505894272138` | Sie können [!DNL traits] nach [!UICONTROL Device ID] filtern, wenn Sie [Lookalike-Modelle](../features/algorithmic-models/create-model.md) erstellen und [Segmente erstellen](../features/segments/segment-builder.md). Sie können die Ergebnisse auch nach [!UICONTROL Device ID] filtern, wenn Sie [Allgemeine Berichte für Eigenschaften](../reporting/general-reports.md) und [Trendberichte für Eigenschaften](../reporting/trend-reports.md) ausführen. |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Dies ist die ID, die einem Unternehmen bei der Anmeldung für ein [!DNL Experience Cloud]-Konto zugewiesen wird. | `5DC5123F5245B1D20A490D46@AdobeOrg` | In der Benutzeroberfläche von [!DNL Audience Manager] nicht sichtbar. Um zu erfahren, wie Sie die [!DNL Organization ID] Ihres Unternehmens finden können, lesen Sie [Organisations-ID suchen](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=de#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. Der [!DNL PID] ist die ID eines Unternehmens in [!DNL Audience Manager]. Audience Manager verknüpft eine [!DNL imsOrgId] mit einer [!DNL PID]. | `1352` | In der Benutzeroberfläche von [!DNL Audience Manager] nicht sichtbar. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. Die [!DNL Experience Cloud]-ID ([!DNL ECID], alte Abkürzungen [!DNL MID] oder [!DNL MCID]) wird mathematisch aus Ihrer [!DNL Organization ID] und dem [!DNL Audience Manager] [!UICONTROL Unique User ID] abgeleitet. Solange diese IDs konstant bleiben, ist die Erstellung der richtigen [!DNL ECID] für einen bestimmten Benutzer einfach ein mathematisches Problem. Mit den gleichen [!DNL Organization ID] und [!DNL Audience Manager] [!DNL UUID] erhalten Sie jedes Mal den gleichen [!DNL ECID]. Weitere Informationen zum [!DNL ECID] finden Sie in der Dokumentation [Cookies und Experience Cloud-ID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=de#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | In der Benutzeroberfläche von [!DNL Audience Manager] nicht sichtbar. |
| [!DNL SID] | [!UICONTROL Trait ID]. Die [!UICONTROL Trait ID] identifiziert [!DNL traits] in der [!DNL Audience Manager]-Umgebung eindeutig. | In [!DNL DCS] Aufrufen wird `SID` das Präfix `d_` vorangestellt. <br>Beispiel `d_sid=289983`. | Jedem [!DNL trait] wird ein [!UICONTROL Trait ID] zugewiesen, der auf der Seite „Eigenschaften[ in der Benutzeroberfläche ](../features/traits/trait-details-page.md) ist. |
| [!DNL SID] | [!UICONTROL Segment ID]. Die [!UICONTROL Segment ID] identifiziert [!DNL segments] in der [!DNL Audience Manager]-Umgebung eindeutig. | In [!DNL DCS] Aufrufen wird `SID` das Präfix `d_` vorangestellt. <br>Beispiel `d_sid=4798574`. | Jedem [!DNL segment] wird ein [!UICONTROL Segment ID] zugewiesen, der auf der Seite „Segmente[ in der Benutzeroberfläche ](../features/segments/segment-summary-view.md) ist. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Diese ID identifiziert Segmente in der [!DNL Audience Manager]-Umgebung eindeutig. | `741232` | Jedem Segment wird ein [!UICONTROL Legacy Segment ID] zugewiesen, der auf der Seite „Segmente“ in der Benutzeroberfläche [ wird](../features/segments/segment-summary-view.md). |
| [!DNL destID] | [!UICONTROL Destination ID]. Die [!UICONTROL Destination ID] identifiziert [!DNL destinations] in der [!DNL Audience Manager]-Umgebung eindeutig. Jedem [!DNL destination] in der Benutzeroberfläche wird eine ID zugewiesen. | `2523` | Jedem [!DNL destination] wird ein [!UICONTROL Destination ID] zugewiesen, der in der Benutzeroberfläche auf der Seite [Ziele“ ](../features/destinations/destinations-home.md) ist. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (auch als [!UICONTROL Data Provider ID] bezeichnet). Der [!UICONTROL Data Source ID] ist ein Namespace für IDs oder [!DNL traits]. Jedem [!DNL data source] (Datenanbieter) wird in der Benutzeroberfläche eine ID zugewiesen. | In [!DNL DCS] Aufrufen wird `dpid` das Präfix `d_` vorangestellt. <br>Beispiel: `d_dpid=39217`. | Jedem [!DNL data source] wird ein [!UICONTROL Data Provider ID] zugewiesen, der in der Benutzeroberfläche auf der Seite [Datenquellen“ ](../features/datasources-list-and-settings.md) ist. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], auch als [!DNL CRM ID] oder [!UICONTROL Cross-Device ID] bezeichnet. Eine Drittanbieter-ID. Dies ist die ID, mit der Sie Endbenutzer in Ihrem eigenen [!DNL CRM] identifizieren. Sie können [!DNL DPUUIDs] mit [!DNL Audience Manager] [!DNL UUIDs] synchronisieren und [!DNL DPUUIDs] aus Ihren verschiedenen [!UICONTROL Data Sources] ([!DNL DPIDs]) im ID-Synchronisierungsprozess synchronisieren. | In [!DNL DCS] Aufrufen wird `dpuuid` das Präfix `d_` vorangestellt. <br> Beispiel `d_dpuuid=2132-3423vn-343fds-3432r`. | Sie können [!DNL traits] nach [!UICONTROL Cross-Device ID] filtern, wenn Sie [Lookalike-Modelle](../features/algorithmic-models/create-model.md) erstellen und [Segmente erstellen](../features/segments/segment-builder.md). Sie können die Ergebnisse auch nach [!UICONTROL Cross-Device ID] filtern, wenn Sie [Allgemeine Berichte für Eigenschaften](../reporting/general-reports.md) und [Trendberichte für Eigenschaften](../reporting/trend-reports.md) ausführen. |
| [!DNL CRM ID] | Siehe `DPUUID`. | Siehe `DPUUID`. | Siehe `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Die Schlüssel-Wert-Paare [!DNL CID] und [!DNL CID_IC] ersetzen [!DNL DPID] und [!DNL DPUUID]. Sie bieten dieselben Funktionen wie die [!DNL DPID] und [!DNL DPUUID], sind aber effizienter, da sie die Datenanbieter-ID und die Benutzer-ID (oder den Integrations-Code) in einem einzigen Schlüssel-Wert-Paar enthalten. | In [!DNL DCS] Aufrufen wird diesen IDs das Präfix `d_` vorangestellt. <br>Beispiel: `d_cid_ic=39217_myIntegrationCode`. | Siehe `DPID` und `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Eine ID, die für jedes Hardwaregerät eindeutig ist und für Werbezwecke verwendet wird. Wird in der Regel vom Hersteller des Geräts oder des Geräte-Betriebssystems bereitgestellt. | Siehe [Globale Geräte-IDs](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Globale Geräte-IDs sind Geräte-Werbe-IDs, die für jedes Gerät eindeutig sind und vom Gerätehersteller oder Betriebssystem bereitgestellt werden. In der folgenden Tabelle wird erläutert, was diese IDs sind und welches ihr Format ist. Weitere Informationen zu globalen Geräte-IDs und deren Verwendung in [!DNL Audience Manager] finden Sie unter [Globale Datenquellen](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Name und Beschreibung | Beispiel |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers]-IDs sind vom Gerätehersteller bereitgestellte Kennungen von Mobilgeräten. Diese IDs stellen Geräte dar, auf denen das [!DNL iOS] Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Großbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche in der Form 8-4-4-4-12 getrennt sind, was insgesamt 36 Zeichen ergibt.<br>: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sind Kennung für Mobilgeräte, die von Android-Geräteherstellern bereitgestellt wird. Diese IDs stellen Geräte dar, auf denen das [!DNL Android] Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche in der Form 8-4-4-4-12 getrennt sind, was insgesamt 36 Zeichen ergibt. <br>Beispiel: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] stellen [!DNL Roku] Streaming-Geräte dar. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche in der Form 8-4-4-4-12 getrennt sind, was insgesamt 36 Zeichen ergibt. <br>Beispiel: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sind Geräte-IDs, die von [!DNL Windows 10] pro Gerät und Benutzer generiert werden. | [!DNL MAID] werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] sind Gerätekennungen, die von [!DNL Samsung] Smart-TVs bereitgestellt werden. | [!DNL Samsung] [!DNL TIFA] IDs werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Gerätekennungen, die Geräte darstellen, auf denen das [!DNL Fire OS] Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche in der Form 8-4-4-4-12 getrennt sind, was insgesamt 36 Zeichen ergibt. <br>Beispiel: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | Gerätekennungen, die Geräte darstellen, auf denen das [!DNL LG webOS] Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche in der Form 8-4-4-4-12 getrennt sind, was insgesamt 36 Zeichen ergibt. <br>Beispiel: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Gerätekennungen, die Geräte darstellen, auf denen das Betriebssystem Vizio Smart TV ausgeführt wird. | [!DNL Vizio IFA] IDs werden als alphanumerische Zeichenfolgen formatiert. <br>Beispiel: `7XCBNROQJQPYW`. |

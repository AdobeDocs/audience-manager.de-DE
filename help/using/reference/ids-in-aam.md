---
description: Die vollständige Liste der Adobe Audience Manager-IDs finden Sie in diesem Dokument.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Die vollständige Liste der Adobe Audience Manager-IDs finden Sie in diesem Dokument.
seo-title: Index der IDs in Audience Manager
solution: Audience Manager
title: Index der IDs in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: f8916812a31513d3d8401a0598f37dae02a3fd02

---


# Index der IDs in Audience Manager{#index-of-ids-in-audience-manager}

## Überblick {#overview}

Audience Manager verwendet mehrere IDs, um die Daten zu identifizieren und zu verwalten, die Sie an ihn senden. In diesem Artikel finden Sie eine vollständige Liste der Adobe Audience Manager-IDs sowie Beispiele der Präfixe, mit denen Sie sie verwenden sollten.

## ID-Vorgabe {#prefixing}

Die meisten dieser IDs sind zwar mit eigenständigen Namen gekennzeichnet, die meisten sind jedoch für die Verwendung mit verschiedenen Präfixen vorgesehen, wenn Daten über DCS-Aufrufe weitergegeben werden. Einige dieser IDs werden von Audience Manager verwendet, ohne dass sie Benutzern zur Verfügung stehen, während andere auch in der Benutzeroberfläche (Benutzeroberfläche) sichtbar sind.

Informationen zu den in den folgenden Beispielen verwendeten Präfixen finden Sie unter [Unterstützte Attribute für DCS-API-Aufrufe](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## Audience Manager-Liste der IDs {#id-list}

| ID | Name und Beschreibung | Nutzung und Beispiele | UI-Position |
|---|---|---|---|
| [!DNL AAM UUID] | Audience Manager - Eindeutige Benutzer-ID. Eine numerische, 38-stellige Geräte-ID, die Audience Manager jedem Gerät zuordnet, mit dem er interagiert. Denken Sie an diese ID, wenn Sie in der Benutzeroberfläche von Audience Manager eine Erwähnung individueller Benutzer sehen. Audience Manager speichert diese ID als Cookie in der `demdex.net` Drittanbieterdomäne. | Bei [!DNL DCS] Aufrufen `uuid` wird das `d_` Präfix vorangestellt. <br>Beispiel: `d_uuid = 07955261652886032950143702505894272138` | Nicht in der Benutzeroberfläche von Audience Manager sichtbar. |
| [!DNL ImsOrgId] | Organisations-ID. Diese ID wird einem Unternehmen bei der Anmeldung für ein Experience Cloud-Konto bereitgestellt. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Nicht in der Benutzeroberfläche von Audience Manager sichtbar. Lesen Sie [Suchen Sie nach Ihrer Organisations-ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255), um zu erfahren, wie Sie die Organisations-ID Ihres Unternehmens finden. |
| PID | Partner-ID. Die PID ist die ID eines Unternehmens in Audience Manager. Audience Manager verknüpft eine [!DNL imsOrgId] mit einer [!DNL PID]. | `1352` | Nicht in der Benutzeroberfläche von Audience Manager sichtbar. |
| [!DNL ECID], [!DNL MID] | Experience Cloud-ID. Die Experience Cloud ID ([!DNL ECID], veraltete Abkürzungen [!DNL MID] oder [!DNL MCID]) wird mathematisch aus Ihrer Organisations-ID und der eindeutigen Benutzer-ID von Audience Manager abgeleitet. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. Weitere Informationen zur ECID finden Sie in der Dokumentation zu [Cookies und Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Nicht in der Benutzeroberfläche von Audience Manager sichtbar. |
| [!DNL SID] | Eigenschaften-ID. Die Eigenschaften-ID identifiziert Eigenschaften eindeutig in der Audience Manager-Umgebung. | Bei [!DNL DCS] Aufrufen `SID` wird das `d_` Präfix vorangestellt. <br>Beispiel `d_sid=289983`. | Jeder Eigenschaft wird eine Eigenschaften-ID zugewiesen und auf der Seite &quot; [Eigenschaften](../features/traits/trait-details-page.md) &quot;in der Benutzeroberfläche angezeigt. |
| [!DNL SID] | Segment-ID. Die Segment-ID identifiziert Segmente eindeutig in der Audience Manager-Umgebung. | Bei [!DNL DCS] Aufrufen `SID` wird das `d_` Präfix vorangestellt. <br>Beispiel `d_sid=4798574`. | Jedem Segment wird eine Segment-ID zugewiesen, die in der Benutzeroberfläche auf der Seite &quot; [Segmente](../features/segments/segment-summary-view.md) &quot;angezeigt wird. |
| [!DNL csegID] | Legacy-Segment-ID. Diese ID identifiziert Segmente eindeutig in der Audience Manager-Umgebung. | `741232` | Jedem Segment wird eine Legacy-Segment-ID zugewiesen, die in der Benutzeroberfläche auf der Seite &quot; [Segmente](../features/segments/segment-summary-view.md) &quot;angezeigt wird. |
| [!DNL destID] | Ziel-ID. Die Ziel-ID identifiziert Ziele eindeutig in der Audience Manager-Umgebung. Jedem Ziel in der Benutzeroberfläche wird eine ID zugewiesen. | `2523` | Jedem Ziel wird eine Ziel-ID zugewiesen, die in der Benutzeroberfläche auf der Seite &quot; [Ziele](../features/destinations/destinations-home.md) &quot;angezeigt wird. |
| [!DNL DPID] | Datenquellen-ID (auch als Datenanbieter-ID bezeichnet). Die Datenquellen-ID ist ein Namespace für IDs oder Eigenschaften. Jeder Datenquelle (Datenanbieter) in der Benutzeroberfläche wird eine ID zugewiesen. | Bei [!DNL DCS] Aufrufen `dpid` wird das `d_` Präfix vorangestellt. <br>Beispiel: `d_dpid=39217`. | Jeder Datenquelle wird eine Datenanbieter-ID zugewiesen und auf der Seite &quot; [Datenquellen](../features/datasources-list-and-settings.md) &quot;in der Benutzeroberfläche angezeigt. |
| [!DNL DPUUID] | Eindeutige Datenanbieter-Benutzer-ID (auch als [!DNL CRM ID]bezeichnet). Eine Drittanbieter-ID. Mit dieser ID können Sie Endbenutzer in Ihrem eigenen [!DNL CRM] System identifizieren. Sie können [!DNL DPUUIDs] mit Audience Manager synchronisieren [!DNL UUIDs] und im ID-Synchronisierungsprozess aus [!DNL DPUUIDs] den verschiedenen Datenquellen ([!DNL DPIDs]) synchronisieren. | Bei DCS-Aufrufen `dpuuid` wird das `d_` Präfix vorangestellt. <br> Beispiel `d_dpuuid=2132-3423vn-343fds-3432r`. | Nicht in der Benutzeroberfläche von Audience Manager sichtbar. |
| [!DNL CRM ID] | Siehe `DPUUID`. | Siehe `DPUUID`. | Siehe `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | Kunden-ID, Kunden-ID-Integrationscode. Die Paare [!DNL CID] und [!DNL CID_IC] Schlüssel-Wert ersetzen [!DNL DPID] und [!DNL DPUUID]. Sie bieten die gleichen Funktionen wie die [!DNL DPID] und [!DNL DPUUID]sind jedoch effizienter, da sie die Datenanbieter-ID und die Benutzer-ID (oder den Integrationscode) in einem einzelnen Schlüssel-Wert-Paar enthalten. | Bei DCS-Aufrufen wird diesen IDs das `d_` Präfix vorangestellt. <br>Beispiel: `d_cid_ic=39217_myIntegrationCode`. | Siehe `DPID` und `DPUUID`. |
| [!DNL DAID] | Geräte-Werbe-ID. Eine ID, die für jedes Hardwaregerät eindeutig ist und für Werbezwecke verwendet wird. In der Regel vom Hersteller des Geräts oder Betriebssystems bereitgestellt. | Siehe [Globale Geräte-IDs](#global-device-ids). |  |

## Globale Geräte-IDs {#global-device-ids}

Globale Geräte-IDs sind Anzeigen-IDs für Geräte, die für jedes Gerät einzeln vom Gerätehersteller oder vom Betriebssystem bereitgestellt werden. In der folgenden Tabelle werden die IDs und ihr Format erläutert. Weitere Informationen zu globalen Geräte-IDs und ihrer Verwendung in Audience Manager finden Sie unter [Globale Datenquellen](/help/using/features/global-data-sources.md).

| ID | Globale Datenquelle-ID | Name und Beschreibung | Beispiel  |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] IDs sind vom Gerätehersteller bereitgestellte Mobilgerätekennungen. Diese IDs stellen Geräte dar, auf denen das iOS-Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Großbuchstaben, die in fünf Gruppen angezeigt und durch Bindestriche getrennt werden, im Format 8-4-4-4-12, mit einer Gesamtlänge von 36 Zeichen.<br> Beispiel: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sind Mobilgerätekennungen, die von Android-Geräteherstellern bereitgestellt werden. Diese IDs stellen Geräte dar, auf denen das [!DNL Android] Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen. <br>Beispiel: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] repräsentieren [!DNL Roku] Streaming-Geräte. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen. <br>Beispiel: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sind Geräte-IDs, die von [!DNL Windows 10] pro Gerät und pro Benutzer generiert werden. | [!DNL MAID]s werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s sind Gerätekennungen, die von Samsung Smart TVs bereitgestellt werden. | Samsung [!DNL DUID]s werden als alphanumerische Zeichenfolgen formatiert. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Geräte-IDs, die Geräte darstellen, auf denen das [!DNL Fire OS] Betriebssystem ausgeführt wird. | Das Format besteht ausschließlich aus 32 Hexadezimalziffern in Kleinbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, im Format 8-4-4-4-12, mit insgesamt 36 Zeichen. <br>Beispiel: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |


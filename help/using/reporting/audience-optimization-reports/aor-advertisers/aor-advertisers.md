---
description: Audience Optimization für Werbetreibende kann Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Kampagnen zu ermitteln. Diese Berichte kombinieren Leistungsdaten zur Kampagne auf Protokollierungsebene mit Segmentmetriken auf Audience Manager-Ebene, um segmentorientierte Optimierungen und einen effektiven Kanal-Mix zu ermöglichen.
seo-description: Audience Optimization für Werbetreibende kann Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Kampagnen zu ermitteln. Diese Berichte kombinieren Leistungsdaten zur Kampagne auf Protokollierungsebene mit Segmentmetriken auf Audience Manager-Ebene, um segmentorientierte Optimierungen und einen effektiven Kanal-Mix zu ermöglichen.
seo-title: Zielgruppenoptimierung für Advertiser
solution: Audience Manager
title: Zielgruppenoptimierung für Advertiser
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 3%

---

# [!UICONTROL Audience Optimization] für Werbetreibende{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] für Werbetreibende können Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medien-Kampagnen zu identifizieren. Diese Berichte kombinieren Leistungsdaten zur Kampagne auf Protokollebene mit Audience Manager [!UICONTROL segment]-Metriken, um segmentorientierte Optimierungen und einen effektiven Kanal-Mix zu ermöglichen.

## Datenaufnahmemethoden {#data-ingestion-methods}

Sie können Daten mit einer der folgenden Methoden an [!DNL Audience Manager] zur Verwendung in diesen Berichten senden. Manchmal senden Kunden Daten mit beiden Methoden. Auf diese Weise stellen Sie sicher, dass Ihre Berichte die umfassendsten und genauesten Informationen über einen Besucher enthalten. Um die Berichte [!UICONTROL Audience Optimization] zu verwenden, müssen Ihre Ereignis-Aufrufe *alle* der Parameter enthalten, die in der [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)-Dokumentation aufgeführt sind. Sie können Daten mit den folgenden Methoden senden.

* Pixelaufrufe: Informationen zum Übermitteln der erforderlichen Metadatenparameter an [!DNL Audience Manager] finden Sie unter [Erfassen von Kampagnen-Klickdaten über Pixelaufrufe](../../../integration/media-data-integration/click-data-pixels.md) und [Erfassen von Kampagnen-Impressionsdaten über Pixelaufrufe](../../../integration/media-data-integration/impression-data-pixels.md).

* Datendateien: Wenn Sie diese Berichte verwenden möchten, um Ihre eigenen Daten oder Daten aus einer Quelle zu analysieren, die nicht mit [!DNL Audience Manager] integriert ist, müssen Sie Daten- und Metadatendateien für diese Daten erstellen und hochladen. Weitere Informationen finden Sie unter [Datendateien für Audience Optimizationen-Berichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) und [Daten- und Metadatendateien für Audience Optimizationen-Berichte](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

Die Art der Berichte, die Sie Ansichten vornehmen können, hängt von der [!UICONTROL RBAC]-Gruppe ab, der Sie zugewiesen sind. Weitere Informationen finden Sie unter [Administration](../../../features/administration/administration-overview.md) und [Gruppe erstellen](../../../features/administration/administration-overview.md#create-group).

[!UICONTROL RBAC] müssen einige Datenquellen eingerichtet sein, um die  [!UICONTROL Audience Optimization] Berichte Ansicht. Ihr [!DNL Audience Manager]-Berater richtet diese [!UICONTROL data sources] für Sie ein. Je mehr [!UICONTROL data sources] in jeder [!UICONTROL RBAC]-Benutzergruppe vorhanden ist, desto mehr Daten haben diese Gruppenmitglieder Zugriff darauf. Mindestens eine der folgenden [!UICONTROL data sources] wird von Ihrem Berater eingerichtet:

* Advertiser [!UICONTROL data source ]
* Marke [!UICONTROL data source]
* Plattform [!UICONTROL data source]

Benutzer, die zu mehr als einer [!UICONTROL RBAC]-Benutzergruppe gehören, können zwischen der Ansicht der einzelnen Gruppen wechseln. Die angezeigten Daten werden aktualisiert, um die ausgewählte Gruppe zu berücksichtigen. Wenn Ihre Firma [!UICONTROL RBAC] nicht verwendet, verfügen alle Benutzer über Administratorrechte und Zugriff auf alle [!UICONTROL data sources] (Konversionsgruppen).

## Umrechnungsgruppen {#conversion-groups}

In den [!UICONTROL Audience Optimization]-Berichten sind **[!UICONTROL Conversion Groups]** mit [!UICONTROL data sources] synonym, die mindestens eine Konversionseigenschaft enthalten. [!UICONTROL Data sources] die nicht mindestens eine Konversionseigenschaft enthalten, werden nicht in den  [!UICONTROL Audience Optimization] Berichten angezeigt. Sie können die Konversionseigenschaften für Konversionsgruppen im Bericht [Berichtete Konversionseigenschaften](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) Ansicht haben.

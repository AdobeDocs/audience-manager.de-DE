---
description: Audience Optimization für Advertiser kann Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medienkampagnen zu ermitteln. Diese Berichte kombinieren Kampagnenleistungsdaten auf Protokollebene mit Audience Manager-Segmentmetriken, um segmentorientierte Optimierungen und einen effektiven Kanalmix zu ermöglichen.
seo-description: Audience Optimization für Advertiser kann Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medienkampagnen zu ermitteln. Diese Berichte kombinieren Kampagnenleistungsdaten auf Protokollebene mit Audience Manager-Segmentmetriken, um segmentorientierte Optimierungen und einen effektiven Kanalmix zu ermöglichen.
seo-title: Zielgruppenoptimierung für Advertiser
solution: Audience Manager
title: Zielgruppenoptimierung für Advertiser
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Berichte zur Zielgruppenoptimierung
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 3%

---

# [!UICONTROL Audience Optimization] für Advertiser{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] für Advertiser können Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren Paid-Media-Kampagnen zu ermitteln. Diese Berichte kombinieren Kampagnenleistungsdaten auf Protokollebene mit Audience Manager-Metriken [!UICONTROL segment] , um segmentorientierte Optimierungen und einen effektiven Kanalmix zu ermöglichen.

## Datenerfassungsmethoden {#data-ingestion-methods}

Sie können Daten mithilfe einer dieser Methoden an [!DNL Audience Manager] senden, um sie in diesen Berichten zu verwenden. Manchmal senden Kunden Daten mit beiden Methoden. Dadurch wird sichergestellt, dass Ihre Berichte die umfassendsten und genauesten Informationen über einen Besucher enthalten. Um die [!UICONTROL Audience Optimization] -Berichte verwenden zu können, müssen Ihre Ereignisaufrufe *alle* der Parameter umfassen, die in der Dokumentation [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) aufgeführt sind. Sie können Daten mit den folgenden Methoden versenden.

* Pixelaufrufe: Informationen zum Übergeben der erforderlichen Metadatenparameter an [!DNL Audience Manager] finden Sie unter [Erfassen von Kampagnen-Klickdaten über Pixelaufrufe](../../../integration/media-data-integration/click-data-pixels.md) und [Erfassen von Kampagnen-Impressionsdaten über Pixelaufrufe](../../../integration/media-data-integration/impression-data-pixels.md).

* Datendateien: Wenn Sie diese Berichte verwenden möchten, um Ihre eigenen Daten oder Daten aus einer Quelle zu analysieren, die nicht mit [!DNL Audience Manager] integriert ist, müssen Sie Daten- und Metadatendateien für diese Daten erstellen und hochladen. Weitere Informationen finden Sie unter [Datendateien für Audience Optimization-Berichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) und [Daten- und Metadatendateien für Audience Optimization-Berichte](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Die Art der Berichte, die Sie anzeigen können, hängt von der [!UICONTROL RBAC] Gruppe ab, der Sie zugewiesen sind. Weitere Informationen finden Sie unter [Administration](../../../features/administration/administration-overview.md) und [Erstellen einer Gruppe](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] -Gruppen müssen einige Datenquellen eingerichtet haben, um die  [!UICONTROL Audience Optimization] Berichte anzeigen zu können. Ihr [!DNL Audience Manager] -Berater wird diese [!UICONTROL data sources] für Sie einrichten. Je mehr [!UICONTROL data sources] in jeder [!UICONTROL RBAC]-Benutzergruppe enthalten ist, desto mehr Daten haben diese Gruppenmitglieder Zugriff auf diese. Ihr Berater richtet mindestens einen der folgenden [!UICONTROL data sources] ein:

* Advertiser [!UICONTROL data source ]
* Marke [!UICONTROL data source]
* Plattform [!UICONTROL data source]

Benutzer, die zu mehr als einer [!UICONTROL RBAC] Benutzergruppe gehören, können zwischen den Ansichten jeder Gruppe wechseln. Die angezeigten Daten werden entsprechend der ausgewählten Gruppe aktualisiert. Wenn Ihr Unternehmen [!UICONTROL RBAC] nicht verwendet, verfügen alle Benutzer über Administratorrechte und Zugriff auf alle [!UICONTROL data sources] (Konversionsgruppen).

## Konversionsgruppen {#conversion-groups}

In den [!UICONTROL Audience Optimization] -Berichten sind **[!UICONTROL Conversion Groups]** Synonyme für [!UICONTROL data sources], die mindestens eine Konversionseigenschaft enthalten. [!UICONTROL Data sources] die nicht mindestens eine Konversionseigenschaft enthalten, werden nicht in den  [!UICONTROL Audience Optimization] Berichten angezeigt. Sie können die Konversionseigenschaften für Konversionsgruppen im Bericht [Gemeldete Konversionseigenschaften](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) anzeigen.

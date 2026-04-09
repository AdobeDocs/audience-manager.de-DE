---
description: Audience Optimization for Advertisers kann Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren Paid-Media-Kampagnen zu identifizieren. Diese Berichte kombinieren Kampagnenleistungsdaten auf Protokollebene mit Audience Manager-Segmentmetriken, um segmentorientierte Optimierungen und einen effektiven Kanalmix zu erzielen.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization für Werbetreibende
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
TQID: https://experienceleague.adobe.com/U9Rg-4rwjGdqYsjGDlctn0PBuxAlDjwIBtorAnGtqHU
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 406
ht-degree: 0%

---

# [!UICONTROL Audience Optimization] für Advertiser{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] für Werbetreibende können Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren Paid-Media-Kampagnen zu identifizieren. Diese Berichte kombinieren Kampagnenleistungsdaten auf Protokollebene mit Audience Manager-[!UICONTROL segment], um segmentorientierte Optimierungen und einen effektiven Kanalmix zu erzielen.

## Methoden zur Datenaufnahme {#data-ingestion-methods}

Sie können Daten zur Verwendung in diesen Berichten an [!DNL Audience Manager] senden, indem Sie eine der beiden folgenden Methoden verwenden. Manchmal senden Kundinnen und Kunden Daten mit beiden Methoden. Dadurch wird sichergestellt, dass Ihre Berichte möglichst umfassende und genaue Informationen über einen Besucher enthalten. Um die [!UICONTROL Audience Optimization] Berichte verwenden zu können, müssen Ihre Ereignisaufrufe *alle* der Parameter enthalten, die in der Dokumentation [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) aufgeführt sind. Sie können Daten über die folgenden Methoden senden.

* Pixel-Aufrufe: Zum Übergeben der erforderlichen Metadatenparameter, um [!DNL Audience Manager] zu sehen [Erfassen von Kampagnenklick-Daten über Pixel-Aufrufe](../../../integration/media-data-integration/click-data-pixels.md) und [Erfassen von Kampagnen-Impressionsdaten über Pixel-Aufrufe](../../../integration/media-data-integration/impression-data-pixels.md).

* Datendateien: Wenn Sie diese Berichte verwenden möchten, um Ihre eigenen Daten oder Daten aus einer Quelle zu analysieren, die nicht mit [!DNL Audience Manager] integriert ist, müssen Sie Daten- und Metadatendateien für diese Daten erstellen und hochladen. Weitere Informationen finden Sie unter [Datendateien für Audience Optimization-](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) und [Daten- und Metadatendateien für Audience Optimization-Berichte](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Die Art der Berichte, die Sie anzeigen können, hängt von der [!UICONTROL RBAC] ab, der Sie zugewiesen sind. Weitere Informationen finden [&#x200B; unter &#x200B;](../../../features/administration/administration-overview.md) und [Erstellen &#x200B;](../../../features/administration/administration-overview.md#create-group) Gruppe“.

[!UICONTROL RBAC] müssen einige Datenquellen eingerichtet haben, um die [!UICONTROL Audience Optimization] Berichte anzeigen zu können. Ihr [!DNL Audience Manager] Berater richtet diese [!UICONTROL data sources] für Sie ein. Je mehr [!UICONTROL data sources] in jeder [!UICONTROL RBAC] Benutzergruppe vorhanden sind, desto mehr Daten haben diese Gruppenmitglieder Zugriff. Ihr Berater richtet mindestens eine der folgenden [!UICONTROL data sources] ein:

* Advertiser [!UICONTROL data source]
* Brand [!UICONTROL data source]
* [!UICONTROL data source]

Benutzer, die zu mehr als einer [!UICONTROL RBAC] Benutzergruppe gehören, können zwischen den Ansichten jeder Gruppe wechseln. Die angezeigten Daten werden entsprechend der ausgewählten Gruppe aktualisiert. Wenn Ihr Unternehmen [!UICONTROL RBAC] nicht verwendet, haben alle Benutzer Administratorrechte und Zugriff auf alle [!UICONTROL data sources] (Konversionsgruppen).

## Konversionsgruppen {#conversion-groups}

In den [!UICONTROL Audience Optimization] Berichten sind **[!UICONTROL Conversion Groups]** synonym mit [!UICONTROL data sources], die mindestens ein Konversionsmerkmal enthalten. [!UICONTROL Data sources], die nicht mindestens ein Konversionseigenschaft enthalten, werden nicht in den [!UICONTROL Audience Optimization]-Berichten angezeigt. Sie können die Konversionseigenschaften für Konversionsgruppen im Bericht &quot;[&#x200B; Konversionseigenschaften“ &#x200B;](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).

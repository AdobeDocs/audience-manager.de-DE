---
description: Die Optimierung der Audience für Werbetreibende kann Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager in Ihren gebührenpflichtigen Kampagnen zu ermitteln. Diese Berichte kombinieren Leistungsdaten zur Kampagne auf Protokollierungsebene mit Segmentmetriken auf Audience Manager-Ebene, um segmentorientierte Optimierungen und einen effektiven Kanal-Mix zu ermöglichen.
seo-description: Die Optimierung der Audience für Werbetreibende kann Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager in Ihren gebührenpflichtigen Kampagnen zu ermitteln. Diese Berichte kombinieren Leistungsdaten zur Kampagne auf Protokollierungsebene mit Segmentmetriken auf Audience Manager-Ebene, um segmentorientierte Optimierungen und einen effektiven Kanal-Mix zu ermöglichen.
seo-title: Zielgruppenoptimierung für Advertiser
solution: Audience Manager
title: Zielgruppenoptimierung für Advertiser
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---


# [!UICONTROL Audience Optimization] für Werbetreibende{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] für Werbetreibende können Ihnen dabei helfen, potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medien-Kampagnen zu identifizieren. Diese Berichte kombinieren Leistungsdaten zur Kampagne auf Protokollebene mit [!UICONTROL segment] den Audience Manager-Metriken, um segmentorientierte Optimierungen und einen effektiven Kanal-Mix zu ermöglichen.

## Datenaufnahmemethoden {#data-ingestion-methods}

Sie können Daten mit einer der folgenden Methoden zur Verwendung in diesen Berichten senden [!DNL Audience Manager] . Manchmal senden Kunden Daten mit beiden Methoden. Auf diese Weise stellen Sie sicher, dass Ihre Berichte die umfassendsten und genauesten Informationen über einen Besucher enthalten. Zur Verwendung der [!UICONTROL Audience Optimization] Berichte müssen Ihre Ereignis-Aufrufe *alle* Parameter enthalten, die in der Dokumentation [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) aufgeführt sind. Sie können Daten mit den folgenden Methoden senden.

* Pixelaufrufe: Um die erforderlichen Metadatenparameter zu übergeben, [!DNL Audience Manager] um die [Erfassung von Klickdaten über Pixelaufrufe](../../../integration/media-data-integration/click-data-pixels.md) und die [Erfassung von Kampagne-Impressionsdaten über Pixelaufrufe](../../../integration/media-data-integration/impression-data-pixels.md)zu sehen.

* Datendateien: Wenn Sie diese Berichte verwenden möchten, um Ihre eigenen Daten oder Daten aus einer Quelle zu analysieren, die nicht mit integriert ist, [!DNL Audience Manager]müssen Sie Daten- und Metadatendateien für diese Daten erstellen und hochladen. Weitere Informationen finden Sie unter [Datendateien für Optimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) für Audiencen und [Daten- und Metadatendateien für Audiencen-Optimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Die Art der Berichte, die Sie Ansichten vornehmen können, hängt von der [!UICONTROL RBAC] Gruppe ab, der Sie zugewiesen sind. Weitere Informationen finden Sie unter [Administration](../../../features/administration/administration-overview.md) und [Erstellen einer Gruppe](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] müssen einige Datenquellen eingerichtet sein, um die [!UICONTROL Audience Optimization] Berichte Ansicht. Ihr [!DNL Audience Manager] Berater wird diese [!UICONTROL data sources] für Sie einrichten. Je mehr Daten [!UICONTROL data sources] in jeder [!UICONTROL RBAC] Benutzergruppe vorhanden sind, desto mehr können die Gruppenmitglieder darauf zugreifen. Mindestens eine der folgenden Aufgaben wird von Ihrem Berater eingerichtet [!UICONTROL data sources]:

* Advertiser [!UICONTROL data source ]
* Marke [!UICONTROL data source]
* Plattform [!UICONTROL data source]

Benutzer, die zu mehr als einer [!UICONTROL RBAC] Benutzergruppe gehören, können zwischen den Ansichten der einzelnen Gruppen wechseln. Die angezeigten Daten werden aktualisiert, um die ausgewählte Gruppe zu berücksichtigen. Wenn Ihre Firma nicht verwendet [!UICONTROL RBAC]wird, verfügen alle Benutzer über Administratorrechte und Zugriff auf alle [!UICONTROL data sources] (Konversionsgruppen).

## Konversionsgruppen {#conversion-groups}

In den [!UICONTROL Audience Optimization] Berichten **[!UICONTROL Conversion Groups]** sind synonym mit [!UICONTROL data sources] , die mindestens eine Konversionseigenschaft enthalten. [!UICONTROL Data sources] die nicht mindestens eine Konversionseigenschaft enthalten, werden nicht in den [!UICONTROL Audience Optimization] Berichten angezeigt. Sie können die Konversionseigenschaften für Konversionsgruppen im Bericht &quot; [Berichtete Konversionseigenschaften](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) &quot;Ansicht haben.

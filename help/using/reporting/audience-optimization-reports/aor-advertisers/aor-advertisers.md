---
description: Mit der Zielgruppenoptimierung für Werbetreibende können Sie potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medienkampagnen identifizieren. Diese Berichte kombinieren Kampagnenleistungsdaten auf Protokollebene mit Segmentmetriken von Audience Manager, um segmentorientierte Optimierungen und einen effektiven Kanalmix zu ermöglichen.
seo-description: Mit der Zielgruppenoptimierung für Werbetreibende können Sie potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medienkampagnen identifizieren. Diese Berichte kombinieren Kampagnenleistungsdaten auf Protokollebene mit Segmentmetriken von Audience Manager, um segmentorientierte Optimierungen und einen effektiven Kanalmix zu ermöglichen.
seo-title: Zielgruppenoptimierung für Werbetreibende
solution: Audience Manager
title: Zielgruppenoptimierung für Werbetreibende
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

Mit der Zielgruppenoptimierung für Werbetreibende können Sie potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medienkampagnen identifizieren. Diese Berichte kombinieren Kampagnenleistungsdaten auf Protokollebene mit Segmentmetriken von Audience Manager, um segmentorientierte Optimierungen und einen effektiven Kanalmix zu ermöglichen.

## Datenaufnahmemethoden {#data-ingestion-methods}

Sie können Daten mit einer der folgenden Methoden zur Verwendung in diesen Berichten senden [!DNL Audience Manager] . Manchmal senden Kunden Daten mit beiden Methoden. Auf diese Weise stellen Sie sicher, dass Ihre Berichte die umfassendsten und genauesten Informationen über einen Besucher enthalten. Zur Verwendung der [!UICONTROL Audience Optimization] Berichte müssen Ihre Ereignisaufrufe *alle* Parameter enthalten, die in der Dokumentation [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) aufgeführt sind. Sie können Daten mit den folgenden Methoden senden.

* Pixelaufrufe: Um die erforderlichen Metadaten-Parameter zu übermitteln, um die [!DNL Audience Manager]Erfassung von Kampagnen-Klickdaten über Pixelaufrufe[ und die ](../../../integration/media-data-integration/click-data-pixels.md)Erfassung von Kampagnenimpressionsdaten über Pixelaufrufe[](../../../integration/media-data-integration/impression-data-pixels.md) zu sehen.

* Datendateien: Wenn Sie diese Berichte verwenden möchten, um Ihre eigenen Daten oder Daten aus einer Quelle zu analysieren, die nicht mit integriert ist, [!DNL Audience Manager]müssen Sie Daten- und Metadatendateien für diese Daten erstellen und hochladen. Weitere Informationen finden Sie unter [Datendateien für Zielgruppenoptimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) und [Daten- und Metadatendateien für Zielgruppenoptimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## Rollenbasierte Zugriffssteuerung (RBAC) {#rbac}

Die Art der Berichte, die Sie anzeigen können, hängt von der [!UICONTROL RBAC] Gruppe ab, der Sie zugewiesen sind. Weitere Informationen finden Sie unter [Administration](../../../features/administration/administration-overview.md) und [Erstellen einer Gruppe](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] müssen einige Datenquellen eingerichtet sein, um die [!UICONTROL Audience Optimization] Berichte anzeigen zu können. Ihr [!DNL Audience Manager] Berater wird diese Datenquellen für Sie einrichten. Je mehr Datenquellen in jeder [!UICONTROL RBAC] Benutzergruppe vorhanden sind, desto mehr Daten haben diese Gruppenmitglieder Zugriff. Mindestens eine dieser Datenquellen wird von Ihrem Berater eingerichtet:

* Advertiser-Datenquelle
* Markendatenquelle
* Plattformdatenquelle

Benutzer, die zu mehr als einer [!UICONTROL RBAC] Benutzergruppe gehören, können zwischen den Ansichten jeder Gruppe wechseln. Die angezeigten Daten werden aktualisiert, um die ausgewählte Gruppe zu berücksichtigen. Wenn Ihr Unternehmen nicht verwendet [!UICONTROL RBAC]wird, verfügen alle Benutzer über Administratorrechte und Zugriff auf alle Datenquellen (Konvertierungsgruppen).

## Konversionsgruppen {#conversion-groups}

In den [!UICONTROL Audience Optimization] Berichten sind **[!UICONTROL Conversion Groups]** Datenquellen, die mindestens eine Konversionseigenschaft enthalten, synonym. Datenquellen, die nicht mindestens eine Konversionseigenschaft enthalten, werden nicht in den [!UICONTROL Audience Optimization] Berichten angezeigt. Sie können die Konversionseigenschaften für Konversionsgruppen im Bericht " [Berichtete Konversionseigenschaften](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) "anzeigen.

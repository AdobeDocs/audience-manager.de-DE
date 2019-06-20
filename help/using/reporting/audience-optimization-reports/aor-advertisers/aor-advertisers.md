---
description: Mit Audience Optimization for Advertisers können Sie potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medienkampagnen identifizieren. Diese Berichte kombinieren Protokollierungsdaten auf Protokollebenen mit Audience Manager-Segmentmetriken, um segmentorientierte Optimierungen und einen effektiven Kanalmix zu informieren.
seo-description: Mit Audience Optimization for Advertisers können Sie potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medienkampagnen identifizieren. Diese Berichte kombinieren Protokollierungsdaten auf Protokollebenen mit Audience Manager-Segmentmetriken, um segmentorientierte Optimierungen und einen effektiven Kanalmix zu informieren.
seo-title: Zielgruppenoptimierung für Advertiser
solution: Audience Manager
title: Zielgruppenoptimierung für Advertiser
uuid: 852 d 550 e -3 c 7 f -4750-9 abc -365 c 3 a 6 f 7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Zielgruppenoptimierung für Advertiser{#audience-optimization-for-advertisers}

Mit Audience Optimization for Advertisers können Sie potenzielle Leistungsmöglichkeiten für Audience Manager-Segmente in Ihren gebührenpflichtigen Medienkampagnen identifizieren. Diese Berichte kombinieren Protokollierungsdaten auf Protokollebenen mit Audience Manager-Segmentmetriken, um segmentorientierte Optimierungen und einen effektiven Kanalmix zu informieren.

## Datenerfassungsmethoden {#data-ingestion-methods}

Sie können Daten von diesen beiden Methoden [!DNL Audience Manager] zur Verwendung in diesen Berichten senden. Manchmal senden Kunden Daten nach beiden Methoden. Dadurch stellen Sie sicher, dass Ihre Berichte die umfassendsten und genauesten Informationen über einen Besucher enthalten. Um die [!UICONTROL Audience Optimization] Berichte zu verwenden, müssen Ihre Ereignisaufrufe *alle* in der Dokumentation [Übersicht und Zuordnungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) aufgeführten Parameter enthalten. Sie können Daten über die folgenden unten aufgeführten Methoden senden.

* Pixelaufrufe: Um die erforderlichen Metadatenparameter zu übermitteln, um [!DNL Audience Manager] die [Erfassung von Kampagnen-Klickdaten über Pixel-Aufrufe](../../../integration/media-data-integration/click-data-pixels.md) und [die Erfassung von Kampagnen-Impressionsdaten über Pixelaufrufe zu sehen](../../../integration/media-data-integration/impression-data-pixels.md).

* Datendateien: Wenn Sie Ihre eigenen Daten oder Daten aus einer nicht integrierten Quelle analysieren möchten, müssen [!DNL Audience Manager]Sie Daten- und Metadatendateien für diese Daten erstellen und hochladen. Weitere Informationen finden Sie unter [Datendateien für Berichte zur Zielgruppenoptimierung](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) und [Daten- und Metadatendateien für Zielgruppenoptimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## Rollenbasierte Zugriffssteuerungssteuerung (RBAC) {#rbac}

Welche Art von Berichten Sie anzeigen können, hängt von der [!UICONTROL RBAC] Gruppe ab, die Ihnen zugewiesen ist. Weitere Informationen finden Sie unter [Administration](../../../features/administration/administration-overview.md) und [Erstellen einer Gruppe](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] müssen einige Datenquellen eingerichtet werden, damit die [!UICONTROL Audience Optimization] Berichte angezeigt werden. Ihr [!DNL Audience Manager] Berater richtet diese Datenquellen für Sie ein. Je mehr Datenquellen in den einzelnen [!UICONTROL RBAC] Benutzergruppen vorhanden sind, desto mehr Daten erhalten diese Gruppenmitglieder. Ihr Berater richtet mindestens eine dieser Datenquellen ein:

* Advertiser-Datenquelle
* Markendatenquelle
* Plattform-Datenquelle

Benutzer, die mehreren [!UICONTROL RBAC] Benutzern angehören, können zwischen der Ansicht der einzelnen Gruppen wechseln. Die angezeigten Daten werden aktualisiert, um die ausgewählte Gruppe zu berücksichtigen. Wenn Ihr Unternehmen nicht verwendet [!UICONTROL RBAC]wird, verfügen alle Benutzer über Administratorrechte und Zugriff auf alle Datenquellen (Konversionsgruppen).

## Konversionsgruppen {#conversion-groups}

Stellen Sie in den [!UICONTROL Audience Optimization] Berichten Synonyme mit Datenquellen **[!UICONTROL Conversion Groups]** dar, die mindestens eine Konversionseigenschaft enthalten. Datenquellen, die nicht mindestens eine Konversionseigenschaft enthalten, werden in den [!UICONTROL Audience Optimization] Berichten nicht angezeigt. Sie können die Konversionseigenschaften für Konversionsgruppen im Bericht [&quot;Gemeldete Konversionseigenschaften](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) &quot; anzeigen.

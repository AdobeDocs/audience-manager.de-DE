---
description: 'Benutzerbasierte Ziele bieten die Vorstellung von Shareable Audiences in Audience Manager. Diese Metrik hilft Ihnen, zu verstehen, wie viele der Hash-E-Email-Adressen Audience Manager für die Zielplattform freigeben können. '
seo-description: 'Benutzerbasierte Ziele bieten die Vorstellung von Shareable Audiences in Audience Manager. Diese Metrik hilft Ihnen, zu verstehen, wie viele der Hash-E-Email-Adressen Audience Manager für die Zielplattform freigeben können. '
seo-title: Shareable Audiences
solution: Audience Manager
title: Shareable Audiences
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Shareable Audiences {#shareable-audiences}

[!DNL People-Based Destinations] bringt die Idee [!DNL Shareable Audiences] von Audience Manager. Diese Metrik hilft Ihnen, zu verstehen, wie viele der Hash-E-Email-Adressen Audience Manager für die Zielplattform freigeben können.

[!DNL Shareable Audiences] ist eine Metrik, die Ihnen dabei hilft, Zielgruppendaten im Kontext zu [!DNL People-Based Destinations]interpretieren. Diese Metrik kann auf der [!UICONTROL Destinations] Seite und auf der [!UICONTROL Segment] Seite angezeigt werden.

## Segmentnutzbare Zielgruppen {#segment-shareable-audiences}

Die [!DNL Segment Shareable Audience] Metrik auf der Segmentseite zeigt die Anzahl der Hash-E-Email-Adressen aus der Datenquelle mit übereinstimmenden [dpuuids an](../../reference/ids-in-aam.md), die auch für das angegebene Segment im angegebenen Look-Back-Zeitraum qualifiziert sind, vorausgesetzt, die darauf angewendete Regel für die Profilzusammenführung wurde angewendet, und Audience Manager kann die Zielplattform gemeinsam nutzen.

Diese Metrik hat einen Look-Backback-Zeitraum von 1 Tag. Dies hilft Ihnen dabei, die Zielgruppenreichweite für das Segment in einem bestimmten Ziel zu verstehen.

## Ziel-Shareable Audience {#destination-shareable-audience}

Die [!DNL Destination Shareable Audience] Metrik auf einer benutzerbasierten Zielseite zeigt die Gesamtzahl der Hash-E-Email-Adressen aus der Datenquelle mit übereinstimmenden [dpuuids an](../../reference/ids-in-aam.md), die Audience Manager aus allen diesem Ziel zugeordneten Segmenten gemeinsam mit der Zielplattform verwenden kann.

![shareable-audiences](assets/dest-shareable-audiences.png)

Diese Metrik hat einen Lebensdauerzeitraum. Auf diese Weise erkennen Sie die Skalierung der Zielgruppe, die Sie aus der Hash-E-Mail-Adresse der Hash-E-Mail erhalten können.

## Beispiel 

Ein Audience Manager-Kunde verfügt über eine Datenquelle mit 110.000 [dpuuids](../../reference/ids-in-aam.md) (CRM-IDs). Sie erfassen 100.000 E-Email-Adressen mit Hash in Audience Manager, um sie mit mehreren benutzerbasierten Zielen zu verwenden und eine ID-Synchronisierung für die 100.000 Hash-E-Email-Adressen mit den CRM-IDs durchzuführen. Der Kunde kann die [!DNL All Cross-Device Profiles] Zusammenführungsregel verwenden, um drei Zielgruppensegmente zu erstellen:

* Segment A mit einer Populationsanzahl von 10.000, "Destination A" zugeordnet;
* Segment B mit einer Populationsanzahl von 20.000, "Destination A" zugeordnet;
* Segment C mit einer Bevölkerung von 50.000, die Ziel B zugeordnet ist.

In diesem Szenario:

* Segment A Shareable Audience = 10.000;
* Segment B Shareable Audience = 20.000;
* Segment C Shareable Audience = 50.000;
* Ziel A Shareable Audience = Segment A Shareable Audience + Segment B shareable audience = 30.000;
* Ziel B Shareable Audience = Segment C shareable Audience = 50.000.

![shareable-audiences-chart](assets/shareable-audiences.png)

> [!NOTE]
>
> Im obigen Beispiel bedeutet dies nicht, dass alle 80.000 Hash-E-Mail-Adressen aus den drei Segmenten vorhandenen Konten auf den Zielplattformen entsprechen. Das bedeutet nur, dass Audience Manager die Hash-ids aus den drei Segmenten an ihre jeweiligen Ziele sendet. Wenn Zielgruppensegmente an benutzerbasierte Ziele gesendet werden, erfolgt die Zuordnung der Zielgruppe auf dem Partner. Ziel A kann bis zu 30.000 übereinstimmende Benutzerkonten aufweisen, während Ziel B über bis zu 50.000 übereinstimmende Benutzerkonten verfügt, aber es gibt keine Garantie für Übereinstimmungsraten. Adobe hat keinen Zugriff auf Partner-spezifische Metriken. Unter [Übereinstimmungsraten](../../faq/faq-people-based-destinations.md#match-rates) finden Sie häufig gestellte Fragen zu benutzerbasierten Ziele für Ziele in Übereinstimmungsraten.

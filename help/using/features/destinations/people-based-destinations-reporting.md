---
description: Personenbasierte Ziele führen Audience Manager das Konzept der Freigabe von Zielgruppen ein. Diese Metrik hilft zu verstehen, wie viele der gehashten E-Mail-Adressen der Audience Manager für die Zielplattform freigeben kann.
seo-description: People-Based Destinations introduce the notion of Shareable Audiences to Audience Manager. This metric helps you understand how many of the hashed email addresses Audience Manager can share with the destination platform.
seo-title: Shareable Audiences
solution: Audience Manager
title: Freigebbare Zielgruppen
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Freigebbare Zielgruppen {#shareable-audiences}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Verwendung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um Rechtsberatung zu erhalten.

[!DNL People-Based Destinations] bringen das Konzept der [!DNL Shareable Audiences] in den Audience Manager. Diese Metrik hilft zu verstehen, wie viele der gehashten E-Mail-Adressen der Audience Manager für die Zielplattform freigeben kann.

[!DNL Shareable Audiences] ist eine Metrik, die Ihnen bei der Interpretation von Zielgruppendaten im Kontext von [!DNL People-Based Destinations] hilft. Sie können diese Metrik auf der Seite [!UICONTROL Destinations] und auf der Seite [!UICONTROL Segment] sehen.

## Freigebbare Zielgruppen segmentieren {#segment-shareable-audiences}

Die [!DNL Segment Shareable Audience] auf der Segmentseite gibt die Anzahl der Hash-E-Mail-Adressen aus der Datenquelle mit übereinstimmenden [DPUUIDs](../../reference/ids-in-aam.md) an, die sich auch für das definierte Segment in der angegebenen Lookback-Periode qualifizieren, wenn die Profilzusammenführungsregel auf es angewendet wird, und die dieser Audience Manager für die Zielplattform freigeben kann.

Diese Metrik hat einen eintägigen Lookback-Zeitraum. Auf diese Weise lässt sich die Reichweite der Zielgruppe für das Segment in einem bestimmten Ziel besser verstehen.

## Ziel der freigebbaren Zielgruppe {#destination-shareable-audience}

Die [!DNL Destination Shareable Audience]-Metrik in einer personenbasierten Zielseite gibt die Gesamtzahl der gehashten E-Mail-Adressen aus der Datenquelle mit übereinstimmenden [DPUUIDs](../../reference/ids-in-aam.md) an, die dieser Audience Manager für die Zielplattform aus allen Segmenten, die diesem Ziel zugeordnet sind, freigeben kann.

![shareable-audience](assets/dest-shareable-audiences.png)

Diese Metrik hat eine Lebensdauer-Lookback-Periode. Auf diese Weise lässt sich die Größe der Zielgruppe besser verstehen, die Sie über die Datenquelle für gehashte E-Mail-Adressen erreichen können.

## Beispiel

Ein Audience Manager-Kunde verfügt über eine Datenquelle mit 110.000 [DPUUIDs](../../reference/ids-in-aam.md) (CRM-IDs). Sie nehmen 100.000 gehashte E-Mail-Adressen in den Audience Manager auf, um sie für mehrere personenbasierte Ziele zu verwenden, und führen eine ID-Synchronisierung für die 100.000 gehashten E-Mail-Adressen mit den CRM-IDs durch. Der Kunde kann die [!DNL All Cross-Device Profiles]-Zusammenführungsregel verwenden, um drei Zielgruppensegmente zu erstellen:

* Segment A mit einer Bevölkerungszahl von 10.000, das Ziel A zugeordnet ist;
* Segment B mit einer Einwohnerzahl von 20.000, das Ziel A zugeordnet ist;
* Segment C mit einer Populationsanzahl von 50.000, zugeordnet zu Ziel B.

In diesem Szenario:

* Segment A Freigabe-Zielgruppe = 10.000;
* Freigebbare Zielgruppe von Segment B = 20.000;
* Freigebbare Zielgruppe von Segment C = 50.000;
* Ziel A Freigabe-Zielgruppe = Segment A Freigabe-Zielgruppe + Segment B Freigabe-Zielgruppe = 30.000;
* Ziel B Freigabe-Zielgruppe = Segment C Freigabe-Zielgruppe = 50.000.

![shareable-audience-diagram](assets/shareable-audiences.png)

>[!NOTE]
>
>Im obigen Beispiel bedeutet dies nicht, dass alle 80.000 gehashten E-Mail-Adressen aus den drei Segmenten mit vorhandenen Konten in den Zielplattformen übereinstimmen. Dies bedeutet nur, dass der -Audience Manager die Hash-Kennungen aus den drei Segmenten an ihre jeweiligen Ziele sendet. Beim Senden von Zielgruppensegmenten an personenbasierte Ziele erfolgt der Zielgruppenabgleich auf der Partnerseite. Ziel A kann bis zu 30.000 übereinstimmende Benutzerkonten haben, während Ziel B bis zu 50.000 übereinstimmende Benutzerkonten haben kann, aber es gibt keine Garantie für Übereinstimmungsraten. Adobe hat keinen Zugriff auf partnerspezifische Metriken. Unter [Übereinstimmungsraten](../../faq/faq-people-based-destinations.md#match-rates) finden Sie häufig gestellte Fragen zur Sichtbarkeit von personenbasierten Zielen in Übereinstimmungsraten.

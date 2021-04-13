---
description: 'Personenbezogene Reiseziele führen den Begriff der freigegebenen Audiencen in Audience Manager ein. Anhand dieser Metrik können Sie erkennen, wie viele der Hash-E-Mail-Adressen Audience Manager für die Zielplattform freigeben können. '
seo-description: 'Personenbezogene Reiseziele führen den Begriff der freigegebenen Audiencen in Audience Manager ein. Anhand dieser Metrik können Sie erkennen, wie viele der Hash-E-Mail-Adressen Audience Manager für die Zielplattform freigeben können. '
seo-title: Teilbare Zielgruppen
solution: Audience Manager
title: Teilbare Zielgruppen
feature: Benutzerbasierte Ziele
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Teilbare Zielgruppen {#shareable-audiences}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

[!DNL People-Based Destinations] Audience Manager  [!DNL Shareable Audiences] zu bringen. Anhand dieser Metrik können Sie erkennen, wie viele der Hash-E-Mail-Adressen Audience Manager für die Zielplattform freigeben können.

[!DNL Shareable Audiences] ist eine Metrik, die Ihnen bei der Interpretation von Audiencen-Daten im Kontext von  [!DNL People-Based Destinations]dient. Sie können diese Metrik auf der Seite [!UICONTROL Destinations] und auf der Seite [!UICONTROL Segment] sehen.

## Freigegebene Audiencen für Segmente {#segment-shareable-audiences}

Die [!DNL Segment Shareable Audience]-Metrik auf der Segmentseite gibt die Anzahl der Hash-E-Mail-Adressen aus der Datenquelle mit übereinstimmenden [DPUUIDs](../../reference/ids-in-aam.md) an, die sich auch für das definierte Segment in der angegebenen Rückblickzeit qualifizieren, da die Profil-Merge-Regel darauf angewendet wird, und dieser Audience Manager kann mit der Zielplattform gemeinsam verwendet werden.

Diese Metrik verfügt über eine Rückblickzeit von 1 Tag. Auf diese Weise können Sie die SegmentReichweite für die Audience eines bestimmten Ziels verstehen.

## Ziel-Freigabe-Audience {#destination-shareable-audience}

Die [!DNL Destination Shareable Audience]-Metrik auf einer benutzerbasierten Zielseite gibt die Gesamtanzahl der Hash-E-Mail-Adressen aus der Datenquelle mit übereinstimmenden [DPUUIDs](../../reference/ids-in-aam.md) an, die dieser Audience Manager von allen Segmenten, die diesem Ziel zugeordnet sind, an die Zielplattform weitergeben kann.

![shareable-Audiencen](assets/dest-shareable-audiences.png)

Diese Metrik verfügt über eine Lebensdauer-Rückblickzeit. Auf diese Weise können Sie den Umfang der Audience verstehen, die Sie aus der Datenquelle für Hash-E-Mail-Adressen erreichen können.

## Beispiel

Ein Audience Manager hat eine Datenquelle mit 110.000 [DPUUIDs](../../reference/ids-in-aam.md) (CRM-IDs). Sie erfassen 100.000 Hash-E-Mail-Adressen in Audience Manager, verwenden sie mit mehreren benutzerbasierten Zielen und führen eine ID-Synchronisierung für die 100.000 Hash-E-Mail-Adressen mit den CRM-IDs durch. Der Kunde kann die Zusammenführungsregel [!DNL All Cross-Device Profiles] verwenden, um drei Audiencen zu erstellen:

* Segment A mit einer Bevölkerungszahl von 10.000, zugeordnet zu Ziel A;
* Segment B mit einer Bevölkerungszahl von 20.000, zugeordnet zu Ziel A;
* Segment C mit einer Bevölkerungszahl von 50.000, zugeordnet zu Ziel B.

In diesem Szenario:

* Segment A freigegebene Audience = 10.000;
* Segment B: Shareable Audience = 20.000;
* Segment C: Shareable Audience = 50.000;
* Ziel einer freigegebenen Audience = Segment A freigegebene Audience + Segment B: Freigegebene Audience = 30.000;
* Ziel B: Gemeinsam nutzbare Audience = Segment C Audience = 50.000.

![shareable-Audiencen-Diagramm](assets/shareable-audiences.png)

>[!NOTE]
>
>Im obigen Beispiel bedeutet dies nicht, dass alle 80.000 Hash-E-Mail-Adressen aus den drei Segmenten mit vorhandenen Konten in den Zielplattformen übereinstimmen. Dies bedeutet nur, dass Audience Manager die Hash-IDs von den drei Segmenten an ihre jeweiligen Ziele sendet. Wenn Sie Audiencen an benutzerbasierte Ziele senden, erfolgt die Zuordnung von Audiencen auf der Partnerseite. Ziel A kann bis zu 30.000 passende Benutzerkonten haben, während Ziel B bis zu 50.000 passende Benutzerkonten haben kann, aber es gibt keine Garantie für Übereinstimmungsraten. Adobe hat keinen Zugriff auf partnerspezifische Metriken. Unter [Übereinstimmungsraten](../../faq/faq-people-based-destinations.md#match-rates) finden Sie häufig gestellte Fragen zur Sichtbarkeit benutzerbasierter Ziele in Übereinstimmungsraten.

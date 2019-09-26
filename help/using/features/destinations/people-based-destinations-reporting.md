---
description: 'Personalisierte Ziele führen den Begriff "Zielgruppen"in Audience Manager ein. Anhand dieser Metrik können Sie erkennen, wie viele der Hash-E-Mail-Adressen Audience Manager für die Zielplattform freigeben kann. '
seo-description: 'Personalisierte Ziele führen den Begriff "Zielgruppen"in Audience Manager ein. Anhand dieser Metrik können Sie erkennen, wie viele der Hash-E-Mail-Adressen Audience Manager für die Zielplattform freigeben kann. '
seo-title: Zielgruppen freigeben
solution: Audience Manager
title: Zielgruppen freigeben
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Zielgruppen freigeben {#shareable-audiences}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

[!DNL People-Based Destinations] bringen Sie den Begriff " [!DNL Shareable Audiences] in Audience Manager". Anhand dieser Metrik können Sie erkennen, wie viele der Hash-E-Mail-Adressen Audience Manager für die Zielplattform freigeben kann.

[!DNL Shareable Audiences] ist eine Metrik, mit der Sie Zielgruppendaten im Kontext von interpretieren [!DNL People-Based Destinations]können. Sie können diese Metrik auf der [!UICONTROL Destinations] Seite und auf der [!UICONTROL Segment] Seite sehen.

## Zielgruppen segmentieren {#segment-shareable-audiences}

Die [!DNL Segment Shareable Audience] Metrik auf der Segmentseite gibt die Anzahl der Hash-E-Mail-Adressen aus der Datenquelle mit übereinstimmenden [DPUUIDs](../../reference/ids-in-aam.md)an, die sich auch in der angegebenen Rückblickzeit für das definierte Segment qualifizieren, da die Regel zur Profilzusammenführung auf das Segment angewendet wird und dass Audience Manager mit der Zielplattform freigegeben werden kann.

Diese Metrik verfügt über eine Rückblickzeit von 1 Tag. Auf diese Weise können Sie die Reichweite der Zielgruppe für das Segment in einem bestimmten Ziel verstehen.

## Zielpublikum {#destination-shareable-audience}

Die [!DNL Destination Shareable Audience] Metrik auf einer benutzerbasierten Zielseite gibt die Gesamtanzahl der Hash-E-Mail-Adressen aus der Datenquelle mit übereinstimmenden [DPUUIDs](../../reference/ids-in-aam.md)an, die Audience Manager für die Zielplattform freigeben kann, aus allen Segmenten, die diesem Ziel zugeordnet sind.

![shareable-audiences](assets/dest-shareable-audiences.png)

Diese Metrik verfügt über eine Lebensdauer-Rückblickzeit. Auf diese Weise können Sie die Größe der Zielgruppe verstehen, die Sie aus der Datenquelle für Hash-E-Mail-Adressen erreichen können.

## Beispiel 

Ein Audience Manager-Kunde verfügt über eine Datenquelle mit 110.000 [DPUUIDs](../../reference/ids-in-aam.md) (CRM-IDs). Sie erfassen 100.000 Hash-E-Mail-Adressen in Audience Manager, verwenden sie mit mehreren benutzerbasierten Zielen und führen eine ID-Synchronisierung für die 100.000 Hash-E-Mail-Adressen mit den CRM-IDs durch. Der Kunde kann die [!DNL All Cross-Device Profiles] Zusammenführungsregel verwenden, um drei Zielgruppensegmente zu erstellen:

* Segment A mit einer Bevölkerungszahl von 10.000, zugeordnet zu Ziel A;
* Segment B mit einer Bevölkerungszahl von 20.000, zugeordnet zu Ziel A;
* Segment C mit einer Bevölkerungszahl von 50.000, zugeordnet zu Ziel B.

In diesem Szenario:

* Segment A Zielgruppe = 10.000;
* Segment B Zielgruppe = 20.000;
* Segment C Zielgruppe = 50.000;
* Ziel einer freigegebenen Zielgruppe = Segment A freigegebene Zielgruppe + Segment B freigegebene Zielgruppe = 30.000;
* Ziel B Zielgruppe = Segment C Zielgruppe = 50.000

![shareable-audiences-diagramm](assets/shareable-audiences.png)

> [!NOTE]
>
> Im obigen Beispiel bedeutet dies nicht, dass alle 80.000 Hash-E-Mail-Adressen aus den drei Segmenten mit vorhandenen Konten in den Zielplattformen übereinstimmen. Dies bedeutet nur, dass Audience Manager die Hash-IDs von den drei Segmenten an ihre jeweiligen Ziele sendet. Wenn Zielgruppensegmente an benutzerbasierte Ziele gesendet werden, erfolgt die Zielgruppenzuordnung auf der Partnerseite. Ziel A kann bis zu 30.000 passende Benutzerkonten haben, während Ziel B bis zu 50.000 passende Benutzerkonten haben kann, aber keine Garantie für Übereinstimmungsraten besteht. Adobe hat keinen Zugriff auf Partner-spezifische Metriken. Unter [Übereinstimmungsraten](../../faq/faq-people-based-destinations.md#match-rates) finden Sie häufig gestellte Fragen zur Sichtbarkeit benutzerbasierter Ziele in Übereinstimmungsraten.

---
description: Wie sich Eigenschaften von Eigenschafts-to-Live (TTL) auf die Segmentmitgliedschaft auswirken.
seo-description: Wie sich Eigenschaften von Eigenschafts-to-Live (TTL) auf die Segmentmitgliedschaft auswirken.
seo-title: Segment und Trait-Zeit zu Live Explained
solution: Audience Manager
title: Segmentzeit zu Live erklärt
uuid: 5 b 2 c 6911-50 b 9-4 b 68-9 dd 4-21128 d 112 eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Segment and Trait Time-to-Live Explained {#segment-time-to-live-explained}

How trait [!UICONTROL time-to-live] ([!DNL TTL]) interval affects segment membership.

<!-- segment-ttl-explained.xml -->

## Zeit für Live

[!DNL TTL] definiert, wie lange ein Site-Besucher nach dem letzten Qualifizierungsereignis in einem Segment verbleibt. [!DNL TTL] auf Eigenschaften und nicht auf Segmenten eingestellt ist. Visitors fall out of a segment if they do not see a qualifying trait before the end of the [!DNL TTL] interval. The default [!DNL TTL] for new traits is 120 days. Wenn sie auf 0 Tage gesetzt ist, läuft die Eigenschaft nie ab. [Legen Sie den TTL-Wert](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) fest, wenn Sie eine Eigenschaft im [!UICONTROL Advanced Options] Abschnitt der Benutzeroberfläche für die Eigenschaften erstellen oder bearbeiten.

## [!DNL TTL] und Entfernen eines Segments

A user falls out of a segment if they do not see any of its traits within the [!DNL TTL] interval. For example, if you have a 1-trait segment with a 30 days [!DNL TTL], the user will drop out of that segment if they do not see the trait again within the 30 days.

![](assets/ttl_1.png)

## [!DNL TTL] und Segmentverlängerung

The [!DNL TTL] resets, and the user remains in a segment, if they see that segment’s trait within the [!DNL TTL] period. Also, because most segments contain multiple traits with their own [!DNL TTL] periods, a user can remain in a segment (and reset the [!DNL TTL] interval) as long as they keep seeing any traits associated with a segment. For example, say you have Segment 1 composed of Trait A (30 day [!DNL TTL]) and Trait B (15 day [!DNL TTL]). Assuming the user sees each trait only once, the illustration below outlines the [!DNL TTL] renewal process and total in-segment duration.

![](assets/ttl_2.png)

## [!DNL Audience Manager] Ttls sind unabhängig von TTL-Einstellungen von Drittanbietern

Remember, the [!DNL TTL] set on your [!DNL Audience Manager] pixel operates independently from the [!DNL TTL] set on other pixels used by third parties ([!DNL DSP]s, ad networks, etc.).

>[!MORE_ LIKE_ THIS]
>
>* [Festlegen eines Eigenschaftsablaufintervalls](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)


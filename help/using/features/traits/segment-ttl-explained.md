---
description: Auswirkungen des TTL-Intervalls (Time-to-Live) der Eigenschaft auf die Segmentzugehörigkeit.
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: Erklärung der Segmentzeit bis zur Live-Schaltung
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Erklärung zur Lebensdauer von Segmenten und Eigenschaften {#segment-time-to-live-explained}

Wie sich das [!UICONTROL time-to-live] ([!DNL TTL]) auf die Segmentzugehörigkeit auswirkt.

<!-- segment-ttl-explained.xml -->

## Time to Live

[!DNL TTL] definiert, wie lange ein Site-Besucher nach dem letzten Eigenschaftsqualifikationsereignis in einem Segment verbleibt. [!DNL TTL] wird auf Eigenschaften und nicht auf Segmenten festgelegt. Besucherinnen und Besucher verlieren den Status eines Segments, wenn sie sich vor dem Ende des [!DNL TTL] nicht für eine Eigenschaft qualifizieren. Der [!DNL TTL] für neue Eigenschaften beträgt 120 Tage. Bei Festlegung auf 0 Tage läuft das Merkmal nie ab. [Legen Sie den TTL](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)Wert fest, wenn Sie im [!UICONTROL Advanced Options] Abschnitt der Benutzeroberfläche zur Eigenschaftenerstellung eine Eigenschaft erstellen oder bearbeiten.

### 1 Tag TTL - Erklärung

Wenn Sie die [!DNL TTL] auf 1 Tag festlegen, startet der TTL-Timer am nächsten Tag nach der Realisierung der Eigenschaft, ohne die Stunden zu zählen, die im Tag der Realisierung der Eigenschaft verbleiben.

Audience Manager berechnet den [!DNL TTL] für Eigenschaften mit einer [!DNL TTL] von einem Tag anhand der folgenden Formel:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Beispiel 1**: Ein Merkmal, das um 1:00 [!DNL UTC] mit einer [!DNL TTL] von 1 Tag realisiert wurde. [!DNL TTL] läuft 24 + 24 - 1 = 47 Stunden später ab.
* **Beispiel 2**: Ein Merkmal, das um 23 :00 [!DNL UTC] mit einer [!DNL TTL] von 1 Tag realisiert wurde. [!DNL TTL] läuft 24 + 24 - 23 = 25 Stunden später ab.

## [!DNL TTL] und Abbrechen eines Segments

Ein Benutzer fällt aus einem Segment aus, wenn er innerhalb des [!DNL TTL]-Intervalls für keines seiner Merkmale qualifiziert ist. Wenn Sie beispielsweise ein Segment mit einer Eigenschaft von 1 und einer [!DNL TTL] von 30 Tagen haben, wird der Benutzer aus diesem Segment aussteigen, wenn er innerhalb der nächsten 30 Tage nicht erneut für das Merkmal qualifiziert ist.

![](assets/ttl-explained.png)

## [!DNL TTL] und Segmenterneuerung

Die [!DNL TTL] wird zurückgesetzt, und der Benutzer verbleibt in einem Segment, wenn er innerhalb des [!DNL TTL] Zeitraums für das Merkmal dieses Segments qualifiziert ist. Da die meisten Segmente mehrere Eigenschaften mit eigenen [!DNL TTL] enthalten, kann ein Benutzer in einem Segment bleiben und das [!DNL TTL] zurücksetzen, sofern er sich weiterhin für alle mit dem Segment verknüpften Eigenschaften qualifiziert.

Angenommen, Sie haben Segment 1, das aus Merkmal A (30-Tage-[!DNL TTL]) und Merkmal B (15-Tage-[!DNL TTL]) besteht. Angenommen, ein Besucher qualifiziert sich nur einmal für jedes Merkmal, wird in der folgenden Abbildung der [!DNL TTL] Erneuerungsprozess und die gesamte Dauer innerhalb des Segments dargestellt.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTLs sind unabhängig von TTL-Einstellungen von Drittanbietern

Denken Sie daran, dass der [!DNL TTL] auf Ihrem [!DNL Audience Manager] Pixel unabhängig von dem [!DNL TTL] funktioniert, der auf anderen Pixeln festgelegt wurde, die von Dritten verwendet werden ([!DNL DSP]s, Anzeigennetzwerke usw.).

>[!MORELIKETHIS]
>
>* [Festlegen des Ablaufintervalls für Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

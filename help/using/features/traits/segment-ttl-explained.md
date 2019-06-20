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


# Erläuterung von Segment und Trait - Erläuterung {#segment-time-to-live-explained}

Einfluss von Trait [!UICONTROL time-to-live] ([!DNL TTL])-Intervallen auf die Segmentmitgliedschaft.

<!-- segment-ttl-explained.xml -->

## Zeit für Live

[!DNL TTL] definiert, wie lange ein Site-Besucher nach dem letzten Qualifizierungsereignis in einem Segment verbleibt. [!DNL TTL] auf Eigenschaften und nicht auf Segmenten eingestellt ist. Besucher verlassen sich aus einem Segment, wenn vor dem Ende des [!DNL TTL] Intervalls keine qualifizierende Eigenschaft angezeigt wird. Die Standardeinstellung [!DNL TTL] für neue Eigenschaften beträgt 120 Tage. Wenn sie auf 0 Tage gesetzt ist, läuft die Eigenschaft nie ab. [Legen Sie den TTL-Wert](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) fest, wenn Sie eine Eigenschaft im [!UICONTROL Advanced Options] Abschnitt der Benutzeroberfläche für die Eigenschaften erstellen oder bearbeiten.

## [!DNL TTL] und Entfernen eines Segments

Ein Benutzer verlässt sich aus einem Segment, wenn ihm keine seiner Eigenschaften innerhalb des [!DNL TTL] Intervalls angezeigt wird. Wenn Sie z. B. ein Segment mit 1 Eigenschaften mit 30 Tagen [!DNL TTL]haben, wird der Benutzer aus diesem Segment abgelegt, wenn er die Eigenschaft innerhalb der 30 Tage nicht erneut ansieht.

![](assets/ttl_1.png)

## [!DNL TTL] und Segmentverlängerung

Die [!DNL TTL] Zurücksetzung und der Benutzer bleiben in einem Segment, wenn sie innerhalb des [!DNL TTL] Zeitraums die Eigenschaft des Segments sehen. Da die meisten Segmente mehrere Eigenschaften mit ihren eigenen [!DNL TTL] Zeiträumen enthalten, kann ein Benutzer in einem Segment bleiben (und das [!DNL TTL] Intervall zurücksetzen), solange die Eigenschaften weiterhin mit einem Segment verknüpft sind. Angenommen, Sie haben Segment 1 aus Eigenschaften A (30 Tag [!DNL TTL]) und Trait B (15 Tag [!DNL TTL]). Wenn der Benutzer die einzelnen Eigenschaften nur einmal ansieht, wird in der unten stehenden Abbildung der [!DNL TTL] Verlängerungsvorgang und die Gesamtdauer des Segmentabschlusses erläutert.

![](assets/ttl_2.png)

## [!DNL Audience Manager] Ttls sind unabhängig von TTL-Einstellungen von Drittanbietern

Denken Sie daran, dass der [!DNL TTL] Satz in [!DNL Audience Manager] Ihrem Pixel unabhängig vom [!DNL TTL] Satz auf anderen Pixeln funktioniert, die von Dritten, Werbenetzwerken usw[!DNL DSP]. verwendet werden.

>[!MORE_ LIKE_ THIS]
>
>* [Festlegen eines Eigenschaftsablaufintervalls](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)


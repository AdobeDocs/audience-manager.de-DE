---
description: Inwieweit beeinflusst das Intervall für die Gültigkeitsdauer der Eigenschaften die Segmentmitgliedschaft.
seo-description: Inwieweit beeinflusst das Intervall für die Gültigkeitsdauer der Eigenschaften die Segmentmitgliedschaft.
seo-title: Erläuterung zu Segment- und Eigenschaftenzeit
solution: Audience Manager
title: Erläuterung der Segmentzeit bis zur Live-Übertragung
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Erläuterung der Segment- und Eigenschaftenzeit bis zum Live {#segment-time-to-live-explained}

Einfluss des Intervalls [!UICONTROL time-to-live] für Eigenschaften ([!DNL TTL]) auf die Segmentmitgliedschaft.

<!-- segment-ttl-explained.xml -->

## Zeit bis zum Live

[!DNL TTL] definiert, wie lange ein Besucher der Site nach dem letzten Ereignis zur Qualifizierung der Eigenschaften in einem Segment verbleibt. [!DNL TTL] wird auf Eigenschaften und nicht auf Segmenten eingestellt. Besucher fallen aus einem Segment heraus, wenn sie vor Ende des [!DNL TTL] Intervalls keine qualifizierenden Eigenschaften sehen. Die Standardeinstellung [!DNL TTL] für neue Eigenschaften ist 120 Tage. Bei Festlegung auf 0 Tage läuft die Eigenschaft nie ab. [Legen Sie den TTL-Wert](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) fest, wenn Sie eine Eigenschaft im Abschnitt der Benutzeroberfläche für die [!UICONTROL Advanced Options] Eigenschaftserstellung erstellen oder bearbeiten.

## [!DNL TTL] und Abbrechen aus einem Segment

Ein Benutzer wird aus einem Segment entfernt, wenn er keine Eigenschaften innerhalb des [!DNL TTL] Intervalls sieht. Wenn Sie z. B. ein Segment mit 1 Eigenschaft mit 30 Tagen haben, [!DNL TTL]wird der Benutzer dieses Segment verlassen, wenn er die Eigenschaft nicht innerhalb von 30 Tagen erneut sieht.

![](assets/ttl_1.png)

## [!DNL TTL] und Segmentverlängerung

Die [!DNL TTL] Zurücksetzung und der Benutzer bleibt in einem Segment, wenn er die Eigenschaften dieses Segments innerhalb des [!DNL TTL] Zeitraums sieht. Da die meisten Segmente mehrere Eigenschaften mit eigenen [!DNL TTL] Zeiträumen enthalten, kann ein Benutzer auch in einem Segment verbleiben (und das [!DNL TTL] Intervall zurücksetzen), solange er alle Eigenschaften anzeigt, die mit einem Segment verbunden sind. Beispiel: Sie haben Segment 1, das aus Eigenschaft A (30 Tage [!DNL TTL]) und Eigenschaft B (15 Tage [!DNL TTL]) besteht. Wenn der Benutzer die einzelnen Eigenschaften nur einmal sieht, wird in der folgenden Abbildung der [!DNL TTL] Erneuerungsprozess und die Gesamtdauer im Segment beschrieben.

![](assets/ttl_2.png)

## [!DNL Audience Manager] TTLs sind unabhängig von TTL-Einstellungen von Drittanbietern

Denken Sie daran, dass das [!DNL TTL] Set auf Ihrem [!DNL Audience Manager] Pixel unabhängig von dem [!DNL TTL] Satz auf anderen Pixeln von Drittanbietern ([!DNL DSP]s, Werbenetzwerke usw.) funktioniert.

>[!MORE_LIKE_THIS]
>
>* [Ablaufintervall für Eigenschaften festlegen](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)


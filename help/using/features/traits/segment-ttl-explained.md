---
description: Inwieweit beeinflusst das Intervall für die Gültigkeitsdauer der Eigenschaften (TTL) die Segmentmitgliedschaft.
seo-description: Inwieweit beeinflusst das Intervall für die Gültigkeitsdauer der Eigenschaften (TTL) die Segmentmitgliedschaft.
seo-title: Erläuterung zu Segment- und Eigenschaftenzeit
solution: Audience Manager
title: Erläuterung der Segmentzeit bis zur Live-Übertragung
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 3%

---


# Segment und TTL einer Eigenschaft – Erklärung {#segment-time-to-live-explained}

Einfluss des Intervalls [!UICONTROL time-to-live] für Eigenschaften ([!DNL TTL]) auf die Segmentmitgliedschaft.

<!-- segment-ttl-explained.xml -->

## Zeit bis zum Live

[!DNL TTL] definiert, wie lange ein Site-Besucher nach dem Ereignis der letzten Eigenschaftenqualifikation in einem Segment verbleibt. [!DNL TTL] wird für Eigenschaften und nicht für Segmente festgelegt. Visitors fall out of a segment if they do not qualify for a trait before the end of the [!DNL TTL] interval. Die Standardeinstellung [!DNL TTL] für neue Eigenschaften ist 120 Tage. Bei Festlegung auf 0 Tage läuft die Eigenschaft nie ab. [Legen Sie den TTL-Wert](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) fest, wenn Sie eine Eigenschaft im Abschnitt der Benutzeroberfläche für die [!UICONTROL Advanced Options] Eigenschaftserstellung erstellen oder bearbeiten.

### 1 Tag TTL Erläuterung

Bei der Einstellung [!DNL TTL] auf 1 Tag wird der TTL-Timer am nächsten Tag nach der Erkennung der Eigenschaften Beginn, wobei die Stunden, die im Tag der Eigenschaftenrealisierung verbleiben, nicht berücksichtigt werden.

Audience Manager berechnet die [!DNL TTL] Ablaufzeit für Eigenschaften mit 1 Tag [!DNL TTL] anhand der folgenden Formel:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Beispiel 1**: Eine Eigenschaft, die um 1:00 [!DNL UTC]mit einem 1 Tag realisiert wurde [!DNL TTL]. [!DNL TTL] läuft 24 + 24 - 1 = 47 Stunden später ab.
* **Beispiel 2**: Eine Eigenschaft, die um 23:00 Uhr [!DNL UTC], mit einem 1 Tag realisiert [!DNL TTL]. [!DNL TTL] läuft 24 + 24 - 23 = 25 Stunden später ab.

## [!DNL TTL] und Abbrechen aus einem Segment

Ein Benutzer wird aus einem Segment ausgeschlossen, wenn er innerhalb des [!DNL TTL] Intervalls für keine seiner Eigenschaften qualifiziert ist. Wenn Sie z. B. ein Segment mit 1 Eigenschaft mit 30 Tagen haben, [!DNL TTL]wird der Benutzer dieses Segment abbrechen, wenn er sich nicht innerhalb der nächsten 30 Tage erneut für die Eigenschaft qualifiziert.

![](assets/ttl-explained.png)

## [!DNL TTL] und Segmentverlängerung

Die [!DNL TTL] Zurücksetzung und der Benutzer verbleibt in einem Segment, wenn er sich innerhalb des [!DNL TTL] Zeitraums für die Eigenschaft dieses Segments qualifiziert. Da die meisten Segmente mehrere Eigenschaften mit eigenen [!DNL TTL] Intervallen enthalten, kann ein Benutzer auch in einem Segment bleiben und das [!DNL TTL] Intervall zurücksetzen, solange er sich weiterhin für alle Eigenschaften qualifiziert, die mit dem Segment verbunden sind.

Beispiel: Sie haben Segment 1, das aus Eigenschaft A (30 Tage [!DNL TTL]) und Eigenschaft B (15 Tage [!DNL TTL]) besteht. Wenn ein Besucher nur einmal für jede Eigenschaft qualifiziert ist, wird in der folgenden Abbildung der [!DNL TTL] Erneuerungsprozess und die Gesamtdauer im Segment beschrieben.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTLs sind unabhängig von TTL-Einstellungen von Drittanbietern

Denken Sie daran, dass das [!DNL TTL] Set auf Ihrem [!DNL Audience Manager] Pixel unabhängig von dem [!DNL TTL] Satz auf anderen Pixeln von Drittanbietern ([!DNL DSP]s, Werbenetzwerke usw.) funktioniert.

>[!MORELIKETHIS]
>
>* [Ablaufintervall für Eigenschaften festlegen](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)


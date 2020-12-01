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

Inwieweit beeinflusst das Intervall für die Eigenschaft [!UICONTROL time-to-live] ([!DNL TTL]) die Segmentmitgliedschaft.

<!-- segment-ttl-explained.xml -->

## Zeit bis zum Live

[!DNL TTL] definiert, wie lange ein Site-Besucher nach dem Ereignis der letzten Eigenschaftenqualifikation in einem Segment verbleibt. [!DNL TTL] wird für Eigenschaften und nicht für Segmente festgelegt. Besucher werden aus einem Segment ausgeschlossen, wenn sie sich vor dem Ende des [!DNL TTL]-Intervalls nicht für eine Eigenschaft qualifizieren. Die Standardeinstellung für [!DNL TTL] für neue Eigenschaften ist 120 Tage. Bei Festlegung auf 0 Tage läuft die Eigenschaft nie ab. [Legen Sie den TTL-](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) Wert fest, wenn Sie eine Eigenschaft im  [!UICONTROL Advanced Options] Abschnitt der Benutzeroberfläche zur Eigenschaftenerstellung erstellen oder bearbeiten.

### 1 Tag TTL Erläuterung

Beim Setzen von [!DNL TTL] auf 1 Tag wird der TTL-Timer am nächsten Tag nach der Erkennung der Eigenschaften Beginn, wobei die verbleibenden Stunden im Tag der Eigenschaftenrealisierung nicht berücksichtigt werden.

Audience Manager berechnet das Ablaufdatum für Eigenschaften mit 1 Tag [!DNL TTL] anhand der folgenden Formel:[!DNL TTL]

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Beispiel 1**: Eine Eigenschaft, die um 1:00  [!DNL UTC]mit einem 1 Tag realisiert wurde  [!DNL TTL]. [!DNL TTL] läuft 24 + 24 - 1 = 47 Stunden später ab.
* **Beispiel 2**: Eine Eigenschaft, die um 23:00 Uhr  [!DNL UTC], mit einem 1 Tag realisiert  [!DNL TTL]. [!DNL TTL] läuft 24 + 24 - 23 = 25 Stunden später ab.

## [!DNL TTL] und Abbrechen aus einem Segment

Ein Benutzer wird aus einem Segment ausgeschlossen, wenn er sich innerhalb des [!DNL TTL]-Intervalls nicht für eine seiner Eigenschaften qualifiziert. Wenn Sie z. B. ein Segment mit einer Eigenschaft von 1 mit einer Länge von 30 Tagen [!DNL TTL] haben, wird der Benutzer dieses Segment abbrechen, wenn er sich nicht innerhalb der nächsten 30 Tage erneut für die Eigenschaft qualifiziert.

![](assets/ttl-explained.png)

## [!DNL TTL] und Segmentverlängerung

Das [!DNL TTL] wird zurückgesetzt, und der Benutzer bleibt in einem Segment, wenn er sich innerhalb des [!DNL TTL]-Zeitraums für die Eigenschaft dieses Segments qualifiziert. Da die meisten Segmente auch mehrere Eigenschaften mit eigenen [!DNL TTL]-Intervallen enthalten, kann ein Benutzer in einem Segment bleiben und das [!DNL TTL]-Intervall zurücksetzen, solange er sich für alle mit dem Segment verbundenen Eigenschaften qualifiziert.

Beispiel: Sie haben Segment 1 aus Eigenschaft A (30 Tage [!DNL TTL]) und Eigenschaft B (15 Tage [!DNL TTL]). Wenn ein Besucher nur einmal für jede Eigenschaft qualifiziert ist, wird in der folgenden Abbildung der Erneuerungsprozess und die Gesamtdauer im Segment beschrieben.[!DNL TTL]

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTLs sind unabhängig von TTL-Einstellungen von Drittanbietern

Denken Sie daran, dass das [!DNL TTL]-Set in Ihrem [!DNL Audience Manager]-Pixel unabhängig von dem [!DNL TTL]-Satz in anderen Pixeln funktioniert, die von Drittanbietern ([!DNL DSP]s, Werbenetzwerke usw.) verwendet werden.

>[!MORELIKETHIS]
>
>* [Ablaufintervall für Eigenschaften festlegen](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)


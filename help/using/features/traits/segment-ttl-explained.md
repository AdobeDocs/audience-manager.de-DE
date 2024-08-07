---
description: Auswirkungen des TTL-Intervalls (Trait Time-to-Live) auf die Segmentzugehörigkeit.
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: Segment Time to Live - Erklärung
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Segment und Eigenschaftszeit - Erklärung {#segment-time-to-live-explained}

Wie sich das Eigenschaftsintervall [!UICONTROL time-to-live] ([!DNL TTL]) auf die Segmentzugehörigkeit auswirkt.

<!-- segment-ttl-explained.xml -->

## Time to Live

[!DNL TTL] definiert, wie lange ein Site-Besucher nach dem letzten Ereignis zur Eigenschaftsqualifizierung in einem Segment verbleibt. [!DNL TTL] wird für Eigenschaften und nicht für Segmente festgelegt. Besucher werden aus einem Segment ausgeschlossen, wenn sie sich vor Ende des [!DNL TTL] -Intervalls nicht für eine Eigenschaft qualifizieren. Der Standardwert [!DNL TTL] für neue Eigenschaften beträgt 120 Tage. Wenn die Eigenschaft auf 0 Tage festgelegt ist, läuft sie nie ab. [Legen Sie den TTL-Wert ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) fest, wenn Sie eine Eigenschaft im Abschnitt [!UICONTROL Advanced Options] der Benutzeroberfläche zur Erstellung von Eigenschaften erstellen oder bearbeiten.

### 1 Tag TTL Erklärung

Beim Festlegen von [!DNL TTL] auf 1 Tag startet der TTL-Timer den nächsten Tag nach der Realisierung der Eigenschaften, wobei die Stunden, die im Tag der Realisierung der Eigenschaften verbleiben, nicht gezählt werden.

Audience Manager berechnet die [!DNL TTL] Gültigkeit für Eigenschaften mit 1 Tag [!DNL TTL] anhand der folgenden Formel:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Beispiel 1**: Eine Eigenschaft, die um 1:00 [!DNL UTC] mit 1 Tag [!DNL TTL] realisiert wurde. [!DNL TTL] läuft 24 + 24 - 1 = 47 Stunden später ab.
* **Beispiel 2**: Eine Eigenschaft, die um 23:00 [!DNL UTC] mit einem Tag [!DNL TTL] realisiert wurde. [!DNL TTL] läuft 24 + 24 - 23 = 25 Stunden später ab.

## [!DNL TTL] und Löschen aus einem Segment

Ein Benutzer verlässt ein Segment, wenn er sich nicht für eine seiner Eigenschaften innerhalb des [!DNL TTL] -Intervalls qualifiziert hat. Wenn Sie beispielsweise ein Segment mit einer Eigenschaft von 1 mit 30 Tagen [!DNL TTL] haben, wird der Benutzer dieses Segment abbrechen, wenn er sich innerhalb der nächsten 30 Tage nicht erneut für die Eigenschaft qualifiziert hat.

![](assets/ttl-explained.png)

## [!DNL TTL] und Segmenterneuerung

Die [!DNL TTL] wird zurückgesetzt und der Benutzer bleibt in einem Segment, wenn er sich innerhalb des [!DNL TTL] -Zeitraums für die Eigenschaft dieses Segments qualifiziert. Da die meisten Segmente mehrere Eigenschaften mit eigenen [!DNL TTL] -Intervallen enthalten, kann ein Benutzer in einem Segment verbleiben und das [!DNL TTL] -Intervall zurücksetzen, solange er sich für alle Eigenschaften qualifiziert, die mit dem Segment verknüpft sind.

Angenommen, Sie haben Segment 1 aus Eigenschaft A (30 Tage [!DNL TTL]) und Eigenschaft B (15 Tage [!DNL TTL]). Wenn ein Besucher nur einmal für jede Eigenschaft qualifiziert ist, wird in der folgenden Abbildung der Verlängerungsprozess für [!DNL TTL] und die gesamte Dauer innerhalb des Segments beschrieben.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTLs sind unabhängig von TTL-Einstellungen von Drittanbietern

Beachten Sie, dass das für Ihr [!DNL Audience Manager]-Pixel festgelegte [!DNL TTL]-Zeichen unabhängig von dem für andere von Drittanbietern verwendete Pixel ([!DNL DSP]s, Anzeigennetzwerke usw.) ist.[!DNL TTL]

>[!MORELIKETHIS]
>
>* [Festlegen eines Ablaufintervalls für Eigenschaften](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

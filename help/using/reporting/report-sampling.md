---
description: Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerquoten und eine Liste von Berichten, die Informationen basierend auf Stichprobendaten zurückgeben.
seo-description: Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerquoten und eine Liste von Berichten, die Informationen basierend auf Stichprobendaten zurückgeben.
seo-title: Datenstichproben und Fehlerraten in ausgewählten Audience Manager-Berichten
solution: Audience Manager
title: Datenstichproben und Fehlerraten in ausgewählten Audience Manager-Berichten
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Datenstichproben und Fehlerraten in ausgewählten Audience Manager-Berichten{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerquoten und eine Liste von Berichten, die Informationen basierend auf Stichprobendaten zurückgeben.

## Datenstichprobenverhältnis und Mindestanforderungen {#data-sampling-ratio}

Einige [!DNL Audience Manager] Berichte zeigen Ergebnisse basierend auf einem Stichprobensatz der insgesamt verfügbaren Daten an. Das Stichprobendatenverhältnis beträgt 1:54. Bei Berichten, die Stichprobendaten verwenden, basieren Ihre Ergebnisse auf einem Datensatz aus jeweils 54 Datensätzen.

Diese Berichte verwenden Stichprobendaten, weil sie eine enorme Rechenleistung benötigen, um Ergebnisse zu erzielen. Die Probenahme hilft dabei, ein Gleichgewicht zwischen geringeren Rechenanforderungen, der Aufrechterhaltung der Systemleistung und der Bereitstellung präziser Ergebnisse herzustellen.

Berichte, die Stichproben verwenden, schließen Eigenschaften und Segmente aus, wenn sie die Mindestanforderungen an individuelle Besucher nicht erfüllen. Diese Mindestanforderungen lauten wie folgt:

* Eigenschaften: 28.000 [einzigartige Eigenschaften](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) über einen Zeitraum von 14 Tagen.
* Segmente: 70.000 Echtzeit-Benutzer über einen Zeitraum von 14 Tagen.

## Fehlerquoten {#error-rates}

Fehler können in Berichten auftreten, die überlappende Daten generieren. Ein Fehler wird definiert als der Prozentsatz der Datensätze, die:

* Hätte nicht in einen Bericht aufgenommen, aber trotzdem hinzugefügt werden sollen.
* Hätte in einen Bericht aufgenommen werden sollen, aber nicht berücksichtigt.

Beachten Sie, dass unsere Tests und Modelle zeigen, dass die Fehlerquote im umgekehrten Verhältnis zur Anzahl der Datensätze in Ihrem Datensatz *sinkt* . Datensätze mit vielen Datensätzen führen zu weniger Fehlern als Datensätze mit einer geringen Anzahl von Datensätzen. Betrachten wir diese Behauptung quantitativer. Wie in der folgenden Tabelle dargestellt, liegen 95 % Ihrer Berichtsergebnisse bei einer bestimmten Anzahl von Datensätzen unter einer bestimmten Fehlerquote.

| Anzahl der Datensätze | Fehlerquote |
|--- |--- |
| 500 - 1,000 | 95 % weisen eine Fehlerquote von 42 % auf. |
| 1,000 - 1,500 | 95 % weisen eine Fehlerquote von 34 % auf. |
| 10,000 - 50,000 | 95 % weisen eine Fehlerquote von 14 % auf. |
| 50.000 | 95 % weisen eine Fehlerquote von 6 % auf. |
| 100,000 | 95 % weisen eine Fehlerquote von 4 % auf. |
| 500.000 (oder mehr) | 95 % weisen eine Fehlerquote von 2 % auf. |

## Berichte mit Beispieldaten {#reports-using-sampled-data}

Zu den [!DNL Audience Manager] Berichten, die Stichprobendaten verwenden, gehören:

* [Berichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) überlappen (Eigenschaften in Eigenschaften, Segmente in Eigenschaften und Segmente in Segmente).
* [Addressable Audience](../features/addressable-audiences.md) Data (Daten auf Kunden- und Segmentebene).
* Die Metrik [Geräte](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) insgesamt für einen [!UICONTROL Profile Merge Rule].

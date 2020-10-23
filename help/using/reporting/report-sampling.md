---
description: Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerquoten und eine Liste von Berichten, die Informationen basierend auf Stichprobendaten zurückgeben.
seo-description: Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerquoten und eine Liste von Berichten, die Informationen basierend auf Stichprobendaten zurückgeben.
seo-title: Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten
solution: Audience Manager
title: Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 33d844578c5cd620f9d4c33ec931ae0778aabb07
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 7%

---


# Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerquoten und eine Liste von Berichten, die Informationen basierend auf Stichprobendaten zurückgeben.

## Datenstichprobenverhältnis {#data-sampling-ratio}

Einige [!DNL Audience Manager] Berichte zeigen Ergebnisse basierend auf einem Stichprobensatz der insgesamt verfügbaren Daten an. Das Stichprobendatenverhältnis beträgt 1:54. Bei Berichten, die Stichprobendaten verwenden, basieren Ihre Ergebnisse auf einem Datensatz aus jeweils 54 Datensätzen.

Diese Berichte verwenden Daten aus statistischen Stichproben, weil sie eine enorme Rechenleistung benötigen, um Ergebnisse zu erzielen. Die Probenahme hilft dabei, ein Gleichgewicht zwischen geringeren Rechenanforderungen, der Aufrechterhaltung der Systemleistung und der Bereitstellung präziser Ergebnisse herzustellen.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

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

## Verwenden der Minhash-Stichprobenmethode {#minhash}

Auf der Grundlage der [Minhash](https://en.wikipedia.org/wiki/MinHash) -Stichprobenmethode verwendet Audience Manager eine neuartige Methode, um Eigenschaften- und Segmentaussagen auf einer Datenskizze mit One Permutation Hashing zu berechnen. Diese neue Methode erzeugt eine geringere Varianz als der Standardaussagewert für Jaccard-Ähnlichkeitsschätzer. Die Berichte, die diese Methode verwenden, finden Sie im folgenden Abschnitt.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Berichte, die Beispieldaten verwenden {#reports-using-sampled-data}

Zu den [!DNL Audience Manager] Berichten mit statistischen Stichprobendaten und der Minhash-Stichprobenmethode gehören:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Statistische Stichproben | Minhash-Stichprobenmethode |
|--- |--- |
| [Addressable Audience](../features/addressable-audiences.md) Data (Daten auf Kunden- und Segmentebene). | [Überschneidungsberichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (Eigenschaften in Eigenschaften, Segmente in Eigenschaften und Segmente in Segmente) |
| Die Metrik [Geräte](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) insgesamt für einen [!UICONTROL Profile Merge Rule]. | [Eigenschaftenempfehlungen](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) verwendet Stichprobendaten auf der [!UICONTROL Search] Registerkarte und beliebige [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |

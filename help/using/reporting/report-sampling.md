---
description: Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerraten und eine Liste von Berichten, die Informationen auf der Grundlage von Stichprobendaten liefern.
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Daten-Sampling und Fehlerraten in ausgewählten Audience Manager-Berichten{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerraten und eine Liste von Berichten, die Informationen auf der Grundlage von Stichprobendaten liefern.

## Daten-Sampling-Verhältnis {#data-sampling-ratio}

Einige [!DNL Audience Manager] -Berichte zeigen Ergebnisse basierend auf einem Stichprobensatz der insgesamt verfügbaren Datenmenge an. Das Datenverhältnis der Stichprobe beträgt 1:54. Für Berichte, die Stichprobendaten verwenden, bedeutet dies, dass Ihre Ergebnisse auf 1 Datensatz aus jedem Satz von 54 Datensätzen basieren.

Diese Berichte verwenden Daten aus statistischen Stichproben, da sie eine enorme Rechenleistung benötigen, um Ergebnisse zu erzielen. Das Sampling hilft, ein Gleichgewicht zwischen reduzierten Rechenanforderungen, der Aufrechterhaltung der Systemleistung und der Bereitstellung genauer Ergebnisse zu finden.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Fehlerraten {#error-rates}

Fehler können in Berichten auftreten, die Überlagerungsdaten generieren. Ein Fehler ist definiert als der Prozentsatz an Datensätzen, die:

* Hätte nicht in einen Bericht aufgenommen, aber trotzdem hinzugefügt werden sollen.
* Sollte in einen Bericht aufgenommen, aber nicht berücksichtigt werden.

Beachten Sie, dass unsere Tests und Modelle zeigen, dass die Fehlerrate *im umgekehrten Verhältnis zur Anzahl der Datensätze in Ihrem Datensatz abnimmt*. Datensätze mit vielen Datensätzen erzeugen weniger Fehler als Datensätze mit einer geringen Datensatzanzahl. Sehen wir uns diese Behauptung quantitativer an. Wie in der folgenden Tabelle dargestellt, liegen 95 % der Berichtsergebnisse bei einer bestimmten Anzahl von Datensätzen unter einer bestimmten Fehlerrate.

| Anzahl Datensätze | Fehlerrate |
|--- |--- |
| 500-1.000 | 95 % weisen eine Fehlerrate von 42 % auf. |
| 1.000-1.500 | 95 % weisen eine Fehlerrate von 34 % auf. |
| 10.000 - 50.000 | 95 % weisen eine Fehlerrate von 14 % auf. |
| 50.000 | 95 % weisen eine Fehlerrate von 6 % auf. |
| 100.000 | 95 % weisen eine Fehlerrate von 4 % auf. |
| 500.000 (oder mehr) | 95 % weisen eine Fehlerrate von 2 % auf. |

## Verwenden der Minhash-Sampling-Methode {#minhash}

Basierend auf der Sampling-Methode [Minhash](https://en.wikipedia.org/wiki/MinHash) verwendet Audience Manager eine neuartige Methode, um Eigenschaften- und Segmentschätzungen über einer Datenskizze vom Typ One Permutation Hashing zu berechnen. Diese neue Methode erzeugt eine geringere Varianz als der Standardschätzer für die Ähnlichkeit von Jaccard. Im folgenden Abschnitt finden Sie die Berichte, die diese Methode verwenden.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Berichte mit Stichprobendaten {#reports-using-sampled-data}

Die [!DNL Audience Manager] -Berichte, die statistische Stichprobendaten verwenden, und die Minhash-Stichprobenmethode umfassen:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Statistische Auswahl | Minhash-Sampling-Methode |
|--- |--- |
| [Addressable Audience](../features/addressable-audiences.md) -Daten (Daten auf Kunden- und Segmentebene). | [Überlagerungsberichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (Eigenschaften-zu-Eigenschaften-, Segment-zu-Merkmal- und Segment-zu-Segment-Berichte) |
| Die Metrik [Geräte insgesamt](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) für einen Wert [!UICONTROL Profile Merge Rule]. | [Eigenschaftenempfehlungen](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) verwendet gesampelte Daten auf der Registerkarte [!UICONTROL Search] und beliebige [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |

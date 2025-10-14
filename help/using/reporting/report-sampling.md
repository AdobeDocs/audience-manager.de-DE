---
description: Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerraten und eine Liste von Berichten, die Informationen auf der Grundlage von Stichprobendaten zurückgeben.
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: Datenstichproben und Fehlerquoten in ausgewählten Audience Manager-Berichten
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Datenstichproben und Fehlerquoten in ausgewählten Audience Manager-Berichten{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Eine Zusammenfassung der für einige Berichte verwendeten Stichprobenmethodik, Stichprobenfehlerraten und eine Liste von Berichten, die Informationen auf der Grundlage von Stichprobendaten zurückgeben.

## Verhältnis von Datenabtastung {#data-sampling-ratio}

Einige [!DNL Audience Manager] zeigen Ergebnisse basierend auf einem Stichprobensatz der Gesamtmenge der verfügbaren Daten an. Das Verhältnis der abgetasteten Daten beträgt 1:54. Für Berichte, die Stichprobendaten verwenden, bedeutet dies, dass Ihre Ergebnisse auf einem Datensatz aus jedem Satz von 54 Datensätzen basieren.

Diese Berichte verwenden statistische Stichprobendaten, da sie eine enorme Rechenleistung benötigen, um Ergebnisse zu generieren. Das Sampling hilft, ein Gleichgewicht zwischen reduzierten Rechenanforderungen, Aufrechterhaltung der Systemleistung und Bereitstellung genauer Ergebnisse zu finden.

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

Fehler können in Berichten auftreten, die Überschneidungsdaten generieren. Ein Fehler wird als Prozentsatz der Datensätze definiert, die:

* Sollte nicht in einem Bericht enthalten sein, wurde aber trotzdem hinzugefügt.
* Sie hätten in einen Bericht aufgenommen werden müssen, wurden aber nicht berücksichtigt.

Beachten Sie, dass unsere Tests und Modelle zeigen, dass die Fehlerrate *sinkt* umgekehrt proportional zur Anzahl der Datensätze in Ihrem Datensatz ist. Datensätze mit vielen Datensätzen generieren weniger Fehler als Datensätze mit einer geringen Anzahl von Datensätzen. Sehen wir uns diese Behauptung quantitativ an. Wie in der folgenden Tabelle gezeigt, liegen 95 % der Berichtsergebnisse für eine bestimmte Anzahl von Datensätzen unter einer bestimmten Fehlerrate.

| Anzahl Datensätze | Fehlerrate |
|--- |--- |
| 500 - 1.000 | 95 % liegen unter einer Fehlerquote von 42 %. |
| 1.000 - 1.500 | Bei 95 % liegt die Fehlerquote unter 34 %. |
| 10.000 - 50.000 | 95 % liegen unter einer Fehlerquote von 14 %. |
| 50.000 | 95 % liegen unter einer Fehlerquote von 6 %. |
| 100.000 | 95 % liegen unter einer Fehlerquote von 4 %. |
| 500.000 (oder mehr) | 95 % liegen unter einer Fehlerquote von 2 %. |

## Verwenden der Minhash-Stichprobenmethode {#minhash}

Basierend auf der [Minhash](https://en.wikipedia.org/wiki/MinHash)-Stichprobenmethode verwendet Audience Manager eine neuartige Methode zur Berechnung von Eigenschaften- und Segmentschätzungen auf der Grundlage einer Datenskizze mit einem Permutations-Hashing. Diese neue Methode erzeugt eine niedrigere Varianz als die Standardschätzung für die Jaccard-Ähnlichkeit. Im folgenden Abschnitt finden Sie die Berichte, die diese Methode verwenden.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Berichte, die Beispieldaten verwenden {#reports-using-sampled-data}

Die [!DNL Audience Manager] Berichte, die statistische Stichprobendaten und die Minhash-Stichprobenmethode verwenden, umfassen Folgendes:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Statistische Stichprobenziehung | Minhash-Stichprobenmethode |
|--- |--- |
| [Adressierbare &#x200B;](../features/addressable-audiences.md)) (Daten auf Kunden- und Segmentebene). | [Überschneidungsberichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (Eigenschaft-zu-Eigenschaft, Segment-zu-Eigenschaft und Segment-zu-Segment) |
| Die [Gesamtzahl der Geräte](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) für eine [!UICONTROL Profile Merge Rule]. | [Eigenschaftenempfehlungen](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) verwendet auf der Registerkarte &quot;[!UICONTROL Search]&quot; und in allen [!UICONTROL Saved Searches] Stichprobendaten | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |

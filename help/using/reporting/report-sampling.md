---
description: Eine Zusammenfassung der Stichprobenmethode für einige Berichte, Stichprobenfehlerquoten und eine Liste von Berichten, die Informationen basierend auf Stichproben zurückgeben.
seo-description: Eine Zusammenfassung der Stichprobenmethode für einige Berichte, Stichprobenfehlerquoten und eine Liste von Berichten, die Informationen basierend auf Stichproben zurückgeben.
seo-title: Datenstichproben und Fehlersätze in ausgewählten Audience Manager-Berichten
solution: Audience Manager
title: Datenstichproben und Fehlersätze in ausgewählten Audience Manager-Berichten
uuid: 3 d 8 bd 764-a 9 da -40 f 1-8794-54304457 bb 9 a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Eine Zusammenfassung der Stichprobenmethode für einige Berichte, Stichprobenfehlerquoten und eine Liste von Berichten, die Informationen basierend auf Stichproben zurückgeben.

## Data Sampling Ratio and Minimum Requirements {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. Das berechnete Datenverhältnis beträgt 1:54. Bei Berichten, die Stichprobendaten verwenden, basieren Ihre Ergebnisse auf 1 Datensätzen aus allen 54 Datensätzen.

Diese Berichte verwenden Stichprobendaten, da sie eine enorme Datenverarbeitungsstärke benötigen, um Ergebnisse zu generieren. Mithilfe von Stichproben können Sie ein Gleichgewicht zwischen verringerten berechneten Anforderungen erzielen, die Systemleistung gewährleisten und genaue Ergebnisse erzielen.

Berichte, die Eigenschaften und Segmente mit Stichproben verwenden, wenn sie die Mindestanforderungen an individuelle Besucher nicht erfüllen. Folgende Mindestanforderungen gelten:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) over a 14-day period.
* Segmente: 70.000 Echtzeit-Benutzer über einen Zeitraum von 14 Tagen.

## Error Rates {#error-rates}

Fehler können in Berichten auftreten, die Überlappungsdaten erzeugen. Ein Fehler wird als Prozentsatz der Datensätze definiert, die:

* Sollte nicht in einen Bericht aufgenommen werden, aber trotzdem hinzugefügt werden.
* Sollte in einen Bericht aufgenommen worden sein, aber nicht beendet worden sein.

It's important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. Datensätze mit vielen Datensätzen generieren weniger Fehler als Sätze mit einer geringen Anzahl von Datensätzen. Lassen Sie uns diese Zusicherung auf eine quantitativer Weise betrachten. Wie in der folgenden Tabelle dargestellt, liegen 95% Ihrer Berichtsergebnisse bei einer festgelegten Anzahl von Datensätzen unter einer bestimmten Fehlerrate.

| Anzahl Datensätze | Fehlerrate |
|--- |--- |
| 500 - 1,000 | 95% liegen unter einer 42%-Fehlerrate. |
| 1,000 - 1,500 | 95% liegen unter einer 34%-Fehlerrate. |
| 10,000 - 50,000 | 95% liegen unter einer 14%-Fehlerrate. |
| 50.000 | 95% liegen unter einer Fehlerrate von 6%. |
| 100,000 | 95% liegen unter einer 4%-Fehlerrate. |
| 500.000 (oder mehr) | 95% liegen unter einer 2%-Fehlerrate. |

## Reports That Use Sampled Data {#reports-using-sampled-data}

The [!DNL Audience Manager] reports that use sampled data include:

* [Überlappungsberichte](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (Trait-to-Trait, Segment-to-Trait und Segment-to-Segment).
* [Addressable Audience](../features/addressable-audiences.md) -Daten (Daten auf Kunden- und Segmentebene).
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].

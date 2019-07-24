---
description: In diesem Artikel werden die Vergleichsoperatoren beschrieben, die von Eigenschaften Builder verwendet werden.
seo-description: In diesem Artikel werden die Vergleichsoperatoren beschrieben, die von Eigenschaften Builder verwendet werden.
seo-title: Arbeiten mit Vergleichsoperatoren im Eigenschaftenaufbau
solution: Audience Manager
title: Arbeiten mit Vergleichsoperatoren im Eigenschaftenaufbau
uuid: 41 bec 3 b 3-e 5 df -4 a 6 f-abb 0-80 ce 4 c 75 f 5 e 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Working with Comparison Operators in Trait Builder {#working-with-comparison-operators-in-trait-builder}

This article describes the comparison operators used by [!UICONTROL Trait Builder].

## Zweck von Vergleichsoperatoren

<!-- c_tb_comparison_operators.xml -->

Vergleichsoperatoren (oder relationale Operatoren) werden verwendet, um die Beziehung zwischen verschiedenen Werten zu vergleichen, zu testen oder zu bewerten. In [!UICONTROL Trait Builder], when building signal rules, comparison operators let you test the relationship between different key-value pairs. Sie können beispielsweise eine Signaturregel erstellen, um eine Zielgruppe für teure Kamera-Käufer zu definieren. In diesem Fall können Sie ein Kamera-/Preisschlüssel-Paar erstellen und einen Benutzer qualifizieren, wenn sie nach einer Kamera gesucht haben, deren Preis einem oder mehreren Sätzen entspricht.

## Vorteile von Vergleichsoperatoren

Vergleichsoperatoren sind nützlich, wenn Sie Eigenschaften auf Grundlage mehrerer Werte bewerten und erstellen müssen. Diese Bedingung kann sich auf die Preise für Produkte und Dienste beziehen. Beispielsweise könnte Ihr Unternehmen Besucher anhand der Preise der Produkte identifizieren wollen, die sie anzeigen. Es kann jedoch verwaltungsfähig sein, einzelne Segmente auf Basis bestimmter Werte zu definieren. Vergleichsoperatoren helfen diese Hürde, indem sie Segmentierungsauslöser basierend auf Preisschwellenwerten oder Bereichen einrichten.

## Vergleichsoperatoren

Sie können Regeln mit den folgenden Vergleichsoperatoren erstellen:

| Operator | Definition |
|---|---|
| **==** | Gleich |
| **!=** | Nicht gleich |
| **&gt;** | Größer als |
| **&lt;** | Kleiner als |
| **=&gt;** | Größer als/gleich |
| **&lt;=** | Kleiner als/gleich |

## Benannte Operatoren

Sie können Regeln mit den folgenden benannten Operatoren erstellen:

| Operator | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Matcheswords]** | The value in a key-value pair *matches* the pattern specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |
| **[!UICONTROL Matchesregex]** | The value in a key-value pair *matches* the pattern specified by a regular expression. [Erfahren Sie mehr](../../features/traits/trait-builder-regex.md) über die Verwendung regulärer Ausdrücke.[!UICONTROL Trait Builder] |

>[!MORE_ LIKE_ THIS]
>
>* [Boolesche Ausdrücke in Eigenschaften und Segmentaufbau](../../reference/boolean-expressions-tsb.md)
>* [Erläuterungen zu Booleschen Ausdrücken in traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Reihenfolge der Vorgänge in traitbuilder-Ausdrücken](../../features/traits/trait-operator-precedence.md)
>* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)


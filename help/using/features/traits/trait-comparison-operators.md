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


# Arbeiten mit Vergleichsoperatoren im Eigenschaftenaufbau {#working-with-comparison-operators-in-trait-builder}

In diesem Artikel werden die von Ihnen verwendeten Vergleichsoperatoren beschrieben [!UICONTROL Trait Builder].

## Zweck von Vergleichsoperatoren

<!-- c_tb_comparison_operators.xml -->

Vergleichsoperatoren (oder relationale Operatoren) werden verwendet, um die Beziehung zwischen verschiedenen Werten zu vergleichen, zu testen oder zu bewerten. Beim [!UICONTROL Trait Builder]Erstellen von Signalregeln können Vergleichsoperatoren die Beziehung zwischen verschiedenen Schlüssel-Wert-Paaren testen. Sie können beispielsweise eine Signaturregel erstellen, um eine Zielgruppe für teure Kamera-Käufer zu definieren. In diesem Fall können Sie ein Kamera-/Preisschlüssel-Paar erstellen und einen Benutzer qualifizieren, wenn sie nach einer Kamera gesucht haben, deren Preis einem oder mehreren Sätzen entspricht.

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
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Matcheswords]** | Der Wert in einem Schlüssel-Wert-Paar *stimmt mit* dem von diesem Operator angegebenen Muster überein. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *beginnt mit* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Matchesregex]** | Der Wert in einem Schlüssel-Wert-Paar *stimmt mit* dem durch einen regulären Ausdruck angegebenen Muster überein. [Learn more](../../features/traits/trait-builder-regex.md) about using regular expressions in [!UICONTROL Trait Builder]. |

>[!MORE_ LIKE_ THIS]
>
>* [Boolesche Ausdrücke in Eigenschaften und Segmentaufbau](../../reference/boolean-expressions-tsb.md)
>* [Erläuterungen zu Booleschen Ausdrücken in traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Reihenfolge der Vorgänge in traitbuilder-Ausdrücken](../../features/traits/trait-operator-precedence.md)
>* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)


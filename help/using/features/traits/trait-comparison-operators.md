---
description: In diesem Artikel werden die Vergleichsoperatoren beschrieben, die von Eigenschaften Builder verwendet werden.
seo-description: In diesem Artikel werden die Vergleichsoperatoren beschrieben, die von Eigenschaften Builder verwendet werden.
seo-title: Arbeiten mit Vergleichsoperatoren in Trait Builder
solution: Audience Manager
title: Arbeiten mit Vergleichsoperatoren in Trait Builder
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# Arbeiten mit Vergleichsoperatoren in Trait Builder {#working-with-comparison-operators-in-trait-builder}

In diesem Artikel werden die Vergleichsoperatoren beschrieben, die von [!UICONTROL Trait Builder] verwendet werden.

## Zweck der Vergleichsoperatoren

<!-- c_tb_comparison_operators.xml -->

Vergleichsoperatoren (oder relationale Operatoren) werden verwendet, um die Beziehung zwischen verschiedenen Werten zu vergleichen, zu testen oder zu bewerten. In [!UICONTROL Trait Builder] können Sie beim Erstellen von Signalregeln mithilfe von Vergleichsoperatoren die Beziehung zwischen verschiedenen Schlüssel/Wert-Paaren testen. Sie können beispielsweise eine Signalregel erstellen, um eine Audience für teure Kamerabezocke zu definieren. In diesem Fall können Sie ein Schlüssel-Wert-Paar für Kamera/Preis erstellen und einen Benutzer qualifizieren, wenn er nach einer Kamera gesucht hat, deren Preis mindestens einem bestimmten Betrag entspricht.

## Vorteile von Vergleichsoperatoren

Vergleichsoperatoren sind nützlich, wenn Sie Eigenschaften auf der Grundlage mehrerer Werte bewerten und erstellen müssen. Eine Betrachtung der Preise für Waren und Dienstleistungen kann diese Bedingung illustrieren. Ihr Unternehmen könnte z. B. Besucher anhand der Preise der von Ihnen Ansicht Produkte identifizieren wollen. Es kann jedoch administrativ ineffizient sein, einzelne Segmente basierend auf bestimmten Werten zu definieren. Vergleichsoperatoren tragen dazu bei, diese Hürde zu überwinden, indem sie Trigger für die Segmentierung auf der Grundlage von Preisschwellen oder -bereichen festlegen.

## Vergleichsoperatoren

Sie können Regeln mit den folgenden Vergleichsoperatoren erstellen:

| Operator | Definition |
|---|---|
| **==** | Gleich |
| **!=** | Nicht gleich |
| **>** | Größer als |
| **&lt;** | Kleiner als |
| **=>** | Größer als/gleich |
| **&lt;=** | Kleiner als/gleich |

## Benannte Operatoren

Sie können Regeln mit den folgenden benannten Operatoren erstellen:

| Operator | Wertet für [!DNL True] Wenn aus |
|---|---|
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Matcheswords]** | Der Wert in einem Schlüssel-Wert-Paar *entspricht* dem von diesem Operator angegebenen Muster. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *Beginn mit* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Matchesregex]** | Der Wert in einem Schlüssel-Wert-Paar *entspricht* dem von einem regulären Ausdruck angegebenen Muster. [Erfahren Sie mehr ](../../features/traits/trait-builder-regex.md) über die Verwendung von regulären Ausdrücken in  [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Boolesche Ausdruck in Trait und Segment Builder](../../reference/boolean-expressions-tsb.md)
>* [Die booleschen Ausdruck in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Reihenfolge der Vorgänge in TraitBuilder-Ausdrücken](../../features/traits/trait-operator-precedence.md)
>* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)


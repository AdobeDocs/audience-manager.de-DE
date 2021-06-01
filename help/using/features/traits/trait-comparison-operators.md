---
description: In diesem Artikel werden die von Trait Builder verwendeten Vergleichsoperatoren beschrieben.
seo-description: In diesem Artikel werden die von Trait Builder verwendeten Vergleichsoperatoren beschrieben.
seo-title: Arbeiten mit Vergleichsoperatoren in Trait Builder
solution: Audience Manager
title: Arbeiten mit Vergleichsoperatoren in Trait Builder
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: 'Eigenschaften '
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 12%

---

# Arbeiten mit Vergleichsoperatoren in Trait Builder {#working-with-comparison-operators-in-trait-builder}

In diesem Artikel werden die von [!UICONTROL Trait Builder] verwendeten Vergleichsoperatoren beschrieben.

## Zweck der Vergleichsoperatoren

<!-- c_tb_comparison_operators.xml -->

Vergleichsoperatoren (oder relationale Operatoren) werden verwendet, um die Beziehung zwischen verschiedenen Werten zu vergleichen, zu testen oder zu bewerten. In [!UICONTROL Trait Builder] können Sie beim Erstellen von Signalregeln mithilfe von Vergleichsoperatoren die Beziehung zwischen verschiedenen Schlüssel-Wert-Paaren testen. Sie können beispielsweise eine Signalregel erstellen, um eine Zielgruppe für teure Kamerakäufer zu definieren. In diesem Fall können Sie ein Schlüssel-Wert-Paar zwischen Kamera und Preis erstellen und einen Benutzer qualifizieren, wenn er nach einer Kamera gesucht hat, deren Preis mindestens einem bestimmten Betrag entspricht.

## Vorteile von Vergleichsoperatoren

Vergleichsoperatoren sind nützlich, wenn Sie Eigenschaften anhand mehrerer Werte bewerten und erstellen müssen. Ein Blick auf die Preise für Waren und Dienstleistungen kann diese Bedingung verdeutlichen. Ihr Unternehmen kann beispielsweise Besucher anhand der Preise der von ihm angesehenen Produkte identifizieren wollen. Es kann jedoch administrativ ineffizient sein, einzelne Segmente basierend auf bestimmten Werten zu definieren. Vergleichsoperatoren tragen dazu bei, diese Hürde zu überwinden, indem sie Trigger für die Segmentierung auf der Grundlage von Preisschwellen oder -bereichen festlegen.

## Vergleichsoperatoren

Sie können Regeln mit den folgenden Vergleichsoperatoren erstellen:

| Operator | Definition |
|---|---|
| **==** | Gleich |
| **!=** | Ungleich |
| **>** | Größer als |
| **&lt;** | Kleiner als |
| **=>** | Größer/gleich |
| **&lt;=** | Kleiner/gleich |

## Benannte Operatoren

Sie können Regeln mit den folgenden benannten Operatoren erstellen:

| Operator | Wertet nach [!DNL True] wenn aus |
|---|---|
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* die von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Matcheswords]** | Der Wert in einem Schlüssel-Wert-Paar *entspricht* dem von diesem Operator angegebenen Muster. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *beginnt mit* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Matchesregex]** | Der Wert in einem Schlüssel-Wert-Paar *entspricht* dem Muster, das durch einen regulären Ausdruck angegeben wird. [Erfahren Sie mehr ](../../features/traits/trait-builder-regex.md) über die Verwendung regulärer Ausdrücke in  [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Boolesche Ausdruck in Trait und Segment Builder](../../reference/boolean-expressions-tsb.md)
* [Grundlegendes zu booleschen Ausdrücken in TraitBuilder](../../reference/boolean-expressions-tsb.md)
* [Reihenfolge der Vorgänge in TraitBuilder-Ausdrücken](../../features/traits/trait-operator-precedence.md)
* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)


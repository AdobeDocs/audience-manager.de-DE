---
description: In diesem Artikel werden die von Trait Builder verwendeten Vergleichsoperatoren beschrieben.
seo-description: This article describes the comparison operators used by Trait Builder.
seo-title: Working with Comparison Operators in Trait Builder
solution: Audience Manager
title: Arbeiten mit Vergleichsoperatoren in Trait Builder
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
TQID: https://experienceleague.adobe.com/Mbrgy2gmtUB5wrjmxIYjFaYOxbnrvh3bMKbkJ4zrM4o
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 339
ht-degree: 6%

---

# Arbeiten mit Vergleichsoperatoren in Trait Builder {#working-with-comparison-operators-in-trait-builder}

In diesem Artikel werden die von [!UICONTROL Trait Builder] verwendeten Vergleichsoperatoren beschrieben.

## Zweck von Vergleichsoperatoren

<!-- c_tb_comparison_operators.xml -->

Vergleichsoperatoren (oder relationale Operatoren) werden verwendet, um die Beziehung zwischen verschiedenen Werten zu vergleichen, zu testen oder auszuwerten. [!UICONTROL Trait Builder] können Sie beim Erstellen von Signalregeln mit Vergleichsoperatoren die Beziehung zwischen verschiedenen Schlüssel-Wert-Paaren testen. Sie können beispielsweise eine Signalregel erstellen, um eine Zielgruppe für teure Käufer von Kameras zu definieren. In diesem Fall können Sie ein Schlüssel-Wert-Paar aus Kamera/Preis erstellen und einen Benutzer qualifizieren, wenn er nach einer Kamera mit einem Preis gesucht hat, der gleich oder größer als ein festgelegter Betrag ist.

## Vorteile von Vergleichsoperatoren

Vergleichsoperatoren sind nützlich, wenn Sie Eigenschaften basierend auf mehreren Werten auswerten und erstellen möchten. Ein Blick auf die Preise für Waren und Dienstleistungen kann diese Bedingung veranschaulichen. Beispielsweise kann Ihr Unternehmen Besuchende anhand der Preise der angezeigten Produkte identifizieren. Es kann jedoch administrativ ineffizient sein, einzelne Segmente basierend auf bestimmten Werten zu definieren. Vergleichsoperatoren helfen, diese Hürde zu überwinden, indem sie Segmentierungs-Trigger auf der Grundlage von Preisschwellen oder -spannen festlegen.

## Vergleichsoperatoren

Sie können Regeln mit den folgenden Vergleichsoperatoren erstellen:

| Benutzerin oder Benutzer | Definition |
|---|---|
| **==** | Gleich |
| **!=** | Ungleich |
| **>** | Größer als |
| **&#x200B;**&#x200B;| Kleiner als |
| **=>** | Größer als/gleich |
| **&lt;=** | Kleiner/gleich |

## Benannte Operatoren

Sie können Regeln mit den folgenden benannten Operatoren erstellen:

| Benutzerin oder Benutzer | Wird zu [!DNL True] ausgewertet, wenn |
|---|---|
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* von diesem Operator angegebene Zeichen. |
| **[!UICONTROL Matcheswords]** | Der Wert in einem Schlüssel-Wert-Paar *stimmt überein mit* von diesem Operator angegebenen Muster. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *beginnt mit* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Matchesregex]** | Der Wert in einem Schlüssel-Wert-Paar *stimmt überein mit* durch einen regulären Ausdruck angegebenen Muster. [Weitere Informationen](../../features/traits/trait-builder-regex.md) über die Verwendung regulärer Ausdrücke in [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Boolesche Ausdruck in Trait und Segment Builder](../../reference/boolean-expressions-tsb.md)
>* [Boolesche Ausdrücke in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Reihenfolge der Vorgänge in TraitBuilder-Ausdrücken](../../features/traits/trait-operator-precedence.md)
>* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)

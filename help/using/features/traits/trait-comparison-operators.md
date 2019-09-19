---
description: In diesem Artikel werden die Vergleichsoperatoren beschrieben, die von Eigenschaften Builder verwendet werden.
seo-description: In diesem Artikel werden die Vergleichsoperatoren beschrieben, die von Eigenschaften Builder verwendet werden.
seo-title: Arbeiten mit Vergleichsoperatoren im Eigenschaften-Aufbau
solution: Audience Manager
title: Arbeiten mit Vergleichsoperatoren im Eigenschaften-Aufbau
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Arbeiten mit Vergleichsoperatoren im Eigenschaften-Aufbau {#working-with-comparison-operators-in-trait-builder}

In diesem Artikel werden die Vergleichsoperatoren beschrieben, die von [!UICONTROL Trait Builder]verwendet werden.

## Zweck der Vergleichsoperatoren

<!-- c_tb_comparison_operators.xml -->

Vergleichsoperatoren (oder relationale Operatoren) werden verwendet, um die Beziehung zwischen verschiedenen Werten zu vergleichen, zu testen oder zu bewerten. Bei [!UICONTROL Trait Builder]der Erstellung von Signalregeln können Sie mit Vergleichsoperatoren die Beziehung zwischen verschiedenen Schlüssel/Wert-Paaren testen. Sie können beispielsweise eine Signalregel erstellen, um eine Zielgruppe für teure Kamerakäufer zu definieren. In diesem Fall können Sie ein Schlüssel-Wert-Paar für Kamera/Preis erstellen und einen Benutzer qualifizieren, wenn er nach einer Kamera gesucht hat, deren Preis mindestens einem bestimmten Betrag entspricht.

## Vorteile von Vergleichsoperatoren

Vergleichsoperatoren sind nützlich, wenn Sie Eigenschaften auf der Grundlage mehrerer Werte bewerten und erstellen müssen. Eine Betrachtung der Preise für Waren und Dienstleistungen kann diese Bedingung illustrieren. Ihr Unternehmen könnte z. B. Besucher anhand der Preise der von Ihnen angezeigten Produkte identifizieren wollen. Es kann jedoch administrativ ineffizient sein, einzelne Segmente basierend auf bestimmten Werten zu definieren. Vergleichsoperatoren tragen dazu bei, diese Hürde zu überwinden, indem Segmentierungsauslöser auf der Grundlage von Preisschwellen oder -bereichen eingerichtet werden.

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

| Operator | Wertet [!DNL True] wann aus |
|---|---|
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* die von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Matcheswords]** | Der Wert in einem Schlüssel-Wert-Paar *entspricht* dem von diesem Operator angegebenen Muster. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *beginnt mit* den von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Matchesregex]** | Der Wert in einem Schlüssel-Wert-Paar *entspricht* dem Muster, das durch einen regulären Ausdruck angegeben wird. [Erfahren Sie mehr](../../features/traits/trait-builder-regex.md) über die Verwendung regulärer Ausdrücke in [!UICONTROL Trait Builder]. |

>[!MORE_LIKE_THIS]
>
>* [Boolesche Ausdrücke im Eigenschaften- und Segmentaufbau](../../reference/boolean-expressions-tsb.md)
>* [Boolesche Ausdrücke in EigenschaftenBuilder](../../reference/boolean-expressions-tsb.md)
>* [Reihenfolge der Vorgänge in EigenschaftenBuilder-Ausdrücken](../../features/traits/trait-operator-precedence.md)
>* [Beispielausdrücke mit booleschen Operatoren und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)


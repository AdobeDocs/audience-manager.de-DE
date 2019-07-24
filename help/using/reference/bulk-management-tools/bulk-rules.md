---
description: Das Erstellen und Aktualisieren von Arbeitsblättern akzeptiert eine traitrule-Kopfzeile, mit der Sie mehrere Regeln in einem einzelnen Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen zu erstellen.
seo-description: Das Erstellen und Aktualisieren von Arbeitsblättern akzeptiert eine traitrule-Kopfzeile, mit der Sie mehrere Regeln in einem einzelnen Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen zu erstellen.
seo-title: Erstellen oder Aktualisieren von Trait-Regeln und Segmentregeln
solution: Audience Manager
title: Erstellen oder Aktualisieren von Trait-Regeln und Segmentregeln
uuid: bdd 5 f 8 f 1-bb 83-4844-b 681-654 e 45 ace 3 e 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create or Update Trait Rules and Segment Rules{#create-or-update-trait-rules-and-segment-rules}

Das Erstellen und Aktualisieren von Arbeitsblättern akzeptiert eine traitrule-Kopfzeile, mit der Sie mehrere Regeln in einem einzelnen Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen zu erstellen.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

## Working with trait rules {#trait-rules}

In Ihrem Arbeitsblatt gibt die Spalte der Eigenschaftenregel Regeln zurück, die aus booleschen Ausdrücken, Vergleichsoperatoren und regulären Ausdrücken bestehen. You can create rules with trait or segment builder in [!DNL Audience Manager] and copy them to your worksheet. Wenn Sie mit der Regelsyntax vertraut sind, können Sie Ausdrücke direkt in den Arbeitsblättern schreiben.

## Rule builder example {#rule-builder-example}

Let's take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. Es handelt sich jedoch nicht um eine schrittweise Anleitung für diese Tools. Stattdessen beginnen wir mit einer einfachen Regel, die bereits erstellt wurde. For instructions about how to use the rule builders see [Segment Builder](../../features/segments/segment-builder.md) and [Trait Builder](../../features/traits/about-trait-builder.md).

With the visual rule builder, we've created a segment rule with 3 traits and a Boolean [!UICONTROL AND] operator.

![](assets/visualrule.png)

Click **[!UICONTROL Code View]** to get the text version of this rule.

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. Dadurch wird verhindert, dass Sie eine ungültige Regel hochladen.

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## Creating your own rules {#create-rules}

You can write your own rules outside of [!UICONTROL Rule Builder]. Bevor Sie beginnen, lesen Sie die Dokumentation, die sich auf Dinge wie Operatoren, Ausdruck und erforderliche Variablen bezieht. Wir empfehlen Ihnen Folgendes:

* [Arbeiten mit Vergleichsoperatoren im Eigenschaftenaufbau](../../features/traits/trait-comparison-operators.md)
* [Reihenfolge der Vorgänge](../../features/traits/trait-operator-precedence.md)
* [Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)
* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)


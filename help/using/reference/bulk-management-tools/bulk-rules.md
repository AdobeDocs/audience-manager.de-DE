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


# Erstellen oder Aktualisieren von Trait-Regeln und Segmentregeln{#create-or-update-trait-rules-and-segment-rules}

Das Erstellen und Aktualisieren von Arbeitsblättern akzeptiert eine traitrule-Kopfzeile, mit der Sie mehrere Regeln in einem einzelnen Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen zu erstellen.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>Die Variable [!UICONTROL Bulk Management Tools]*wird nicht* unterstützt [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. Für Massenänderungen wird empfohlen, stattdessen mit den [Audience Manager-apis](../../api/rest-api-main/aam-api-getting-started.md) zu arbeiten. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

## Arbeiten mit Trait-Regeln {#trait-rules}

In Ihrem Arbeitsblatt gibt die Spalte der Eigenschaftenregel Regeln zurück, die aus booleschen Ausdrücken, Vergleichsoperatoren und regulären Ausdrücken bestehen. Sie können Regeln mit Eigenschaften oder Segmentaufbau erstellen [!DNL Audience Manager] und in Ihr Arbeitsblatt kopieren. Wenn Sie mit der Regelsyntax vertraut sind, können Sie Ausdrücke direkt in den Arbeitsblättern schreiben.

## Beispiel für einen Regel-Builder {#rule-builder-example}

Sehen wir uns ein Beispiel an, in dem gezeigt wird, wie Sie eine [!UICONTROL Segment Builder] Regel zum Erstellen einer Regel zum Massen-Arbeitsblatt verwenden. Es handelt sich jedoch nicht um eine schrittweise Anleitung für diese Tools. Stattdessen beginnen wir mit einer einfachen Regel, die bereits erstellt wurde. Anweisungen zum Verwenden der Regelaufbau finden Sie unter [Segmentaufbau](../../features/segments/segment-builder.md) und [Eigenschaftenaufbau](../../features/traits/about-trait-builder.md).

Mit dem visuellen Regelaufbau haben wir eine Segmentregel mit 3 Eigenschaften und einem booleschen [!UICONTROL AND] Operator erstellt.

![](assets/visualrule.png)

Klicken **[!UICONTROL Code View]** Sie auf, um die Textversion dieser Regel abzurufen.

>[!TIP]
>
>Klicken **[!UICONTROL Validate Expression]** Sie auf, um Ihre Regellogik zu prüfen. Dadurch wird verhindert, dass Sie eine ungültige Regel hochladen.

![](assets/coderule.png)

Fügen Sie die Regel in das [!UICONTROL Bulk Management Tools] Arbeitsblatt ein und übernehmen Sie Ihre Änderungen, um die Segmentregeln stapelweise zu aktualisieren.

![](assets/segmentrule.png)

## Erstellen eigener Regeln {#create-rules}

Sie können eigene Regeln außerhalb [!UICONTROL Rule Builder]von erstellen. Bevor Sie beginnen, lesen Sie die Dokumentation, die sich auf Dinge wie Operatoren, Ausdruck und erforderliche Variablen bezieht. Wir empfehlen Ihnen Folgendes:

* [Arbeiten mit Vergleichsoperatoren im Eigenschaftenaufbau](../../features/traits/trait-comparison-operators.md)
* [Reihenfolge der Vorgänge](../../features/traits/trait-operator-precedence.md)
* [Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)
* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)


---
description: Die Arbeitsblätter zum Erstellen und Aktualisieren akzeptieren einen traitRule -Header, mit dem Sie mehrere Regeln in einem Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen durchzuführen.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Erstellen oder Aktualisieren von Eigenschaftsregeln und Segmentregeln
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 8%

---

# Erstellen oder Aktualisieren von Eigenschaftsregeln und Segmentregeln{#create-or-update-trait-rules-and-segment-rules}

Die Arbeitsblätter zum Erstellen und Aktualisieren akzeptieren einen traitRule -Header, mit dem Sie mehrere Regeln in einem Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen durchzuführen.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support durch die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) in der [!DNL Audience Manager] Die Benutzeroberfläche wird im Abschnitt [!UICONTROL Bulk Management Tools].

## Arbeiten mit Eigenschaftsregeln {#trait-rules}

In Ihrem Arbeitsblatt gibt die Spalte mit den Eigenschaftsregeln Regeln zurück und akzeptiert Regeln, die aus booleschen Ausdrücken, Vergleichsoperatoren und regulären Ausdrücken bestehen. Sie können Regeln mit Eigenschaften- oder Segment-Builder in [!DNL Audience Manager] und kopieren Sie sie in das Arbeitsblatt. Oder wenn Sie mit der Regelsyntax vertraut sind, können Sie Ausdrücke direkt in die Arbeitsblätter schreiben.

## Beispiel für Rule Builder {#rule-builder-example}

Sehen wir uns ein Beispiel an, das zeigt, wie [!UICONTROL Segment Builder] , um eine Regel zu erstellen, die Sie zum Bulk-Arbeitsblatt hinzufügen können. Dies ist jedoch keine schrittweise Anleitung für diese Tools. Stattdessen beginnen wir mit einer einfachen Regel, die bereits erstellt wurde. Anweisungen zur Verwendung der Regel-Builder finden Sie unter [Segment Builder](../../features/segments/segment-builder.md) und [Trait Builder](../../features/traits/about-trait-builder.md).

Mit dem visuellen Regel-Builder haben wir eine Segmentregel mit 3 Eigenschaften und einer booleschen [!UICONTROL AND] Operator.

![](assets/visualrule.png)

Klicks **[!UICONTROL Code View]** , um die Textversion dieser Regel zu erhalten.

>[!TIP]
>
>Klicks **[!UICONTROL Validate Expression]** , um Ihre Regellogik zu überprüfen. Dadurch wird verhindert, dass Sie eine ungültige Regel hochladen.

![](assets/coderule.png)

Fügen Sie die Regel in die [!UICONTROL Bulk Management Tools] Arbeitsblatt erstellen und Ihre Änderungen übernehmen, um Segmentregeln stapelweise zu aktualisieren.

![](assets/segmentrule.png)

## Erstellen eigener Regeln {#create-rules}

Sie können Ihre eigenen Regeln außerhalb von [!UICONTROL Rule Builder]. Bevor Sie beginnen, lesen Sie unbedingt die Dokumentation, die sich mit Operatoren, Ausdrücken und erforderlichen Variablen befasst. Es wird empfohlen, Folgendes zu überprüfen:

* [Arbeiten mit Vergleichsoperatoren in Trait Builder](../../features/traits/trait-comparison-operators.md)
* [Reihenfolge der Vorgänge](../../features/traits/trait-operator-precedence.md)
* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)
* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)

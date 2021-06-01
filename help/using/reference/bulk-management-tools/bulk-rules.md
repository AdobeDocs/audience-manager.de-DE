---
description: Die Arbeitsblätter zum Erstellen und Aktualisieren akzeptieren einen traitRule -Header, mit dem Sie mehrere Regeln in einem Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen durchzuführen.
seo-description: Die Arbeitsblätter zum Erstellen und Aktualisieren akzeptieren einen traitRule -Header, mit dem Sie mehrere Regeln in einem Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen durchzuführen.
seo-title: Erstellen oder Aktualisieren von Eigenschaftsregeln und Segmentregeln
solution: Audience Manager
title: Erstellen oder Aktualisieren von Eigenschaftsregeln und Segmentregeln
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 10%

---

# Erstellen oder Aktualisieren von Eigenschaftsregeln und Segmentregeln{#create-or-update-trait-rules-and-segment-rules}

Die Arbeitsblätter zum Erstellen und Aktualisieren akzeptieren einen traitRule -Header, mit dem Sie mehrere Regeln in einem Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen durchzuführen.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[In der ](../../features/administration/administration-overview.md) Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen werden in der berücksichtigt  [!DNL Audience Manager]   [!UICONTROL Bulk Management Tools].

## Arbeiten mit Eigenschaftsregeln {#trait-rules}

In Ihrem Arbeitsblatt gibt die Spalte mit den Eigenschaftsregeln Regeln zurück und akzeptiert Regeln, die aus booleschen Ausdrücken, Vergleichsoperatoren und regulären Ausdrücken bestehen. Sie können Regeln mit Eigenschaften- oder Segment-Builder in [!DNL Audience Manager] erstellen und sie in Ihr Arbeitsblatt kopieren. Oder wenn Sie mit der Regelsyntax vertraut sind, können Sie Ausdrücke direkt in die Arbeitsblätter schreiben.

## Beispiel für Rule Builder {#rule-builder-example}

Sehen wir uns ein Beispiel an, in dem gezeigt wird, wie [!UICONTROL Segment Builder] verwendet wird, um eine Regel zu erstellen, die Sie zum Massenarbeitsblatt hinzufügen können. Dies ist jedoch keine schrittweise Anleitung für diese Tools. Stattdessen beginnen wir mit einer einfachen Regel, die bereits erstellt wurde. Anweisungen zur Verwendung der Regel-Builder finden Sie unter [Segment Builder](../../features/segments/segment-builder.md) und [Trait Builder](../../features/traits/about-trait-builder.md).

Mit dem visuellen Regel-Builder haben wir eine Segmentregel mit 3 Eigenschaften und einem booleschen [!UICONTROL AND] -Operator erstellt.

![](assets/visualrule.png)

Klicken Sie auf **[!UICONTROL Code View]** , um die Textversion dieser Regel abzurufen.

>[!TIP]
>
>Klicken Sie auf **[!UICONTROL Validate Expression]** , um Ihre Regellogik zu überprüfen. Dadurch wird verhindert, dass Sie eine ungültige Regel hochladen.

![](assets/coderule.png)

Fügen Sie die Regel in das Arbeitsblatt [!UICONTROL Bulk Management Tools] ein und verpflichten Sie sich, Ihre Änderungen zu übernehmen, um Segmentregeln stapelweise zu aktualisieren.

![](assets/segmentrule.png)

## Erstellen eigener Regeln {#create-rules}

Sie können Ihre eigenen Regeln außerhalb von [!UICONTROL Rule Builder] schreiben. Bevor Sie beginnen, lesen Sie unbedingt die Dokumentation, die sich mit Operatoren, Ausdrücken und erforderlichen Variablen befasst. Es wird empfohlen, Folgendes zu überprüfen:

* [Arbeiten mit Vergleichsoperatoren in Trait Builder](../../features/traits/trait-comparison-operators.md)
* [Reihenfolge der Vorgänge](../../features/traits/trait-operator-precedence.md)
* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)
* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)

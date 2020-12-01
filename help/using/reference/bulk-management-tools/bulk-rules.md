---
description: Die Arbeitsblätter zum Erstellen und Aktualisieren akzeptieren einen Header der EigenschaftRegel, mit dem Sie mehrere Regeln in einem Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen durchzuführen.
seo-description: Die Arbeitsblätter zum Erstellen und Aktualisieren akzeptieren einen Header der EigenschaftRegel, mit dem Sie mehrere Regeln in einem Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen durchzuführen.
seo-title: Erstellen oder Aktualisieren von Eigenschaftsregeln und Segmentregeln
solution: Audience Manager
title: Erstellen oder Aktualisieren von Eigenschaftsregeln und Segmentregeln
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 10%

---


# Erstellen oder Aktualisieren von Eigenschaftsregeln und Segmentregeln{#create-or-update-trait-rules-and-segment-rules}

Die Arbeitsblätter zum Erstellen und Aktualisieren akzeptieren einen Header der EigenschaftRegel, mit dem Sie mehrere Regeln in einem Vorgang anwenden können. Befolgen Sie diese Anweisungen, um Massenregelanforderungen durchzuführen.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[In der ](../../features/administration/administration-overview.md) Benutzeroberfläche zugewiesene  [!DNL Audience Manager] RBAC-Gruppenberechtigungen werden berücksichtigt  [!UICONTROL Bulk Management Tools].

## Arbeiten mit Eigenschaftsregeln {#trait-rules}

In Ihrem Arbeitsblatt gibt die Spalte mit den Eigenschaftsregeln Regeln zurück, die aus booleschen Ausdrücken, Vergleichsoperatoren und regulären Ausdrücken bestehen, und akzeptiert diese. Sie können Regeln mit Eigenschaften oder Segmentaufbau in [!DNL Audience Manager] erstellen und sie in Ihr Arbeitsblatt kopieren. Wenn Sie mit der Regelsyntax vertraut sind, können Sie Ausdruck direkt in die Arbeitsblätter schreiben.

## Rule Builder-Beispiel {#rule-builder-example}

Sehen wir uns ein Beispiel an, das zeigt, wie [!UICONTROL Segment Builder] zum Erstellen einer Regel verwendet werden kann, die Sie zum Massenarbeitsblatt verwenden können. Es handelt sich jedoch nicht um eine Reihe von schrittweisen Anleitungen für diese Werkzeuge. Stattdessen werden wir mit einer einfachen Regel Beginn machen, die bereits erstellt wurde. Anweisungen zur Verwendung der Regelaufbau finden Sie unter [Segmentaufbau](../../features/segments/segment-builder.md) und [Eigenschaften-Aufbau](../../features/traits/about-trait-builder.md).

Mit dem visuellen Rule Builder haben wir eine Segmentregel mit 3 Eigenschaften und einem booleschen [!UICONTROL AND]-Operator erstellt.

![](assets/visualrule.png)

Klicken Sie auf **[!UICONTROL Code View]**, um die Textversion dieser Regel abzurufen.

>[!TIP]
>
>Klicken Sie auf **[!UICONTROL Validate Expression]**, um Ihre Regellogik zu überprüfen. Dadurch wird verhindert, dass Sie eine ungültige Regel hochladen.

![](assets/coderule.png)

Fügen Sie die Regel in das Arbeitsblatt [!UICONTROL Bulk Management Tools] ein und übernehmen Sie Ihre Änderungen, um Segmentregeln stapelweise zu aktualisieren.

![](assets/segmentrule.png)

## Erstellen eigener Regeln {#create-rules}

Sie können Ihre eigenen Regeln außerhalb von [!UICONTROL Rule Builder] schreiben. Lesen Sie vor dem Beginn unbedingt die Dokumentation zu Operatoren, Ausdrücken und erforderlichen Variablen. Es wird empfohlen, Folgendes zu überprüfen:

* [Arbeiten mit Vergleichsoperatoren im Eigenschaften-Aufbau](../../features/traits/trait-comparison-operators.md)
* [Reihenfolge der Vorgänge](../../features/traits/trait-operator-precedence.md)
* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)
* [Beispielausdrücke mit Booleschen und Vergleichsoperatoren](../../features/traits/trait-expression-samples.md)


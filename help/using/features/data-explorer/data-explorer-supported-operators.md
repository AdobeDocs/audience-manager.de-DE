---
description: Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.
seo-description: Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.
seo-title: Unterstützte logische Operatoren
title: Unterstützte logische Operatoren
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---


# Unterstützte logische Operatoren {#supported-logical-operators}

Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.

## Unterstützte Operatoren für die Signalsuche {#supported-operators-search}

Verwenden Sie die folgenden unterstützten logischen Operatoren, um nach Schlüssel/Wert-Paaren zu suchen:

### Vergleichsoperatoren

| Operator | Definition |
|---|---|
| **==** | Gleich |
| **>** | Größer als |
| **&lt;** | Kleiner als |
| **=>** | Größer als/gleich |
| **&lt;=** | Kleiner als/gleich |

### Benannte Operatoren

| Operator | Wertet [!DNL True] wann aus |
|---|---|
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* die von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *Beginn mit* den von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |

## Unterstützte Operatoren für die Aufstockung und Schätzung von Eigenschaften {#supported-operators-backfilling}

Sie können Eigenschaften aufstocken, die Ausdruck enthalten, die die von unterstützten Operatoren enthalten [!UICONTROL Signal Search]. Zusätzlich zu diesen Operatoren unterstützen Eigenschafts-Aufstockungen und Schätzungen auch die [!UICONTROL AND]-, [!UICONTROL OR]- und [!UICONTROL AND NOT] -logischen Operatoren, die zum Kombinieren von Schlüsselwertpaaren innerhalb der hinterfüllten Eigenschaftsvariablen verwendet werden.
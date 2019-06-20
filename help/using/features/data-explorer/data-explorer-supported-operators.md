---
description: Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.
seo-description: Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.
seo-title: Unterstützte logische Operatoren
title: Unterstützte logische Operatoren
uuid: 645 fcb 6 f -50 ac -49 bc -8 df 9-c 699 c 749 cf 8 f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Unterstützte logische Operatoren {#supported-logical-operators}

Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.

## Unterstützte Operatoren für die Signalsuche {#supported-operators-search}

Verwenden Sie die folgenden unterstützten logischen Operatoren, um nach Schlüssel/Wert-Paaren zu suchen:

### Vergleichsoperatoren

| Operator | Definition |
|---|---|
| **==** | Gleich |
| **&gt;** | Größer als |
| **&lt;** | Kleiner als |
| **=&gt;** | Größer als/gleich |
| **&lt;=** | Kleiner als/gleich |

### Benannte Operatoren

| Operator | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *beginnt mit* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |

## Unterstützte Operatoren für Trait-Aufstockung und Schätzung {#supported-operators-backfilling}

Sie können Eigenschaften aufstocken, die Ausdrücke enthalten, die eine der von [!UICONTROL Signal Search]Ihnen unterstützten Operatoren enthalten. Zusätzlich zu diesen Operatoren unterstützen die Aufstockung und Schätzung auch die [!UICONTROL AND]Operatoren und [!UICONTROL OR]und [!UICONTROL AND NOT] logische Operatoren, die zum Kombinieren von Schlüssel-Wert-Paaren innerhalb der backfill-Eigenschaftsausdrücke verwendet werden.
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
ht-degree: 9%

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

| Operator | Wertet für [!DNL True] Wenn aus |
|---|---|
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *Beginn mit* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |

## Unterstützte Operatoren für das Aufstocken von Eigenschaften und für die Schätzung {#supported-operators-backfilling}

Sie können Eigenschaften aufstocken, die Ausdruck enthalten, die die von [!UICONTROL Signal Search] unterstützten Operatoren enthalten. Zusätzlich zu diesen Operatoren unterstützen Eigenschafts-Aufstockungen und Schätzungen auch die logischen Operatoren [!UICONTROL AND], [!UICONTROL OR] und [!UICONTROL AND NOT], die zum Kombinieren von Schlüsselwertpaaren innerhalb der hinterfüllten Eigenschaftsvariablen verwendet werden.
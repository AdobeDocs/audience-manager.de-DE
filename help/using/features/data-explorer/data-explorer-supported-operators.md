---
description: Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.
seo-description: Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.
seo-title: Unterstützte logische Operatoren
title: Unterstützte logische Operatoren
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
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

| Operator | Wertet [!DNL True] wann aus |
|---|---|
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* die von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *beginnt mit* den von diesem Operator angegebenen Zeichen. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |

## Unterstützte Operatoren für die Aufstockung und Schätzung von Eigenschaften {#supported-operators-backfilling}

Sie können Eigenschaften, die Ausdrücke enthalten, die eine der von unterstützten Operatoren enthalten, aufstocken [!UICONTROL Signal Search]. Zusätzlich zu diesen Operatoren unterstützen Eigenschafts-Aufstockungen und Schätzungen auch die [!UICONTROL AND]-, [!UICONTROL OR]- und [!UICONTROL AND NOT] -logischen Operatoren, die zum Kombinieren von Schlüsselwertpaaren in den hinterfüllten Eigenschaftsausdrücken verwendet werden.
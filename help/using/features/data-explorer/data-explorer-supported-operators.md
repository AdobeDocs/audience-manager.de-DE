---
description: Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: Unterstützte logische Operatoren
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 4%

---

# Unterstützte logische Operatoren {#supported-logical-operators}

Verwenden Sie logische Operatoren, um Schlüssel-Wert-Paare und Aufstockungseigenschaften zu gruppieren.

## Unterstützte Operatoren für die Signalsuche {#supported-operators-search}

Verwenden Sie die folgenden unterstützten logischen Operatoren, um nach Schlüssel-Wert-Paaren zu suchen:

### Vergleichsoperatoren

| Benutzerin oder Benutzer | Definition |
|---|---|
| **==** | Gleich |
| **>** | Größer als |
| **&lt;** | Kleiner als |
| **=>** | Größer/gleich |
| **&lt;=** | Kleiner/gleich |

### Benannte Operatoren

| Benutzerin oder Benutzer | Wertet für [!DNL True] aus, wenn |
|---|---|
| **[!UICONTROL Contains]** | Der Wert in einem Schlüssel-Wert-Paar *enthält* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Startswith]** | Der Wert in einem Schlüssel-Wert-Paar *beginnt mit* Zeichen, die von diesem Operator angegeben werden. |
| **[!UICONTROL Endswith]** | Der Wert in einem Schlüssel-Wert-Paar *endet mit* den von diesem Operator angegebenen Zeichen. |

## Unterstützte Operatoren für Aufstockung und Schätzung von Eigenschaften {#supported-operators-backfilling}

Sie können Eigenschaften mit Ausdrücken aufstocken, die die von [!UICONTROL Signal Search] unterstützten Operatoren enthalten. Zusätzlich zu diesen Operatoren unterstützen die Aufstockung und Schätzung von Eigenschaften auch die logischen Operatoren [!UICONTROL AND], [!UICONTROL OR] und [!UICONTROL AND NOT], die zum Kombinieren von Schlüssel-Wert-Paaren innerhalb der aufgestockten Eigenschaftsausdrücke verwendet werden.

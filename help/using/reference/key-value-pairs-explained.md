---
description: Definiert und beschreibt Standard- und serialisierte Schlüssel/Wert-Paare.
keywords: integration code
seo-description: Definiert und beschreibt Standard- und serialisierte Schlüssel/Wert-Paare.
seo-title: Schlüssel-Wert-Paare – Erklärung
solution: Audience Manager
title: Schlüssel-Wert-Paare – Erklärung
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%

---

# Schlüssel-Wert-Paare – Erklärung{#key-value-pairs-explained}

Definiert und beschreibt Standard- und serialisierte Schlüssel/Wert-Paare.

<!-- 

c_key_value_explained.xml

 -->

Ein Schlüssel-Wert-Paar besteht aus zwei zugehörigen Datenelementen: Ein Schlüssel, bei dem es sich um eine Konstante handelt, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis), und ein Wert, bei dem es sich um eine Variable handelt, die zum Datensatz gehört (z. B. männlich/weiblich, grün, 100). Vollständig geformt könnte ein Schlüssel-Wert-Paar wie folgt aussehen:

* `gender = male`
* `color = green`
* `price > 100`

## Standard- und serialisierte Schlüsselwertpaare {#standard-serialized-pairs}

Ziele akzeptieren Schlüsselwertdaten im Format *`standard`* oder *`serialized`*. Die Standardformatierung ordnet Daten in separate Schlüssel/Wert-Paare an. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren. Bei der serialisierten Formatierung werden dagegen mehrere Werte zu einem Satz zusammengefasst, der durch einen einzigen Schlüssel definiert wird. Bei einem serialisierten Paar wird außerdem ein spezieller Indikator verwendet, um die Werte innerhalb des Schlüsselwertsatzes zu trennen. Schließlich können die standardmäßigen und serialisierten Schlüsselwerte einzelne oder mehrere Werte enthalten. Die folgende Tabelle enthält Beispiele für die Formate für Standard- und serielle Schlüsselwerte.

| Formatierung | Einzelner Schlüssel | Schlüsselwertpaare |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serialisiert** | `x=1;2` | `x=1;2&y=3;4` |



## Tasten, Trennzeichen und Trennzeichen {#keys-delimiters-separators}

Beim Arbeiten mit serialisierten Daten müssen Sie die Zeichen angeben, die die Werte *innerhalb* und *zwischen* und die Schlüssel-Wert-Paare trennen. Elemente in Schlüssel-Wert-Paaren werden wie folgt definiert:

* **Schlüssel:** Eine eindeutige Kennung im Schlüssel-Wert-Paar.
* **Wertetrennzeichen:** Trennt einzelne Schlüssel/Wert-Paare.
* **Trennzeichen für Schlüsselwerte:** Trennt einen Schlüssel von den Werten in einem Schlüssel-Wert-Paar.
* **Serielles Trennzeichen:** Trennt einzelne Werte innerhalb serialisierter Schlüssel/Wert-Paare.

## Standardelemente und serialisierte Schlüsselwertelemente {#standard-serialized-key-value-elements}


| Typ | Beispiel | Schlüssel | Trennzeichen für Schlüsselwerte | Trennzeichen für Schlüsselwerte | Serielle Trennlinie |
---------|----------|---------|---------|----------|---------
| **Einzelschlüssel**  (Standard) | `x=1&x=2` | `x` | `=` | `&` | Keine |
| **Schlüssel-Wert-Paare** (Standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | Keine |
| **Einzelschlüssel**  (seriell) | `x=1;2;3` | `x` | `=` | Keine | `;` |
| **Schlüsselwertpaare**  (seriell) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |

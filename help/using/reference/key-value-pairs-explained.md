---
description: Definiert und beschreibt standardmäßige und serialisierte Schlüssel-Wert-Paare.
keywords: integration code
seo-description: Definiert und beschreibt standardmäßige und serialisierte Schlüssel-Wert-Paare.
seo-title: Schlüssel-Wert-Paare – Erklärung
solution: Audience Manager
title: Schlüssel-Wert-Paare – Erklärung
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: 'Referenz '
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%

---

# Schlüssel-Wert-Paare – Erklärung{#key-value-pairs-explained}

Definiert und beschreibt standardmäßige und serialisierte Schlüssel-Wert-Paare.

<!-- 

c_key_value_explained.xml

 -->

Ein Schlüssel-Wert-Paar besteht aus zwei verwandten Datenelementen: Ein Schlüssel, der eine Konstante ist, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis), und ein Wert, der eine Variable ist, die zum Satz gehört (z. B. männlich/weiblich, grün, 100). Vollständig gebildet, könnte ein Schlüssel-Wert-Paar wie folgt aussehen:

* `gender = male`
* `color = green`
* `price > 100`

## Standardmäßige und serialisierte Schlüssel-Wert-Paare {#standard-serialized-pairs}

Ziele akzeptieren Schlüsselwertdaten im Format *`standard`* oder *`serialized`*. Die Standardformatierung organisiert Daten in separate Schlüssel-Wert-Paare. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren. Im Gegensatz dazu werden bei der serialisierten Formatierung mehrere Werte zu einem Satz zusammengefasst, der durch einen einzigen Schlüssel definiert wird. Außerdem wird in einem serialisierten Paar ein spezieller Indikator verwendet, um die Werte innerhalb des Schlüssel-Wert-Satzes zu trennen. Schließlich können standardmäßige und serialisierte Schlüsselwerte einzelne oder mehrere Werte enthalten. Die folgende Tabelle enthält Beispiele für standardmäßige und serielle Schlüsselwertformate.

| Formatierung | Einzelschlüssel | Schlüssel-Wert-Paare |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serialisiert** | `x=1;2` | `x=1;2&y=3;4` |



## Schlüssel, Trennzeichen und Trennzeichen {#keys-delimiters-separators}

Beim Arbeiten mit serialisierten Daten müssen Sie die Zeichen angeben, die die Werte *innerhalb* und *zwischen* und den Schlüssel-Wert-Paaren trennen. Elemente in Schlüssel-Wert-Paaren werden wie folgt definiert:

* **Schlüssel:** Eine eindeutige Kennung im Schlüssel-Wert-Paar.
* **Werttrennzeichen:** Trennt einzelne Schlüssel-Wert-Paare.
* **Schlüssel-Wert-Trennzeichen:**  Trennt einen Schlüssel von den Werten in einem Schlüssel-Wert-Paar.
* **Serielles Trennzeichen:** Trennt einzelne Werte in serialisierten Schlüssel-Wert-Paaren.

## Standardelemente und serialisierte Schlüsselwertelemente {#standard-serialized-key-value-elements}


| Typ | Beispiel | Schlüssel | Trennzeichen für Schlüsselwerte | Trennzeichen für Schlüsselwerte | Serielle Trennlinie |
|---------|----------|---------|---------|----------|---------|
| **Einzelschlüssel**  (Standard) | `x=1&x=2` | `x` | `=` | `&` | Keine |
| **Schlüssel-Wert-Paare**  (Standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | Keine |
| **Einzelschlüssel**  (seriell) | `x=1;2;3` | `x` | `=` | Keine | `;` |
| **Schlüssel-Wert-Paare**  (seriell) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |

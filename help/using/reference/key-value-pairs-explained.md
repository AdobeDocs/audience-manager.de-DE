---
description: Definiert und beschreibt standardmäßige und serialisierte Schlüssel-Wert-Paare.
keywords: Integrationscode
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: Erläuterung von Schlüssel-Wert-Paaren
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 3%

---

# Erläuterung von Schlüssel-Wert-Paaren{#key-value-pairs-explained}

Definiert und beschreibt standardmäßige und serialisierte Schlüssel-Wert-Paare.

<!-- 

c_key_value_explained.xml

 -->

Ein Schlüssel-Wert-Paar besteht aus zwei zusammenhängenden Datenelementen: einem Schlüssel, der eine Konstante ist, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis), und einem Wert, der eine Variable ist, die zum Satz gehört (z. B. männlich/weiblich, grün, 100). Ein vollständig geformtes Schlüssel-Wert-Paar könnte wie folgt aussehen:

* `gender = male`
* `color = green`
* `price > 100`

## Standard- und serialisierte Schlüssel-Wert-Paare {#standard-serialized-pairs}

Ziele akzeptieren Schlüssel-Wert-Daten im *`standard`*- oder *`serialized`*. Bei der Standardformatierung werden Daten in separate Schlüssel-Wert-Paare organisiert. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut zum Definieren eines anderen Werts verwendet wird. Im Gegensatz dazu werden bei der serialisierten Formatierung mehrere Werte zu einem Satz zusammengefasst, der durch einen einzigen Schlüssel definiert wird. Außerdem wird in einem serialisierten Paar ein spezieller Indikator verwendet, um die Werte innerhalb des Schlüssel-Wert-Satzes zu trennen. Schließlich können standardmäßige und serialisierte Schlüsselwerte einzelne oder mehrere Werte enthalten. Die folgende Tabelle enthält Beispiele für standardmäßige und serielle Schlüssel-Wert-Formate.

| Formatierung | Einzelschlüssel | Schlüssel-Wert-Paare |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **serialisiert** | `x=1;2` | `x=1;2&y=3;4` |



## Schlüssel, Trennzeichen und Trennzeichen {#keys-delimiters-separators}

Beim Arbeiten mit serialisierten Daten müssen Sie die Zeichen angeben, die die Werte *innerhalb* und *zwischen* den Schlüssel-Wert-Paaren trennen. Elemente in Schlüssel-Wert-Paaren werden wie folgt definiert:

* **Key:** Eine eindeutige Kennung im Schlüssel-Wert-Paar.
* **Werttrennzeichen:** Trennt einzelne Schlüssel-Wert-Paare.
* **Schlüssel-Wert-Trennzeichen:** Trennt einen Schlüssel von den Werten in einem Schlüssel-Wert-Paar.
* **Serielles Trennzeichen:** Trennt einzelne Werte innerhalb serialisierter Schlüssel-Wert-Paare.

## Standardmäßige und serialisierte Schlüssel-Wert-Elemente {#standard-serialized-key-value-elements}


| Typ | Beispiel | Schlüssel | Schlüssel-Wert-Trennzeichen | Schlüssel-Wert-Trennzeichen | Serientrennzeichen |
|---------|----------|---------|---------|----------|---------|
| **Einzelschlüssel** (Standard) | `x=1&x=2` | `x` | `=` | `&` | Keine |
| **Schlüssel-Wert-Paare** (Standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | Keine |
| **Einzel-Schlüssel** (seriell) | `x=1;2;3` | `x` | `=` | Keine | `;` |
| **Schlüssel-Wert-Paare** (seriell) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |

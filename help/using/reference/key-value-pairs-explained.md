---
description: Definiert und beschreibt Standard- und serialisierte Schlüssel/Wert-Paare.
keywords: integration code
seo-description: Definiert und beschreibt Standard- und serialisierte Schlüssel/Wert-Paare.
seo-title: Schlüssel-Wert-Paare – Erklärung
solution: Audience Manager
title: Schlüssel-Wert-Paare – Erklärung
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '280'
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

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Ziele akzeptieren Schlüsselwertdaten in *`standard`* oder *`serialized`* Format. Die Standardformatierung ordnet Daten in separate Schlüssel/Wert-Paare an. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren. Bei der serialisierten Formatierung werden dagegen mehrere Werte zu einem Satz zusammengefasst, der durch einen einzigen Schlüssel definiert wird. Bei einem serialisierten Paar wird außerdem ein spezieller Indikator verwendet, um die Werte innerhalb des Schlüsselwertsatzes zu trennen. Schließlich können die standardmäßigen und serialisierten Schlüsselwerte einzelne oder mehrere Werte enthalten. Die folgende Tabelle enthält Beispiele für die Formate für Standard- und serielle Schlüsselwerte.

| Formatierung | Einzelner Schlüssel | Schlüsselwertpaare |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serialisiert** | `x=1;2` | `x=1;2&y=3;4` |



## Tasten, Trennzeichen und Trennzeichen {#keys-delimiters-separators}

Beim Arbeiten mit serialisierten Daten müssen Sie die Zeichen angeben, die Werte *innerhalb* und *zwischen* den Schlüssel-Wert-Paaren trennen. Elemente in Schlüssel-Wert-Paaren werden wie folgt definiert:

* **Schlüssel:** Ein eindeutiger Bezeichner im Schlüssel-Wert-Paar.
* **Wertetrennzeichen:** Trennt einzelne Schlüssel/Wert-Paare.
* **Trennzeichen für Schlüsselwerte:** Trennt einen Schlüssel von den Werten in einem Schlüssel-Wert-Paar.
* **Serielles Trennzeichen:** Trennt einzelne Werte in serialisierten Schlüssel/Wert-Paaren.

## Standardelemente und serialisierte Schlüsselwertelemente {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Beispiel </th> 
   <th colname="col3" class="entry"> Schlüssel </th> 
   <th colname="col4" class="entry"> Trennzeichen für Schlüsselwerte </th> 
   <th colname="col5" class="entry"> Trennzeichen für Schlüsselwerte </th> 
   <th colname="col6" class="entry"> Serielle Trennlinie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Einzelner Schlüssel</b> <p>(Standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> Keine </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schlüsselwertpaare</b> <p>(Standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Einzelner Schlüssel</b> <p>(seriell) </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> Keine </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schlüsselwertpaare</b> (seriell) </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>


---
description: Definiert und beschreibt standardmäßige und serialisierte Schlüssel-Wert-Paare.
keywords: integration code
seo-description: Definiert und beschreibt standardmäßige und serialisierte Schlüssel-Wert-Paare.
seo-title: Wichtige Wertpaare
solution: Audience Manager
title: Wichtige Wertpaare
uuid: f 1435742-81 ca -4964-8370-accf 2 f 1 c 47 a 5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Key-Value Pairs Explained{#key-value-pairs-explained}

Definiert und beschreibt standardmäßige und serialisierte Schlüssel-Wert-Paare.

<!-- 

c_key_value_explained.xml

 -->

Ein Schlüssel-Wert-Paar besteht aus zwei zusammenhängenden Datenelementen: Ein Schlüssel, der eine Konstante für den Datensatz definiert (z. B. Geschlecht, Farbe, Preis) und einen Wert, der zu dem Satz gehört (z. B. männlich/weiblich, grün, grün, 100). In voller Form könnte ein Schlüssel-Wert-Paar wie folgt aussehen:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format. Die Standardformatierung gliedert Daten in separate Schlüssel-Wert-Paare. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren. Serialisierte Formatierung führt dagegen mehrere Werte zu einem Satz, der durch einen einzelnen Schlüssel definiert ist. Außerdem wird in einem serialisierten Paar ein Sonderindikator verwendet, um die Werte innerhalb des Schlüsselwertsatzes zu trennen. Schließlich können Standardmäßige und serialisierte Schlüsselwerte einzelne oder mehrere Werte enthalten. Die folgende Tabelle zeigt Beispiele für standardmäßige und serielle Schlüsselwertformate.

| Formatierung | Einzelschlüssel | Schlüssel-Wert-Paare |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serialisiert** | `x=1;2` | `x=1;2&y=3;4` |



## Keys, Delimiters, and Separators {#keys-delimiters-separators}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. Elemente in Schlüssel/Wert-Paaren sind wie folgt definiert:

* **Schlüssel:** Eine eindeutige Kennung im Schlüssel-Wert-Paar.
* **Trennzeichen:** Trennt einzelne Schlüssel/Wert-Paare.
* **Schlüsselwerttrennzeichen:** Trennt einen Schlüssel von den Werten in einem Schlüssel-Wert-Paar.
* **Reihentrennzeichen:** Trennt einzelne Werte innerhalb serialisierter Schlüssel-Wert-Paare.

## Standard and Serialized Key-Value Elements {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Beispiel </th> 
   <th colname="col3" class="entry"> Schlüssel </th> 
   <th colname="col4" class="entry"> Schlüsselwerttrennzeichen </th> 
   <th colname="col5" class="entry"> Schlüsselwerttrennzeichen </th> 
   <th colname="col6" class="entry"> Serieller Trennstrich </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Einzelner Schlüssel</b> <p>(Standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> Keine </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schlüssel-Wert-Paare</b> <p>(Standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Einzelner Schlüssel</b> <p>(serielle) </p> </td> 
   <td colname="col2"> <code> x = 1; 2; 3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> Keine </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Schlüssel-Wert-Paare</b> (serielle Werte) </td> 
   <td colname="col2"> <code> x = 1; 2 &amp; y = 3; 4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>


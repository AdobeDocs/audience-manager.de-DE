---
description: Eigenschaftsaufbau wertet Ausdrücke entsprechend der unten aufgeführten Reihenfolge aus, von oben nach unten. Trait-Elemente, die von Operatoren mit hoher Priorität definiert werden, werden zuerst ausgewertet, bevor andere Operatoren für den Prioritätspreis verwendet werden. Dieser Abschnitt ordnet jeden Operator nach Rangfolge von oben nach unten zu.
seo-description: Eigenschaftsaufbau wertet Ausdrücke entsprechend der unten aufgeführten Reihenfolge aus, von oben nach unten. Trait-Elemente, die von Operatoren mit hoher Priorität definiert werden, werden zuerst ausgewertet, bevor andere Operatoren für den Prioritätspreis verwendet werden. Dieser Abschnitt ordnet jeden Operator nach Rangfolge von oben nach unten zu.
seo-title: Reihenfolge der Vorgänge im Eigenschaftenaufbau
solution: Audience Manager
title: Reihenfolge der Vorgänge im Eigenschaftenaufbau
uuid: df 325047-af 62-45 ad -9 ca 1-046 bfcbe 5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Reihenfolge der Vorgänge im Eigenschaftenaufbau {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] auswählen ausdrücken nach der unten aufgeführten Reihenfolge der Vorgänge von oben nach unten. Trait-Elemente, die von Operatoren mit hoher Priorität definiert werden, werden zuerst ausgewertet, bevor andere Operatoren für den Prioritätspreis verwendet werden. Dieser Abschnitt ordnet jeden Operator nach Rangfolge von oben nach unten zu.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operatorpriorität </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> Kommentare </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Klammern </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Ausdrücke in Klammern werden immer zuerst ausgewertet und folgen der Rangfolge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vergleichsoperatoren </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Kleiner als, größer als, kleiner als/gleich, größer als/gleich. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gleichheitsoperatoren </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Gleich, wird jedoch nach den vorherigen Operatoren nicht gleich bewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolescher <span class="wintitle"> Wert UND</span> </td> 
   <td colname="col2"><span class="wintitle"> UND</span> </td> 
   <td colname="col3" morerows="1"> Keine </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolescher <span class="wintitle"> Wert ODER</span> </td> 
   <td colname="col2"><span class="wintitle"> ODER</span> </td> 
   <td colname="col3" morerows="1"> Keine </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Arbeiten mit Booleschen Ausdrücken (AND, OR, NOT) in traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Arbeiten mit Vergleichsoperatoren in traitbuilder](../../features/traits/trait-comparison-operators.md)


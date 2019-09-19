---
description: Eigenschaften-Aufbau bewertet Ausdrücke nach der Reihenfolge der unten aufgeführten Vorgänge, von hoher bis niedriger Priorität. Eigenschaftselemente, die von Operatoren mit hoher Priorität definiert werden, werden zuerst bewertet, bevor andere Vorrangoperatoren verwendet werden. In diesem Abschnitt werden die Operatoren nach Priorität geordnet, von hoch bis niedrig.
seo-description: Eigenschaften-Aufbau bewertet Ausdrücke nach der Reihenfolge der unten aufgeführten Vorgänge, von hoher bis niedriger Priorität. Eigenschaftselemente, die von Operatoren mit hoher Priorität definiert werden, werden zuerst bewertet, bevor andere Vorrangoperatoren verwendet werden. In diesem Abschnitt werden die Operatoren nach Priorität geordnet, von hoch bis niedrig.
seo-title: Reihenfolge der Vorgänge im Eigenschaften-Aufbau
solution: Audience Manager
title: Reihenfolge der Vorgänge im Eigenschaften-Aufbau
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Reihenfolge der Vorgänge im Eigenschaften-Aufbau {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] Ausdrücke werden entsprechend der Reihenfolge der unten aufgeführten Vorgänge ausgewertet, von der höchsten bis zur niedrigsten Priorität. Eigenschaftselemente, die von Operatoren mit hoher Priorität definiert werden, werden zuerst bewertet, bevor andere Vorrangoperatoren verwendet werden. In diesem Abschnitt werden die Operatoren nach Priorität geordnet, von hoch bis niedrig.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Priorität des Operators </th> 
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
   <td colname="col3"> Kleiner als, größer als, kleiner als/gleich, größer als/gleich werden als Nächstes ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gleichstellungsoperatoren </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Equal to, not equal to werden nach den vorherigen Operatoren ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolesche <span class="wintitle"> UND</span> </td> 
   <td colname="col2"><span class="wintitle"> UND</span> </td> 
   <td colname="col3" morerows="1"> Keine </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolesche <span class="wintitle"> ODER</span> </td> 
   <td colname="col2"><span class="wintitle"> ODER</span> </td> 
   <td colname="col3" morerows="1"> Keine </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [Arbeiten mit booleschen Ausdrücken (AND, OR, NOT) in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Arbeiten mit Vergleichsoperatoren in TraitBuilder](../../features/traits/trait-comparison-operators.md)


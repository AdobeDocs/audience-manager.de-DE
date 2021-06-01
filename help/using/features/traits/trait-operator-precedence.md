---
description: Trait Builder wertet Ausdrücke anhand der unten aufgeführten Vorgangsreihenfolge aus, von hoher bis niedriger Priorität. Eigenschaftselemente, die von Operatoren mit hoher Priorität definiert werden, werden zuerst ausgewertet, bevor andere Vorrangoperatoren verwendet werden. In diesem Abschnitt werden die einzelnen Operatoren nach Priorität (von oben nach unten) geordnet.
seo-description: Trait Builder wertet Ausdrücke anhand der unten aufgeführten Vorgangsreihenfolge aus, von hoher bis niedriger Priorität. Eigenschaftselemente, die von Operatoren mit hoher Priorität definiert werden, werden zuerst ausgewertet, bevor andere Vorrangoperatoren verwendet werden. In diesem Abschnitt werden die einzelnen Operatoren nach Priorität (von oben nach unten) geordnet.
seo-title: Reihenfolge der Vorgänge in Trait Builder
solution: Audience Manager
title: Reihenfolge der Vorgänge in Trait Builder
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: 'Eigenschaften '
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 13%

---

# Reihenfolge der Vorgänge in Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] wertet Ausdrücke gemäß der unten aufgeführten Reihenfolge der Vorgänge aus, von hoher bis niedriger Priorität. Eigenschaftselemente, die von Operatoren mit hoher Priorität definiert werden, werden zuerst ausgewertet, bevor andere Vorrangoperatoren verwendet werden. In diesem Abschnitt werden die einzelnen Operatoren nach Priorität (von oben nach unten) geordnet.

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
   <td colname="col1"> Klammer </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Ausdrücke in Klammern werden immer zuerst ausgewertet und folgen der Rangfolge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vergleichsoperatoren </td> 
   <td colname="col2"> &lt;&gt; &lt;&gt;= </td> 
   <td colname="col3"> Kleiner, größer als, kleiner gleich, größer als/gleich, größer/gleich werden als Nächstes ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gleichstellungsoperatoren </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Gleich, ungleich gleich werden nach den vorherigen Operatoren ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolesch <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> UND</span> </td> 
   <td colname="col3" morerows="1"> Keine </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolesch <span class="wintitle"> ODER</span> </td> 
   <td colname="col2"><span class="wintitle"> ODER</span> </td> 
   <td colname="col3" morerows="1"> Keine </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Arbeiten mit booleschen Ausdrücken (AND, OR, NOT) in TraitBuilder](../../reference/boolean-expressions-tsb.md)
* [Arbeiten mit Vergleichsoperatoren in TraitBuilder](../../features/traits/trait-comparison-operators.md)


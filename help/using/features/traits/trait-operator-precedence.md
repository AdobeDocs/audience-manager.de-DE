---
description: Der Trait Builder bewertet Ausdrücke anhand der unten aufgeführten Reihenfolge von Vorgängen mit hoher bis niedriger Priorität. Von Operatoren mit hoher Priorität definierte Eigenschaftenelemente werden zuerst ausgewertet, bevor andere Operatoren mit hoher Priorität verwendet werden. In diesem Abschnitt werden die einzelnen Operatoren nach ihrer Priorität geordnet, von hoch bis niedrig.
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: Reihenfolge der Vorgänge in Trait Builder
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
TQID: https://experienceleague.adobe.com/Jfmytv1c-4Uc8q2UGVU5Lgx-iOZ-yk2sSzc8iRviBAs
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 161
ht-degree: 3%

---

# Reihenfolge der Vorgänge in Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] bewertet Ausdrücke entsprechend der unten aufgeführten Reihenfolge der Vorgänge von der höchsten zur niedrigsten Priorität. Von Operatoren mit hoher Priorität definierte Eigenschaftenelemente werden zuerst ausgewertet, bevor andere Operatoren mit hoher Priorität verwendet werden. In diesem Abschnitt werden die einzelnen Operatoren nach ihrer Priorität geordnet, von hoch bis niedrig.

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
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Kleiner als, größer als, kleiner/gleich, größer/gleich werden als Nächstes ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gleichheitsoperatoren </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Gleich, ungleich werden nach den vorherigen Operatoren ausgewertet. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolescher <span class="wintitle"> UND</span> </td> 
   <td colname="col2"><span class="wintitle"> UND</span> </td> 
   <td colname="col3" morerows="1"> Keine </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolesches <span class="wintitle"> ODER</span> </td> 
   <td colname="col2"><span class="wintitle"> ODER</span> </td> 
   <td colname="col3" morerows="1"> Keine </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Arbeiten mit booleschen Ausdrücken (AND, OR, NOT) in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Arbeiten mit Vergleichsoperatoren in TraitBuilder](../../features/traits/trait-comparison-operators.md)

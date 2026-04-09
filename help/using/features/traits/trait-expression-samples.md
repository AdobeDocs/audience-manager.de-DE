---
description: Beispiele zum Erstellen von Ausdrücken im Code-Editor von Expression Builder.
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: Beispielausdrücke mit booleschen und Vergleichsoperatoren
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
TQID: https://experienceleague.adobe.com/mVpbP-ob3VclgLEBQWtI4zxthppaf5j7L8DPKBjF9Wo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 193
ht-degree: 3%

---

# Beispielausdrücke mit booleschen und Vergleichsoperatoren {#sample-expressions-with-boolean-and-comparison-operators}

Beispiele zum Erstellen von Ausdrücken im [!UICONTROL Expression Builder]-Code-Editor.

## Übersicht über Codebeispiele {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Erstellen Sie Ihre eigenen Eigenschaftsregeln mit dem [!UICONTROL Expression Builder] Code-Editor. Die folgenden Beispiele helfen Ihnen bei den ersten Schritten. Einige der Beispiele stellen der *`key`*-Variablen `c_` voran, um sie als benutzerdefinierte Variable zu identifizieren. Schließen Sie das `c_` (oder eine andere Namenskonvention) für *`key`* Variable ein, wenn Ihre Ereignisaufrufe Daten an [!DNL Audience Manager] senden, die diese Syntax verwenden.

## Boolesche Ausdrücke {#boolean-expressions}

### UND-Beispiel

Die Regel stellt Anforderungen an die Eigenschaftsqualifizierung mithilfe von booleschen [!UICONTROL AND]-Operatoren fest.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispielcode </th> 
   <th colname="col2" class="entry"> Um sich zu qualifizieren, muss ein Besucher </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Suchen Sie nach einer bestimmten Marke und einem bestimmten Modell. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Suchen des Produkts auf einer Suchergebnisseite (Suche = „1“ oder „true„). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### ODER-Beispiel

Diese Regel legt Anforderungen an die Eigenschaftsqualifizierung mithilfe von [!DNL Boolean]-[!UICONTROL OR] und [!UICONTROL AND] fest.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispielcode </th> 
   <th colname="col2" class="entry"> Um sich zu qualifizieren, muss ein Besucher </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> Sie erfüllen die von den Variablen <code><i>a </i></code> oder <code><i>b </i></code> und <code><i>c </i></code> festgelegten Bedingungen. </td> 
  </tr> 
 </tbody> 
</table>

## Bereichsbeispiel mit „größer als“, „kleiner als“, „gleich“

Diese Regel legt Anforderungen für die Eigenschaftsqualifizierung anhand eines Bereichs fest.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispielcode </th> 
   <th colname="col2" class="entry"> Um sich zu qualifizieren, muss ein Besucher </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> Erfüllen Sie alle Preisbedingungen zwischen 1.00 und 100.00. </td> 
  </tr> 
 </tbody> 
</table>

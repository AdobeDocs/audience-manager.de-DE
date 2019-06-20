---
description: Beispiele für die Erstellung von Ausdrücken im Expression Builder-Codeeditor.
seo-description: Beispiele für die Erstellung von Ausdrücken im Expression Builder-Codeeditor.
seo-title: Beispielausdrücke mit Booleschen und Vergleichsoperatoren
solution: Audience Manager
title: Beispielausdrücke mit Booleschen und Vergleichsoperatoren
uuid: ee 74 c 376-2099-4816-8694-43 f 58845 a 0 ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# Beispielausdrücke mit Booleschen und Vergleichsoperatoren {#sample-expressions-with-boolean-and-comparison-operators}

Beispiele für die Erstellung von Ausdrücken im [!UICONTROL Expression Builder] Code-Editor.

## Übersicht über Codebeispiele {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Erstellen Sie Ihre eigenen Eigenschaftsregeln mit dem [!UICONTROL Expression Builder] Code-Editor. Die folgenden Beispiele helfen Ihnen beim Einstieg. Einige der Beispiele enthalten die *`key`* Variable, mit `c_` der sie als benutzerdefinierte Variable identifiziert wird. Fügen Sie das `c_` Präfix (oder eine andere Benennungsregel) für *`key`* die Variable ein, wenn Ihre Ereignisaufrufe Daten an [!DNL Audience Manager] die Verwendung dieser Syntax senden.

## Boolesche Ausdrücke {#boolean-expressions}

### UND-Beispiel

Die Regel legt Eigenschaften für die Eigenschaftenberechtigung mithilfe von booleschen [!UICONTROL AND] Operatoren fest.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispielcode </th> 
   <th colname="col2" class="entry"> Zur Qualifizierung muss ein Besucher </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_ make = = "A") AND (c_ model = = "B") AND (c_ search = = "1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Suchen Sie nach einer spezifischen Fabrikation und einem bestimmten Modell. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Suchen Sie das Produkt von einer Suchergebnisseite (search = "1" oder "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### ODER-Beispiel

Diese Regel legt die Voraussetzungen für die Qualifizierung von Eigenschaften mit und [!DNL Boolean][!UICONTROL OR][!UICONTROL AND] Operatoren fest.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispielcode </th> 
   <th colname="col2" class="entry"> Zur Qualifizierung muss ein Besucher </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a = = "1" OR b = = "1") AND (c = = "new")</code> </td> 
   <td colname="col2"> Erfüllen Sie die Bedingungen von Variablen <code><i>a </i></code> oder <code><i>b </i></code> und <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Bereichsbeispiel mit Größer als, Kleiner als, Gleich

Diese Regel legt die Voraussetzungen für die Qualifizierung von Eigenschaften mithilfe eines Bereichs fest.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispielcode </th> 
   <th colname="col2" class="entry"> Zur Qualifizierung muss ein Besucher </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(Preis &gt; = 1,00 AND Price &lt; = 100,00)</code> </td> 
   <td colname="col2"> Erfüllen Sie eine beliebige Preisbedingung zwischen 1,00 und 100,00. </td> 
  </tr> 
 </tbody> 
</table>
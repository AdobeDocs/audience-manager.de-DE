---
description: Beispiele für das Erstellen von Ausdrücken im Code-Editor von Expression Builder.
seo-description: Beispiele für das Erstellen von Ausdrücken im Code-Editor von Expression Builder.
seo-title: Beispielausdrücke mit booleschen Operatoren und Vergleichsoperatoren
solution: Audience Manager
title: Beispielausdrücke mit booleschen Operatoren und Vergleichsoperatoren
uuid: ee74c376-2099-4816-8694-43f58845a0ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# Beispielausdrücke mit booleschen Operatoren und Vergleichsoperatoren {#sample-expressions-with-boolean-and-comparison-operators}

Beispiele für das Erstellen von Ausdrücken im [!UICONTROL Expression Builder] Code-Editor.

## Übersicht über Codebeispiele {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Erstellen Sie mit dem [!UICONTROL Expression Builder] Code-Editor eigene Eigenschaftsregeln. Die folgenden Beispiele helfen Ihnen beim Einstieg. In einigen Beispielen wird der *`key`* `c_` Variablen der Vorwand gegeben, um sie als benutzerdefinierte Variable zu identifizieren. Schließen Sie das `c_` Präfix (oder eine andere Benennungsregel) für die *`key`* Variable ein, wenn Ihre Ereignisaufrufe Daten an die [!DNL Audience Manager] Verwendung dieser Syntax senden.

## Boolesche Ausdrücke {#boolean-expressions}

### UND Beispiel

Die Regel stellt Anforderungen an die Eigenschaftsqualifikation mit booleschen [!UICONTROL AND] Operatoren fest.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispielcode </th> 
   <th colname="col2" class="entry"> Zur Qualifizierung muss ein Besucher </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make="A") AND (c_model="B") AND (c_search="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Suchen Sie nach einer bestimmten Marke und einem bestimmten Modell. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Suchen Sie das Produkt auf einer Suchergebnisseite (suchen = "1"oder "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### ODER-Beispiel

Diese Regel legt Anforderungen an die Eigenschaftsqualifikation mit [!DNL Boolean] und [!UICONTROL OR] [!UICONTROL AND] Operatoren fest.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispielcode </th> 
   <th colname="col2" class="entry"> Zur Qualifizierung muss ein Besucher </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a= "1" OR b="1") AND (c="neu")</code> </td> 
   <td colname="col2"> Erfüllen Sie die durch Variablen <code><i>a </i></code> oder <code><i>b </i></code> und <code><i>c festgelegten Bedingungen </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Bereichsbeispiel mit Größer als, Kleiner als, gleich

Diese Regel legt Anforderungen an die Eigenschaftsqualifikation anhand eines Bereichs fest.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispielcode </th> 
   <th colname="col2" class="entry"> Zur Qualifizierung muss ein Besucher </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(Preis &gt;= 1,00 UND Preis &lt;= 100,00)</code> </td> 
   <td colname="col2"> Erfüllen Sie alle Preisbedingungen zwischen 1.00 und 10.00 Uhr. </td> 
  </tr> 
 </tbody> 
</table>
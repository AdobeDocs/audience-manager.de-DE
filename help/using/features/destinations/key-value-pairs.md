---
description: A [!DNL key-value pair] besteht aus verwandten Elementen. Ein Schlüssel, bei dem es sich um eine Konstante handelt, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis), und ein Wert, bei dem es sich um eine Variable handelt, die zum Datensatz gehört (z. B. männlich/weiblich, grün, 100). Der Destination Builder sendet Daten, die als Schlüssel/Wert-Paare formatiert sind.
solution: Audience Manager
title: Standard und Serial [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Zielgrundlagen
exl-id: b37c829b-66be-4c31-8198-bc032371279e
translation-type: tm+mt
source-git-commit: f9f5cb5f83f095ad8cac01447ef0c360f0acd5fc
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 2%

---

# Standardmäßige und serialisierte Schlüssel-Wert-Paare {#standard-and-serial-key-value-pairs}

Ein Schlüssel-Wert-Paar besteht aus verwandten Elementen: Ein Schlüssel, bei dem es sich um eine Konstante handelt, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis), und ein Wert, bei dem es sich um eine Variable handelt, die zum Datensatz gehört (z. B. männlich/weiblich, grün, 100). [!UICONTROL Destination Builder] sendet Daten, die als Schlüssel-Wert-Paare formatiert sind.

## Basis-Schlüsselwertpaare {#basic-key-value-pairs}

Voll geformt könnte ein einfacher Satz Schlüssel-Wert-Paars wie folgt aussehen:

* `gender = male`
* `color = green`
* `price > 100`

## Standardmäßige und serialisierte Schlüssel-Wert-Paare {#standard-serial-key-value-pairs}

Ziele akzeptieren Schlüsselwertdaten im Format *`standard`* oder *`serialized`*.

* **Standard-Schlüssel-Wert-Paare:** Formatiert die Zieldaten in separate Schlüssel-Wert-Paare. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren.
* **Serialisierte Schlüssel-Wert-Paare:** Verfasst mehrere Werte in einem Schlüssel-Wert-Paar. In einem serialisierten Schlüssel-Wert-Paar trennt ein spezieller Indikator die Werte innerhalb des Schlüssel-Wert-Satzes.

Sowohl Standard- als auch serialisierte Schlüsselwerte können einzelne oder mehrere Werte enthalten. Die folgende Tabelle enthält Beispiele für die Formate für Standard- und serielle Schlüsselwerte.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formatierung </th>
   <th colname="col2" class="entry"> Einzelne Schlüsselwertpaare </th>
   <th colname="col3" class="entry"> Mehrere Schlüssel/Wert-Paare </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standard</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Serialisiert</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Trennzeichen und Trennzeichen {#delimiters-separators}

Die Zeichen, die Werte innerhalb und zwischen Schlüsseln und Werten trennen, werden als *`delimiters`* und *`separators`* bezeichnet. Diese werden besonders dann wichtig, wenn Sie Segmente in einem seriellen Format an ein Ziel senden. Mit der Serialisierung können Sie mehrere Werte mit einem Schlüssel übergeben und Schlüssel/Wert-Paare kombinieren. Trennzeichen und Trennzeichen werden wie folgt definiert:

* **Trennzeichen für Schlüsselwerte:** Trennt einen Schlüssel und einen Wert in einem Schlüssel/Wert-Paar.
* **Trennzeichen für Schlüsselwerte:** Trennt Sätze von Schlüssel/Wert-Paaren.
* **Serielles Trennzeichen:** Trennt mehrere Werte innerhalb von Sätzen von serialisierten Schlüssel/Wert-Paaren.

## Beispiele {#examples}

Mit [!UICONTROL Destination Builder] können Sie Schlüsselwertdaten auf verschiedene Weise formatieren. Schauen wir uns einige Beispiele für jeden Typ an.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispiele für Schlüsselwertpaare </th> 
   <th colname="col2" class="entry"> Beispiel </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standard-Einzelschlüssel</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Ein einfacher Satz Schlüssel-Wert-Paare. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Schlüssel: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Werte: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Trennzeichen: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Trennzeichen für Schlüsselwerte: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mehrere Schlüssel/Wert-Paare</b>  (nicht seriell) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Eine Reihe von mehreren Schlüssel/Wert-Paaren, die Werte mit separaten Schlüssel/Wert-Sets übergeben. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Schlüssel: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Werte: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Trennzeichen: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Trennzeichen für Schlüsselwerte: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Serieller Einzelschlüssel</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>Ein Schlüsselwertsatz, der mehrere Werte mit einem Schlüssel übergibt. Da dieser Schlüssel mehrere Werte hat, wird er als serialisiertes Schlüssel-Wert-Paar bezeichnet. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Schlüssel: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Werte: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Trennzeichen: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Serielles Trennzeichen: Semikolon </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mehrere Schlüssel/Wert-Paare</b>  (seriell) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>Eine Reihe von mehreren Schlüssel/Wert-Paaren, die mehrere Werte auf separaten Schlüsseln übergeben. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Schlüssel: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Werte: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Trennzeichen: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Trennzeichen: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Serielles Trennzeichen: Semikolon </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Ziel-Serialisierung {#destination-serialized}

Ein serialisiertes Ziel kombiniert mehrere Eigenschaften in einer einzigen Zeichenfolge und sendet diese Informationen an ein Ziel.

<!-- c_dest_serialized.xml -->

Die serialisierte Datenübertragung hilft, die Effizienz zu verbessern, da mehrere Eigenschaften nacheinander und nicht parallel ausgelöst werden. Dadurch erhält der Zielserver genügend Zeit, um Daten zu empfangen, zu verarbeiten und zurückzugeben, bevor er auf zusätzliche Anforderungen reagiert.

### Unterstützte Ziele

In [!DNL Audience Manager] können Sie Daten serialisieren und an nahezu jedes Ziel senden, mit dem Sie arbeiten möchten. Bevor Sie diese Funktion verwenden, müssen Sie jedoch das Ziel [!DNL URL] kennen und wissen, wo Sie einige erforderliche oder optionale Makros platzieren können. Informationen zur Makroplatzierung erhalten Sie von Ihrem Zielpartner. Weitere Informationen finden Sie unter [Definierte Zielmakros](../../features/destinations/destination-macros.md#destination-macros-defined).

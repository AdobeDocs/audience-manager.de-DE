---
description: A [!DNL key-value pair] besteht aus [!DNL related elements]. Ein Schlüssel, der eine Konstante ist, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis), und ein Wert, der eine Variable ist, die zum Satz gehört (z. B. männlich/weiblich, grün, 100). Destination Builder sendet Daten, die als Schlüssel-Wert-Paare formatiert sind.
solution: Audience Manager
title: Standard und Serial [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Zielgrundlagen
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 2%

---

# Standardmäßige und serialisierte Schlüssel-Wert-Paare {#standard-and-serial-key-value-pairs}

Ein Schlüssel-Wert-Paar besteht aus verwandten Elementen: Ein Schlüssel, der eine Konstante ist, die den Datensatz definiert (z. B.: Geschlecht, Farbe, Preis) und ein Wert, der eine Variable ist, die zum Satz gehört (z. B. männlich/weiblich, grün, 100). [!UICONTROL Destination Builder] sendet Daten, die als Schlüssel-Wert-Paare formatiert sind.

## Grundlegende Schlüssel-Wert-Paare {#basic-key-value-pairs}

Vollständig gebildet, könnte ein einfacher Satz von Schlüssel-Wert-Paaren wie folgt aussehen:

* `gender = male`
* `color = green`
* `price > 100`

## Standardmäßige und serialisierte Schlüssel-Wert-Paare {#standard-serial-key-value-pairs}

Ziele akzeptieren Schlüsselwertdaten im Format *`standard`* oder *`serialized`*.

* **Standardmäßige Schlüssel-Wert-Paare:**  Formatiert Zieldaten in separate Schlüssel-Wert-Paare. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren.
* **Serialisierte Schlüssel-Wert-Paare:** Zusammenfasst mehrere Werte in einem einzelnen Schlüssel-Wert-Paar. In einem serialisierten Schlüssel-Wert-Paar trennt ein spezieller Indikator die Werte innerhalb des Schlüssel-Wert-Satzes.

Sowohl standardmäßige als auch serialisierte Schlüsselwerte können einzelne oder mehrere Werte enthalten. Die folgende Tabelle enthält Beispiele für standardmäßige und serielle Schlüsselwertformate.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formatierung </th>
   <th colname="col2" class="entry"> Einzelne Schlüssel-Wert-Paare </th>
   <th colname="col3" class="entry"> Mehrere Schlüssel-Wert-Paare </th>
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

Die Zeichen, die Werte innerhalb von und zwischen Schlüsseln und Werten trennen, werden als *`delimiters`* und *`separators`* bezeichnet. Diese sind besonders wichtig, wenn Sie Segmente in einem seriellen Format an ein Ziel senden. Mit der Serialisierung können Sie mehrere Werte mit einem Schlüssel übergeben und Schlüssel-Wert-Paare kombinieren. Trennzeichen und Trennzeichen werden wie folgt definiert:

* **Schlüssel-Wert-Trennzeichen:**  Trennt einen Schlüssel und einen Wert in einem Schlüssel-Wert-Paar.
* **Trennzeichen für Schlüssel-Wert:** Trennt Sätze von Schlüssel-Wert-Paaren.
* **Serielles Trennzeichen:** Trennt mehrere Werte in Sets von serialisierten Schlüssel-Wert-Paaren.

## Beispiele {#examples}

Mit [!UICONTROL Destination Builder] können Sie Schlüssel-Wert-Daten auf verschiedene Arten formatieren. Sehen wir uns einige Beispiele für jeden Typ an.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beispiele für Schlüssel-Wert-Paare </th> 
   <th colname="col2" class="entry"> Beispiel </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standard-Einzelschlüssel</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Ein einfacher Satz von Schlüssel-Wert-Paaren. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Schlüssel: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Werte: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Trennzeichen: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Trennzeichen für Schlüsselwerte: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mehrere Schlüssel-Wert-Paare</b>  (nicht seriell) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Ein Satz aus mehreren Schlüssel-Wert-Paaren, die Werte mit separaten Schlüssel-Wert-Sets übergeben. Das Beispiel enthält folgende Elemente: </p> 
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
   <td colname="col3"> <p>Ein Schlüssel-Wert-Satz, der mehrere Werte mit einem Schlüssel übergibt. Da dieser Schlüssel mehrere Werte aufweist, wird er als serialisiertes Schlüssel-Wert-Paar bezeichnet. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Schlüssel: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Werte: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Trennzeichen: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Serielles Trennzeichen: Semikolon </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mehrere Schlüssel-Wert-Paare</b>  (seriell) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>Ein Satz mehrerer Schlüssel-Wert-Paare, die mehrere Werte in separaten Schlüsseln übergeben. Das Beispiel enthält folgende Elemente: </p> 
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

Ein serialisiertes Ziel kombiniert mehrere Eigenschaften in einer Zeichenfolge und sendet diese Informationen an ein Ziel.

<!-- c_dest_serialized.xml -->

Die serialisierte Datenübertragung trägt zur Verbesserung der Effizienz bei, da mehrere Eigenschaften nacheinander statt parallel ausgelöst werden. Dadurch erhält der Zielserver ausreichend Zeit, Daten zu empfangen, zu verarbeiten und zurückzugeben, bevor er auf zusätzliche Anfragen reagiert.

### Unterstützte Ziele

In [!DNL Audience Manager] können Sie Daten serialisieren und an nahezu jedes Ziel senden, mit dem Sie arbeiten möchten. Bevor Sie diese Funktion verwenden, müssen Sie jedoch das Ziel [!DNL URL] kennen und wissen, wo Sie einige erforderliche oder optionale Makros platzieren können. Rufen Sie die Informationen zur Makroplatzierung von Ihrem Zielpartner ab. Weitere Informationen finden Sie unter [Definierte Zielmakros](../../features/destinations/destination-macros.md#destination-macros-defined) .

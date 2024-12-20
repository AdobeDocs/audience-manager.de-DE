---
description: A [!DNL key-value pair] besteht aus [!DNL related elements]. Ein Schlüssel, bei dem es sich um eine Konstante handelt, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis), und einen Wert, der zu dem Satz gehört (z. B. männlich/weiblich, grün, 100). Destination Builder sendet Daten, die als Schlüssel-Wert-Paare formatiert sind.
solution: Audience Manager
title: Standard und seriell [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Standard- und serielle Schlüssel-Wert-Paare {#standard-and-serial-key-value-pairs}

Ein Schlüssel-Wert-Paar besteht aus verwandten Elementen: einem Schlüssel, der eine Konstante ist, die den Datensatz definiert (z. B.: Geschlecht, Farbe, Preis), und einem Wert, der eine Variable ist, die zum Satz gehört (z. B. männlich/weiblich, grün, 100). [!UICONTROL Destination Builder] sendet Daten formatiert als Schlüssel-Wert-Paare.

## Grundlegende Schlüssel-Wert-Paare {#basic-key-value-pairs}

Vollständig geformt könnte ein einfacher Satz von Schlüssel-Wert-Paaren wie folgt aussehen:

* `gender = male`
* `color = green`
* `price > 100`

## Standard- und serielle Schlüssel-Wert-Paare {#standard-serial-key-value-pairs}

Ziele akzeptieren Schlüssel-Wert-Daten im *`standard`*- oder *`serialized`*.

* **Standard-Schlüssel-Wert-Paare:** Formatiert Zieldaten in separate Schlüssel-Wert-Paare. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut zum Definieren eines anderen Werts verwendet wird.
* **Serialisierte Schlüssel-Wert-Paare:** Fasst mehrere Werte zu einem einzigen Schlüssel-Wert-Paar zusammen. In einem serialisierten Schlüssel-Wert-Paar trennt ein spezieller Indikator die Werte innerhalb des Schlüssel-Wert-Satzes.

Sowohl standardmäßige als auch serialisierte Schlüsselwerte können einzelne oder mehrere Werte enthalten. Die folgende Tabelle enthält Beispiele für standardmäßige und serielle Schlüssel-Wert-Formate.

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
   <td colname="col1"> <p> <b>serialisiert</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Trennzeichen und Trennzeichen {#delimiters-separators}

Die Zeichen, die Werte innerhalb und zwischen Schlüsseln und Werten trennen, werden als *`delimiters`* und *`separators`* bezeichnet. Diese sind besonders wichtig, wenn Sie Segmente in einem seriellen Format an ein Ziel senden. Mit der Serialisierung können Sie mehrere Werte mit einem einzigen Schlüssel übergeben und Schlüssel-Wert-Paare kombinieren. Trennzeichen und Trennzeichen werden wie folgt definiert:

* **Schlüssel-Wert-Trennzeichen:** Trennt einen Schlüssel und einen Wert innerhalb eines Schlüssel-Wert-Paares.
* **Schlüssel-Wert-Trennzeichen:** Trennt Sätze von Schlüssel-Wert-Paaren.
* **Serielles Trennzeichen:** Trennt mehrere Werte innerhalb von Sätzen von serialisierten Schlüssel-Wert-Paaren.

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
   <td colname="col3"> <p>Ein einfacher Satz von Schlüssel-Wert-Paaren. Das Beispiel enthält die folgenden Elemente: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Schlüssel: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Werte: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Trennzeichen: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Schlüssel-Wert-Trennzeichen: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mehrere Schlüssel-Wert-Paare</b> (nicht seriell) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Ein Satz mehrerer Schlüssel-Wert-Paare, die Werte mit separaten Schlüssel-Wert-Sätzen übergeben. Das Beispiel enthält die folgenden Elemente: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Tasten: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Werte: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Trennzeichen: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Schlüssel-Wert-Trennzeichen: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Serieller Einzelschlüssel</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>Ein Schlüssel-Wert-Set, das mehrere Werte mit einem einzigen Schlüssel übergibt. Da dieser Schlüssel mehrere Werte hat, wird er als serialisiertes Schlüssel-Wert-Paar bezeichnet. Das Beispiel enthält die folgenden Elemente: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Schlüssel: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Werte: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Trennzeichen: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Serielles Trennzeichen: Semikolon </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mehrere Schlüssel-Wert-Paare</b> (seriell) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>Ein Satz mehrerer Schlüssel-Wert-Paare, die mehrere Werte auf separaten Schlüsseln übergeben. Das Beispiel enthält die folgenden Elemente: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Tasten: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Werte: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Trennzeichen: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Trennzeichen: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Serielles Trennzeichen: Semikolon </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Ziel-Serialisierung {#destination-serialized}

Ein serialisiertes Ziel kombiniert mehrere Eigenschaften zu einer einzigen Zeichenfolge und sendet diese Informationen an ein Ziel.

<!-- c_dest_serialized.xml -->

Die serialisierte Datenübertragung verbessert die Effizienz, da mehrere Eigenschaften nicht parallel, sondern nacheinander ausgelöst werden. Dadurch hat der Ziel-Server genügend Zeit, Daten zu empfangen, zu verarbeiten und zurückzugeben, bevor er auf zusätzliche Anfragen reagieren kann.

### Unterstützte Ziele

[!DNL Audience Manager] können Sie Daten an praktisch jedes Ziel serialisieren und senden, mit dem Sie arbeiten möchten. Bevor Sie diese Funktion verwenden, müssen Sie jedoch wissen, welche [!DNL URL] Sie verwenden und wo Sie einige erforderliche oder optionale Makros platzieren können. Erhalten Sie die Informationen zur Makroplatzierung von Ihrem Zielpartner. Weitere Informationen [ Sie unter ](../../features/destinations/destination-macros.md#destination-macros-defined) definiert.

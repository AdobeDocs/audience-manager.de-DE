---
description: Ein Schlüssel-Wert-Paar besteht aus verwandten Elementen, wobei es sich um eine Konstante handelt, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis) und einen Wert (z. B. Geschlecht, Farbe, Grün, 100). Zielaufbau sendet Daten, die als Schlüssel-Wert-Paare formatiert sind.
seo-description: Ein Schlüssel-Wert-Paar besteht aus verwandten Elementen, wobei es sich um eine Konstante handelt, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis) und einen Wert (z. B. Geschlecht, Farbe, Grün, 100). Zielaufbau sendet Daten, die als Schlüssel-Wert-Paare formatiert sind.
seo-title: Standard- und Serienschlüssel-Wert-Paare
solution: Audience Manager
title: Standard- und Serienschlüssel-Wert-Paare
uuid: 43789419-5 b 3 f -4 e 62-b 2 e 0-2722340 bdd 41
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Standard and Serial Key-Value Pairs {#standard-and-serial-key-value-pairs}

Ein Schlüssel-Wert-Paar besteht aus verwandten Elementen: Ein Schlüssel, der eine Konstante ist, die den Datensatz definiert (z. B. Geschlecht, Farbe, Preis) und einen Wert, der zu dem Satz gehört (z. B. männlich/weiblich, grün, grün, 100). [!UICONTROL Destination Builder] sendet Daten, die als Schlüssel-Wert-Paare formatiert sind.

## Basic Key-Value Pairs {#basic-key-value-pairs}

Vollständig formatiert, könnte ein Basissatz von Schlüssel-Wert-Paar wie folgt aussehen:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serial Key-Value Pairs {#standard-serial-key-value-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format.

* **Standardschlüssel-/Wertpaare:** Formatiert Zieldaten in separate Schlüssel/Wert-Paare. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren.
* **Serialisierte Schlüssel-Wert-Paare:** Führt mehrere Werte zu einem einzelnen Schlüssel-Wert-Paar zusammen. In einem serialisierten Schlüssel-Wert-Paar trennt ein Sonderindikator die Werte innerhalb des Schlüsselwertsatzes.

Sowohl standardmäßige als auch serialisierte Schlüsselwerte können einzelne oder mehrere Werte enthalten. Die folgende Tabelle zeigt Beispiele für standardmäßige und serielle Schlüsselwertformate.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formatierung </th>
   <th colname="col2" class="entry"> Einzelschlüssel-Wertpaare </th>
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
   <td colname="col2"> <p> <code> x = 1; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1; 2 &amp; y = 3; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimiters and Separators {#delimiters-separators}

The characters that separate values within and between keys and values are known as *`delimiters`* and *`separators`*. Diese werden besonders wichtig, wenn Sie Segmente in einem Serienformat an ein Ziel senden. Mit der Serialisierung können Sie mehrere Werte mit einem einzelnen Schlüssel übergeben und Schlüssel-Wert-Paare kombinieren. Trennzeichen und Trennzeichen werden wie folgt definiert:

* **Schlüsselwerttrennzeichen:** Trennt einen Schlüssel und einen Wert innerhalb eines Schlüssel-Wert-Paars.
* **Schlüsselwerttrennzeichen:** Trennt Sätze von Schlüssel/Wert-Paaren.
* **Reihentrennzeichen:** Trennt mehrere Werte innerhalb von Sätzen serialisierter Schlüssel-Wert-Paare.

## Beispiele {#examples}

With [!UICONTROL Destination Builder] you can format key-value data in several different ways. Sehen wir uns einige Beispiele für jeden Typ an.

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
   <td colname="col1"> <p> <b>Standardmäßiger Einzelschlüssel</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>Ein einfacher Satz von Schlüssel/Wert-Paaren. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Schlüssel: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Werte: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Trennzeichen: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Schlüsselwerttrennzeichen: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mehrere Schlüssel/Wert-Paare</b> (nicht serielle) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>Ein Satz mehrerer Schlüssel/Wert-Paare, die Werte mit separaten Schlüsselwertsätzen übergeben. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Schlüssel: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Werte: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Trennzeichen: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Schlüsselwerttrennzeichen: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Serieller Einzelschlüssel</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1; 2; 3 </code> </p> </td> 
   <td colname="col3"> <p>Ein Schlüsselwertsatz, der mehrere Werte mit einem einzelnen Schlüssel übergibt. Da dieser Schlüssel mehrere Werte hat, wird er als serialisiertes Schlüssel-Wert-Paar bezeichnet. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Schlüssel: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Werte: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Trennzeichen: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Reihentrennzeichen: Semikolon </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Mehrere Schlüssel/Wert-Paare</b> (serielle) </p> </td> 
   <td colname="col2"> <p> <code> X = 1; 2 &amp; Y = 3; 4 </code> </p> </td> 
   <td colname="col3"> <p>Ein Satz mehrerer Schlüssel/Wert-Paare, die mehrere Werte in separaten Schlüsseln übergeben. Das Beispiel enthält folgende Elemente: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Schlüssel: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Werte: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Trennzeichen: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Trennzeichen: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Reihentrennzeichen: Semikolon </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Destination Serialization {#destination-serialized}

Ein serialisiertes Ziel kombiniert mehrere Eigenschaften in einer einzelnen Zeichenfolge und sendet diese Informationen an ein Ziel.

<!-- c_dest_serialized.xml -->

Die serialisierte Datenübertragung verbessert die Effizienz, da mehrere Eigenschaften nacheinander und nicht parallel ausgelöst werden. Dies stellt den Zielserver mit ausreichend Zeit zum Empfangen, Verarbeiten und Zurückgeben von Daten bereit, bevor er auf zusätzliche Anforderungen reagiert.

### Unterstützte Ziele

In [!DNL Audience Manager], you can serialize and send data to just about any destination you want to work with. However, before using this feature, you will need to know the destination [!DNL URL] and where to place some required or optional macros. Rufen Sie die Informationen zur Makroplatzierung von Ihrem Zielpartner ab. See [Destination Macros Defined](../../features/destinations/destination-macros.md#destination-macros-defined) for more information.
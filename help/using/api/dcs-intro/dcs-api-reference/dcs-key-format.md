---
description: Bei einem Aufruf akzeptiert das DCS wichtige Wertdaten im Standard- oder serialisierten Format. Lesen Sie diesen Abschnitt, um Informationen zur Formatierung von standardmäßigen und serialisierten Schlüsselwertdaten zu erhalten.
seo-description: Bei einem Aufruf akzeptiert das DCS wichtige Wertdaten im Standard- oder serialisierten Format. Lesen Sie diesen Abschnitt, um Informationen zur Formatierung von standardmäßigen und serialisierten Schlüsselwertdaten zu erhalten.
seo-title: Formatieren von Schlüsselwertpaaren in DCS-Aufrufen
solution: Audience Manager
title: Formatieren von Schlüsselwertpaaren in DCS-Aufrufen
uuid: af 02 f 2 a 1-4388-4074-ab 4 e -66 ee 82023 f 1 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Formatting Key-Value Pairs in DCS Calls {#formatting-key-value-pairs-in-dcs-calls}

When making a call, the [!UICONTROL DCS] accepts key-value data in standard or serialized format. Lesen Sie diesen Abschnitt, um Informationen zur Formatierung von standardmäßigen und serialisierten Schlüsselwertdaten zu erhalten.

## Standard and Serialized Key-Value Pairs {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüsselwerttyp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Beispiel  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>Ein Standardschlüssel-Wert-Paar besteht aus einem einzelnen Schlüssel und einem Wert. Diese Struktur gliedert Daten in separate Schlüssel-Wert-Paare. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren. Dies ist die gängigste Methode zum Senden von Daten an das DCS. </p> </td>
   <td colname="col3"> <code> key 1 = val 1 &amp; key 2 = val 2 &amp; key 3 = val 3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serialisiert</b> </td> 
   <td colname="col2"> <p>Ein serialisiertes Schlüssel-Wert-Paar besteht aus einem einzelnen und mehreren Werten. Dies kann eine effiziente Methode zum Organisieren von Daten sein, aber serialisierte Schlüssel-Wert-Paare erfordern spezielle Symbole, um jeden Schlüssel und jeden Schlüssel-Wert-Satz voneinander zu trennen. </p> </td> 
   <td colname="col3"> <code> key 1 = val 1, val 2, val 3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimiters and Separators for Serialized Key-Value Pairs {#delimiters-separators}

Bei serialisierten Schlüssel-Wert-Paaren müssen Sie die Markierungen angeben, die innerhalb und zwischen diesen Variablen voneinander getrennt sind. Für Audience Manager sind die folgenden Trennzeichen und Trennzeichen erforderlich:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Anforderungen für </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> Trennt einzeln </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Trennzeichen</b> </td> 
   <td colname="col2"> Und &amp; </td> 
   <td colname="col3"> <p>Schlüssel/Wert-Paare: </p> <p><code> key 1 = val 1 &amp; key 2 = val 2, val 3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trennzeichen</b> </td> 
   <td colname="col2"> Komma , </td> 
   <td colname="col3"> <p>Werte in Schlüssel/Wert-Paaren: </p> <p><code> key 1 = val 1, val 2, val 3 &amp; key 2 = vala, valb, valc</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Daten an den DCS senden](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Wichtige Wertpräfixe und vom DCS unterstützte Variablen](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Wichtige Wertpaare](../../../reference/key-value-pairs-explained.md)


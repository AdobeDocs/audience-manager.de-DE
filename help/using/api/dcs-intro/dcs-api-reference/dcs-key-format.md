---
description: Beim Aufrufen akzeptiert der DES Schlüsselwertdaten im standardmäßigen oder serialisierten Format. In diesem Abschnitt finden Sie Informationen zum Formatieren von standardmäßigen und serialisierten Schlüsselwertdaten.
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen {#formatting-key-value-pairs-in-dcs-calls}

Bei einem Aufruf akzeptiert der [!DNL DCS] Schlüsselwertdaten im standardmäßigen oder serialisierten Format. In diesem Abschnitt finden Sie Informationen zum Formatieren von standardmäßigen und serialisierten Schlüsselwertdaten.

## Standardmäßige und serialisierte Schlüssel-Wert-Paare {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüsselwerttyp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
   <th colname="col3" class="entry"> Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>Ein standardmäßiges Schlüssel-Wert-Paar besteht aus einem Schlüssel-Wert-Paar. Diese Struktur organisiert Daten in separate Schlüssel-Wert-Paare. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren. Dies ist die gängigste Methode zum Senden von Daten an den DCS. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>serialized</b> </td> 
   <td colname="col2"> <p>Ein serialisiertes Schlüssel-Wert-Paar besteht aus einem einzelnen Schlüssel und mehreren Werten. Dies kann eine effiziente Methode zur Organisation von Daten sein, aber serialisierte Schlüssel-Wert-Paare erfordern spezifische Symbole, um jeden Schlüssel und jeden Schlüssel-Wert-Satz voneinander zu trennen. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Trennzeichen und Trennzeichen für serialisierte Schlüssel-Wert-Paare {#delimiters-separators}

Bei serialisierten Schlüssel-Wert-Paaren müssen Sie die Marken angeben, die Werte innerhalb und zwischen diesen Variablen trennen. Für Audience Manager sind die folgenden Trennzeichen und Trennzeichen erforderlich:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Voraussetzungen für </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> Trennt einzelne </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Trennzeichen</b> </td> 
   <td colname="col2"> Ampersand &amp; </td> 
   <td colname="col3"> <p>Schlüssel-Wert-Paare: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trennzeichen</b> </td> 
   <td colname="col2"> Komma , </td> 
   <td colname="col3"> <p>Werte innerhalb von Schlüssel-Wert-Paaren: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Senden von Daten an den DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Schlüsselwertpräfixe und -variablen, die vom DCS unterstützt werden](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Schlüssel-Wert-Paare – Erklärung](../../../reference/key-value-pairs-explained.md)

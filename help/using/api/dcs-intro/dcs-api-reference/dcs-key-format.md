---
description: Bei einem Aufruf akzeptiert der DCS Daten mit Schlüsselwerten im standardmäßigen oder serialisierten Format. Informationen zum Formatieren von Standard- und serialisierten Schlüsselwertdaten finden Sie in diesem Abschnitt.
seo-description: Bei einem Aufruf akzeptiert der DCS Daten mit Schlüsselwerten im standardmäßigen oder serialisierten Format. Informationen zum Formatieren von Standard- und serialisierten Schlüsselwertdaten finden Sie in diesem Abschnitt.
seo-title: Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen
solution: Audience Manager
title: Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 12%

---


# Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen {#formatting-key-value-pairs-in-dcs-calls}

Bei einem Aufruf akzeptiert das [!DNL DCS] Schlüsselwertdaten im standardmäßigen oder serialisierten Format. Informationen zum Formatieren von Standard- und serialisierten Schlüsselwertdaten finden Sie in diesem Abschnitt.

## Standard- und serialisierte Schlüsselwertpaare {#standard-serialized}

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
   <td colname="col2"> <p>Ein standardmäßiges Schlüssel-Wert-Paar besteht aus einem Schlüssel und einem Wert. Diese Struktur organisiert Daten in separate Schlüssel-Wert-Paare. Jeder Schlüssel wird explizit angegeben, auch wenn er erneut verwendet wird, um einen anderen Wert zu definieren. Dies ist die häufigste Methode zum Senden von Daten an den DCS. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serialisiert</b> </td> 
   <td colname="col2"> <p>Ein serialisiertes Schlüssel-Wert-Paar besteht aus einem Schlüssel und mehreren Werten. Auf diese Weise können Daten effizient organisiert werden. Für serialisierte Schlüssel/Wert-Paare sind jedoch spezifische Symbole erforderlich, um jeden Schlüssel und jeden Schlüssel-Wert-Satz voneinander zu trennen. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Trennzeichen und Trennzeichen für serialisierte Schlüssel/Wert-Paare {#delimiters-separators}

Bei serialisierten Schlüssel-Wert-Paaren müssen Sie die Marker angeben, die Werte innerhalb und zwischen diesen Variablen trennen. Audience Manager erfordert die folgenden Trennzeichen und Trennzeichen:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Anforderungen für </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> Trennt Einzelne </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Trennzeichen</b> </td> 
   <td colname="col2"> Ampersand &amp; </td> 
   <td colname="col3"> <p>Schlüsselwertpaare: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trennzeichen</b> </td> 
   <td colname="col2"> Komma , </td> 
   <td colname="col3"> <p>Werte innerhalb der Schlüssel-Wert-Paare: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Senden von Daten an den DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Präfixe und Variablen mit Schlüsselwerten, die vom DCS unterstützt werden](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Schlüssel-Wert-Paare – Erklärung](../../../reference/key-value-pairs-explained.md)


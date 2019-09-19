---
description: Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdrücke zum Festlegen von Kriterien für die Zielgruppenqualifizierung und die Art und Weise, wie Daten in einem Ereignisaufruf gesendet werden.
seo-description: Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdrücke zum Festlegen von Kriterien für die Zielgruppenqualifizierung und die Art und Weise, wie Daten in einem Ereignisaufruf gesendet werden.
seo-title: Signale, Eigenschaften und Segmente
solution: Audience Manager
title: Signale, Eigenschaften und Segmente
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signale, Eigenschaften und Segmente{#signals-traits-and-segments}

Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdrücke zum Festlegen von Kriterien für die Zielgruppenqualifizierung und die Art und Weise, wie Daten in einem Ereignisaufruf gesendet werden.

<!-- 

c_signal_trait_segment.xml

 -->

**Zusammensetzung und Zweck**

[!DNL Audience Manager] Daten bestehen aus Signalen, Eigenschaften, Segmenten und zugehörigen Qualifikationsregeln. Die Datenelemente und Regeln werden kombiniert, um Segmente zu erstellen. Segmente organisieren Site-Besucher in verwandte Gruppen. Die folgende Tabelle definiert die drei Hauptkomponenten eines [!DNL Audience Manager] Segments.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Besteht aus </th> 
   <th colname="col3" class="entry"> Beispiel  </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Signal</b> </td> 
   <td colname="col2"> <p>Signale sind die kleinsten Dateneinheiten in <span class="keyword"> Audience Manager</span> und werden als <a href="../reference/key-value-pairs-explained.md"> Schlüssel-Wert-Paare</a>ausgedrückt. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">Der Schlüssel ist eine Konstante, die einen Datensatz definiert (z.B. Geschlecht, Farbe, Preis). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">Der Wert ist eine Variable, die sich auf die Konstante bezieht (z. B. männlich/weiblich, grün, 100). </li> 
    </ul> <p>Vergleichsoperatoren verbinden das Schlüssel-Wert-Paar und legen die Beziehung zwischen ihnen fest. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trait-</b> </td> 
   <td colname="col2"> <p>Kombinationen aus einem oder mehreren Signalen. </p> <p>Mit booleschen Ausdrücken und Vergleichsoperatoren können Sie Eigenschaftenqualifizierungsregeln erstellen. </p> <p>Erstellen Sie präzise Qualifizierungsanforderungen mit Kombinationen aus Eigenschaften und Eigenschaftsgruppen. </p> </td> 
   <td colname="col3"> <p>Aus den verfügbaren Signalen können Sie eine Regel für den High-End-Kamera-Browser erstellen, die wie folgt ausgedrückt wird: </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segment</b> </td> 
   <td colname="col2"> <p>Benutzer, die einen Satz gemeinsamer Attribute verwenden und für verwandte Eigenschaften qualifiziert sind. </p> <p>Mithilfe boolescher Ausdrücke können Sie zusammen mit den Anforderungen an Neuigkeit und Häufigkeit Segmentqualifikationsregeln erstellen. </p> <p>Erstellen Sie präzise Qualifikationsanforderungen mit Kombinationen aus Eigenschaften und Segmentregeln. </p> </td> 
   <td colname="col3"> <p>Aus den verfügbaren Eigenschaften und Signalen können Sie eine Segmentregel erstellen, die wie folgt ausgedrückt wird: </p> <p><code> (product=camera AND type=digital SLR) ODER (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Verwenden Sie das unten stehende Diagramm, um eine mentale Note der Beziehung zwischen Signalen, Eigenschaften und Segmenten zu erhalten.

![](assets/signals-traits-segments.png)

**Eigenschaften und Segmentregeln mit Visual Tools und Codeeditoren erstellen**

Kunden verwalten Eigenschaften und Segmente mit visuellen Werkzeugen und Codeeditoren in der [!DNL Audience Manager] Benutzeroberfläche. Mit den visuellen Werkzeugen können Sie Regeln mit Suchfunktionen, Popup-Optionen, Dropdownmenüs und Drag &amp; Drop-Funktionen erstellen. Die Code-Editoren bieten fortgeschrittenen Benutzern die Möglichkeit, Zielgruppensegmentierungskriterien programmatisch zu entwickeln.

**Ereignisaufrufe Daten an Audience Manager senden**

Ein Ereignisaufruf sendet Daten von Ihrer Website an [!DNL Audience Manager]. Der Aufruf enthält Signal-, Eigenschaften- und Segmentdaten in einer HTTP-Anforderung. Das Ereignis selbst ist alles nach dem `/event` Teil einer URL-Zeichenfolge. Wie im Beispiel unten gezeigt, erfordert dieser Prozess nur einen einzelnen Ereignisaufruf, um mehrere Variablen an [!DNL Audience Manager]weiterzugeben.

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_LIKE_THIS]
>
>* [Segmente: Zweck, Zusammensetzung und Regeln](../features/segments/segments-purpose.md)


---
description: Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdrücke zum Festlegen von Zielgruppenqualifizierungskriterien und die Art und Weise, wie Daten in einem Ereignisaufruf übertragen werden.
seo-description: Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdrücke zum Festlegen von Zielgruppenqualifizierungskriterien und die Art und Weise, wie Daten in einem Ereignisaufruf übertragen werden.
seo-title: Signale, Eigenschaften und Segmente
solution: Audience Manager
title: Signale, Eigenschaften und Segmente
uuid: 485 fcc 5 c-b 289-463 b-a 610-0 d 727 df 90 f 3 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signals, Traits, and Segments{#signals-traits-and-segments}

Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdrücke zum Festlegen von Zielgruppenqualifizierungskriterien und die Art und Weise, wie Daten in einem Ereignisaufruf übertragen werden.

<!-- 

c_signal_trait_segment.xml

 -->

**Zusammensetzung und Zweck**

[!DNL Audience Manager] besteht aus Signalen, Eigenschaften, Segmenten und zugehörigen Qualifizierungsregeln. Die Datenelemente und Regeln kombinieren zum Erstellen von Segmenten. Segmente organisieren Site-Besucher in verwandte Gruppen. The following table defines the three principal components in an [!DNL Audience Manager] segment.

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
   <td colname="col2"> <p>Signals are the smallest data units in <span class="keyword"> Audience Manager</span> and are expressed as <a href="../reference/key-value-pairs-explained.md"> key-value pairs</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">Der Schlüssel ist eine Konstante, die einen Datensatz definiert (z. B. Geschlecht, Farbe, Preis). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">Der Wert ist eine Variable mit Bezug auf die Konstante (z. B. männlich/weiblich, grün, 100). </li> 
    </ul> <p>Vergleichsoperatoren verbinden das Schlüssel-Wert-Paar und stellen die Beziehung zwischen diesen ein. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product = camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> Preis &gt; 1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type = digitale SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trait-</b> </td> 
   <td colname="col2"> <p>Kombinationen eines oder mehrerer Signale. </p> <p>Mit booleschen Ausdrücken und Vergleichsoperatoren können Sie Trait-Qualifizierungsregeln erstellen. </p> <p>Erstellen Sie präzise Qualifikationsanforderungen mit Kombinationen aus Eigenschaften und Eigenschaftsgruppen. </p> </td> 
   <td colname="col3"> <p>Von den verfügbaren Signalen können Sie eine Regel für den High-End-Kamerbrowser erstellen, ausgedrückt als: </p> <p><code> product = camera AND price &gt; 1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segment</b> </td> 
   <td colname="col2"> <p>Benutzer, die einen Satz gängiger Attribute freigeben und für zugehörige Eigenschaften qualifizieren. </p> <p>Boolesche Ausdrücke mit Neuigkeits-/Häufigkeitsanforderungen ermöglichen die Erstellung von Regeln zur Segmentqualifizierung. </p> <p>Erstellen Sie präzise Qualifikationsanforderungen mit Kombinationen aus Eigenschaften und Segmentregeln. </p> </td> 
   <td colname="col3"> <p>Von den verfügbaren Eigenschaften und Signalen können Sie eine Segmentregel erstellen, die wie folgt ausgedrückt wird: </p> <p><code> (product = camera AND type = digital SLR) ODER (Preis &gt; 1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Verwenden Sie das folgende Diagramm, um die Beziehung zwischen Signal, Eigenschaften und Segmenten in einer Mental Note festzuhalten.

![](assets/signals-traits-segments.png)

**Erstellen von Eigenschaften und Segmentregeln mit visuellen Werkzeugen und Code-Editoren**

Clients manage traits and segments with visual tools and code editors in the [!DNL Audience Manager] user interface. Mit den visuellen Werkzeugen können Sie Regeln mithilfe von Suchfunktionen, Popup-Optionen, Dropdown-Menüs und Drag &amp; Drop-Funktionen erstellen. Die Codeeditoren bieten fortgeschrittene Benutzer eine Möglichkeit, die Zielgruppensegmentierungskriterien programmgesteuert zu entwickeln.

**Ereignisaufrufe Daten an Audience Manager senden**

An event call sends data from your website to [!DNL Audience Manager]. Der Aufruf enthält Signal-, Eigenschaften- und Segmentdaten in einer HTTP-Anforderung. The event itself is everything after the `/event` part of a URL string. As shown in the example below, this process requires only a single event call to pass in multiple variables to [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_ LIKE_ THIS]
>
>* [Segmente: Zweck, Zusammensetzung und Regeln](../features/segments/segments-purpose.md)


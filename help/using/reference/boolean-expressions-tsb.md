---
description: In diesem Artikel wird erläutert, wie die Audience Manager-Eigenschaften und Segmentwerkzeuge die booleschen Ausdrücke UND, ODER und NICHT verwenden.
seo-description: In diesem Artikel wird erläutert, wie die Audience Manager-Eigenschaften und Segmentwerkzeuge die booleschen Ausdrücke UND, ODER und NICHT verwenden.
seo-title: Boolesche Ausdruck in Trait und Segment Builder
solution: Audience Manager
title: Boolesche Ausdruck in Trait und Segment Builder
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: 'Referenz '
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# Boolesche Ausdruck in Trait und Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

In diesem Artikel wird erläutert, wie die Audience Manager-Eigenschaften und Segmentwerkzeuge die booleschen Ausdrücke UND, ODER und NICHT verwenden.

<!-- 

c_tb_boolean.xml

 -->

**Boolesche Ausdrücke**

Boolesche Logik ist ein Zweig der Algebra, der mithilfe einiger grundlegender Ausdrücke (oder Operatoren) bestimmt, ob eine Anweisung wahr oder falsch ist. Die häufigsten Operatoren sind [!UICONTROL AND], [!UICONTROL OR] und [!UICONTROL NOT]. Mithilfe der Kombinationen dieser Ausdrücke können Sie fokussierte Eigenschaften- oder Segmentqualifikationsregeln für Ihre Datenanforderungen individuell anpassen. Die folgende Abbildung zeigt, wie grundlegende boolesche Ausdrücke funktionieren.

<br>

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>Der Operator [!UICONTROL NOT] verwendet eine implizite &quot;and&quot;-Bedingung und wird manchmal als [!UICONTROL AND NOT] geschrieben.

**Verwenden boolescher Ausdrücke in Trait und Segment Builder**

Sie erstellen Eigenschaften- und Segmentqualifikationsregeln mit booleschen Ausdrücken. In der folgenden Tabelle werden die allgemeinen Best Practices zum Erstellen von Qualifizierungskriterien mit [!UICONTROL AND], [!UICONTROL OR] und [!UICONTROL NOT] beschrieben.

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ausdruck  </th> 
   <th colname="col2" class="entry"> Verwenden Sie ihn zum Erstellen </th> 
   <th colname="col3" class="entry"> Zu qualifizieren </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> UND</span></b> </p> </td> 
   <td colname="col2"> <p>Eingeschränkte, fokussierte Anforderungen an die Zielgruppenqualifizierung. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>muss</i> zu allen angegebenen Eigenschaften oder Segmenten gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> ODER</span></b> </p> </td> 
   <td colname="col2"> <p>Umfassende, weniger zielgerichtete Anforderungen an die Zielgruppenqualifizierung. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>can</i> gehören zu allen angegebenen Eigenschaften oder Segmenten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NICHT</span></b> </p> </td> 
   <td colname="col2"> <p>Eingeschränkte, fokussierte Anforderungen an die Zielgruppenqualifizierung. </p> <p>Nützlich, wenn mehrere Bedingungen vorliegen, die die Definition von Anforderungen an die Zielgruppenqualifizierung erschweren oder ineffizient machen. Gelegentlich ist es einfacher, anhand von Anforderungen zu validieren, die ausschließen statt einschließen. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>dürfen nicht</i> zu einer ausgeschlossenen Eigenschaft oder einem ausgeschlossenen Segment gehören. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Anwendungsbeispiel**

Der Operator [!UICONTROL AND] ist nützlich, wenn Sie mühelos die Anforderungen an die Mitgliedschaft in Eigenschaften aufzählen können. Angenommen, Sie müssen eine Audience von &quot;teuren Kamerakäufern&quot;erstellen. Mit einem Pixelmodell müssten Sie Pixel für Kameras und einen numerischen Preiswert auf Ihrer Seite erstellen und platzieren. Im Gegensatz dazu können Sie mit Eigenschaften boolesche Operatoren anwenden, um beide Bedingungen zu handhaben (Kameras [!UICONTROL AND] Preis). Das Ergebnis ist eine effiziente Datenerfassung mit weniger HTTP-Aufrufen, was wiederum dazu beiträgt, das Benutzererlebnis auf Ihrer Site zu erhalten.

**[!UICONTROL OR]Anwendungsbeispiel**

Der Operator [!UICONTROL OR] ist nützlich, wenn Sie Signale mit allgemeinen Anforderungen an die Zielgruppenqualifizierung erstellen möchten. Wenn Sie mehrere Anforderungen an Eigenschaften oder Segmentqualifikationen haben, wird der Operator [!UICONTROL OR] als &quot;true&quot;ausgewertet, wenn Ihre Site-Besucher *beliebige* dieser Merkmale aufweisen. [!UICONTROL OR] kann am nützlichsten sein, wenn Sie schnell eine breite Zielgruppe qualifizierter Site-Besucher erstellen möchten.

**[!UICONTROL AND NOT]Anwendungsbeispiel**

Der Operator [!UICONTROL AND NOT] ist nützlich, wenn es einfacher ist, eine Zielgruppe durch *Ausschluss* anstatt durch *Einbindung* zu definieren. Angenommen, Sie haben einen Verkauf und möchten Besucher in Kunden unterteilen, die sich nur vollständige Preisartikel ansehen. Anstatt eine Liste von Signalen für alle qualifizierenden Voll- oder Verkaufspreis-Artikel zu erstellen, ist es möglicherweise einfacher, Besucher zu qualifizieren, wenn sie *nicht* einen Verkaufspreis gesehen haben. Dies ist administrativ effizient, da Sie in der Regel weniger Verkaufspreisartikel haben als die, die zum vollen Preis angeboten werden. Bei einem booleschen [!UICONTROL NOT] dürfen Besucher *nicht* das Verkaufssignal ausgeben, um sich für eine Zielgruppenmitgliedschaft mit vollem Preis zu qualifizieren. Im Gegensatz dazu ist [!UICONTROL AND NOT] das Gegenteil des [!UICONTROL AND]-Anwendungsfalls, der gezeigt hat, wie die Zielgruppenzugehörigkeit durch Einbindung bestimmt wird (d. h. der Besucher qualifiziert sich basierend auf 2 explizit angegebenen Signalen).

>[!MORELIKETHIS]
>
>* [Arbeiten mit Vergleichsoperatoren in TraitBuilder](../features/traits/trait-comparison-operators.md)
* [Reihenfolge der Vorgänge in TraitBuilder-Ausdrücken](../features/traits/trait-operator-precedence.md)


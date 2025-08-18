---
description: In diesem Artikel wird erläutert, wie die Audience Manager-Trait- und Segment-Tools die booleschen Ausdrücke AND, OR und NOT verwenden.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: Boolesche Ausdrücke in Trait und Segment Builder
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Boolesche Ausdrücke in Trait und Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

In diesem Artikel wird erläutert, wie die Audience Manager-Trait- und Segment-Tools die booleschen Ausdrücke AND, OR und NOT verwenden.

<!-- 

c_tb_boolean.xml

 -->

**Boolesche Ausdrücke**

Boolesche Logik ist ein Zweig der Algebra, der einige grundlegende Ausdrücke (oder Operatoren) verwendet, um zu bestimmen, ob eine Anweisung wahr oder falsch ist. Die häufigsten Operatoren sind [!UICONTROL AND], [!UICONTROL OR] und [!UICONTROL NOT]. Kombinationen dieser Ausdrücke helfen Ihnen dabei, fokussierte Regeln für Eigenschaften oder Segmentqualifikationen speziell auf Ihre Datenanforderungen abzustimmen. Die folgende Abbildung zeigt, wie einfache boolesche Ausdrücke funktionieren.

<br>

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>Der [!UICONTROL NOT]-Operator verwendet eine implizite „and“-Bedingung und wird manchmal als [!UICONTROL AND NOT] geschrieben.

**Verwenden boolescher Ausdrücke in Trait und Segment Builder**

Sie erstellen Eigenschaften- und Segmentqualifikationsregeln mit booleschen Ausdrücken. In der folgenden Tabelle werden allgemeine Best Practices für die Erstellung von Qualifikationskriterien mit [!UICONTROL AND], [!UICONTROL OR] und [!UICONTROL NOT] beschrieben.

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ausdruck  </th> 
   <th colname="col2" class="entry"> Verwenden Sie sie zum Erstellen von </th> 
   <th colname="col3" class="entry"> Zu qualifizieren </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> UND</span></b> </p> </td> 
   <td colname="col2"> <p>Enge, fokussierte Anforderungen an die Zielgruppenqualifizierung. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>müssen</i> allen angegebenen Eigenschaften oder Segmenten angehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> ODER</span></b> </p> </td> 
   <td colname="col2"> <p>Anforderungen an die Qualifizierung breiter, weniger fokussierter Zielgruppen. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>können</i> zu beliebigen Eigenschaften oder Segmenten gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NICHT</span></b> </p> </td> 
   <td colname="col2"> <p>Enge, fokussierte Anforderungen an die Zielgruppenqualifizierung. </p> <p>Nützlich, wenn es mehrere Bedingungen gibt, die die Definition von Zielgruppen-Qualifizierungsanforderungen schwierig oder ineffizient machen. Gelegentlich ist es einfacher, Anforderungen zu berücksichtigen, die ausschließen, anstatt sie einzuschließen. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>dürfen</i> keiner ausgeschlossenen Eigenschaft oder einem ausgeschlossenen Segment angehören. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Anwendungsbeispiel**

Der [!UICONTROL AND]-Operator ist nützlich, wenn Sie Anforderungen für die einfache Aufzählung von Eigenschaftenmitgliedschaften haben. Angenommen, Sie müssen eine Zielgruppe aus „teuren Kamerakäufern“ erstellen. Mit einem Pixelmodell müssten Sie Pixel für Kameras erstellen und platzieren und einen numerischen Preiswert auf Ihrer Seite angeben. Im Gegensatz dazu können Sie bei Eigenschaften boolesche Operatoren anwenden, um beide Bedingungen zu handhaben (Kameras [!UICONTROL AND] Preis). Das Ergebnis ist eine effiziente Datenerfassung mit weniger HTTP-Aufrufen, was wiederum dazu beiträgt, das Benutzererlebnis auf Ihrer Site zu erhalten.

**[!UICONTROL OR]Anwendungsbeispiel**

Der Operator [!UICONTROL OR] ist nützlich, wenn Sie Signale mit umfassenden Zielgruppen-Qualifizierungsanforderungen erstellen möchten. Wenn Sie mehrere Anforderungen an die Trait- oder Segmentqualifikation haben, wird der [!UICONTROL OR] als „true“ bewertet, wenn Ihre Site-Besucher *eines* dieser Merkmale aufweisen. [!UICONTROL OR] kann am nützlichsten sein, wenn Sie schnell eine breite Zielgruppe qualifizierter Site-Besucher erstellen möchten.

**[!UICONTROL AND NOT]Anwendungsbeispiel**

Der [!UICONTROL AND NOT]-Operator ist nützlich, wenn es einfacher ist, eine Zielgruppe durch *Ausschluss* statt *Einschluss* zu definieren. Angenommen, Sie haben einen Verkauf und möchten Besucher in Kunden unterteilen, die nur Artikel zum vollen Preis anzeigen. Anstatt eine Liste von Signalen für alle qualifizierten Voll- oder Verkaufspreis-Artikel zu erstellen, kann es einfacher sein, Besucher zu qualifizieren, wenn sie *Verkaufspreis-Artikel gesehen*. Dies ist administrativ effizient, da Sie in der Regel weniger Verkaufspreis-Artikel haben als die, die zum vollen Preis angeboten werden. Bei einem booleschen [!UICONTROL NOT] dürfen *Besucher* Verkaufssignal aussenden, um sich für eine Zielgruppenzugehörigkeit zum vollen Preis zu qualifizieren. Im Gegensatz dazu ist [!UICONTROL AND NOT] das Gegenteil des [!UICONTROL AND] Anwendungsfalls, in dem gezeigt wurde, wie die Zielgruppenzugehörigkeit durch Einbindung bestimmt wird (d. h., der Besucher qualifiziert sich anhand von zwei explizit angegebenen Signalen).

>[!MORELIKETHIS]
>
>* [Arbeiten mit Vergleichsoperatoren in TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Reihenfolge der Vorgänge in TraitBuilder-Ausdrücken](../features/traits/trait-operator-precedence.md)

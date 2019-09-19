---
description: In diesem Artikel wird erläutert, wie die Eigenschaften- und Segmentwerkzeuge von Audience Manager die booleschen Ausdrücke AND, OR und NOT verwenden.
seo-description: In diesem Artikel wird erläutert, wie die Eigenschaften- und Segmentwerkzeuge von Audience Manager die booleschen Ausdrücke AND, OR und NOT verwenden.
seo-title: Boolesche Ausdrücke im Eigenschaften- und Segmentaufbau
solution: Audience Manager
title: Boolesche Ausdrücke im Eigenschaften- und Segmentaufbau
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Boolesche Ausdrücke im Eigenschaften- und Segmentaufbau{#boolean-expressions-in-trait-and-segment-builder}

In diesem Artikel wird erläutert, wie die Eigenschaften- und Segmentwerkzeuge von Audience Manager die booleschen Ausdrücke AND, OR und NOT verwenden.

<!-- 

c_tb_boolean.xml

 -->

**Boolesche Ausdrücke**

Boolesche Logik ist ein Zweig der Algebra, der mithilfe einiger einfacher Ausdrücke (oder Operatoren) bestimmt, ob eine Anweisung wahr oder falsch ist. Die am häufigsten verwendeten Operatoren sind [!UICONTROL AND], [!UICONTROL OR]und [!UICONTROL NOT]. Kombinationen dieser Ausdrücke helfen Ihnen dabei, fokussierte Eigenschaften- oder Segmentqualifizierungsregeln für Ihre Datenanforderungen eindeutig anzupassen. Die folgende Abbildung zeigt, wie einfache boolesche Ausdrücke funktionieren.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>Der [!UICONTROL NOT] Operator verwendet eine implizite "Und"-Bedingung und wird manchmal als [!UICONTROL AND NOT].

**Verwenden boolescher Ausdrücke in Eigenschaften- und Segmentaufbau**

Sie erstellen Eigenschaften- und Segmentqualifizierungsregeln mit booleschen Ausdrücken. In der folgenden Tabelle werden die allgemeinen Best Practices für das Erstellen von Qualifizierungskriterien mit [!UICONTROL AND], [!UICONTROL OR]und [!UICONTROL NOT]beschrieben.

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ausdruck  </th> 
   <th colname="col2" class="entry"> Verwenden Sie ihn zum Erstellen </th> 
   <th colname="col3" class="entry"> Voraussetzungen </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> UND</span></b> </p> </td> 
   <td colname="col2"> <p>Eingeschränkte, zielgerichtete Anforderungen an die Zielgruppenqualifizierung. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>müssen</i> zu allen angegebenen Eigenschaften oder Segmenten gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> ODER</span></b> </p> </td> 
   <td colname="col2"> <p>Weit gefasste, weniger zielgerichtete Anforderungen an die Zielgruppenqualifizierung. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>können</i> zu allen angegebenen Eigenschaften oder Segmenten gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NICHT</span></b> </p> </td> 
   <td colname="col2"> <p>Eingeschränkte, zielgerichtete Anforderungen an die Zielgruppenqualifizierung. </p> <p>Nützlich, wenn es mehrere Bedingungen gibt, die die Definition von Anforderungen an die Zielgruppenqualifikation erschweren oder ineffizient machen. Gelegentlich ist es einfacher, Anforderungen zu validieren, die ausschließen anstatt einschließen. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>dürfen nicht</i> zu einer ausgeschlossenen Eigenschaft oder einem ausgeschlossenen Segment gehören. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Verwendungsfallbeispiel**

Der [!UICONTROL AND] Operator ist nützlich, wenn Sie leicht aufzählbare Anforderungen an die Mitgliedschaft in Eigenschaften haben. Angenommen, Sie müssen eine Zielgruppe von "teuren Kamerakäufern"erstellen. Bei einem Pixelmodell müssten Sie Pixel für Kameras und einen numerischen Preiswert auf Ihrer Seite erstellen und platzieren. Mit Eigenschaften können Sie dagegen boolesche Operatoren anwenden, um beide Bedingungen zu handhaben (Kamerapreis [!UICONTROL AND] ). Das Ergebnis ist eine effiziente Datenerfassung mit weniger HTTP-Aufrufen, was wiederum dazu beiträgt, das Benutzererlebnis auf Ihrer Site zu erhalten.

**[!UICONTROL OR]Verwendungsfallbeispiel**

Der [!UICONTROL OR] Operator ist nützlich, wenn Sie Signale mit allgemeinen Anforderungen an die Zielgruppenqualifikation erstellen möchten. Wenn Sie mehrere Anforderungen an die Eigenschaften- oder Segmentqualifizierung haben, wird der [!UICONTROL OR] Operator als "true"ausgewertet, wenn Ihre Site-Besucher *irgendwelche* Merkmale aufweisen. [!UICONTROL OR] ist möglicherweise am nützlichsten, wenn Sie schnell eine breite Zielgruppe qualifizierter Site-Besucher erstellen möchten.

**[!UICONTROL AND NOT]Verwendungsfallbeispiel**

Der [!UICONTROL AND NOT] Operator ist hilfreich, wenn es einfacher ist, eine Zielgruppe durch *Ausschluss* anstatt durch *Einbeziehung* zu definieren. Angenommen, Sie haben einen Verkauf und möchten Besucher in Kunden segmentieren, die nur Artikel zum vollen Preis betrachten. Anstatt eine Liste der Signale für alle qualifizierenden Voll- oder Verkaufspreise zu erstellen, ist es möglicherweise einfacher, Besucher zu qualifizieren, wenn sie *keinen Verkaufspreis gesehen haben* . Dies ist administrativ effizient, da Sie in der Regel weniger Verkaufspreisartikel haben als die zum vollen Preis angebotenen. Bei einem booleschen Wert [!UICONTROL NOT]dürfen Besucher nicht ** das Verkaufssignal anzeigen, um sich für eine Vollpreismitgliedschaft in der Zielgruppe zu qualifizieren. Im Gegensatz dazu [!UICONTROL AND NOT] ist dies das Gegenteil des [!UICONTROL AND] Anwendungsfalls, der gezeigt hat, wie die Zielgruppenmitgliedschaft durch Einbindung bestimmt wird (d.h. der Besucher qualifiziert sich auf der Grundlage von 2 explizit angegebenen Signalen).

>[!MORE_LIKE_THIS]
>
>* [Arbeiten mit Vergleichsoperatoren in TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Reihenfolge der Vorgänge in EigenschaftenBuilder-Ausdrücken](../features/traits/trait-operator-precedence.md)


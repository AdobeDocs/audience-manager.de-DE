---
description: In diesem Artikel wird erläutert, wie die Eigenschaften und Segmentwerkzeuge von Audience Manager die booleschen Ausdrücke UND, ODER und NOT verwenden.
seo-description: In diesem Artikel wird erläutert, wie die Eigenschaften und Segmentwerkzeuge von Audience Manager die booleschen Ausdrücke UND, ODER und NOT verwenden.
seo-title: Boolesche Ausdrücke in Eigenschaften und Segmentaufbau
solution: Audience Manager
title: Boolesche Ausdrücke in Eigenschaften und Segmentaufbau
uuid: 14 f 02 d 3 f -4 c 84-41 fe-bc 91-b 34 f 0 d 49574 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Boolean Expressions in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

In diesem Artikel wird erläutert, wie die Eigenschaften und Segmentwerkzeuge von Audience Manager die booleschen Ausdrücke UND, ODER und NOT verwenden.

<!-- 

c_tb_boolean.xml

 -->

**Boolesche Ausdrücke**

Die Boolesche Logik ist eine Verzweigung von algebra, die einige einfache Ausdrücke (oder Operatoren) verwendet, um zu bestimmen, ob eine Anweisung wahr oder false ist. The most common operators are [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]. Kombinationen dieser Ausdrücke helfen Ihnen, fokussierte Eigenschaften oder Segmentqualifizierungsregeln für Ihre Datenanforderungen eindeutig zu gestalten. Die folgende Abbildung zeigt, wie einfache boolesche Ausdrücke funktionieren.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>The [!UICONTROL NOT] operator uses an implied "and" condition and is sometimes written as [!UICONTROL AND NOT].

**Verwendung boolescher Ausdrücke in Eigenschaften und Segmentaufbau**

Sie erstellen Regeln für Eigenschaften und Segmentqualifizierungen mit booleschen Ausdrücken. The table below describes general best practices for creating qualification criteria with [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ausdruck  </th> 
   <th colname="col2" class="entry"> Zur Erstellung verwenden </th> 
   <th colname="col3" class="entry"> Qualifizieren </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> UND</span></b> </p> </td> 
   <td colname="col2"> <p>Eingeschränkte, fokussierte Zielgruppenqualifizierungsanforderungen. </p> </td> 
   <td colname="col3"> <p>Users <i>must</i> belong to all specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>Weitgefasst, weniger fokussierte Zielgruppenqualifizierungsanforderungen. </p> </td> 
   <td colname="col3"> <p>Users <i>can</i> belong to any specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NICHT</span></b> </p> </td> 
   <td colname="col2"> <p>Eingeschränkte, fokussierte Zielgruppenqualifizierungsanforderungen. </p> <p>Nützlich, wenn es mehrere Bedingungen gibt, mit denen Anforderungen für die Zielgruppenqualifizierung schwierig oder ineffizient definiert werden können. Gelegentlich ist es einfacher, für Anforderungen, die ausschließlich ausgeschlossen werden, zu validieren. </p> </td> 
   <td colname="col3"> <p>Users <i>must not</i> belong to an excluded trait or segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Verwendungsfallbeispiel**

The [!UICONTROL AND] operator is useful when you have easily enumerated trait membership requirements. Angenommen, Sie müssen eine Zielgruppe von teuren Kamera-Käufern erstellen. » Mit einem Pixelmodell müssten Sie Pixel für Kameras und einen numerischen Preis auf Ihrer Seite erstellen und platzieren. By contrast, with traits you can apply Boolean operators to handle both conditions (cameras [!UICONTROL AND] price). Das Ergebnis ist eine effiziente Datenerfassung mit weniger HTTP-Aufrufen, die wiederum die Benutzererfahrung auf Ihrer Site bewahrt.

**[!UICONTROL OR]Verwendungsfallbeispiel**

The [!UICONTROL OR] operator is useful when you want to create signals with broad audience qualification requirements. If you have several trait or segment qualification requirements, the [!UICONTROL OR] operator will evaluate to true when your site visitors exhibit *any* of those characteristics. [!UICONTROL OR] kann am nützlichsten sein, wenn Sie schnell eine breite Gruppe qualifizierter Site-Besucher erstellen möchten.

**[!UICONTROL AND NOT]Verwendungsfallbeispiel**

The [!UICONTROL AND NOT] operator is useful when it’s easier to define an audience by *exclusion* rather than *inclusion*. Angenommen, Sie haben einen Verkauf und möchten Besucher in Kunden segmentieren, die nur Vollpreisartikel betrachten. Rather than create a list of signals for all qualifying full or sale-price items, it may be easier to qualify visitors if they have *not* seen a sale price item. Dies ist verwaltungseffizient, da Sie im Vergleich zu den zum vollen Preis angebotenen Artikeln in der Regel weniger Artikel verkaufen. With a Boolean [!UICONTROL NOT], visitors *must not* exhibit the sale signal to qualify for full-price audience membership. By contrast, [!UICONTROL AND NOT] is the opposite of the [!UICONTROL AND] use case, which showed how audience membership is determined by inclusion (i.e., the visitor qualified based on 2 explicitly stated signals).

>[!MORE_ LIKE_ THIS]
>
>* [Arbeiten mit Vergleichsoperatoren in traitbuilder](../features/traits/trait-comparison-operators.md)
>* [Reihenfolge der Vorgänge in traitbuilder-Ausdrücken](../features/traits/trait-operator-precedence.md)


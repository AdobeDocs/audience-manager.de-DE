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


# Boolesche Ausdrücke in Eigenschaften und Segmentaufbau{#boolean-expressions-in-trait-and-segment-builder}

In diesem Artikel wird erläutert, wie die Eigenschaften und Segmentwerkzeuge von Audience Manager die booleschen Ausdrücke UND, ODER und NOT verwenden.

<!-- 

c_tb_boolean.xml

 -->

**Boolesche Ausdrücke**

Die Boolesche Logik ist eine Verzweigung von algebra, die einige einfache Ausdrücke (oder Operatoren) verwendet, um zu bestimmen, ob eine Anweisung wahr oder false ist. Die am häufigsten verwendeten Operatoren sind [!UICONTROL AND], [!UICONTROL OR]und [!UICONTROL NOT]. Kombinationen dieser Ausdrücke helfen Ihnen, fokussierte Eigenschaften oder Segmentqualifizierungsregeln für Ihre Datenanforderungen eindeutig zu gestalten. Die folgende Abbildung zeigt, wie einfache boolesche Ausdrücke funktionieren.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>Der [!UICONTROL NOT] Operator verwendet eine implizite &quot;and&quot; -Bedingung und wird manchmal als [!UICONTROL AND NOT].

**Verwendung boolescher Ausdrücke in Eigenschaften und Segmentaufbau**

Sie erstellen Regeln für Eigenschaften und Segmentqualifizierungen mit booleschen Ausdrücken. In der folgenden Tabelle sind allgemeine bewährte Verfahren zum Erstellen von Qualifizierungskriterien mit [!UICONTROL AND], [!UICONTROL OR]und [!UICONTROL NOT]beschrieben.

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
   <td colname="col3"> <p>Benutzer <i>müssen</i> zu allen angegebenen Eigenschaften oder Segmenten gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>Weitgefasst, weniger fokussierte Zielgruppenqualifizierungsanforderungen. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>können</i> zu beliebigen Eigenschaften oder Segmenten gehören. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NICHT</span></b> </p> </td> 
   <td colname="col2"> <p>Eingeschränkte, fokussierte Zielgruppenqualifizierungsanforderungen. </p> <p>Nützlich, wenn es mehrere Bedingungen gibt, mit denen Anforderungen für die Zielgruppenqualifizierung schwierig oder ineffizient definiert werden können. Gelegentlich ist es einfacher, für Anforderungen, die ausschließlich ausgeschlossen werden, zu validieren. </p> </td> 
   <td colname="col3"> <p>Benutzer <i>dürfen nicht</i> zu einer ausgeschlossenen Eigenschaft oder einem Segment gehören. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Verwendungsfallbeispiel**

Der [!UICONTROL AND] Operator ist nützlich, wenn Sie die Anforderungen für die Trait-Mitgliedschaften leicht aufzählen. Angenommen, Sie müssen eine Zielgruppe von teuren Kamera-Käufern erstellen. » Mit einem Pixelmodell müssten Sie Pixel für Kameras und einen numerischen Preis auf Ihrer Seite erstellen und platzieren. Im Gegensatz dazu können Sie mit Eigenschaften Boolesche Operatoren anwenden, um beide Bedingungen (Preis für Kameras [!UICONTROL AND] ) zu verarbeiten. Das Ergebnis ist eine effiziente Datenerfassung mit weniger HTTP-Aufrufen, die wiederum die Benutzererfahrung auf Ihrer Site bewahrt.

**[!UICONTROL OR]Verwendungsfallbeispiel**

Der [!UICONTROL OR] Operator ist nützlich, wenn Sie Signale mit umfassenden Anforderungen an die Zielgruppenqualifikation erstellen möchten. Wenn Sie mehrere Anforderungen an Eigenschaften oder Segmentvoraussetzungen haben, wird der [!UICONTROL OR] Operator &quot;true&quot; bewertet, wenn die Besucher Ihrer Site *diese* Merkmale bereitstellen. [!UICONTROL OR] kann am nützlichsten sein, wenn Sie schnell eine breite Gruppe qualifizierter Site-Besucher erstellen möchten.

**[!UICONTROL AND NOT]Verwendungsfallbeispiel**

Der [!UICONTROL AND NOT] Operator ist nützlich, wenn es einfacher ist, eine Zielgruppe durch *Ausschluss* anstatt *durch Einbeziehung zu definieren*. Angenommen, Sie haben einen Verkauf und möchten Besucher in Kunden segmentieren, die nur Vollpreisartikel betrachten. Anstatt eine Liste mit Signalen für alle qualifizierenden Artikel oder Sonderpreisartikel zu erstellen, kann es einfacher sein, Besucher zu qualifizieren, wenn sie *kein Kaufpreiselement* gesehen haben. Dies ist verwaltungseffizient, da Sie im Vergleich zu den zum vollen Preis angebotenen Artikeln in der Regel weniger Artikel verkaufen. Mit einem Booleschen Wert [!UICONTROL NOT]*dürfen Besucher das Verkaufssignal nicht* so ausfüllen, dass es sich für eine Vollwertezielgruppe qualifiziert. Im Gegensatz dazu [!UICONTROL AND NOT] ist das Gegenteil des [!UICONTROL AND] Anwendungsszenarios, was gezeigt hat, wie die Zielgruppenmitgliedschaft durch Einbeziehung bestimmt wird (d. h. der Besucher qualifiziert auf 2 explizit festgelegte Signale).

>[!MORE_ LIKE_ THIS]
>
>* [Arbeiten mit Vergleichsoperatoren in traitbuilder](../features/traits/trait-comparison-operators.md)
>* [Reihenfolge der Vorgänge in traitbuilder-Ausdrücken](../features/traits/trait-operator-precedence.md)


---
description: Mit Segmentaufbau können Sie Trait-Regeln für ein Segment mithilfe eines Code-Editors erstellen. Klicken Sie im Bereich "Eigenschaften" auf die Registerkarte" Segmentausdrücke (Code-Ansicht)" , um auf diese Funktion zuzugreifen.
seo-description: Mit Segmentaufbau können Sie Trait-Regeln für ein Segment mithilfe eines Code-Editors erstellen. Klicken Sie im Bereich "Eigenschaften" auf die Registerkarte" Segmentausdrücke (Code-Ansicht)" , um auf diese Funktion zuzugreifen.
seo-title: Im Editor für den Segmentausdruck verwendete Code-Syntax
solution: Audience Manager
title: Im Editor für den Segmentausdruck verwendete Code-Syntax
uuid: 7 b 4 b 06 ca -7879-4501-8 ba 7-b 2 b 6467 b 8 a 3 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Im Editor für den Segmentausdruck verwendete Code-Syntax {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] Hiermit können Sie Eigenschaften für ein Segment mithilfe eines Code-Editors erstellen. Klicken Sie auf die **[!UICONTROL Segment Expressions (Code View)]** Registerkarte im [!UICONTROL Traits] Bedienfeld, um auf diese Funktion zuzugreifen.

## Syntax für Ausdrucksgenerator-Code

Sie können einem Segment mit Code Eigenschaften hinzufügen, anstatt Funktionen per Drag &amp; Drop zu verwenden. Ersetzen Sie bei der Kodierung kursiv hervorgehobene Elemente im Beispiel durch einen tatsächlichen Ausdruck oder Wert. Der Basiscode verwendet folgende Syntax:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Standardmäßig gelten [!DNL Boolean][!UICONTROL OR] Bedingungen für mehrere Eigenschaften *in einem* Ausdruck.

### Segmente mit booleschen Operatoren verbinden

Um Gruppen von Segmenten zu erstellen, schließen Sie die Frequenzfunktion in Klammern ein und legen Sie die Beziehung *zwischen den* einzelnen Ausdrücken mit einem [!DNL Boolean] Operator ([!UICONTROL AND][!UICONTROL OR], und [!UICONTROL NOT]) fest.

### Parameter

>[!NOTE]
>
>Alle Parameter sind erforderlich, falls nicht anders vermerkt.

| Name oder Variable | Beschreibung |
|---|---|
| `FREQUENCY` | Ein Literal, das dem Ausdruck vorausgeht. |
| ` [`&lt;`traitID`&gt;`T]` | Ein Array von Eigenschaften-IDs gefolgt vom Brief `T`. Trennen Sie mehrere Eigenschaften durch ein Komma. Beispiel, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Optional)* Legt Neuigkeitsregeln für Eigenschaften im Segment fest. Der Brief `D` zeigt die Neuigkeit in Tagen an. |
| ` <Frequency Operator><Numeric Value>` | Legt Häufigkeitsregeln zu Eigenschaften im Segment fest. |

### Zulässige Neuigkeit- und Häufigkeitsoperatoren

Legen [Sie Neuigkeit- und](../../features/segments/recency-and-frequency.md) Frequenzintervalle mit einem Vergleichsoperator und einer Ganzzahl fest. [!UICONTROL Segment Builder] verwendet Standardausdrücke wie &lt; (kleiner als), &gt; (größer als), = = (equal) usw. Die Typen von zulässigen Operatoren variieren jedoch, wenn Sie Neuigkeit oder Häufigkeit festlegen. In der folgenden Tabelle sind die zulässigen Neuigkeits-/Frequenzoperatoren aufgeführt.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Neuigkeit-Operatoren </th> 
   <th colname="col2" class="entry"> Häufigkeitsoperatoren </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt; = (größer als/gleich) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt; = (kleiner als/gleich) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt; = (größer als/gleich) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt; = (kleiner als/gleich) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">= = (equal to) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md)
>* [Boolesche Ausdrücke in Eigenschaften und Segmentaufbau](../../reference/boolean-expressions-tsb.md)
>* [Arbeiten mit Vergleichsoperatoren in traitbuilder](../../features/traits/trait-comparison-operators.md)
>* [Reihenfolge der Vorgänge in traitbuilder-Ausdrücken](../../features/traits/trait-operator-precedence.md)


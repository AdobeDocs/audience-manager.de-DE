---
description: Mit dem Segmentaufbau können Sie Eigenschaftenregeln für ein Segment mithilfe eines Code-Editors erstellen. Klicken Sie im Bereich "Eigenschaften"auf die Registerkarte "Ausdruck segmentieren (Code-Ansicht)", um auf diese Funktion zuzugreifen.
seo-description: Mit dem Segmentaufbau können Sie Eigenschaftenregeln für ein Segment mithilfe eines Code-Editors erstellen. Klicken Sie im Bereich "Eigenschaften"auf die Registerkarte "Ausdruck segmentieren (Code-Ansicht)", um auf diese Funktion zuzugreifen.
seo-title: Im Ausdruckseditor für Segmente verwendete Code-Syntax
solution: Audience Manager
title: Im Ausdruckseditor für Segmente verwendete Code-Syntax
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 11%

---


# Im Ausdruckseditor für Segmente verwendete Code-Syntax {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] können Sie Eigenschaftenregeln für ein Segment mithilfe eines Code-Editors erstellen. Klicken Sie im Bedienfeld [!UICONTROL Traits] auf die Registerkarte **[!UICONTROL Segment Expressions (Code View)]**, um auf diese Funktion zuzugreifen.

## Syntax des Ausdruck Builder-Codes

Sie können Eigenschaftsregeln zu einem Segment mit Code hinzufügen, anstatt Funktionen per Drag &amp; Drop zu verwenden. Ersetzen Sie beim Kodieren kursiv formatierte Elemente im Beispiel durch einen tatsächlichen Ausdruck oder Wert. Der Basiscode verwendet folgende Syntax:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Standardmäßig gelten [!DNL Boolean] [!UICONTROL OR]-Bedingungen für mehrere Eigenschaften *innerhalb* eines Ausdrucks.

### Verbinden von Segmenten mit booleschen Operatoren

Um Segmentgruppen zu erstellen, schließen Sie die Frequenzfunktion in Klammern ein und legen Sie die Beziehung *zwischen* jedem Ausdruck mit einem [!DNL Boolean]-Operator ([!UICONTROL AND], [!UICONTROL OR] und [!UICONTROL NOT]) fest.

### Parameter

>[!NOTE]
>
>Sofern nicht anders angegeben, sind alle Parameter erforderlich.

| Name oder Variable | Beschreibung |
|---|---|
| `FREQUENCY` | Ein Literal, das dem Ausdruck vorausgehen muss. |
| ` [`&lt;`traitID`>`T]` | Ein Array mit Eigenschaften-IDs, gefolgt vom Buchstaben `T`. Trennen Sie mehrere Eigenschaften durch ein Komma. Beispiel, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Optional)* Legt Neuigkeitsregeln für Eigenschaften im Segment fest. Der Buchstabe `D` gibt die Neuigkeit in Tagen an. |
| ` <Frequency Operator><Numeric Value>` | Legt Frequenzregeln für Eigenschaften im Segment fest. |

### Zulässige Neuigkeits- und Frequenzoperatoren

Stellen Sie die Intervalle [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md) mit einem Vergleichsoperator und einer Ganzzahl ein. [!UICONTROL Segment Builder] verwendet Standard-Ausdruck wie  &lt;> (größer als), == (gleich) usw. Die Typen der zulässigen Operatoren variieren jedoch, wenn Sie Neuigkeit oder Häufigkeit einstellen. Die nachstehende Tabelle Liste die zulässigen Neuigkeits-/Frequenzoperatoren.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Neuigkeitsoperatoren </th> 
   <th colname="col2" class="entry"> Frequenzoperatoren </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (größer als/gleich) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;&gt; </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (größer als/gleich) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;&gt; </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (gleich) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md)
>* [Boolesche Ausdruck in Trait und Segment Builder](../../reference/boolean-expressions-tsb.md)
>* [Arbeiten mit Vergleichsoperatoren in TraitBuilder](../../features/traits/trait-comparison-operators.md)
>* [Reihenfolge der Vorgänge in TraitBuilder-Ausdrücken](../../features/traits/trait-operator-precedence.md)


---
description: Mit Segment Builder können Sie Eigenschaftsregeln für ein Segment mithilfe eines Code-Editors erstellen. Klicken Sie im Bereich Eigenschaften auf die Registerkarte Segmentausdrücke (Codeansicht) , um auf diese Funktion zuzugreifen.
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: Im Ausdruckseditor für Segmente verwendete Code-Syntax
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 4%

---

# Im Ausdruckseditor für Segmente verwendete Code-Syntax {#code-syntax-used-in-the-segment-expression-editor}

Mit [!UICONTROL Segment Builder] können Sie Eigenschaftsregeln für ein Segment mithilfe eines Code-Editors erstellen. Klicken Sie auf die Registerkarte **[!UICONTROL Segment Expressions (Code View)]** im Bedienfeld [!UICONTROL Traits] , um auf diese Funktion zuzugreifen.

## Syntax des Ausdrucksgenerator-Codes

Sie können Eigenschaftsregeln zu einem Segment mit Code hinzufügen, anstatt Funktionen per Drag-and-Drop zu verwenden. Ersetzen Sie beim Kodieren kursiv gedruckte Elemente im Beispiel durch einen tatsächlichen Ausdruck oder Wert. Der Basis-Code verwendet die folgende Syntax:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Standardmäßig gelten [!DNL Boolean] [!UICONTROL OR] -Bedingungen für mehrere Eigenschaften *innerhalb* eines Ausdrucks.

### Verknüpfen von Segmenten mit booleschen Operatoren

Um Segmentgruppen zu erstellen, schließen Sie die Häufigkeitsfunktion in Klammern ein und legen Sie die Beziehung *zwischen* jedem Ausdruck mit einem [!DNL Boolean] -Operator ([!UICONTROL AND], [!UICONTROL OR] und [!UICONTROL NOT]) fest.

### Parameter

>[!NOTE]
>
>Sofern nicht anders angegeben, sind alle Parameter erforderlich.

| Name oder Variable | Beschreibung |
|---|---|
| `FREQUENCY` | Ein Literal, das vor dem Ausdruck stehen muss. |
| ` [`&lt;`traitID`>`T]` | Ein Array von Eigenschaften-IDs, gefolgt vom Buchstaben `T`. Trennen Sie mehrere Eigenschaften durch ein Komma. Beispiel: `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Optional)* Legt Neuigkeitsregeln für Eigenschaften im Segment fest. Der Buchstabe &quot;`D`&quot; gibt die Neuigkeit in Tagen an. |
| ` <Frequency Operator><Numeric Value>` | Legt Frequenzregeln für Eigenschaften im Segment fest. |

### Zulässige Neuigkeit und Häufigkeit

Legen Sie die Intervalle [Neuigkeit und Häufigkeit](../../features/segments/recency-and-frequency.md) mit einem Vergleichsoperator und einer Ganzzahl fest. [!UICONTROL Segment Builder] verwendet Standardausdrücke wie &lt; (kleiner als), > (größer als), == (gleich) usw. Die Typen der zulässigen Operatoren variieren jedoch, wenn Sie Neuigkeit oder Häufigkeit festlegen. In der folgenden Tabelle sind die zulässigen Neuigkeits-/Frequenzoperatoren aufgeführt.

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
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (größer/gleich) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= (kleiner/gleich) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (größer/gleich) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= (kleiner/gleich) </li> 
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

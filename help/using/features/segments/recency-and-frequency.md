---
description: Mit Segment Builder können Sie mit „Aktualität“ und „Häufigkeit“ Besuchende anhand von Aktionen segmentieren, die in einem bestimmten täglichen Intervall auftreten oder sich wiederholen.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: Neuigkeit und Häufigkeit
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 1%

---

# Neuigkeit und Häufigkeit {#recency-and-frequency}

Mit Neuigkeit und Häufigkeit können Sie Besuchende [!UICONTROL Segment Builder] anhand von Aktionen segmentieren, die in einem bestimmten täglichen Intervall auftreten oder sich wiederholen.

Audience Manager definiert [!DNL recency] und [!DNL frequency] wie folgt:

* **[!UICONTROL Recency]:**, wie kürzlich ein Benutzer eine (oder mehrere) [!UICONTROL traits] angezeigt oder sich dafür qualifiziert hat.
* **[!UICONTROL Frequency]:** Die Rate, mit der ein Benutzer eine (oder mehrere) [!UICONTROL traits] angezeigt oder sich dafür qualifiziert hat.

Mit [!UICONTROL Recency]- und [!UICONTROL Frequency] können Sie Besucherinnen und Besucher anhand ihres tatsächlichen (oder wahrgenommenen) Interesses an einer Site, einem Bereich oder einer bestimmten Kreativität segmentieren. Beispielsweise können Benutzende, die sich für ein Segment mit hohen Neuigkeits-/Häufigkeitsanforderungen qualifizieren, stärker an einer Site oder einem Produkt interessiert sein als Benutzende, die seltener oder seltener zu Besuch kommen.

## Speicherort der [!UICONTROL Recency and Frequency] {#location}

In [!UICONTROL Segment Builder] befinden sich [!UICONTROL Recency]- und [!UICONTROL Frequency] im Abschnitt [!UICONTROL Basic View] des [!UICONTROL Traits]. Klicken Sie auf das Uhrensymbol, um diese Steuerelemente anzuzeigen.

![](assets/recency_frequency.png)

## Einschränkungen und Regeln {#limitations-rules}

Überprüfen und verstehen Sie diese Beschränkungen und Regeln, wenn Sie die Neuigkeit und Häufigkeit auf Eigenschaften in Ihren Segmenten anwenden möchten.

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beschränkung oder Regel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Mindestwert</b> </p> </td> 
   <td colname="col2"> <p>Neuigkeit muss größer als 0 sein. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaftstypen</b> </p> </td> 
   <td colname="col2"> <p>Sie können nur auf regelbasierte und Ordnereigenschaften Neuigkeitskontrollen anwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaften von Drittanbietern</b> </p> </td> 
   <td colname="col2"> <p>Sie können keine Neuigkeitsregeln für einzelne Drittanbieter-Eigenschaften oder -Eigenschaftsgruppen festlegen, die Drittanbieter-Eigenschaften enthalten. Neuigkeit und Häufigkeit gelten nur für Ihre eigenen Eigenschaften. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beschränkung oder Regel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaften von Drittanbietern</b> </p> </td> 
   <td colname="col2"> <p>Sie können keine Häufigkeitsregeln für einzelne Drittanbieter-Eigenschaften oder -Eigenschaftsgruppen festlegen, die Drittanbieter-Eigenschaften enthalten. Neuigkeit und Häufigkeit gelten nur für Ihre eigenen Eigenschaften. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaftstypen</b> </p> </td> 
   <td colname="col2"> <p>Häufigkeitskontrollen können nur auf regelbasierte und Ordnereigenschaften angewendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Neuigkeitsanforderungen</b> </p> </td> 
   <td colname="col2"> <p>Sie können die Häufigkeitsanforderungen konfigurieren <i>ohne </i> zu konfigurieren. Legen Sie einfach einen Häufigkeitswert fest und lassen Sie das Feld „Aktualität“ leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profilzusammenführungsrichtlinien</b> </p> </td> 
   <td colname="col2"> <p>Siehe <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules">, Diagramme für externe Geräte und Profilzusammenführungsregeln</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele aus der letzten Zeit {#recency-examples}

Im Folgenden finden Sie zwei Beispiele dafür, wie die Neuigkeit je nach Ihrer Auswahl in der Benutzeroberfläche funktioniert:

### Verwendung eines Operators, der kleiner oder gleich ist (&lt;=)

![Kleiner als gleich](assets/less-than-equal-to.png)

In diesem Beispiel wählen Sie den Operator &lt;= aus, wie im Screenshot gezeigt. Dadurch wird Ihr Benutzer für die [!UICONTROL segment] qualifiziert, wenn er innerhalb der letzten fünf Tage mindestens dreimal für einen der drei [!UICONTROL traits] qualifiziert ist. Die folgende Zeitleiste zeigt die [!UICONTROL segment] zum Zeitpunkt der Erstellung der [!UICONTROL segment], am 1. Oktober und zehn Tage später.

![Letzte fünf Tage](assets/last-5-days.png)

### Verwendung eines Operators, der größer oder gleich ist (=>)

![Größer-als-gleich](assets/greater-than-equal-to.png)

In diesem Beispiel wählen Sie den Operator =>, wie im Screenshot gezeigt. Dadurch werden Benutzer für die [!UICONTROL segment] qualifiziert, wenn sie sich zwischen ihrer ersten Qualifizierung auf der Audience Manager-Plattform und dem Stichtag vor fünf Tagen mindestens dreimal für eine der drei [!UICONTROL traits] qualifizieren. Die folgende Zeitleiste zeigt die [!UICONTROL segment] zum Zeitpunkt der Erstellung der [!UICONTROL segment], am 1. Oktober und zehn Tage später.

![Early-Qualification](assets/earlier-qualification.png)


## Beispiele für Frequenzlimitierungen {#frequency-capping}

Ausdrücke zur Frequenzlimitierung schließen alle Benutzer ein, deren Anzahl [!UICONTROL trait] Realisierungen unter einem gewünschten Wert liegt. Im Folgenden finden Sie einige Beispiele für Richtig und Falsch:

* Falsch - Der `frequency([1000T]) <= 5` umfasst alle Benutzer, die die [!UICONTROL trait] mit der ID „1000“ maximal fünfmal realisiert haben, aber auch Benutzer, die die [!UICONTROL trait] nicht realisiert haben. Daher validiert Audience Manager diesen Ausdruck aus Leistungsgründen nicht, da dies zu viele Benutzende für die [!UICONTROL segment] qualifizieren würde.

* Rechts : Wenn Sie alle Benutzer einbeziehen möchten, die die [!UICONTROL trait] mit der ID „1000“ maximal fünfmal realisiert haben, fügen Sie eine weitere Bedingung zum Ausdruck hinzu, um sicherzustellen, dass die Benutzer sich mindestens einmal für die [!UICONTROL trait] qualifiziert haben: `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Rechts: Wenn Sie möchten, dass die Neuigkeits-/Häufigkeitsanforderungen weniger als eine bestimmte Anzahl von Malen oder Tagen betragen, verbinden Sie diese [!UICONTROL trait] mit einem `AND`. Unter Verwendung des Beispiels im ersten Aufzählungspunkt wird dieser Ausdruck gültig, wenn er mit einem anderen [!UICONTROL trait] verbunden wird, wie hier gezeigt: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Rechts : Für Anwendungsfälle mit Frequenzlimitierung in der Werbung können Sie eine [!UICONTROL segment] Regel wie die folgende erstellen: `(frequency([1000T] <= 2D) >= 5)`. Dieser Ausdruck enthält alle Benutzenden, die die [!UICONTROL trait] mit der ID „1000“ in den letzten 2 Tagen mindestens fünfmal realisiert haben. Legen Sie die Frequenzlimitierung fest, indem Sie diese [!UICONTROL segment] an den Anzeigenserver senden, wobei ein `NOT` auf dem [!UICONTROL segment] im Anzeigenserver festgelegt ist. Dieser Ansatz erreicht eine höhere Leistung bei der [!DNL Audience Manager] und erfüllt dennoch denselben Zweck für die Frequenzlimitierung.

>[!MORELIKETHIS]
>
>* [Segment Builder-Steuerelemente: Abschnitt „Eigenschaften“](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Im Ausdruckseditor für Segmente verwendete Code-Syntax](../../features/segments/segment-code-syntax.md)

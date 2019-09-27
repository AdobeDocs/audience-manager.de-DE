---
description: Im Segmentaufbau können Sie mit Neuigkeit und Häufigkeit Besucher basierend auf Aktionen segmentieren, die in einem bestimmten Tagesintervall stattfinden oder sich wiederholen.
seo-description: Im Segmentaufbau können Sie mit Neuigkeit und Häufigkeit Besucher basierend auf Aktionen segmentieren, die in einem bestimmten Tagesintervall stattfinden oder sich wiederholen.
seo-title: Neuigkeit und Häufigkeit
solution: Audience Manager
title: Neuigkeit und Häufigkeit
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c7e8b67ccad4479487b471668462937c5be6be34

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager definiert [!DNL recency] und [!DNL frequency] wie folgt:

* **[!UICONTROL Recency]** : Wie kürzlich hat ein Benutzer eine (oder mehrere) Eigenschaften angezeigt oder qualifiziert.
* **[!UICONTROL Frequency]** : Die Rate, mit der ein Benutzer eine (oder mehrere) Eigenschaft angezeigt oder qualifiziert hat.

[!UICONTROL Recency] und [!UICONTROL Frequency] Einstellungen helfen Ihnen, Besucher basierend auf ihrem tatsächlichen (oder wahrgenommenen) Interesse an einer Site, einem Abschnitt oder einem bestimmten kreativen Element zu segmentieren. Benutzer, die sich beispielsweise für ein Segment mit hohen Anforderungen an Aktualität und Häufigkeit qualifizieren, sind möglicherweise mehr an einer Site oder einem Produkt interessiert als Benutzer, die die Site oder das Produkt seltener oder seltener besuchen.

## Ort der Neuigkeits- und Häufigkeitseinstellungen {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] und [!UICONTROL Frequency] Einstellungen befinden sich im [!UICONTROL Basic View] Abschnitt des [!UICONTROL Traits] Bedienfelds. Klicken Sie auf das Uhrensymbol, um diese Steuerelemente anzuzeigen.

![](assets/recency_frequency.png)

## Einschränkungen und Regeln {#limitations-rules}

Überprüfen und verstehen Sie diese Beschränkungen und Regeln, wenn Sie Neuigkeit und Häufigkeit auf Eigenschaften in Ihren Segmenten anwenden möchten.

### Neuigkeit

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Grenze oder Regel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Mindestwert</b> </p> </td> 
   <td colname="col2"> <p>Die Neuigkeit muss größer als 0 sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaften von Drittanbietern</b> </p> </td> 
   <td colname="col2"> <p>Sie können keine Neuigkeitsregeln für einzelne Eigenschaften oder Eigenschaftsgruppen von Drittanbietern festlegen, die Eigenschaften von Drittanbietern enthalten. Neuigkeit und Häufigkeit gelten nur für Ihre eigenen Eigenschaften. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Häufigkeit

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Grenze oder Regel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaften von Drittanbietern</b> </p> </td> 
   <td colname="col2"> <p>Sie können keine Frequenzregeln für einzelne Eigenschaften oder Eigenschaftsgruppen von Drittanbietern festlegen, die Eigenschaften von Drittanbietern enthalten. Neuigkeit und Häufigkeit gelten nur für Ihre eigenen Eigenschaften. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Neuigkeitsanforderungen</b> </p> </td> 
   <td colname="col2"> <p>Sie können Frequenzanforderungen konfigurieren, <i>ohne</i> die Neuigkeitsanforderungen zu konfigurieren. Legen Sie einfach einen Frequenzwert fest und lassen Sie das Neuigkeitsfeld leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regeln zum Profilzusammenführen</b> </p> </td> 
   <td colname="col2"> <p>Siehe <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Eigenschafts-, externe Gerätediagramme und Regeln</a>zur Profilzusammenführung. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele zu Neuigkeiten {#recency-examples}

Die folgenden zwei Beispiele zeigen, wie die Neuigkeit funktioniert, je nach Auswahl in der Benutzeroberfläche:

### Verwenden eines Kleiner-als-Zeichen-Operators (&lt;=)

![Kleiner als gleich](assets/less-than-equal-to.png)

In this example, you select the &lt;= operator, as shown in the screenshot. This qualifies your user for the segment if they qualify for any of the three traits a minimum of three times within the last five days. The timeline below shows the segment qualification at the time the segment is created, on October 1st, and ten days later.

![Last-five-days](assets/last-5-days.png)

### Using a greater than or equal to operator (=&gt;)

![Greater-than-equal-to](assets/greater-than-equal-to.png)

In this example, you select the =&gt; operator, as shown in the screenshot. This qualifies your user for the segment if they qualify for any of the three traits a minimum of three times anytime between their first qualification on the Audience Manager platform and the cut-off time five days ago. The timeline below shows the segment qualification at the time the segment is created, on October 1st, and ten days later.

![Earlier-qualification](assets/earlier-qualification.png)


## Frequency Capping Examples {#frequency-capping}

Ausdrücke für die Frequenzbegrenzung umfassen alle Benutzer, deren Anzahl an Eigenschaften unter dem gewünschten Wert liegt. Here are a few examples:

* The expression  includes all users that have realized the trait with the ID "1000" a maximum of five times, including users who have not realized the trait.`frequency([1000T]) <= 5`
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an  operator. `AND` Using the example above, this expression becomes valid when joined with another trait as shown here: .`frequency([1000T]) <= 5 AND isSiteVisitorTrait`

* Für Anwendungsfälle mit der Frequenzbegrenzung für Werbung können Sie eine Segmentregel wie die folgende erstellen: `(frequency([1000T] <= 2D) >= 5)`. Dieser Ausdruck umfasst alle Benutzer, die die Eigenschaft mit der ID "1000"in den letzten 2 Tagen mindestens fünfmal erkannt haben. Legen Sie die Frequenzgrenze fest, indem Sie dieses Segment mit einem `NOT` Satz im Segment im Anzeigenserver an den Anzeigen-Server senden. Dieser Ansatz erreicht eine höhere Leistung bei [!DNL Audience Manager] gleichzeitiger Verwendung des gleichen Zwecks für die Frequenzzuordnung.

>[!MORE_LIKE_THIS]
>
>* [Segmentaufbau-Steuerelemente: Eigenschaftenabschnitt](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Im Segmentausdruckseditor verwendete Code-Syntax](../../features/segments/segment-code-syntax.md)


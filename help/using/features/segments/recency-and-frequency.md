---
description: In Segmentaufbau können Sie anhand von Neuigkeit und Häufigkeit Besucher basierend auf Aktionen segmentieren, die über ein bestimmtes Tagesintervall auftreten oder sich wiederholen.
seo-description: In Segmentaufbau können Sie anhand von Neuigkeit und Häufigkeit Besucher basierend auf Aktionen segmentieren, die über ein bestimmtes Tagesintervall auftreten oder sich wiederholen.
seo-title: Neuigkeit und Häufigkeit
solution: Audience Manager
title: Neuigkeit und Häufigkeit
uuid: faadd 18 a-bf 27-4 b 73-995 e -9809 f 52 f 5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]:** Die Anzahl der Tage, in denen ein Benutzer eine (oder mehr) Eigenschaften angesehen oder für diese qualifiziert hat.
* **[!UICONTROL Frequency]:** Die Rate, mit der ein Benutzer eine (oder mehr) Eigenschaften angesehen oder für diese qualifiziert hat.

[!UICONTROL Recency] Mithilfe [!UICONTROL Frequency] von Einstellungen können Sie Besucher anhand ihrer tatsächlichen (oder wahrgenommenen) Zielwertstufe auf einer Site, einem Abschnitt oder einem bestimmten Kreativen segmentieren. Beispielsweise könnten Benutzer, die sich für ein Segment mit hohen Neuigkeits-/Häufigkeitsanforderungen qualifizieren, an einer Site oder einem Produkt interessiert sein als Benutzer, die seltener oder weniger häufig besuchen.

## Location of Recency and Frequency Settings {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] and [!UICONTROL Frequency] settings are located in the [!UICONTROL Basic View] section of the [!UICONTROL Traits] panel. Klicken Sie auf das Uhrsymbol, um diese Steuerelemente anzuzeigen.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

Prüfen und verstehen Sie diese Beschränkungen und Regeln, wenn Sie Neuigkeit und Häufigkeit auf Eigenschaften in Ihren Segmenten anwenden möchten.

### Neuigkeit

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit oder Regel </th> 
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
   <td colname="col2"> <p>Sie können keine Neuigkeitsregeln für Eigenschaften von Drittanbietern oder Eigenschaftsgruppen mit Eigenschaften von Drittanbietern festlegen. Neuigkeit und Häufigkeit gelten nur für Ihre eigenen Eigenschaften. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Häufigkeit

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit oder Regel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaften von Drittanbietern</b> </p> </td> 
   <td colname="col2"> <p>Sie können keine Häufigkeitsregeln für Eigenschaften von Drittanbietern oder Trait-Gruppen festlegen, die Eigenschaften von Drittanbietern enthalten. Neuigkeit und Häufigkeit gelten nur für Ihre eigenen Eigenschaften. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Neuigkeitsanforderungen</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements <i>without</i> configuring recency requirements. Legen Sie einfach einen Frequenzwert fest und lassen Sie das Neuigkeit-Feld leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regeln für die Profilzusammenführung</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequency Capping Examples {#frequency-capping}

Zum Zwischenspeichern von Ausdrücken zählen alle Benutzer, deren Anzahl der Eigenschaften unter dem gewünschten Wert liegt. Beispiele:

* The expression `frequency([1000T]) <= 5` includes all users that have realized the trait with the ID &quot;1000&quot; a maximum of five times, including users who have not realized the trait.
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an `AND` operator. Using the example above, this expression becomes valid when joined with another trait as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* For advertising frequency-capping use cases, you could create a segment rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. Dieser Ausdruck enthält alle Benutzer, die die Eigenschaft mit der ID &quot;1000&quot; in den letzten 2 Tagen mindestens fünfmal lokalisiert haben. Set frequency capping by sending this segment to the ad server with a `NOT` set on the segment in the ad server. This approach achieves greater performance in [!DNL Audience Manager] while still serving the same purpose for frequency capping.

>[!MORE_ LIKE_ THIS]
>
>* [Steuerelemente für Segmentaufbau: Abschnitt &quot;Eigenschaften «](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Im Editor für den Segmentausdruck verwendete Code-Syntax](../../features/segments/segment-code-syntax.md)


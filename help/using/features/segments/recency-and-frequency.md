---
description: Im Segmentaufbau können Sie mit Neuigkeit und Häufigkeit Besucher basierend auf Aktionen segmentieren, die in einem bestimmten Tagesintervall stattfinden oder sich wiederholen.
seo-description: Im Segmentaufbau können Sie mit Neuigkeit und Häufigkeit Besucher basierend auf Aktionen segmentieren, die in einem bestimmten Tagesintervall stattfinden oder sich wiederholen.
seo-title: Neuigkeit und Häufigkeit
solution: Audience Manager
title: Neuigkeit und Häufigkeit
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: 1cbff10b9e978755e139e7d5b996249de5ebb5bd

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder]Neuigkeit und Häufigkeit können Sie Besucher basierend auf Aktionen segmentieren, die in einem bestimmten Tagesintervall stattfinden oder sich wiederholen.

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
   <td colname="col1"> <p> <b>Eigenschaftstypen</b> </p> </td> 
   <td colname="col2"> <p>Sie können Neuigkeitssteuerelemente nur auf regelbasierte und Ordnereigenschaften anwenden. </p> </td> 
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
   <td colname="col2"> <p>Sie können keine Frequenzregeln für einzelne Eigenschaften oder Eigenschaftsgruppen von Drittanbietern festlegen, die Eigenschaften von Drittanbietern enthalten. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Trait Types</b> </p> </td> 
   <td colname="col2"> <p>You can apply frequency controls to rule-based and folder traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Recency Requirements</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements without configuring recency requirements. <i></i> Just set a frequency value and leave the recency field blank. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profile Merge Rules</b> </p> </td> 
   <td colname="col2"> <p>See  Trait Frequency, External Device Graphs, and Profile Merge Rules.<a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"></a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recency Examples {#recency-examples}

Here are two examples of how recency works, depending on your selection in the UI:

### Using a less than or equal to operator (&lt;=)

![Less-than-equal-to](assets/less-than-equal-to.png)

In this example, you select the &lt;= operator, as shown in the screenshot. This qualifies your user for the segment if they qualify for any of the three traits a minimum of three times within the last five days. The timeline below shows the segment qualification at the time the segment is created, on October 1st, and ten days later.

![Letzte fünf Tage](assets/last-5-days.png)

### Verwenden eines Größer- oder Gleichheitszeichens (=&gt;)

![Größer als gleich](assets/greater-than-equal-to.png)

In diesem Beispiel wählen Sie den Operator =&gt;, wie im Screenshot dargestellt. Dadurch wird Ihr Benutzer für das Segment qualifiziert, wenn er zwischen der ersten Qualifizierung auf der Audience Manager-Plattform und der Unterbrechung vor fünf Tagen mindestens dreimal für eine der drei Eigenschaften qualifiziert ist. Die nachstehende Zeitschiene zeigt die Segmentqualifikation zum Zeitpunkt der Segmenterstellung, am 1. Oktober und zehn Tage später.

![Frühere Qualifizierung](assets/earlier-qualification.png)


## Beispiele für Frequenzzuordnung {#frequency-capping}

Ausdrücke für die Frequenzbegrenzung umfassen alle Benutzer, deren Anzahl an Eigenschaften unter dem gewünschten Wert liegt. Im Folgenden finden Sie einige Beispiele zu Recht und falsch:

* Falsch - Der Ausdruck `frequency([1000T]) <= 5` umfasst alle Benutzer, die die Eigenschaft mit der ID "1000"maximal fünfmal erkannt haben, aber auch Benutzer, die die Eigenschaft nicht erkannt haben. Deshalb validiert Audience Manager diesen Ausdruck nicht aus Leistungsgründen, da er zu viele Benutzer für das Segment qualifiziert.

* Recht: Wenn Sie alle Benutzer einbeziehen möchten, die die Eigenschaft mit der ID "1000"maximal fünfmal erfüllt haben, fügen Sie dem Ausdruck eine weitere Bedingung hinzu, um sicherzustellen, dass die Benutzer mindestens einmal für die Eigenschaft qualifiziert sind:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Rechts- Wenn Sie möchten, dass die Neuigkeits-/Frequenzanforderungen weniger als eine bestimmte Anzahl von Malen oder Tagen betragen, verbinden Sie diese Eigenschaft mit einem anderen `AND` Operator. Anhand des Beispiels im ersten Aufzählungspunkt wird dieser Ausdruck gültig, wenn er mit einer anderen Eigenschaft verbunden wird, wie im Folgenden gezeigt: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Right - Für Anwendungsfälle mit der Beschränkung der Werbefrequenz können Sie eine Segmentregel wie die folgende erstellen: `(frequency([1000T] <= 2D) >= 5)`. Dieser Ausdruck umfasst alle Benutzer, die die Eigenschaft mit der ID "1000"in den letzten 2 Tagen mindestens fünfmal erkannt haben. Legen Sie die Frequenzgrenze fest, indem Sie dieses Segment mit einem `NOT` Satz im Segment im Anzeigenserver an den Anzeigen-Server senden. Dieser Ansatz erreicht eine höhere Leistung bei [!DNL Audience Manager] gleichzeitiger Verwendung des gleichen Zwecks für die Frequenzzuordnung.

>[!MORE_LIKE_THIS]
>
>* [Segmentaufbau-Steuerelemente: Eigenschaftenabschnitt](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Im Segmentausdruckseditor verwendete Code-Syntax](../../features/segments/segment-code-syntax.md)


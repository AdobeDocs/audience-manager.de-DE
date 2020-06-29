---
description: Im Segmentaufbau können Sie mit Neuigkeit und Häufigkeit Besucher basierend auf Aktionen segmentieren, die in einem bestimmten Tagesintervall stattfinden oder sich wiederholen.
seo-description: Im Segmentaufbau können Sie mit Neuigkeit und Häufigkeit Besucher basierend auf Aktionen segmentieren, die in einem bestimmten Tagesintervall stattfinden oder sich wiederholen.
seo-title: Neuigkeit und Häufigkeit
solution: Audience Manager
title: Neuigkeit und Häufigkeit
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder]Neuigkeit und Häufigkeit können Sie Besucher basierend auf Aktionen segmentieren, die in einem bestimmten Tagesintervall stattfinden oder sich wiederholen.

Audience Manager definiert [!DNL recency] und [!DNL frequency] wie folgt:

* **[!UICONTROL Recency]:**Wie kürzlich hat ein Benutzer eine (oder mehrere) Datei angezeigt oder qualifiziert[!UICONTROL traits].
* **[!UICONTROL Frequency]:**Die Rate, mit der ein Benutzer eine Anzeige oder Qualifikation für eine (oder mehrere)[!UICONTROL traits]durchgeführt hat.

[!UICONTROL Recency] und [!UICONTROL Frequency] Einstellungen helfen Ihnen, Besucher basierend auf ihrem tatsächlichen (oder wahrgenommenen) Interesse an einer Site, einem Abschnitt oder einem bestimmten kreativen Element zu segmentieren. Benutzer, die sich beispielsweise für ein Segment mit hohen Anforderungen an Aktualität und Häufigkeit qualifizieren, sind möglicherweise mehr an einer Site oder einem Produkt interessiert als Benutzer, die die Site oder das Produkt seltener oder seltener besuchen.

## Speicherort der [!UICONTROL Recency and Frequency] Einstellungen {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] und [!UICONTROL Frequency] Einstellungen befinden sich im [!UICONTROL Basic View] Abschnitt des [!UICONTROL Traits] Bedienfelds. Klicken Sie auf das Uhrensymbol, um diese Steuerelemente anzuzeigen.

![](assets/recency_frequency.png)

## Einschränkungen und Regeln {#limitations-rules}

Überprüfen und verstehen Sie diese Beschränkungen und Regeln, wenn Sie Neuigkeit und Häufigkeit auf Eigenschaften in Ihren Segmenten anwenden möchten.

### [!UICONTROL Recency] {#recency}

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

### [!UICONTROL Frequency] {#frequency}

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
   <td colname="col1"> <p> <b>Eigenschaftstypen</b> </p> </td> 
   <td colname="col2"> <p>Sie können Frequenzsteuerelemente nur auf regelbasierte und Ordnereigenschaften anwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Neuigkeitsanforderungen</b> </p> </td> 
   <td colname="col2"> <p>Sie können Frequenzanforderungen konfigurieren, <i>ohne</i> die Neuigkeitsanforderungen zu konfigurieren. Legen Sie einfach einen Frequenzwert fest und lassen Sie das Neuigkeitsfeld leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regeln zum Zusammenführen von Profilen</b> </p> </td> 
   <td colname="col2"> <p>Siehe <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Eigenschafts-, externe Gerätediagramme und Profil-Zusammenführungsregeln</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele zu Neuigkeiten {#recency-examples}

Die folgenden zwei Beispiele zeigen, wie die Neuigkeit funktioniert, je nach Auswahl in der Benutzeroberfläche:

### Verwenden eines Kleiner-als-Zeichen-Operators (&lt;=)

![Kleiner als gleich](assets/less-than-equal-to.png)

In diesem Beispiel wählen Sie den Operator &lt;= aus, wie im Screenshot dargestellt. Dies qualifiziert Ihren Benutzer für die , [!UICONTROL segment] wenn er innerhalb der letzten fünf Tage mindestens drei [!UICONTROL traits] Mal berechtigt ist. Die nachstehende Zeitschiene zeigt die [!UICONTROL segment] Qualifikation zum Zeitpunkt der Erstellung des Dokuments, am 1. Oktober und zehn Tage später [!UICONTROL segment] an.

![Letzte fünf Tage](assets/last-5-days.png)

### Verwenden eines Größer- oder Gleichheitszeichens (=>)

![Größer als gleich](assets/greater-than-equal-to.png)

In diesem Beispiel wählen Sie den Operator =>, wie im Screenshot dargestellt. Dies qualifiziert Ihren Benutzer für die [!UICONTROL segment] dann, wenn er zwischen der ersten Qualifikation auf der Audience Manager-Plattform und der Sperrzeit vor fünf Tagen mindestens drei [!UICONTROL traits] - und dreimal berechtigt ist. Die nachstehende Zeitschiene zeigt die [!UICONTROL segment] Qualifikation zum Zeitpunkt der Erstellung des Dokuments, am 1. Oktober und zehn Tage später [!UICONTROL segment] an.

![Frühere Qualifizierung](assets/earlier-qualification.png)


## Beispiele für Frequenzzuordnung {#frequency-capping}

Häufigkeitsbeschränkende Ausdruck umfassen alle Benutzer, deren Anzahl an [!UICONTROL trait] Erkennungen unter dem gewünschten Wert liegt. Im Folgenden finden Sie einige Beispiele zu Recht und falsch:

* Falsch - Der Ausdruck `frequency([1000T]) <= 5` umfasst alle Benutzer, die die [!UICONTROL trait] mit der ID &quot;1000&quot;maximal fünfmal implementiert haben, aber auch Benutzer, die die ID nicht erkannt haben [!UICONTROL trait]. Daher validiert Audience Manager diesen Ausdruck aus Leistungsgründen nicht, da er zu viele Benutzer für den [!UICONTROL segment]Dienst qualifizieren würde.

* Recht: Wenn Sie alle Benutzer einbeziehen möchten, die die [!UICONTROL trait] ID &quot;1000&quot;maximal fünfmal verwendet haben, fügen Sie dem Ausdruck eine weitere Bedingung hinzu, um sicherzustellen, dass die Benutzer sich für die [!UICONTROL trait] Mindestanzahl der folgenden Punkte qualifiziert haben:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Rechts- Wenn Sie möchten, dass die Neuigkeits-/Frequenzanforderungen kleiner als eine bestimmte Anzahl von Malen oder Tagen sein müssen, verbinden Sie diese [!UICONTROL trait] mit einem anderen Operator `AND` . Anhand des Beispiels im ersten Aufzählungspunkt wird dieser Ausdruck gültig, wenn er mit einem anderen verbunden wird, [!UICONTROL trait] wie im Folgenden gezeigt: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Right - Für Anwendungsfälle mit Frequenzzuordnung, bei denen die Häufigkeit der Werbung begrenzt ist, können Sie eine ähnliche [!UICONTROL segment] Regel erstellen: `(frequency([1000T] <= 2D) >= 5)`. Dieser Ausdruck umfasst alle Benutzer, die die ID &quot;1000&quot;in den letzten 2 Tagen mindestens fünfmal [!UICONTROL trait] implementiert haben. Legen Sie eine Frequenzgrenze fest, indem Sie diese [!UICONTROL segment] an den Anzeigen-Server mit einem `NOT` Satz auf dem [!UICONTROL segment] Anzeigen-Server senden. Dieser Ansatz erreicht eine höhere Leistung bei [!DNL Audience Manager] gleichzeitiger Verwendung des gleichen Zwecks für die Frequenzzuordnung.

>[!MORELIKETHIS]
>
>* [Segmentaufbau-Steuerelemente: Eigenschaftenabschnitt](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Im Segment-Ausdruck-Editor verwendete Code-Syntax](../../features/segments/segment-code-syntax.md)


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
ht-degree: 3%

---


# Neuigkeit und Häufigkeit {#recency-and-frequency}

In [!UICONTROL Segment Builder] können Sie Besucher anhand von Neuigkeiten und Häufigkeit basierend auf Aktionen segmentieren, die in einem bestimmten Tagesintervall stattfinden oder wiederholt werden.

Audience Manager definiert [!DNL recency] und [!DNL frequency] wie folgt:

* **[!UICONTROL Recency]:** Wie kürzlich ein Benutzer für einen (oder mehrere) Benutzer angezeigt oder qualifiziert hat  [!UICONTROL traits].
* **[!UICONTROL Frequency]:** Die Rate, mit der ein Benutzer eine Anzeige oder Qualifikation für einen (oder mehrere) Benutzer angezeigt oder qualifiziert hat  [!UICONTROL traits].

[!UICONTROL Recency] und  [!UICONTROL Frequency] Einstellungen helfen Ihnen, Besucher basierend auf ihrem tatsächlichen (oder wahrgenommenen) Interesse an einer Site, einem Abschnitt oder einem bestimmten kreativen Element zu segmentieren. Benutzer, die sich beispielsweise für ein Segment mit hohen Anforderungen an Aktualität und Häufigkeit qualifizieren, sind möglicherweise mehr an einer Site oder einem Produkt interessiert als Benutzer, die die Site oder das Produkt seltener oder seltener besuchen.

## Speicherort von [!UICONTROL Recency and Frequency] Einstellungen {#location}

Die Einstellungen für [!UICONTROL Segment Builder] und [!UICONTROL Recency] befinden sich im Abschnitt [!UICONTROL Basic View] des Bedienfelds [!UICONTROL Traits]. [!UICONTROL Frequency] Klicken Sie auf das Uhrensymbol, um diese Steuerelemente anzuzeigen.

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
   <td colname="col2"> <p>Sie können die Frequenzanforderungen <i>konfigurieren, ohne die Neuigkeitsanforderungen zu konfigurieren. </i> Legen Sie einfach einen Frequenzwert fest und lassen Sie das Neuigkeitsfeld leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profilzusammenführungsrichtlinien</b> </p> </td> 
   <td colname="col2"> <p>Siehe <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Eigenschaftsfrequenz, externe Gerätediagramme und Profil-Zusammenführungsregeln</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele für Neuigkeiten {#recency-examples}

Die folgenden zwei Beispiele zeigen, wie die Neuigkeit funktioniert, je nach Auswahl in der Benutzeroberfläche:

### Verwenden eines Kleiner-als-Zeichen-Operators (&lt;=)

![Kleiner als gleich](assets/less-than-equal-to.png)

In diesem Beispiel wählen Sie den Operator &lt;= aus, wie im Screenshot dargestellt. Dies qualifiziert Ihren Benutzer für das [!UICONTROL segment], wenn er sich innerhalb der letzten fünf Tage für eines der drei [!UICONTROL traits] mindestens dreimal qualifiziert. Die nachstehende Zeitschiene zeigt die [!UICONTROL segment]-Qualifikation zum Zeitpunkt der Erstellung des [!UICONTROL segment], am 1. Oktober und zehn Tage später.

![Letzte fünf Tage](assets/last-5-days.png)

### Verwenden eines Größer- oder Gleichheitszeichens (=>)

![Größer als gleich](assets/greater-than-equal-to.png)

In diesem Beispiel wählen Sie den Operator =>, wie im Screenshot dargestellt. Dies qualifiziert Ihren Benutzer für das [!UICONTROL segment], wenn er sich für eines der drei [!UICONTROL traits] mindestens dreimal zwischen der ersten Qualifikation auf der Audience Manager-Plattform und der Sperrzeit vor fünf Tagen qualifiziert. Die nachstehende Zeitschiene zeigt die [!UICONTROL segment]-Qualifikation zum Zeitpunkt der Erstellung des [!UICONTROL segment], am 1. Oktober und zehn Tage später.

![Frühere Qualifizierung](assets/earlier-qualification.png)


## Beispiele für Frequenzzuordnung {#frequency-capping}

Ausdruck mit Frequenzbegrenzung schließen alle Benutzer ein, deren Anzahl der [!UICONTROL trait]-Realisierungen unter dem gewünschten Wert liegt. Im Folgenden finden Sie einige Beispiele zu Recht und falsch:

* Falsch - Der Ausdruck `frequency([1000T]) <= 5` umfasst alle Benutzer, die die [!UICONTROL trait] mit der ID &quot;1000&quot;bis zu fünfmal implementiert haben, aber auch Benutzer, die die [!UICONTROL trait]-Variable nicht erkannt haben. Daher validiert Audience Manager diesen Ausdruck aus Leistungsgründen nicht, da zu viele Benutzer für das [!UICONTROL segment]-Attribut qualifiziert wären.

* Rechts - Wenn Sie alle Benutzer einbeziehen möchten, die die [!UICONTROL trait]-ID &quot;1000&quot;maximal fünfmal erhalten haben, fügen Sie dem Ausdruck eine weitere Bedingung hinzu, um sicherzustellen, dass die Benutzer sich mindestens einmal für [!UICONTROL trait] qualifiziert haben:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Rechts- Wenn die Neuigkeits-/Frequenzanforderungen kleiner als eine bestimmte Anzahl von Malen oder Tagen sein müssen, verbinden Sie [!UICONTROL trait] mit einem `AND`-Operator. Anhand des Beispiels im ersten Aufzählungspunkt wird dieser Ausdruck gültig, wenn er mit einem anderen [!UICONTROL trait] verbunden wird, wie im Folgenden gezeigt: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Right - Für Anwendungsfälle mit der Beschränkung der Werbefrequenz können Sie eine [!UICONTROL segment]-Regel erstellen, die der folgenden ähnelt: `(frequency([1000T] <= 2D) >= 5)`. Dieser Ausdruck umfasst alle Benutzer, die die [!UICONTROL trait] mit der ID &quot;1000&quot;in den letzten 2 Tagen mindestens fünfmal ausgeführt haben. Stellen Sie die Frequenzgrenze ein, indem Sie dieses [!UICONTROL segment] an den Anzeigen-Server senden, wobei das `NOT` auf dem [!UICONTROL segment] im Anzeigen-Server eingestellt ist. Dieser Ansatz erreicht eine höhere Leistung in [!DNL Audience Manager], während er gleichzeitig dem gleichen Zweck für die Frequenzzuordnung dient.

>[!MORELIKETHIS]
>
>* [Segmentaufbau-Steuerelemente: Eigenschaftenabschnitt](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Im Ausdruckseditor für Segmente verwendete Code-Syntax](../../features/segments/segment-code-syntax.md)


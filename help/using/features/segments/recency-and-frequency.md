---
description: Mit Neuigkeit und Häufigkeit in Segment Builder können Sie Besucher anhand von Aktionen segmentieren, die in einem bestimmten täglichen Intervall auftreten oder sich wiederholen.
seo-description: Mit Neuigkeit und Häufigkeit in Segment Builder können Sie Besucher anhand von Aktionen segmentieren, die in einem bestimmten täglichen Intervall auftreten oder sich wiederholen.
seo-title: Neuigkeit und Häufigkeit
solution: Audience Manager
title: Neuigkeit und Häufigkeit
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: 'Segmente '
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 3%

---

# Neuigkeit und Häufigkeit {#recency-and-frequency}

In [!UICONTROL Segment Builder] können Sie mit Neuigkeit und Häufigkeit Besucher basierend auf Aktionen segmentieren, die in einem bestimmten täglichen Intervall auftreten oder wiederholt werden.

Audience Manager definiert [!DNL recency] und [!DNL frequency] wie folgt:

* **[!UICONTROL Recency]:** Wie kürzlich ein Benutzer eine (oder mehrere) Seite angezeigt oder sich qualifiziert hat  [!UICONTROL traits].
* **[!UICONTROL Frequency]:** Die Rate, mit der ein Benutzer eine(oder mehrere) Seite angesehen oder sich qualifiziert hat  [!UICONTROL traits].

[!UICONTROL Recency] Mithilfe der  [!UICONTROL Frequency] Einstellungen und können Sie Besucher anhand ihres tatsächlichen (oder wahrgenommenen) Interesses an einer Site, einem Abschnitt oder bestimmten kreativen Elementen segmentieren. Beispielsweise können Benutzer, die sich für ein Segment mit hohen Anforderungen an Neuigkeit/Häufigkeit qualifizieren, mehr an einer Site oder einem Produkt interessiert sein als Benutzer, die weniger oder weniger häufig besuchen.

## Speicherort der [!UICONTROL Recency and Frequency]-Einstellungen {#location}

In [!UICONTROL Segment Builder] befinden sich die Einstellungen [!UICONTROL Recency] und [!UICONTROL Frequency] im Abschnitt [!UICONTROL Basic View] des Bedienfelds [!UICONTROL Traits]. Klicken Sie auf das Uhrensymbol, um diese Steuerelemente anzuzeigen.

![](assets/recency_frequency.png)

## Einschränkungen und Regeln {#limitations-rules}

Lesen und verstehen Sie diese Einschränkungen und Regeln, wenn Sie Neuigkeit und Häufigkeit auf Eigenschaften in Ihren Segmenten anwenden möchten.

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
   <td colname="col2"> <p>Sie können Neuigkeitssteuerungen nur auf regelbasierte und Ordnereigenschaften anwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaften von Drittanbietern</b> </p> </td> 
   <td colname="col2"> <p>Sie können keine Neuigkeitsregeln für einzelne Eigenschaften von Drittanbietern oder Eigenschaftsgruppen festlegen, die Eigenschaften von Drittanbietern enthalten. Neuigkeit und Häufigkeit gelten nur für Ihre eigenen Eigenschaften. </p> </td> 
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
   <td colname="col2"> <p>Sie können keine Häufigkeitsregeln für einzelne Eigenschaften von Drittanbietern oder Eigenschaftsgruppen festlegen, die Eigenschaften von Drittanbietern enthalten. Neuigkeit und Häufigkeit gelten nur für Ihre eigenen Eigenschaften. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Eigenschaftstypen</b> </p> </td> 
   <td colname="col2"> <p>Sie können Frequenzsteuerungen nur auf regelbasierte und Ordnereigenschaften anwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Neuigkeitsanforderungen</b> </p> </td> 
   <td colname="col2"> <p>Sie können die Frequenzanforderungen <i>konfigurieren, ohne die Neuigkeitsanforderungen zu konfigurieren. </i> Legen Sie einfach einen Frequenzwert fest und lassen Sie das Neuigkeitsfeld leer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profilzusammenführungsrichtlinien</b> </p> </td> 
   <td colname="col2"> <p>Siehe <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Häufigkeit von Eigenschaften, externe Gerätediagramme und Profilzusammenführungsrichtlinien</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Neuigkeitsbeispiele {#recency-examples}

Im Folgenden finden Sie zwei Beispiele, wie Neuigkeit je nach Auswahl in der Benutzeroberfläche funktioniert:

### Operator kleiner oder gleich (&lt;=)

![Kleiner als gleich](assets/less-than-equal-to.png)

In diesem Beispiel wählen Sie den Operator &lt;= aus, wie im Screenshot gezeigt. Dies qualifiziert Ihren Benutzer für [!UICONTROL segment], wenn er sich innerhalb der letzten fünf Tage für eine der drei [!UICONTROL traits] mindestens dreimal qualifiziert hat. In der folgenden Zeitleiste sehen Sie die [!UICONTROL segment]-Qualifizierung zum Zeitpunkt der Erstellung von [!UICONTROL segment], zum 1. Oktober und zehn Tage später.

![Letzte fünf Tage](assets/last-5-days.png)

### Verwenden eines Operators größer oder gleich (=>)

![Größer als gleich](assets/greater-than-equal-to.png)

In diesem Beispiel wählen Sie den Operator => aus, wie im Screenshot gezeigt. Dies qualifiziert Ihren Benutzer für das [!UICONTROL segment], wenn er sich zwischen der ersten Qualifikation auf der Audience Manager-Plattform und der Cut-Off-Zeit vor fünf Tagen für eines der drei [!UICONTROL traits]-Werte qualifiziert hat. In der folgenden Zeitleiste sehen Sie die [!UICONTROL segment]-Qualifizierung zum Zeitpunkt der Erstellung von [!UICONTROL segment], zum 1. Oktober und zehn Tage später.

![Frühere Qualifizierung](assets/earlier-qualification.png)


## Beispiele für Frequenzlimitierung {#frequency-capping}

Frequenzlimitierungsausdrücke umfassen alle Benutzer, deren Anzahl an [!UICONTROL trait] -Realisierungen unter dem gewünschten Wert liegt. Im Folgenden finden Sie einige Beispiele für &quot;Richtig&quot;und &quot;Falsch&quot;:

* Falsch - Der Ausdruck `frequency([1000T]) <= 5` umfasst alle Benutzer, die die [!UICONTROL trait] mit der ID &quot;1000&quot;bis zu fünfmal realisiert haben, enthält aber auch Benutzer, die die [!UICONTROL trait] nicht erkannt haben. Daher validiert Audience Manager diesen Ausdruck aus Leistungsgründen nicht, da er zu viele Benutzer für [!UICONTROL segment] qualifizieren würde.

* Rechts - Wenn Sie alle Benutzer einbeziehen möchten, die das [!UICONTROL trait]-Zeichen mit der ID &quot;1000&quot;bis zu fünfmal implementiert haben, fügen Sie dem Ausdruck eine weitere Bedingung hinzu, um sicherzustellen, dass sich die Benutzer mindestens einmal für das [!UICONTROL trait] qualifiziert haben:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Rechts: Wenn Sie Neuigkeits-/Häufigkeitserfordernisse benötigen, die kleiner als eine bestimmte Anzahl von Malen oder Tagen sind, fügen Sie [!UICONTROL trait] einem anderen mit dem Operator `AND` hinzu. Anhand des Beispiels im ersten Aufzählungspunkt wird dieser Ausdruck gültig, wenn er mit einem anderen [!UICONTROL trait] verbunden wird, wie hier gezeigt: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Rechts - In Anwendungsfällen mit Frequenzlimitierung für Werbung können Sie eine [!UICONTROL segment]-Regel erstellen, die der folgenden ähnelt: `(frequency([1000T] <= 2D) >= 5)`. Dieser Ausdruck enthält alle Benutzer, die in den letzten 2 Tagen mindestens fünfmal die [!UICONTROL trait] mit der ID &quot;1000&quot;realisiert haben. Legen Sie die Frequenzlimitierung fest, indem Sie dieses [!UICONTROL segment] an den Anzeigen-Server senden, wobei auf dem [!UICONTROL segment] im Anzeigen-Server ein `NOT`-Wert eingestellt ist. Dieser Ansatz erzielt eine höhere Leistung in [!DNL Audience Manager] und erfüllt dabei immer noch denselben Zweck für die Frequenzlimitierung.

>[!MORELIKETHIS]
>
>* [Steuerelemente für den Segmentaufbau: Eigenschaftsbereich](../../features/segments/segment-builder.md#segment-builder-controls-traits)
* [Im Ausdruckseditor für Segmente verwendete Code-Syntax](../../features/segments/segment-code-syntax.md)


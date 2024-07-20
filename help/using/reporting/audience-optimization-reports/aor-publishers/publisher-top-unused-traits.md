---
description: Die wichtigsten nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch nicht Mitglieder eines Segments sind, basierend auf dem Eigenschaftstyp, der Datenquelle und der Leistung.
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: Häufigste nicht verwendete Eigenschaften
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---

# Häufigste nicht verwendete Eigenschaften{#top-unused-traits}

Die wichtigsten nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch nicht Mitglieder eines Segments sind, basierend auf dem Eigenschaftstyp, der Datenquelle und der Leistung.

## Anwendungsfall {#use-cases}

Mit dem Bericht [!UICONTROL Top Unused Traits] können Sie die Leistung von Erstanbieter- und Drittanbietereigenschaften analysieren und vergleichen, die derzeit keinem Segment zugeordnet sind. Diese Ansicht kann die besten Eigenschaften hervorheben, die in einem Zielgruppensegment zur Kampagnenoptimierung oder zu neuen Chancen verwendet werden können.

## Verwenden des Berichts &quot;Häufigste nicht verwendete Eigenschaften&quot; {#using-the-report}

Verwenden Sie die **[!UICONTROL Data Provider Type]** -Steuerelemente, um zwischen Erstanbieter- und Drittanbieter-Eigenschaften umzuschalten. Wählen Sie **[!UICONTROL All]** aus, um Erstanbieter- und Drittanbieter-Eigenschaften im Bericht zurückzugeben.

Mit dem Schieberegler **[!UICONTROL Impressions]** können Sie einen Mindest- und einen Höchstwert für zurückgegebene Impressionen auswählen. Eigenschaften, die für weniger oder mehr als die von Ihnen festgelegten Beschränkungen verantwortlich sind, werden nicht im Bericht angezeigt.

Verwenden Sie die Steuerelemente **[!UICONTROL Day Range]** und **[!UICONTROL Date Through]** , um Ihren Rückblickbereich anzupassen. Beachten Sie, dass für diesen Bericht nur der 30-Tage-Rückblickzeitraum verfügbar ist.

Verwenden Sie das Dropdown-Feld &quot;**[!UICONTROL Order]**&quot;, um die Webeigenschaften in Ihrem Portfolio auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie in der Dropdown-Liste **[!UICONTROL Data Provider]** die Datenquellen aus, die die Eigenschaften enthalten, die Sie im Bericht sehen möchten.

Wählen Sie über das Dropdownfeld **[!UICONTROL Traits]** aus, welche Eigenschaften im Bericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Beim Aktivieren von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Order IDs] einfügen, wie in Schritt 3 von [Importieren von Google Ad Manager-Datendateien (ehemals DFP) in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md) beschrieben. Dadurch stellen Sie sicher, dass der Bericht die Webeigenschaft als [!UICONTROL Order] anstelle von [!UICONTROL Order ID] detailliert beschreibt.

## Interpretieren der Ergebnisse {#interpreting-results}

**Beispielbericht**

Ihr [!UICONTROL Top Unused Traits] -Bericht könnte dem unten stehenden ähneln. Klicken Sie in Ihrem Bericht auf eine Blase, um die zugrunde liegenden Daten anzuzeigen.

Weitere Informationen finden Sie in der Tabelle unter dem Beispielbericht.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Datenanbietertyp</span> </p> </td> 
   <td colname="col2"> <p>Gibt an, ob die ausgewählte Datenquelle Erstanbieter- oder Drittanbieter-Eigenschaften enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschafts-ID</span> </p> </td> 
   <td colname="col2"> <p>Die eindeutige ID dieser Eigenschaft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschaftsname</span> </p> </td> 
   <td colname="col2"> <p>Der alphanumerische Name, den Sie oder der Datenanbieter dieser Eigenschaft zugewiesen haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Bestellung</span> </p> </td> 
   <td colname="col2"> <p>Die Webeigenschaft, für die dieser Bericht angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressionen</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihrem Inventar ausgesetzt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eindeutige Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Eigenschaftsmitglieder innerhalb der letzten 30 Tage. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

Die Position Ihrer Eigenschaften in einem Bericht kann Ihnen viel darüber vermitteln, welche Eigenschaften Sie zur Optimierung vorhandener Zielgruppensegmente verwenden können.

Die Eigenschaften, die höher auf der Impressionsachse liegen, sind diejenigen, die Sie in Ihren Kampagnen verwenden möchten. Bei Eigenschaften mit einer geringen Anzahl von Impressionen ist es unwahrscheinlich, dass Sie diese Zielgruppe basierend auf Ihren [!DNL Google Ad Manager] -Daten in Ihrer Webeigenschaft erreichen.

Suchen Sie nach links von der [!UICONTROL Unique Trait Realizations]-Achse nach hochpräzisen Eigenschaften und nach rechts nach Eigenschaften, die die Skalierung fördern können.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Platzierungsangaben </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Oben links</b> </p> </td> 
   <td colname="col2"> <p>Hohe Anzahl von Impressionen, geringe Anzahl von Realisierungen von Eigenschaften. </p> <p>Dies ist eine hochgenaue Zielgruppe, die noch nicht Mitglied eines Segments ist. Erwägen Sie Targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten links</b> </p> </td> 
   <td colname="col2"> <p>Geringe Anzahl von Impressionen, geringe Anzahl von Realisierungen von Eigenschaften. </p> <p> Lassen Sie diese Eigenschaften außer Kraft, da die Mitglieder nicht zu Impressionen in Ihren Web-Eigenschaften beitragen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Oben rechts</b> </p> </td> 
   <td colname="col2"> <p>Hohe Anzahl von Impressionen, hohe Anzahl von Realisierungen von Eigenschaften. </p> <p>Hohe Reichweite gegenüber einer Zielgruppe, die noch nicht in einem Segment angezeigt wird. Diese Zielgruppe ist aufgrund der hohen Anzahl von Impressionen und der Skala ein Hauptkandidat für das Targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten rechts</b> </p> </td> 
   <td colname="col2"> <p>Geringe Anzahl von Impressionen, hohe Anzahl von Realisierungen von Eigenschaften. </p> <p> Sie können diese Eigenschaften ausschließen, da die Mitglieder nicht zu Impressionen in Ihren Webeigenschaften beitragen. </p> </td> 
  </tr> 
 </tbody> 
</table>

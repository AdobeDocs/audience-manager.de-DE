---
description: Die häufigsten nicht verwendeten Eigenschaften werden anhand von Eigenschaftstyp, Datenquelle und Leistung als Streudiagramm von Eigenschaften dargestellt, die noch nicht zu einem Segment gehören.
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: Top der nicht verwendeten Eigenschaften
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---

# Top der nicht verwendeten Eigenschaften{#top-unused-traits}

Die häufigsten nicht verwendeten Eigenschaften werden anhand von Eigenschaftstyp, Datenquelle und Leistung als Streudiagramm von Eigenschaften dargestellt, die noch nicht zu einem Segment gehören.

## Anwendungsfall {#use-cases}

Mit dem [!UICONTROL Top Unused Traits] Bericht können Sie die Leistung von Erst- und Drittanbieter-Eigenschaften analysieren und vergleichen, die derzeit keinem Segment zugeordnet sind. Diese Ansicht kann die besten Eigenschaften aufzeigen, die in einem Zielgruppensegment zur Kampagnenoptimierung oder für neue Opportunities verwendet werden können.

## Verwenden des Berichts „Top Unused Traits“ {#using-the-report}

Verwenden Sie die **[!UICONTROL Data Provider Type]**, um zwischen First-Party- und Third-Party-Eigenschaften umzuschalten. Wählen Sie **[!UICONTROL All]** aus, um im Bericht Erstanbieter- und Drittanbieter-Eigenschaften zurückzugeben.

Mit dem Schieberegler **[!UICONTROL Impressions]** können Sie einen Mindest- und Höchstwert für die zurückgegebenen Impressionen auswählen. Eigenschaften, die für weniger oder mehr als die von Ihnen festgelegten Beschränkungen verantwortlich sind, werden im Bericht nicht angezeigt.

Verwenden Sie die Steuerelemente **[!UICONTROL Day Range]** und **[!UICONTROL Date Through]** , um den Lookback-Bereich anzupassen. Beachten Sie, dass für diesen Bericht nur der 30-tägige Lookback-Zeitraum verfügbar ist.

Verwenden Sie das Dropdown-Feld **[!UICONTROL Order]** , um die Web-Eigenschaften in Ihrem Portfolio auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie in der Dropdown-Liste **[!UICONTROL Data Provider]** die Datenquellen aus, die die Eigenschaften enthalten, die Sie im Bericht sehen möchten.

Verwenden Sie das Dropdown-Feld **[!UICONTROL Traits]** , um die Eigenschaften auszuwählen, die im Bericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Bei der Aktivierung von [!UICONTROL Audience Optimization for Publishers] müssen Sie beschreibende Metadaten für [!UICONTROL Order IDs] einbeziehen, wie in Schritt 3 von [Importieren von Datendateien des Google Ad Manager (ehemals DFP) in den Audience Manager beschrieben](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Auf diese Weise können Sie sicherstellen, dass der Bericht die Web-Eigenschaft als [!UICONTROL Order] anstelle des [!UICONTROL Order ID] angibt.

## Interpretieren der Ergebnisse {#interpreting-results}

**Beispielbericht**

Ihr [!UICONTROL Top Unused Traits] könnte in etwa wie der unten stehende aussehen. Klicken Sie in Ihrem Bericht auf eine Blase, um die zugrunde liegenden Daten anzuzeigen.

Weitere Informationen finden Sie in den Beschreibungen in der Tabelle unten im Beispielbericht.

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
   <td colname="col1"> <p><span class="wintitle"> Datenanbieter-Typ</span> </p> </td> 
   <td colname="col2"> <p>Gibt an, ob die ausgewählte Datenquelle Erstanbieter- oder Drittanbieter-Eigenschaften enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">-ID</span> </p> </td> 
   <td colname="col2"> <p>Die eindeutige ID dieser Eigenschaft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschaftsname</span> </p> </td> 
   <td colname="col2"> <p>Der alphanumerische Name, den Sie oder der Datenanbieter dieser Eigenschaft zugewiesen haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Bestellung</span> </p> </td> 
   <td colname="col2"> <p>Die Web-Eigenschaft, für die dieser Bericht angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihrem Inventar ausgesetzt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschaft ist einzigartig</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Mitglieder eines Merkmals innerhalb der letzten 30 Tage. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

Die Position Ihrer Eigenschaften in einem Bericht kann Ihnen eine Menge darüber verraten, welche Eigenschaften Sie zur Optimierung vorhandener Zielgruppensegmente verwenden könnten.

Die Eigenschaften, die sich oben auf der Impressions-Achse befinden, sind die Eigenschaften, die Sie in Ihren Kampagnen verwenden möchten. Bei Eigenschaften mit einer geringen Anzahl von Impressionen ist es basierend auf Ihren [!DNL Google Ad Manager] unwahrscheinlich, dass Sie diese Zielgruppe in Ihrer Web-Eigenschaft erreichen.

Achten Sie auf der linken Seite der [!UICONTROL Unique Trait Realizations] auf hochgenaue Eigenschaften und auf der rechten Seite auf Eigenschaften, die den Maßstab beeinflussen können.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Platzierung zeigt Folgendes an </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Oben links</b> </p> </td> 
   <td colname="col2"> <p>Hohe Anzahl von Impressionen, geringe Anzahl von Eigenschaftenrealisierungen. </p> <p>Dies ist eine hochgenaue Zielgruppe, die noch nicht Mitglied eines Segments ist. Erwägen Sie die Zielgruppenbestimmung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten links</b> </p> </td> 
   <td colname="col2"> <p>Niedrige Anzahl von Impressionen, geringe Anzahl von Eigenschaftenrealisierungen. </p> <p> Schließen Sie diese Eigenschaften aus, da die Mitglieder nicht zu Impressions in Ihren Web-Eigenschaften beitragen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Oben rechts</b> </p> </td> 
   <td colname="col2"> <p>Hohe Anzahl von Impressionen, hohe Anzahl von Eigenschaftenrealisierungen. </p> <p>Eine hohe Reichweite für eine Zielgruppe, die noch nicht in einem Segment aufgeführt ist. Diese Zielgruppe eignet sich aufgrund der hohen Anzahl an Impressionen und der Größenordnung besonders gut für die Zielgruppenbestimmung. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten rechts</b> </p> </td> 
   <td colname="col2"> <p>Niedrige Anzahl von Impressionen, hohe Anzahl von Eigenschaftenrealisierungen. </p> <p> Sie können diese Eigenschaften ausschließen, da die Mitglieder nicht zu Impressionen in Ihren Web-Eigenschaften beitragen. </p> </td> 
  </tr> 
 </tbody> 
</table>

---
description: Die wichtigsten nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch nicht zu einem Segment gehören, basierend auf dem Eigenschaftstyp, der Datenquelle und der Leistung.
seo-description: Die wichtigsten nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch nicht zu einem Segment gehören, basierend auf dem Eigenschaftstyp, der Datenquelle und der Leistung.
seo-title: Häufigste nicht verwendete Eigenschaften
solution: Audience Manager
title: Häufigste nicht verwendete Eigenschaften
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 2%

---

# Häufigste nicht verwendete Eigenschaften{#top-unused-traits}

Die wichtigsten nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch nicht zu einem Segment gehören, basierend auf dem Eigenschaftstyp, der Datenquelle und der Leistung.

## Anwendungsfall {#use-cases}

Mit dem Bericht [!UICONTROL Top Unused Traits] können Sie die Leistung von Erst- und Drittanbietereigenschaften analysieren und vergleichen, die derzeit keinem Segment zugeordnet sind. Diese Ansicht kann auf die besten Eigenschaften hinweisen, die in einem Audiencen-Segment zur Optimierung der Kampagne oder zu neuen Netto-Chancen verwendet werden.

## Verwenden des Berichts zu den wichtigsten nicht verwendeten Eigenschaften {#using-the-report}

Mit den **[!UICONTROL Data Provider Type]**-Steuerelementen können Sie zwischen Eigenschaften von Erstanbietern und Drittanbietern umschalten. Wählen Sie **[!UICONTROL All]** aus, um Eigenschaften von Erstanbietern und Drittanbietern im Bericht zurückzugeben.

Mit dem Schieberegler **[!UICONTROL Impressions]** können Sie einen minimalen und einen maximalen Wert für zurückgegebene Impressionen auswählen. Alle Eigenschaften, die für weniger oder mehr als die von Ihnen festgelegten Beschränkungen verantwortlich sind, werden nicht im Bericht angezeigt.

Verwenden Sie die Steuerelemente **[!UICONTROL Day Range]** und **[!UICONTROL Date Through]**, um Ihren Lookback-Bereich anzupassen. Beachten Sie, dass für diesen Bericht nur der 30-Tage-Rückblickzeitraum verfügbar ist.

Verwenden Sie das Dropdownfeld **[!UICONTROL Order]**, um die Webeigenschaften in Ihrem Portfolio auszuwählen, für die Sie Informationen zurückgeben möchten.

Wählen Sie im Dropdownfeld **[!UICONTROL Data Provider]** die Datenquellen mit den Eigenschaften aus, die Sie im Bericht sehen möchten.

Verwenden Sie das Dropdownfeld **[!UICONTROL Traits]**, um auszuwählen, welche Eigenschaften im Bericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Wenn Sie [!UICONTROL Audience Optimization for Publishers] aktivieren, müssen Sie beschreibende Metadaten für [!UICONTROL Order IDs] einfügen, wie in Schritt 3 von [Google Ad Manager (ehemals DFP)-Datendateien in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md) beschrieben. Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft als [!UICONTROL Order] und nicht als [!UICONTROL Order ID] bezeichnet.

## Interpretieren der Ergebnisse {#interpreting-results}

**Beispielbericht**

Ihr [!UICONTROL Top Unused Traits]-Bericht könnte ähnlich wie der unten stehende aussehen. Klicken Sie in Ihrem Bericht auf einen Punkt, um die zugrunde liegenden Daten Ansicht.

Siehe Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col2"> <p>Gibt an, ob die ausgewählte Datenquelle Eigenschaften von Erstanbietern oder Drittanbietern enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschaften-ID</span> </p> </td> 
   <td colname="col2"> <p>Die eindeutige ID dieser Eigenschaft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschaftsname</span> </p> </td> 
   <td colname="col2"> <p>Der alphanumerische Name, den Sie oder der Datenanbieter dieser Eigenschaft zugewiesen haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Bestellung</span> </p> </td> 
   <td colname="col2"> <p>Die Webeigenschaft, für die Sie diesen Bericht sehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eindrücke</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihrem Bestand ausgesetzt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschaftsvariablen</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Eigenschaftsmitglieder innerhalb der letzten 30 Tage. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

Die Position Ihrer Eigenschaften in einem Bericht kann Ihnen viele Informationen darüber liefern, welche Eigenschaften Sie zur Optimierung vorhandener Audiencen verwenden können.

Die Eigenschaften, die höher auf der Impressionsachse liegen, sind die Eigenschaften, die Sie in Ihren Kampagnen verwenden möchten. Bei Eigenschaften mit einer geringen Anzahl von Impressionen ist es unwahrscheinlich, dass Sie diese Audience in Ihrer Webeigenschaft erreichen, basierend auf Ihren [!DNL Google Ad Manager]-Daten.

Suchen Sie links neben der [!UICONTROL Unique Trait Realizations]-Achse nach hochpräzisen Eigenschaften und rechts nach Eigenschaften, die die Skalierung fördern können.

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
   <td colname="col2"> <p>Hohe Anzahl von Impressionen, niedrige Anzahl von Eigenschaften. </p> <p>Dies ist eine hochgenaue Audience, die noch nicht Teil eines Segments ist. Erwägen Sie Targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten links</b> </p> </td> 
   <td colname="col2"> <p>Geringe Anzahl von Impressionen, niedrige Anzahl von Eigenschaften. </p> <p> Schließen Sie diese Eigenschaften aus, da die Mitglieder nicht zu Impressionen in Ihren Webeigenschaften beitragen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Oben rechts</b> </p> </td> 
   <td colname="col2"> <p>Hohe Anzahl von Impressionen, hohe Anzahl von Eigenschaften Realisierungen. </p> <p>Eine hohe Reichweite gegen eine Audience, die noch nicht in einem Segment gekennzeichnet ist. Diese Audience ist aufgrund der hohen Anzahl von Impressionen und der Größenordnung ein erstklassiger Kandidat für das Targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten rechts</b> </p> </td> 
   <td colname="col2"> <p>Geringe Anzahl von Impressionen, hohe Anzahl von Eigenschaften. </p> <p> Sie können diese Eigenschaften ausschließen, da die Mitglieder nicht zu Impressionen in Ihren Webeigenschaften beitragen. </p> </td> 
  </tr> 
 </tbody> 
</table>

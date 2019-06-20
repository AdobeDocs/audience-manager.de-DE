---
description: Die nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch keine Mitglieder eines Segments sind, basierend auf Eigenschaften, Datenquelle und Leistung.
seo-description: Die nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch keine Mitglieder eines Segments sind, basierend auf Eigenschaften, Datenquelle und Leistung.
seo-title: Nicht verwendete Eigenschaften
solution: Audience Manager
title: Nicht verwendete Eigenschaften
uuid: 90 bcd 333-41 b 8-416 e-aa 4 e-a 6661891 df 50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Nicht verwendete Eigenschaften{#top-unused-traits}

Die nicht verwendeten Eigenschaften werden als Streudiagramm von Eigenschaften dargestellt, die noch keine Mitglieder eines Segments sind, basierend auf Eigenschaften, Datenquelle und Leistung.

## Nutzungsszenario {#use-cases}

Mit dem [!UICONTROL Top Unused Traits] Bericht können Sie die Leistung der Eigenschaften erster und dritter Partei analysieren und vergleichen, die derzeit keinem Segment zugeordnet sind. Diese Ansicht kann auf die besten Eigenschaften hinweisen, die in einem Zielgruppensegment für die Kampagnenoptimierung oder für neue neue Gelegenheiten verwendet werden.

## Verwenden des Berichts &quot;Bevorzugte Eigenschaften « {#using-the-report}

Verwenden Sie **[!UICONTROL Data Provider Type]** die Steuerelemente, um zwischen Eigenschaften von Erstanbietern und Drittanbietern umzuschalten. Wählen Sie diese Option, um **[!UICONTROL All]** die ersten und dritten Eigenschaften des Berichts zurückzugeben.

Mit **[!UICONTROL Impressions]** dem Schieberegler können Sie einen minimalen und einen maximalen Wert für zurückgegebene Impressionen auswählen. Alle Eigenschaften, die für weniger oder mehr als die eingestellten Beschränkungen verantwortlich sind, werden nicht im Bericht angezeigt.

Verwenden Sie die **[!UICONTROL Day Range]** Steuerelemente und **[!UICONTROL Date Through]** Steuerelemente, um Ihren Look-Back-Bereich anzupassen. Beachten Sie, dass für diesen Bericht nur der 30-Tage-Blickzeitraum zur Verfügung steht.

Wählen **[!UICONTROL Order]** Sie die Webeigenschaften in Ihrem Portfolio aus, für die Sie Informationen zurückgeben möchten.

Wählen Sie in der **[!UICONTROL Data Provider]** Dropdown-Liste die Datenquellen aus, die die Eigenschaften enthalten, die im Bericht angezeigt werden sollen.

Verwenden Sie die **[!UICONTROL Traits]** Dropdownliste, um auszuwählen, welche Eigenschaften im Bericht angezeigt werden sollen.

>[!IMPORTANT]
>
>Bei Aktivierung [!UICONTROL Audience Optimization for Publishers]müssen Sie beschreibende Metadaten hinzufügen, [!UICONTROL Order IDs]wie in Schritt 3 von [DFP-Datendateien in Audience Manager importieren](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)beschrieben. Auf diese Weise stellen Sie sicher, dass der Bericht die Webeigenschaft anstelle [!UICONTROL Order] von &quot;und [!UICONTROL Order ID]«ausführt.

## Interpretieren der Ergebnisse {#interpreting-results}

**Beispielbericht**

Ihr [!UICONTROL Top Unused Traits] Bericht könnte wie folgt aussehen. Klicken Sie in Ihrem Bericht auf ein Punktdiagramm, um die zugrunde liegenden Daten anzuzeigen.

Weitere Informationen finden Sie unter Beschreibungen der zusätzlichen Informationen in der Tabelle unter dem Beispielbericht.

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
   <td colname="col1"> <p><span class="wintitle"> Datenprovider-Typ</span> </p> </td> 
   <td colname="col2"> <p>Gibt an, ob die ausgewählte Datenquelle Erstanbieter- oder Drittanbieter-Eigenschaften enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschafts-ID</span> </p> </td> 
   <td colname="col2"> <p>Die eindeutige ID dieser Eigenschaft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eigenschaftsname</span> </p> </td> 
   <td colname="col2"> <p>Der alphanumerische Name, den Sie oder der Datenprovider dieser Eigenschaft zugewiesen haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Bestellung</span> </p> </td> 
   <td colname="col2"> <p>Die Webeigenschaft, für die dieser Bericht angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Eindrücke</span> </p> </td> 
   <td colname="col2"> <p>Die Häufigkeit, mit der Mitglieder dieser Eigenschaft Ihren Bestand speichern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait Uniques</span> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Eigenschaftsmitglieder innerhalb der letzten 30 Tage. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

Die Position Ihrer Eigenschaften in einem Bericht kann Ihnen sehr viel darüber informieren, welche Eigenschaften Sie zur Optimierung vorhandener Zielgruppensegmente verwenden könnten.

Die Eigenschaften, die sich oben auf der Impressions-Achse befinden, sind diejenigen, die Sie in Ihren Kampagnen verwenden möchten. Bei Eigenschaften mit einer geringen Anzahl von Impressionen ist es unwahrscheinlich, dass Sie diese Zielgruppe auf Ihrer Webeigenschaft basierend auf Ihren DFP-Daten erreichen.

Auf der linken Seite der [!UICONTROL Unique Trait Realizations] Achse finden Sie hochpräzise Eigenschaften und rechts für Eigenschaften, die eine Skalierung ermöglichen.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Platzierung zeigt an </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Oben links</b> </p> </td> 
   <td colname="col2"> <p>Eine hohe Anzahl von Impressionen, niedrige Anzahl von Eigenschaften. </p> <p>Dies ist eine sehr genaue Zielgruppe, die noch kein Mitglied eines Segments ist. Erwägen Sie das Targeting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten links</b> </p> </td> 
   <td colname="col2"> <p>Geringe Anzahl von Impressionen, niedrige Anzahl von Eigenschaften. </p> <p> Schließen Sie diese Eigenschaften ab, da die Mitglieder nicht zu Impressionen in Ihren Webeigenschaften beitragen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Oben rechts</b> </p> </td> 
   <td colname="col2"> <p>Eine hohe Anzahl von Impressionen, eine große Anzahl von Eigenschaften. </p> <p>Eine hohe Reichweite gegenüber einer Zielgruppe, die noch nicht in einem Segment angezeigt wird. Diese Zielgruppe ist ein primärer Kandidat für Targeting aufgrund der hohen Anzahl von Impressionen und der Skala. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten rechts</b> </p> </td> 
   <td colname="col2"> <p>Geringe Anzahl von Impressionen, hohe Anzahl von Eigenschaften. </p> <p> Sie können diese Eigenschaften ausschließen, da die Mitglieder nicht zu Impressionen in Ihren Webeigenschaften beitragen. </p> </td> 
  </tr> 
 </tbody> 
</table>

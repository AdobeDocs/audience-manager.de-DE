---
description: Informationen zum Verlauf ausgehender Batch-Aufträge für ein bestimmtes Ziel und einen bestimmten Zeitraum anzeigen.
seo-description: Informationen zum Verlauf ausgehender Batch-Aufträge für ein bestimmtes Ziel und einen bestimmten Zeitraum anzeigen.
seo-title: Ausgehender Dateiverlauf
solution: Audience Manager
title: Ausgehender Dateiverlauf
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Eingehende und ausgehende Berichte
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 7%

---

# Ausgehender Dateiverlauf {#outbound-file-history}

Informationen zum Verlauf ausgehender Batch-Aufträge für ein bestimmtes Ziel und einen bestimmten Zeitraum anzeigen.

<!-- 

t_reports_outbound_history.xml

 -->

1. Klicken **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Schrittergebnis](assets/outbound_history.png)

1. Geben Sie im Feld **[!UICONTROL Search for a Destination]** die gewünschten Zielorte ein und wählen Sie sie aus.
1. Geben Sie im Feld **[!UICONTROL Select a Date Range]** das Start- und Enddatum für Ihren Bericht an und klicken Sie dann auf **[!UICONTROL Apply Date Filter]**.

   ![Schrittergebnis](assets/outbound_history_stats.png)

   Die folgende Tabelle enthält Informationen, die den Spalten des Berichts entsprechen:

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linie </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Data Sync File Name </td> 
   <td colname="col2"> <p>Liste aller ausgehenden Dateien, die <span class="keyword"> Adobe</span> für dieses Ziel generiert und zusammen verarbeitet wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erfolgreich </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, die erfolgreich vom Audience Manager <span class="keyword"> </span> an das Ziel gesendet wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> „Fehlgeschlagen“ </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, die nicht an das Ziel gesendet werden konnten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erhaltene Datensätze </td> 
   <td colname="col2"> <p>Gesamtzahl der Datensätze <span class="keyword"> Adobe</span>, die in den Dateien generiert und an das Ziel gesendet wurden. In den meisten Fällen sollte dies die Gesamtzahl der erfolgreichen und fehlgeschlagenen Dateien sein. </p> </td> 
  </tr> 
 </tbody> 
</table>

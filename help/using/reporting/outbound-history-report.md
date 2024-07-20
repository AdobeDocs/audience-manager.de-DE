---
description: Informationen zum Verlauf ausgehender Batch-Aufträge für ein bestimmtes Ziel und einen bestimmten Zeitraum anzeigen.
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: Ausgehender Dateiverlauf
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Inbound and Outbound Reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 1%

---

# Ausgehender Dateiverlauf {#outbound-file-history}

Informationen zum Verlauf ausgehender Batch-Aufträge für ein bestimmtes Ziel und einen bestimmten Zeitraum anzeigen.

<!-- 

t_reports_outbound_history.xml

 -->

1. Klicken Sie auf **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Schrittergebnis](assets/outbound_history.png)

1. Geben Sie in das Feld **[!UICONTROL Search for a Destination]** ein und wählen Sie das gewünschte Ziel aus.
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
   <td colname="col2"> <p>Liste aller ausgehenden Dateien, die von <span class="keyword"> Adobe</span> für dieses Ziel generiert wurden und zusammen verarbeitet wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erfolgreich </td> 
   <td colname="col2"> <p>Anzahl der erfolgreich von <span class="keyword"> Audience Manager</span> an das Ziel gesendeten Datensätze. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> „Fehlgeschlagen“ </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, die nicht an das Ziel gesendet werden konnten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erhaltene Datensätze </td> 
   <td colname="col2"> <p>Gesamtzahl der Einträge <span class="keyword"> Adobe</span> , die in den Dateien generiert wurden und versucht haben, an das Ziel zu senden. In den meisten Fällen sollte dies die Gesamtzahl der erfolgreichen und fehlgeschlagenen Dateien sein. </p> </td> 
  </tr> 
 </tbody> 
</table>

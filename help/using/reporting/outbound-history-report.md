---
description: Anzeigen ausgehender Informationen zum Vorgangsverlauf für ein bestimmtes Ziel und einen bestimmten Zeitraum.
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: Verlauf ausgehender Dateien
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Inbound and Outbound Reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 1%

---

# Verlauf ausgehender Dateien {#outbound-file-history}

Anzeigen ausgehender Informationen zum Vorgangsverlauf für ein bestimmtes Ziel und einen bestimmten Zeitraum.

<!-- 

t_reports_outbound_history.xml

 -->

1. Klicken Sie auf **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Schrittergebnis](assets/outbound_history.png)

1. Beginnen Sie im **[!UICONTROL Search for a Destination]** mit der Eingabe und wählen Sie das gewünschte Ziel aus.
1. Geben Sie im Feld **[!UICONTROL Select a Date Range]** das Start- und Enddatum für Ihren Bericht ein und klicken Sie dann auf **[!UICONTROL Apply Date Filter]**.

   ![Schrittergebnis](assets/outbound_history_stats.png)

   Die folgende Tabelle enthält Informationen zu den Spalten im Bericht:

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linie </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Name der Datensynchronisationsdatei </td> 
   <td colname="col2"> <p>Liste aller ausgehenden Dateien, die <span class="keyword"> Adobe</span> generiert und gemeinsam verarbeitet wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erfolgreich </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, die erfolgreich von <span class="keyword"> Audience Manager </span> das Ziel gesendet wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> „Fehlgeschlagen“ </td> 
   <td colname="col2"> <p>Anzahl der Datensätze, die nicht an das Ziel gesendet werden konnten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Empfangene Einträge </td> 
   <td colname="col2"> <p>Gesamtzahl der Datensätze <span class="keyword"> Adobe</span> die in den Dateien generiert und versucht wurden, an das Ziel zu senden. In den meisten Fällen sollte dies die Gesamtzahl der erfolgreichen und fehlgeschlagenen Dateien sein. </p> </td> 
  </tr> 
 </tbody> 
</table>

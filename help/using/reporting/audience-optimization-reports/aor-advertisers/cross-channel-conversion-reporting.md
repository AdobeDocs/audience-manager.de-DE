---
description: Mit der Option "Konvertierung über mehrere Kanal"in den Berichten "Audience Optimization"können Sie Offlinekonversionen bereitgestellten Online-Impressionen oder -Klicks zuordnen.
seo-description: Mit der Option "Konvertierung über mehrere Kanal"in den Berichten "Audience Optimization"können Sie Offlinekonversionen bereitgestellten Online-Impressionen oder -Klicks zuordnen.
seo-title: Kanalübergreifende Konversion
solution: Audience Manager
title: Kanalübergreifende Konversion
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Berichte zur Zielgruppenoptimierung
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 5%

---

# Kanalübergreifende Konversion{#cross-channel-conversion}

Mit der Option &quot;Konvertierung über mehrere Kanal&quot;in den Berichten &quot;Audience Optimization&quot;können Sie Offlinekonversionen bereitgestellten Online-Impressionen oder -Klicks zuordnen.

Die [!UICONTROL Cross Channel Conversion]-Berichte kombinieren die Ergebnisse der [!DNL Google Campaign Manager]-Plattform mit [!DNL Audience Manager]-Konversionseigenschaften. Auf diese Weise können Sie Offline-Konversionen mit Online-Impressionen oder -Klicks verknüpfen.

Sie können die Berichte [!UICONTROL Cross Channel Conversion] für [Segmentleistung](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) und [Optimale Häufigkeit](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) verwenden.

Um die Berichte [!UICONTROL Cross Channel Conversion] Ansicht, wählen Sie in der Dropdown-Liste **[!UICONTROL Platform]** das Element **[!UICONTROL AAM + Ad Server Name]** aus.

Die folgende Tabelle enthält wichtige Listen bei der Einrichtung von [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Hinweis </th> 
   <th class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Mindestanzahl von Konversionseigenschaften </p> </td> 
   <td colname="col1"> <p>Mindestens eine Konversionseigenschaft muss einer Datenquelle zugewiesen werden, damit die Berichte <span class="wintitle"> "Konvertierung über mehrere Kanal</span>"ausgeführt werden können. Weitere Informationen zu Eigenschaften finden Sie unter <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Grundlegende Informationen für Eigenschaften</a>. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Zuordnungsfenster </p> </td> 
   <td> <p> <b><span class="uicontrol"> Das Zuordnungs-Fenster AAM+Google Kampagne </span></b> Manager ist 14 Tage lang gültig, d. h., es werden nur Konversionseigenschaften berücksichtigt, die in den letzten zwei Wochen ausgestellt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Last Touch-Methode </p> </td> 
   <td> <p>Das Kreativelement, das der Benutzer vor der Konvertierung zuletzt gesehen hat, ist das Kreativelement, das die Konvertierung erhalten hat. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Klicks versus Impressionen </p> </td> 
   <td> <p>Ein Klick hat bei der Entscheidung über die Zuordnung Vorrang vor einem Impression, wenn sie exakt zur gleichen Zeit erfolgt. Beispielsweise wird auf einer Seite, auf der mehrere kreative Elemente angezeigt werden, die angeklickte Seite mit der Konvertierung ausgezeichnet. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Datenneuigkeit </p> </td> 
   <td> <p>Die Berichte werden immer für die am Vortag verfügbaren Daten berechnet. </p> </td> 
  </tr> 
 </tbody> 
</table>

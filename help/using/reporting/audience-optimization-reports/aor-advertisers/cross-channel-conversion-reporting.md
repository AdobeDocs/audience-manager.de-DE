---
description: Mit der Option Kanalübergreifende Konversion in den Audience Optimization-Berichten können Sie Offline-Konversionen bereitgestellten Onlineimpressionen oder -klicks zuordnen.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Kanalübergreifende Konversion
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Kanalübergreifende Konversion{#cross-channel-conversion}

Mit der Option Kanalübergreifende Konversion in den Audience Optimization-Berichten können Sie Offline-Konversionen bereitgestellten Onlineimpressionen oder -klicks zuordnen.

Die [!UICONTROL Cross Channel Conversion] -Berichte kombinieren Ergebnisse aus der [!DNL Google Campaign Manager] -Plattform mit den [!DNL Audience Manager] -Konversionseigenschaften. Dadurch können Sie Offline-Konversionen mit Online-Impressionen oder -Klicks verknüpfen.

Sie können die [!UICONTROL Cross Channel Conversion] für die Berichte [Segmentleistung](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) und [Optimale Häufigkeit](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) verwenden.

Um die [!UICONTROL Cross Channel Conversion] Berichte anzuzeigen, wählen Sie das Element **[!UICONTROL AAM + Ad Server Name]** in der Dropdownliste **[!UICONTROL Platform]** aus.

In der folgenden Tabelle sind wichtige Überlegungen beim Einrichten von [!UICONTROL Cross Channel Conversion] aufgeführt:

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
   <td colname="col1"> <p>Mindestens eine Konversionseigenschaft muss einer Datenquelle zugewiesen werden, damit die <span class="wintitle"> Berichte zur kanalübergreifenden Konversion</span> ausgeführt werden können. Weitere Informationen zu Eigenschaften finden Sie unter <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Grundlegende Informationen für Eigenschaften</a> . </p> </td> 
  </tr>
  <tr> 
   <td> <p>Attributionsfenster </p> </td> 
   <td> <p> <b><span class="uicontrol"> Das Attributionsfenster AAM+Google Campaign Manager</span></b> beträgt 14 Tage, was bedeutet, dass nur Konversionseigenschaften berücksichtigt werden, die in den letzten zwei Wochen angezeigt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Letztkontakt-Methode </p> </td> 
   <td> <p>Das Kreativelement, das der Benutzer vor der Konvertierung zuletzt gesehen hat, ist das Kreativelement, das die Konvertierung erhalten hat. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Klicks versus Impressionen </p> </td> 
   <td> <p>Ein Klick hat bei der Entscheidung über die Attribution Vorrang vor einer Impression, wenn er zur selben Zeit erfolgt. Auf einer Seite, auf der mehrere Kreative angezeigt werden, wird beispielsweise die Konvertierung für die Seite vergeben, auf die geklickt wird. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Datenaktualität </p> </td> 
   <td> <p>Die Berichte werden immer für Daten berechnet, die am Vortag verfügbar waren. </p> </td> 
  </tr> 
 </tbody> 
</table>

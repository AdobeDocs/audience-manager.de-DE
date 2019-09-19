---
description: Mit der Option "Kanalübergreifende Konversion"in den Berichten zur Zielgruppenoptimierung können Sie Offlinekonversionen bereitgestellten Online-Impressionen oder -Klicks zuordnen.
seo-description: Mit der Option "Kanalübergreifende Konversion"in den Berichten zur Zielgruppenoptimierung können Sie Offlinekonversionen bereitgestellten Online-Impressionen oder -Klicks zuordnen.
seo-title: Kanalübergreifende Konversion
solution: Audience Manager
title: Kanalübergreifende Konversion
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Kanalübergreifende Konversion{#cross-channel-conversion}

Mit der Option "Kanalübergreifende Konversion"in den Berichten zur Zielgruppenoptimierung können Sie Offlinekonversionen bereitgestellten Online-Impressionen oder -Klicks zuordnen.

Die [!UICONTROL Cross Channel Conversion] Berichte kombinieren die Ergebnisse der [!DNL DoubleClick Campaign Manager] (DCM-)Plattform mit [!DNL Audience Manager] Konversionseigenschaften. Auf diese Weise können Sie Offline-Konversionen mit Online-Impressionen oder -Klicks verknüpfen.

Sie können die [!UICONTROL Cross Channel Conversion] für die Berichte [Segmentleistung](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) und [optimale Häufigkeit](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) verwenden.

Um die [!UICONTROL Cross Channel Conversion] Berichte anzuzeigen, wählen Sie das **[!UICONTROL AAM+DCM]** Element in der **[!UICONTROL Platform]** Dropdownliste aus.

In der folgenden Tabelle sind wichtige Aspekte bei der Einrichtung aufgeführt [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>Mindestens ein Konversionseigenschaften muss einer Datenquelle zugewiesen werden, damit die <span class="wintitle"> kanalübergreifenden Konversionsberichte</span> ausgeführt werden können. Weitere Informationen zu Eigenschaften finden Sie unter <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Grundlegende Informationen für Eigenschaften</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Maximale Anzahl an Konversionseigenschaften </p> </td> 
   <td colname="col1"> <p>Die Berichte ziehen <i>maximal</i> 50 Konversionseigenschaften des Benutzers ein. Wenn Sie das Maximum erreichen, verwenden die Berichte die ersten 50 Konversionseigenschaften, die auf der Eigenschaften-ID basieren, in aufsteigender Reihenfolge. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Zuordnungsfenster </p> </td> 
   <td> <p> <b><span class="uicontrol"> Das Zuordnungsfenster von AAM+DCM</span></b> beträgt 14 Tage, d. h., es werden nur Konversionseigenschaften berücksichtigt, die in den letzten zwei Wochen ausgestellt wurden. </p> </td> 
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

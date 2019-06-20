---
description: Mit der Option "Kanalübergreifende Konvertierung" in den Berichten zur Zielgruppenoptimierung können Sie Offline-Konversionen bereitgestellten Online-Impressionen oder -klicks zuordnen.
seo-description: Mit der Option "Kanalübergreifende Konvertierung" in den Berichten zur Zielgruppenoptimierung können Sie Offline-Konversionen bereitgestellten Online-Impressionen oder -klicks zuordnen.
seo-title: Kanalübergreifende Konversion
solution: Audience Manager
title: Kanalübergreifende Konversion
uuid: 0 realec 23-e 502-490 b-b 7 dd -47 a 3753 a 3 f 75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Kanalübergreifende Konversion{#cross-channel-conversion}

Mit der Option &quot;Kanalübergreifende Konvertierung&quot; in den Berichten zur Zielgruppenoptimierung können Sie Offline-Konversionen bereitgestellten Online-Impressionen oder -klicks zuordnen.

Die [!UICONTROL Cross Channel Conversion] Berichte kombinieren Ergebnisse aus der [!DNL DoubleClick Campaign Manager] (DCM) Plattform mit [!DNL Audience Manager] Konversionseigenschaften. Auf diese Weise können Sie Offline-Konversionen mit Online-Impressionen oder -klicks verknüpfen.

Sie können die [!UICONTROL Cross Channel Conversion] Berichte [&quot;Segmentleistung](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) «und [&quot; Optimale Häufigkeit](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) &quot; verwenden.

Um die [!UICONTROL Cross Channel Conversion] Berichte anzuzeigen, wählen Sie das **[!UICONTROL AAM+DCM]** Element in der **[!UICONTROL Platform]** Dropdown-Liste aus.

Die folgende Tabelle listet wichtige Überlegungen bei der Einrichtung [!UICONTROL Cross Channel Conversion]auf:

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
   <td colname="col1"> <p>Es muss mindestens eine Konversionseigenschaft einer Datenquelle zugewiesen werden, damit die Berichte <span class="wintitle"> über kanalübergreifende Konversionsberichte</span> ausgeführt werden. Weitere Informationen zu Eigenschaften finden Sie unter <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Grundlegende Informationen zu Eigenschaften</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Maximale Anzahl von Konversionseigenschaften </p> </td> 
   <td colname="col1"> <p>Die Berichte beziehen sich auf <i>maximal</i> 50 Konversionseigenschaften vom Benutzer. Wenn Sie das Maximum erreichen, verwenden die Berichte die ersten 50 Konversionseigenschaften basierend auf der Eigenschaftskennung in aufsteigender Reihenfolge. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Zuordnungsfenster </p> </td> 
   <td> <p> <b><span class="uicontrol"> Das</span></b> Zuordnungsfenster von AAM + DCM beträgt 14 Tage, d. h., es werden nur Konversionseigenschaften in den letzten beiden Wochen berücksichtigt. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Last Touch-Methode </p> </td> 
   <td> <p>Die Kreativelemente, die der Benutzer zuletzt gesehen hat, bevor er konvertiert wurde, sind die der Konversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Klicks versus Impressionen </p> </td> 
   <td> <p>Ein Klick hat Vorrang vor einer Impression, wenn eine Zuordnung getroffen wird, wenn sie genau zur selben Zeit stattfinden. Auf einer Seite, auf der mehrere kreative Elemente angezeigt werden, wird die Konversion auf einer Seite angezeigt, auf die geklickt wird. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Datenneuigkeit </p> </td> 
   <td> <p>Die Berichte werden immer für Daten berechnet, die den vorherigen Tag verfügbar machen. </p> </td> 
  </tr> 
 </tbody> 
</table>

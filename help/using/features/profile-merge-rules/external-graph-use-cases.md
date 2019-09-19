---
description: Empfehlungen und Anwendungsfälle für Prospektion, Retargeting und Personalisierung für unbekannte Benutzer mit einem externen Gerätediagramm. Ein externes Gerätediagramm wird als Gerätediagramm definiert, das von Audience Manager getrennt ist. Dazu gehören die Adobe Experience Cloud Device Co-op und andere Integrationen, die Adobe mit deterministischen oder probabilistischen Gerätegrafikunternehmen von Drittanbietern hat.
seo-description: Empfehlungen und Anwendungsfälle für Prospektion, Retargeting und Personalisierung für unbekannte Benutzer mit einem externen Gerätediagramm. Ein externes Gerätediagramm wird als Gerätediagramm definiert, das von Audience Manager getrennt ist. Dazu gehören die Adobe Experience Cloud Device Co-op und andere Integrationen, die Adobe mit deterministischen oder probabilistischen Gerätegrafikunternehmen von Drittanbietern hat.
seo-title: Anwendungsbeispiele für Diagramme externer Geräte
solution: Audience Manager
title: Anwendungsbeispiele für Diagramme externer Geräte
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Anwendungsbeispiele für Diagramme externer Geräte {#external-device-graph-use-cases}

Empfehlungen und Anwendungsfälle für Prospektion, Retargeting und Personalisierung für unbekannte Benutzer mit einem externen Gerätediagramm. Ein externes Gerätediagramm wird als Gerätediagramm definiert, das von Audience Manager getrennt ist. Dies umfasst die [!DNL Adobe Experience Cloud Device Co-op] und andere Integrationen, die Adobe mit deterministischen oder probabilistischen Gerätegraphen von Drittanbietern hat.

## Recommendations {#recommendations}

Berücksichtigen Sie die Diagrammoptionen für Geräte [!DNL Experience Cloud Device Co-op] und Drittanbieter für Kampagnen, die:

* Sie haben eine niedrige Authentifizierungsebene über ihre digitalen Eigenschaften. Verwenden Sie die [Gerätediagrammoption](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) "Profillink", wenn Sie eine große Anzahl authentifizierter Benutzer haben.
* Targeting großer Zielgruppen. Die Gerätegrafiken [!DNL Experience Cloud Device Co-op] und Drittanbieter enthalten authentifizierte und nicht authentifizierte Daten.
* Segment authentifizierte und/oder nicht authentifizierte Besucher auf der Ebene des Einzelnen und des Haushalts.

![](assets/merge-rule-triangle1.png)

## Anwendungsfall für die Prospektion/das Branding {#prospecting-branding-use-cases}

Eine Branding-Kampagne soll so viele Personen wie möglich erreichen. Die Segmentqualifizierung wird dadurch kaum eingeschränkt. Diese Kampagnen können jedoch Budgets und Impressionen verschwenden, indem sie ständig auf Personen abzielen, die Ihre Inhalte mehrmals sehen und nicht konvertieren. Eine [!UICONTROL Profile Merge] Regel, die die Option [!DNL Device Co-op] oder Drittanbieter verwendet, kann Ihnen dabei helfen, eine effiziente Branding-Kampagne zu erstellen. Beispielsweise können Sie diese unbekannten Benutzer einem Segment "nicht am Markt"hinzufügen, nachdem Sie sie für die festgelegte Frequenzgrenze über mehrere Geräte hinweg gesehen haben.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nutzungsszenario </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2">Dieser Anwendungsfall geht von folgenden Bedingungen aus: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">Sie möchten einem anonymen Benutzer maximal 10 Impressionen für eine bestimmte Werbekampagne bereitstellen. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">Ein Benutzer verfügt über mehrere Geräte und hat sich möglicherweise für Ihre Site authentifiziert. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">Ein anonymer Benutzer sieht die Anzeige insgesamt zehnmal beim Durchsuchen in einem nicht authentifizierten Zustand auf seinem aktuellen Gerät und bis zu drei Geräte, die mit einem externen Gerätediagramm verknüpft sind. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">Sie haben ein Segment für <span class="keyword"> Audience Manager</span> definiert, um anonyme Benutzer nach 10 Impressionen zu qualifizieren. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Unter diesen Bedingungen <span class="keyword"> kann Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Führt die anonyme, nicht authentifizierte Aktivität zusammen, die vom aktuellen Gerät erfasst wird, und die 3 Geräte, die mit dem externen Gerätediagramm verknüpft sind (die Anzeigenimpressionen von jedem Gerät). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Wertet den nicht authentifizierten Benutzer auf Grundlage einer Kombination aus anonymer Aktivität für alle 3 Geräte aus, die mit dem externen Gerätediagramm und dem aktuellen Gerät verknüpft sind. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Sendet das Segment an ein beliebiges Echtzeit-Ziel zur Verwendung als Unterdrückungssegment auf dem aktuellen Gerät und an alle 3 Geräte, die mit dem externen Gerätediagramm verknüpft sind. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Anwendungsfall für Retargeting oder Site-Personalisierung {#retargeting-use-case}

Diese Strategien sollen einen nicht authentifizierten oder unbekannten Benutzer zurück zu Ihrer Site bringen oder sein Browsing-Erlebnis personalisieren, während er sich auf der Site befindet.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nutzungsszenario </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2">Dieser Anwendungsfall geht von folgenden Bedingungen aus: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">Sie möchten einem anonymen Benutzer ein personalisiertes Onsite- und/oder Offsite-Erlebnis auf der Grundlage seiner Aktivität auf Ihrer Site bereitstellen, während er sich in einem nicht authentifizierten Zustand befindet. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">Ein Benutzer verfügt über mehrere Geräte und hat sich möglicherweise für Ihre Site authentifiziert. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">Ein Benutzer zeigt mehrere Seiten auf Ihrer Site an, während er auf seinem aktuellen Gerät in einem nicht authentifizierten Zustand surft und bis zu drei Geräte, die mit einem externen Gerätediagramm verknüpft sind. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">Sie haben ein Segment für <span class="keyword"> Audience Manager</span> definiert, um Benutzer zu qualifizieren, nachdem sie mehrere Seiten auf Ihrer Site angezeigt haben, während sie in einem nicht authentifizierten Zustand navigieren. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Unter diesen Bedingungen <span class="wintitle"> kann Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Führt die anonyme, nicht authentifizierte Aktivität zusammen, die von den aktuellen Geräten und den 3 Geräten erfasst wird, die mit dem externen Gerätediagramm verknüpft sind (d. h. mehrere Seitenansichten von jedem Gerät). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Wertet den nicht authentifizierten Benutzer auf Grundlage einer Kombination aus anonymer Aktivität für alle 3 Geräte aus, die mit dem externen Gerätediagramm und dem aktuellen Gerät verknüpft sind. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Sendet das Segment an ein beliebiges Echtzeit-Ziel, um ein personalisiertes Onsite- und/oder Offsite-Erlebnis für das aktuelle Gerät und alle 3 Geräte bereitzustellen, die mit dem externen Gerätediagramm verknüpft sind. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Optionen für die Profilzusammenführungsregel für externe Gerätediagramme - Anwendungsfälle {#profile-merge}

Die Optionen für die Zusammenführungsregeln für diese Anwendungsfälle sehen ähnlich aus wie die folgenden verfügbaren Optionen. Die [!UICONTROL Authenticated Profile] Optionen werden deaktiviert, da diese Einstellungen nur bei Auswahl **[!UICONTROL Current Authenticated Profile]** oder **[!UICONTROL Last Authenticated Profile]** Auswahl verfügbar sind. Ihr [!UICONTROL Device Options] hängt von der Art der Gerätediagrammeinstellung ab, die Sie verwenden möchten oder die Ihnen zur Verfügung steht.

![](assets/merge-rules-external.png)

Weitere Informationen zur Funktionsweise dieser Gerätediagrammprozesse finden Sie im PDF-, [Audience Manager- und Externe Gerätediagramme](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_LIKE_THIS]
>
>* [Anwendungsfälle des Profillink-Gerätediagramms](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Häufig gestellte Fragen zu Regeln zur Profilzusammenführung](../../faq/faq-profile-merge.md)


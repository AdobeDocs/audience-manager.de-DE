---
description: Empfehlungen und Anwendungsfälle für die Ermittlung, Retargeting und Personalisierung für unbekannte Benutzer mit einem externen Gerätediagramm. Ein externes Gerätediagramm ist als Gerätediagramm definiert, das sich von Audience Manager unterscheidet. Dies umfasst die Adobe Experience Cloud Device Co-op und andere Integrationen, die Adobe mit deterministischen oder probabilistischen Gerätediagrammunternehmen von Drittanbietern hat.
seo-description: Empfehlungen und Anwendungsfälle für die Ermittlung, Retargeting und Personalisierung für unbekannte Benutzer mit einem externen Gerätediagramm. Ein externes Gerätediagramm ist als Gerätediagramm definiert, das sich von Audience Manager unterscheidet. Dies umfasst die Adobe Experience Cloud Device Co-op und andere Integrationen, die Adobe mit deterministischen oder probabilistischen Gerätediagrammunternehmen von Drittanbietern hat.
seo-title: Anwendungsbeispiele für Diagramme externer Geräte
solution: Audience Manager
title: Anwendungsbeispiele für Diagramme externer Geräte
uuid: f 4 bc 822 d -39 d 2-4680-90 ed -7 ee 2 ead 6 db 6 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Anwendungsbeispiele für Diagramme externer Geräte {#external-device-graph-use-cases}

Empfehlungen und Anwendungsfälle für die Ermittlung, Retargeting und Personalisierung für unbekannte Benutzer mit einem externen Gerätediagramm. Ein externes Gerätediagramm ist als Gerätediagramm definiert, das sich von Audience Manager unterscheidet. This includes the [!DNL Adobe Experience Cloud Device Co-op] and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.

## Recommendations {#recommendations}

Consider the [!DNL Experience Cloud Device Co-op] and third-party device graph options for campaigns that:

* eine niedrige Authentifizierungsstufe für ihre digitalen Eigenschaften. Use the [Profile Link device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a large number of authenticated users.
* Richten Sie große Zielgruppen ein. The [!DNL Experience Cloud Device Co-op] and third-party device graphs contain authenticated and un-authenticated data.
* Segmentauthentifizierte und/oder nicht authentifizierte Besucher auf Einzelpersonen- und Haushaltsebene.

![](assets/merge-rule-triangle1.png)

## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

Eine Branding-Kampagne soll so viele Menschen wie möglich erreichen. Sie platziert Segmentqualifizierung nur wenige Einschränkungen. Diese Kampagnen können jedoch Budgets und Impressionen abwägen, indem sie ständig Personen ansprechen, die Ihren Inhalt mehrmals sehen und nicht konvertieren. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. Sie können diese unbekannten Benutzer zum Beispiel einem "nicht in Market" -Segment hinzufügen, nachdem Sie sie für Ihre Häufigkeit der Häufigkeit auf mehreren Geräten gesehen haben.

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
   <td colname="col2">In diesem Fall werden folgende Bedingungen angenommen: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">Sie möchten für einen anonymen Benutzer maximal 10 Impressionen für eine bestimmte Werbekampagne bereitstellen. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">Ein Benutzer hat mehrere Geräte und kann auf Ihrer Site authentifiziert sein. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">Anonyme Benutzer sehen die Anzeige insgesamt zehnmal während des Browsens in einem nicht authentifizierten Zustand auf ihrem aktuellen Gerät und bis zu 3 Geräten, die mit einem externen Gerätediagramm verknüpft sind. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Führt die anonyme, nicht authentifizierte Aktivität zusammen, die vom aktuellen Gerät erfasst wurde, und den 3 Geräten, die vom externen Gerätediagramm (die Anzeigenimpressionen von jedem Gerät) verknüpft sind. </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Wertet den nicht authentifizierten Benutzer für Segmentqualifizierung basierend auf einer Kombination aus anonyme Aktivität auf allen 3 Geräten aus, die mit dem externen Gerätediagramm und dem aktuellen Gerät verknüpft sind. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Sendet das Segment an ein beliebiges Echtzeit-Ziel zur Verwendung als Unterdrückungssegment auf dem aktuellen Gerät und allen 3 Geräten, die mit dem externen Gerätediagramm verknüpft sind. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

Diese Strategien sollen einen nicht authentifizierten oder unbekannten Benutzer wieder an Ihre Site bringen oder seine Browsererfahrung personalisieren, während sie auf der Site sind.

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
   <td colname="col2">In diesem Fall werden folgende Bedingungen angenommen: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">Sie möchten ein personalisiertes Onsite- und/oder Offsite-Erlebnis für anonyme Benutzer bereitstellen, die auf ihrer Aktivität auf Ihrer Site basieren, während sie nicht authentifiziert sind. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">Ein Benutzer hat mehrere Geräte und kann auf Ihrer Site authentifiziert sein. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">Ein Benutzer sieht sich mehrere Seiten auf Ihrer Site an, während er in einem nicht authentifizierten Zustand auf ihrem aktuellen Gerät und bis zu 3 Geräten mit einem externen Gerätediagramm surft. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Führt die anonyme, nicht authentifizierte Aktivität zusammen, die von den aktuellen Geräten erfasst wurde, und den 3 Geräten, die durch das externe Gerätediagramm verknüpft sind (die mehrere Seitenansichten von jedem Gerät). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Wertet den nicht authentifizierten Benutzer für Segmentqualifizierung basierend auf einer Kombination aus anonyme Aktivität auf allen 3 Geräten aus, die mit dem externen Gerätediagramm und dem aktuellen Gerät verknüpft sind. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Sendet das Segment an ein beliebiges Echtzeit-Ziel, um eine personalisierte On-Site- und/oder Offsite-Erfahrung über das aktuelle Gerät und alle 3 Geräte hinweg zu liefern, die mit dem externen Gerätediagramm verknüpft sind. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Profile Merge Rule Options for External Device Graph Use Cases {#profile-merge}

Ihre Regeloptionen für Zusammenführungsregeln für diese Anwendungsfälle würden ähnlich wie unten dargestellt aussehen. The [!UICONTROL Authenticated Profile] options are deactivated because these settings are only available when you select **[!UICONTROL Current Authenticated Profile]** or **[!UICONTROL Last Authenticated Profile]**. Your [!UICONTROL Device Options] will vary depending on the type of device graph setting that you want to use or that is available to you.

![](assets/merge-rules-external.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Anwendungsbeispiele für Gerätediagramm-Diagramm](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [Häufig gestellte Fragen zur Profilzusammenführung](../../faq/faq-profile-merge.md)


---
description: Recommendations und Anwendungsfälle für die Prospektion, das Retargeting und die Personalisierung für unbekannte Benutzende mit einem externen Gerätediagramm. Ein externes Gerätediagramm wird als Gerätediagramm definiert, das vom Audience Manager getrennt ist. Dazu gehören Integrationen, die Adobe mit deterministischen oder probabilistischen Gerätediagramm-Unternehmen von Drittanbietern hat.
seo-description: Recommendations and use cases for prospecting, retargeting, and personalization for unknown users with an external device graph. An external device graph is defined as a device graph that is separate from Audience Manager. This includes integrations Adobe has with third-party deterministic or probabilistic device graph companies.
seo-title: External Device Graph Use Cases
solution: Audience Manager
title: Anwendungsfälle für Diagramme mit externen Geräten
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
feature: Profile Merge
exl-id: 657aecfd-7fa3-466e-8331-c49cc921e3a9
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 4%

---

# Anwendungsfälle für Diagramme mit externen Geräten {#external-device-graph-use-cases}

Recommendations und Anwendungsfälle für die Prospektion, das Retargeting und die Personalisierung für unbekannte Benutzende mit einem externen Gerätediagramm. Ein externes Gerätediagramm wird als Gerätediagramm definiert, das vom Audience Manager getrennt ist. Dazu gehören Integrationen, die Adobe mit deterministischen oder probabilistischen Gerätediagramm-Unternehmen von Drittanbietern hat.

## Empfehlungen {#recommendations}

Optionen für Gerätediagramme von Drittanbietern für Kampagnen in Betracht ziehen, die:

* verfügen über ein niedriges Authentifizierungsniveau für ihre digitalen Eigenschaften. Verwenden Sie die [!UICONTROL Profile Link Device Graph option], wenn eine große Anzahl authentifizierter Benutzer vorhanden ist.
* Targeting großer Zielgruppen. Diagramme von Drittanbietergeräten enthalten authentifizierte und nicht authentifizierte Daten.
* Segmentieren Sie authentifizierte und/oder nicht authentifizierte Besucher auf Einzel- und Haushaltsebene.

![](assets/merge-rule-triangle1.png)
<!-- 
## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

A branding campaign is designed to reach as many people as possible. It places few limits on segment qualification. But, these campaigns can waste budget and impressions by constantly targeting people who see your content multiple times and don't convert. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. For example, you can add these unknown users to a "not in-market" segment after seeing them across multiple devices for your set frequency cap.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">You want to deliver a maximum of 10 impressions to an anonymous user for a specific ad campaign. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">A user has 4 devices and may or may not have authenticated on your site. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">An anonymous user sees the ad a total of 10 times while browsing in an unauthenticated state on their current device and 3 devices linked to the current device by an external device graph. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Merges the anonymous, unauthenticated activity collected from the current device and the 3 devices linked by the external device graph (the ad impressions from each device). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Sends the segment to any real-time destination for use as a suppression segment on the current device and all 3 devices linked by the external device graph. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

These strategies are designed to bring an unauthenticated or unknown user back to your site or personalize their browsing experience while they're on-site.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">You want to deliver a personalized on-site and/or off-site experience to an anonymous user based on their activity on your site while in an unauthenticated state. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">A user has multiple devices and may or may not have authenticated to your site. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">A user views multiple pages on your site while browsing in an unauthenticated state on their current device and 3 other devices linked by an external device graph. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state.</li>
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Merges the anonymous, unauthenticated activity collected from the current devices and the 3 devices linked by the external device graph (the multiple page views from each device). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Sends the segment to any real-time destination to deliver a personalized on-site and/or off-site experience across the current device and all 3 devices linked by the external device graph. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table> -->

<!-- ## Expanded Device Targeting {#audience-expansion}

This use case exemplifies how you can expand the size of your addressable audience with accurate cross-device personalization, through [!DNL External Device Graphs].

Let's say Jane owns three devices that she uses regularly to search for holiday package deals: her laptop ([!DNL Device 1]), her smartphone ([!DNL Device 2]), and her tablet ([!DNL Device 3]). While using the laptop, Jane searched for flights, hotels, and guided tours. While using the smartphone and tablet, she only visited the homepage of the travel agency.

By using the [!UICONTROL No Cross-Device Profile] + [!DNL External Device Graphs] rule, the travel agency can merge all three devices profiles, since they are linked to the same owner through the [!DNL External Device Graphs].

![audience-expansion-rule](assets/audience-expansion-rule.png)

In our example, the traits required to qualify for the segment have all been collected on [!DNL Device 1]. Since Audience Manager qualifies every device profile that took part in the profile merge for a segment, all of Jane's three device profiles are now segmented.

Through this rule, the device graph has expanded the number of device profiles which qualify for the segment from one to three and has enabled the travel agency to deliver a consistent message to all three devices owned by Jane.

![audience-expansion](assets/audience-expansion.png) -->

## Erweitertes geräteübergreifendes Targeting {#advanced-graph-expansion}

Dieses Anwendungsbeispiel zeigt, wie mithilfe der **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**-Regel die Zielgruppen-Zielgruppenbestimmung für authentifizierte Besucher mit Geräten über ein externes Gerätediagramm erweitert werden kann.

![last-device-graph](assets/last-profile-link.png)

Im folgenden Beispiel möchte das Unternehmen Acme Inc. alle Haushalte mit einem Einkommen von über 100.000 US-Dollar pro Jahr ansprechen, die [!DNL Acme Inc.] Abonnenten auf [!DNL Data Plan A] haben, die ein [!DNL iPhone 7] verwenden.

John verwendet seine iPhone 7 auf Data Plan A, um sich auf der Acme Inc.-Website zu authentifizieren. Gleichzeitig enthält Johns [!DNL Profile Link Device Graph]-Cluster zwei zusätzliche Geräte, die er regelmäßig verwendet: seinen Laptop ([!DNL Device 1]) und sein sekundäres Smartphone [!DNL Device 2] (ein [!DNL Samsung S7] auf [!DNL Data Plan B]).

Durch die Verwendung der **[!UICONTROL Profile Link Device Graph]** **[!UICONTROL Last Authenticated Profiles]** + kann [!DNL Acme Inc.] personalisierte Nachrichten an alle drei Geräte aus dem Gerätediagramm-Cluster von John senden, obwohl zunächst nur eines von ihnen für das Segment qualifiziert ist.

![advanced-graph-expansion](assets/advanced-device-graph-expansion.png)

>[!MORELIKETHIS]
>
>* [Anwendungsfälle für das Profil-Link-Gerätediagramm](profile-link-use-case.md)
>* [Allgemeine Anwendungsfälle für Profilzusammenführungsrichtlinien](merge-rule-targeting-options.md)
>* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)

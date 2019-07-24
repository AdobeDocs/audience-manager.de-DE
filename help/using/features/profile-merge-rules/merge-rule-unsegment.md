---
description: Die Aufhebung der Segmentierung beschreibt Prozesse, die Geräteprofile aus Segmenten ausschließen und entfernen. Die Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, mit der eine Regel zum Profilzusammenführen erstellt wird.
seo-description: Die Aufhebung der Segmentierung beschreibt Prozesse, die Geräteprofile aus Segmenten ausschließen und entfernen. Die Fähigkeit, ein Geräteprofil aus einem Segment zu entfernen, hängt von der Geräteoption ab, mit der eine Regel zum Profilzusammenführen erstellt wird.
seo-title: Regeln für die Profilzusammenführung und das Aufheben der Segmentierung von Geräten
solution: Audience Manager
title: Regeln für die Profilzusammenführung und das Aufheben der Segmentierung von Geräten
uuid: b 61 c 6 de 3-5 fe 4-4892-a 05 a -96 a 4 cb 35 af 34
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Un-Segmentation Processes {#profile-merge-rules-and-device-un-segmentation-processes}

Die Aufhebung der Segmentierung beschreibt Prozesse, die Geräteprofile aus Segmenten ausschließen und entfernen. Your ability to remove a device profile from a segment depends on the device option used to create a [!UICONTROL Profile Merge Rule].

## Available Device Options {#device-options}

As a reminder, the [!UICONTROL Device Options] are available in the [!UICONTROL Profile Merge Rules Setup] section when you create or edit a [!UICONTROL Profile Merge Rule].

![](assets/merge-rules-options.png)

## Current Device Profile Option and Device Unsegmentation {#current-device-profile-options}

**[!UICONTROL Current Device Profile]** ist die standardoption für Geräteprofile für a [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] kann ein Geräteprofil aus einem Segment entfernen, wenn die [!UICONTROL Profile Merge Rule]**[!UICONTROL Current Device Profile]** Option verwendet wird. Unter diesen Bedingungen wird die Segmentierung durchgeführt, wenn:

* Das Geräteprofil ist 120 Tage inaktiv. Ein wöchentlicher Datenbereinigungsprozess entfernt inaktive Geräteprofile aus Ihren Segmenten.
* Das Gerät qualifiziert sich nicht mehr für ein Segment, da es durch Aktualisierungen oder Änderungen am Geräteprofil nicht mehr qualifiziert wird. This happens when segment qualification criteria change, or you apply an [!DNL AND NOT] operator to a segment rule, or specify [recency and frequency](../../features/segments/recency-and-frequency.md) conditions that use the less than/equal to settings. Use cases are described in the [Instant Cross-Device Suppression](../../features/profile-merge-rules/instant-cross-device-suppression.md) documentation.

![](assets/single_device_use_case.png)

<!-- 

<p> <span class="keyword"> Audience Manager</span> can remove a device profile from a segment when your <span class="wintitle"> Profile Merge Rule</span> uses the <b><span class="uicontrol"> Current Device Profile</span></b> option. Under these conditions, unsegmentation happens when: </p> 
<p> 
 <ul id="ul_596501272A224228BD330DD56E01D973"> 
  <li id="li_E4FA1A5C722748CD82AE3A49FCBE86F6">The device profile has been inactive for 120-days. A weekly data cleanup process removes inactive device profiles from your segments. </li> 
  <li id="li_DB0CCD28425048D5B35309B8C2C384F9">The device no longer qualifies for a segment because updates or changes to the device profile disqualify it. This happens when segment qualification criteria change, or you apply an AND NOT operator to a segment rule, or specify <a href="../../features/segments/recency-and-frequency.md"> recency and frequency</a> conditions that use the less than/equal to settings. </li> 
 </ul> </p> 
<p style="text-align: center;"> <img src="assets/unsegment3.png" id="image_B55E5A5EB1964AA08C817211006294E1" /> </p>

 -->

## No Device Option and Device Unsegmentation {#no-device-option}

[!DNL Audience Manager] kann eine geräteübergreifende ID aus einem Segment entfernen, wenn die [!UICONTROL Profile Merge Rule] Option **[!UICONTROL No Device Profile]** + **[!UICONTROL Current Authenticated]** verwendet wird. Unter diesen Bedingungen erfolgt die Segmentierung, wenn die geräteübergreifende ID nicht mehr für ein Segment qualifiziert ist, da Aktualisierungen oder Änderungen am geräteübergreifenden Profil diese nicht mehr erfüllen. This happens when segment qualification criteria change, or you apply an [!UICONTROL AND NOT] operator to a segment rule, or specify [recency and frequency](../../features/segments/recency-and-frequency.md) conditions that use the less than/equal to settings. Use cases are described in the [Instant Cross-Device Suppression](../../features/profile-merge-rules/instant-cross-device-suppression.md) documentation.

![](assets/no_device_use_case.png)

## Device Graph Options and Device Unsegmentation {#device-graph-options-unsegmentation}

[!DNL Audience Manager] kann mehrere Geräteprofile aus einem Segment entfernen, wenn Sie [!UICONTROL Profile Merge Rule] eine Gerätediagrammoption verwenden. Die Segmentierung erfolgt, wenn das zusammengeführte Profil des Geräts vom Gerätediagramm nicht mehr für das Segment qualifiziert ist, da Aktualisierungen oder Änderungen an diesem zusammengeführten Profil diese vom Segment ausschließen. This happens when segment qualification criteria change, or you apply an [!UICONTROL AND NOT] operator to a segment rule, or specify [recency and frequency](../../features/segments/recency-and-frequency.md) conditions that use the less than/equal to settings. Use cases are described in the [Instant Cross-Device Suppression](../../features/profile-merge-rules/instant-cross-device-suppression.md) documentation.

>[!NOTE]
>
>**Die Beschränkung auf vier Geräte für die Segmentauswertung und die Nichtqualifizierung** [!DNL Audience Manager] führt bei der Auswertung von Segmenten mit einer [!UICONTROL Profile Merge Rule] Gerätegrafik bis zu vier Geräte zusammen. [!DNL Audience Manager] bewertet das *aktuelle Gerät und drei zusätzliche Geräte zuletzt in Echtzeit*. Wenn das unsegmentsignal ausgegeben wird, werden das aktuelle Gerät und drei weitere in Echtzeit angezeigte Geräte im Ziel aus dem Segment entfernt. Beispielsweise werden in einem sechs Gerätecluster bis zu vier Geräte zusammengeführt, ausgewertet und für ein Segment qualifiziert. Gleichermaßen werden bis zu vier Geräte zusammengeführt, ausgewertet und nicht segmentiert.

![](assets/cross_device_workflow.png)

<!-- 

<p>Currently, <span class="keyword"> Audience Manager</span> <i>cannot </i> remove a device profile from a segment when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. This applies to rules created with these <span class="wintitle"> Device Options</span> settings: </p> 
<p> 
 <ul id="ul_0923834C984F464E9AB12FF5A8773214"> 
  <li id="li_731F67B7A07342988B13D7F91ECA5A9E">Profile Link Device Graph. </li> 
  <li id="li_D1EFC6F124124E64A0732DD060F788BE">The <span class="keyword"> Adobe</span> device graph. </li> 
  <li id="li_CFD4189D4488432D92732532D23B30C7">Other third-party device graph options available that are available to you. </li> 
 </ul> </p> 
<p> Unlike the previous case above, using the AND NOT operator or less than/equal to settings won't remove all of the devices from a segment profile. However, you can unsegment device profiles if you create simple segment rules and apply unsegment logic in the destination that receives your data. The following sections walks you through different unsegmentation use cases. </p>

 -->



<!-- 

<p>This workaround shows you how to unsegment with Boolean <span class="wintitle"> AND NOT</span> logic when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. This procedure uses separate, simple segments mapped to the same destination. In this case, you apply AND NOT logic on the destination rather than creating rules in Segment Builder. To set up unsegment rules for this use case: </p> 
<p> 
 <ol id="ol_677F0F9E6CB640079D9021DE66819916"> 
  <li id="li_95F898FDFB2D4F5395201FEA2E60A3AF">Create separate, single-trait segments as shown in the following example. <p style="text-align: center;"><img src="assets/unsegment1.png" id="image_9574D599F449482F8475D9AD2B725DE1" /> </p> </li> 
  <li id="li_3A9F6D8B3CBB4F65B9A06EEC3B265158">Map the segments to the same destination. In this case, we're sending these to <span class="keyword"> Media Optimizer</span>. </li> 
  <li id="li_092BB5887D0D4EE4B09F4B1C6703D454">Set AND NOT logic on the destination (<span class="keyword"> Media Optimizer</span>) rather than in <span class="keyword"> Audience Manager</span>. <p style="text-align: center;"><img src="assets/unsegment2.png" id="image_1E707693ABED41129F11F9FBA334DA58" /> </p> </li> 
 </ol> </p> 
<p> If you're not using <span class="keyword"> Media Optimizer</span>, apply AND NOT logic on whatever destination receives these segments. </p>

 -->



<!-- 

<p>This workaround shows you how to unsegment with the < = (less than/equal to) recency and frequency settings when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. To set up unsegment rules for this use case: </p> 
<p> 
 <ol id="ol_DCBEE004B9FE40A881E4EC17FAEA50C2"> 
  <li id="li_DB8C1B6D5C5546E68769902A4F367966">Create a segment that contains a single trait and apply a > = (greater than/equal to) recency and frequency rule to the trait. <p style="text-align: center;"><img src="assets/unsegment4.png" id="image_38069E00B8E8435AAD6E4420CC788D1E" /> </p> </li> 
  <li id="li_0DC50960D83B4B27A40F0BC76B944E0B">Map the segment to a destination. In this case, we're sending the segment to <span class="keyword"> Media Optimizer</span>. </li> 
  <li id="li_FC23194A9FE54296914393F8067A6672">Set NOT logic on the destination (<span class="keyword"> Media Optimizer</span>) rather than in <span class="keyword"> Audience Manager</span>. Use NOT logic to exclude all devices that qualify for this segment from your campaign. <p style="text-align: center;"><img src="assets/unsegment5.png" id="image_BE4408DCB12041A191F208CB1807B9E6" /> </p> </li> 
 </ol> </p> 
<p> If you're not using <span class="keyword"> Media Optimizer</span>, apply NOT logic on whatever destination receives these segments. </p>

 -->

>[!MORE_ LIKE_ THIS]
>
>* [Regeln für die Profilzusammenführung und häufig gestellte Fragen zum Gerätediagramm](../../faq/faq-profile-merge.md)
>* [Sofortige geräteübergreifende Unterdrückung](../../features/profile-merge-rules/instant-cross-device-suppression.md)
>* [Wichtige Überlegungen zu Profilzusammenführungsregeln mit Gerätediagrammen](../../features/profile-merge-rules/considerations-pmr-device-graph.md)


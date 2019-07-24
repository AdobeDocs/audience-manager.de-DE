---
description: Mit den Optionen für Zusammenführungsregeln können Sie steuern, welche Art von Daten Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom Profillink-Gerätediagramm, der Adobe Experience Cloud Device Co-op und/oder anderen Drittanbietern von Gerätediagrammen zugeordnet sind, die in Audience Manager integriert sind. Sie können maximal 3 Profile Zusammenführungsregeln erstellen.
seo-description: Mit den Optionen für Zusammenführungsregeln können Sie steuern, welche Art von Daten Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom Profillink-Gerätediagramm, der Adobe Experience Cloud Device Co-op und/oder anderen Drittanbietern von Gerätediagrammen zugeordnet sind, die in Audience Manager integriert sind. Sie können maximal 3 Profile Zusammenführungsregeln erstellen.
seo-title: Regeloptionen für Profilzusammenführung definiert
solution: Audience Manager
title: Regeloptionen für Profilzusammenführung definiert
uuid: 225 eeaf 7-45 e 9-4 f 21-9360-d 80 a 9 f 90520 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

Mit den Optionen für Zusammenführungsregeln können Sie steuern, welche Art von Daten Audience Manager für die Segmentierung verwendet. A merge rule can include device profiles mapped by the [!UICONTROL Profile Link] device graph, the [!UICONTROL Adobe Experience Cloud Device Co-op], and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 3 [!UICONTROL Profile Merge Rules].

You build a [!UICONTROL Profile Merge Rule] by making a selection from these options:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> Authentifizierte Optionen</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> Authentifizierte Profiloptionen</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Geräteoptionen</a> </li>
</ul>

## Authenticated Options {#auth-options}

The [!UICONTROL Authenticated Options] let you select un-authenticated and authenticated users and leverage their cross-device profile for segmentation. Mit diesen Optionen können Sie bestimmte Benutzer auf einem freigegebenen Gerät identifizieren und erreichen. For more information on anonymous and authenticated users, see [Visitor Authentication States in Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Authentifizierte Option </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Kein authentifiziertes Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use data collected from authenticated users. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuelles authentifiziertes Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read and write data to the authenticated profile if a visitor has logged in to your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zuletzt authentifiziertes Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read data from the authenticated profile of the user who last logged in on the device. </p> <p>When selected, <span class="keyword"> Audience Manager</span> will not write new trait data to the authenticated profile if the user is anonymous. Bei der Authentifizierung werden neue Daten in das authentifizierte Profil des Benutzers geschrieben. </p> </td>
  </tr> 
 </tbody>
</table>

## Authenticated Profile Options {#profile-options}

The [!UICONTROL Authenticated Profile Options] lists your cross-device data sources. These options use the names you provided when you created a cross-device data source (see [Create a Cross-Device Data Source](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). Sie können bis zu 3 geräteübergreifende Datenquellen auswählen, die für jede Profilregel verwendet werden sollen. The [!UICONTROL Authenticated Profile Options] are available when you choose **[!UICONTROL Current Authenticated Profile]** or **[!UICONTROL Last Authenticated Profile]**.

## Device Options {#device-options}

The [!UICONTROL Device Options] let you select the type of *`device profile`* used by a [!UICONTROL Profile Merge Rule]. Ein Geräteprofil besteht aus Eigenschaften, die von Benutzern erfasst werden, wenn sie anonym im Internet surfen. Eine Regel zum Zusammenführen von Profilen enthält mindestens eine authentifizierte Option und eine Geräteoption.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Geräteoption </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Kein Geräteprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> not to use the traits contained in the anonymous profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuelles Geräteprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to use the anonymous device profile for segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profillink Gerätediagramm</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read the profiles from the current device and the last 3 devices that the user has authenticated from. This device graph is built on your own, first-party data in <span class="keyword"> Audience Manager</span>. Es eignet sich ideal für Kunden, die über eine hohe Authentifizierungsstufe für ihre digitalen Eigenschaften verfügen. <span class="wintitle"> Das</span> Gerätediagramm für Profilverknüpfungen wird in Echtzeit aktualisiert. This option is available when you select <b><span class="uicontrol"> Current Authenticated Profile</span></b> or <b><span class="uicontrol"> Last Authenticated Profile</span></b>. When using this option, you can only choose a single authenticated profile (<span class="keyword"> Audience Manager</span> automatically grays out the others). See also, <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Profile Link Device Graph Use Cases</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to merge device profiles using the links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p>Die <span class="keyword">-Device Co-op</span> ist eine digitale Kooperation, bei der teilnehmende Kunden Informationen zu Geräteverknüpfungen freigeben. The <span class="keyword"> Device Co-op</span> processes this data in a <span class="term"> device graph</span>. Geräte-Gerätegeräte vereinen Formulargerätecluster gemeinsam. These links are built from <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistic and deterministic data</a>. Die Cluster stellen eine Gruppe von Geräten dar, die von einer unbekannten Person verwendet werden. Die <span class="keyword">Device Co-op</span> gibt diese Cluster für die Mitglieder frei, wodurch diese ihren Kunden wertvolle und konsistente Erfahrungen über mehrere Geräte hinweg bieten können. </p> <p> For more information about the <span class="wintitle"> Device Co-op</span>, see the: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Device Co-op overview</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Voraussetzungen für eine Mitgliedschaft</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Gerätediagramm: Interne Prozesse und Ausgabe</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager und externe Gerätediagramme</a> (PDF-Download). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Gerätediagrammoptionen von Drittanbietern</b> (Person und Haushalt) </p> </td>
   <td colname="col2"> <p>Mit diesen Optionen können Sie Zusammenführungsregeln erstellen, die auf der Gerätediagrammtechnologie basieren, die von einem Drittanbieter bereitgestellt wird. Ein Gerätediagramm von Drittanbietern bietet Folgendes: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Probabilistische und/oder deterministische Daten. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Daten auf der Person oder auf der Haushaltsebene. </li> 
     </ul> </p> <p>To use these options, you must be a customer of a device graph provides who is already integrated with <span class="keyword"> Audience Manager</span>. Wenden Sie sich an Ihren Kundenbetreuer, um weitere Informationen zu erhalten oder um zu beginnen. </p> <p>Siehe auch &lt; a href = "../../features/profile-merge-rules/external-graph-use-cases. md). </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Häufig gestellte Fragen zur Profilzusammenführung](../../faq/faq-profile-merge.md)


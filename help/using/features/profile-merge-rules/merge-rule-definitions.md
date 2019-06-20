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


# Regeloptionen für Profilzusammenführung definiert {#profile-merge-rule-options-defined}

Mit den Optionen für Zusammenführungsregeln können Sie steuern, welche Art von Daten Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom [!UICONTROL Profile Link] Gerätediagramm, von den Geräten [!UICONTROL Adobe Experience Cloud Device Co-op]und/oder vom Drittanbieter-Gerätediagramm-Provider zugeordnet werden, die in Audience Manager integriert sind. Sie können maximal 3 [!UICONTROL Profile Merge Rules]erstellen.

Sie erstellen eine [!UICONTROL Profile Merge Rule] Auswahl aus folgenden Optionen:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> Authentifizierte Optionen</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> Authentifizierte Profiloptionen</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> Geräteoptionen</a> </li>
</ul>

## Authentifizierte Optionen {#auth-options}

Hier können [!UICONTROL Authenticated Options] Sie nicht authentifizierte und authentifizierte Benutzer auswählen und ihr geräteübergreifenden Profil für die Segmentierung nutzen. Mit diesen Optionen können Sie bestimmte Benutzer auf einem freigegebenen Gerät identifizieren und erreichen. Weitere Informationen zu anonymen und authentifizierten Benutzern finden Sie unter [Besucher-Authentifizierungsstatus in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, keine von authentifizierten Benutzern erfassten Daten zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuelles authentifiziertes Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, Daten in das authentifizierte Profil zu lesen und zu schreiben, wenn ein Besucher sich bei Ihrer Site angemeldet hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zuletzt authentifiziertes Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, Daten aus dem authentifizierten Profil des Benutzers zu lesen, der zuletzt auf dem Gerät angemeldet ist. </p> <p>Wenn diese Option aktiviert ist, schreibt <span class="keyword"> Audience Manager</span> keine neuen Daten für Eigenschaften in das authentifizierte Profil, wenn der Benutzer anonym ist. Bei der Authentifizierung werden neue Daten in das authentifizierte Profil des Benutzers geschrieben. </p> </td>
  </tr> 
 </tbody>
</table>

## Authentifizierte Profiloptionen {#profile-options}

Die [!UICONTROL Authenticated Profile Options] Liste enthält die geräteübergreifenden Datenquellen. Diese Optionen verwenden die Namen, die Sie beim Erstellen einer geräteübergreifenden Datenquelle angegeben haben (siehe [Erstellen einer geräteübergreifenden Datenquelle](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). Sie können bis zu 3 geräteübergreifende Datenquellen auswählen, die für jede Profilregel verwendet werden sollen. Die Verfügbarkeit ist [!UICONTROL Authenticated Profile Options] verfügbar, wenn **[!UICONTROL Current Authenticated Profile]****[!UICONTROL Last Authenticated Profile]** Sie

## Geräteoptionen {#device-options}

Mit dem Befehl [!UICONTROL Device Options] können Sie den von a verwendeten *`device profile`* Typ auswählen [!UICONTROL Profile Merge Rule]. Ein Geräteprofil besteht aus Eigenschaften, die von Benutzern erfasst werden, wenn sie anonym im Internet surfen. Eine Regel zum Zusammenführen von Profilen enthält mindestens eine authentifizierte Option und eine Geräteoption.

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
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die im anonymen Profil enthaltenen Eigenschaften nicht für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuelles Geräteprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Teilt <span class="keyword"> Audience Manager</span> mit, das anonyme Geräteprofil für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profillink Gerätediagramm</span></b> </p> </td> 
   <td colname="col2"> <p>Teilt <span class="keyword"> Audience Manager</span> mit, die Profile vom aktuellen Gerät und den letzten 3 Geräten zu lesen, die der Benutzer authentifiziert hat. Dieses Gerätediagramm basiert auf Ihren eigenen, Erstanbieterdaten in <span class="keyword"> Audience Manager</span>. Es eignet sich ideal für Kunden, die über eine hohe Authentifizierungsstufe für ihre digitalen Eigenschaften verfügen. <span class="wintitle"> Das</span> Gerätediagramm für Profilverknüpfungen wird in Echtzeit aktualisiert. Diese Option ist verfügbar, wenn Sie <b><span class="uicontrol"> aktuell authentifizierte Profile</span></b> oder <b><span class="uicontrol"> zuletzt authentifizierte Profile auswählen</span></b>. Wenn Sie diese Option verwenden, können Sie nur ein authentifiziertes Profil auswählen (<span class="keyword"> Audience Manager</span> wählt automatisch die anderen aus). Siehe auch Anwendungsbeispiele für <a href="../../features/profile-merge-rules/profile-link-use-case.md"> Device Link Device Graph</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Teilt <span class="keyword"> Audience Manager</span> mit, dass sie Geräteprofile mithilfe der Links zusammenführen, die von der <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op bereitgestellt</a>werden. </p> <p>Die <span class="keyword">-Device Co-op</span> ist eine digitale Kooperation, bei der teilnehmende Kunden Informationen zu Geräteverknüpfungen freigeben. Die <span class="keyword"> Gerätekooperation</span> verarbeitet diese Daten in einem <span class="term"> Gerätediagramm</span>. Geräte-Gerätegeräte vereinen Formulargerätecluster gemeinsam. Diese Links basieren auf <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistischen und deterministischen Daten</a>. Die Cluster stellen eine Gruppe von Geräten dar, die von einer unbekannten Person verwendet werden. Die <span class="keyword">Device Co-op</span> gibt diese Cluster für die Mitglieder frei, wodurch diese ihren Kunden wertvolle und konsistente Erfahrungen über mehrere Geräte hinweg bieten können. </p> <p> Weitere Informationen zur <span class="wintitle"> Gerätekooperation finden Sie unter</span>: </p> <p> 
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
     </ul> </p> <p>Um diese Optionen zu verwenden, müssen Sie ein Kunde eines Gerätediagramms sein, der bereits mit <span class="keyword"> Audience Manager integriert</span>ist. Wenden Sie sich an Ihren Kundenbetreuer, um weitere Informationen zu erhalten oder um zu beginnen. </p> <p>Siehe auch &lt; a href = "../../features/profile-merge-rules/external-graph-use-cases. md). </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Häufig gestellte Fragen zur Profilzusammenführung](../../faq/faq-profile-merge.md)


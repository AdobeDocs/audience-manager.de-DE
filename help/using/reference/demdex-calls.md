---
description: Audience Manager und der Experience Cloud ID-Dienst senden Aufrufe an die und empfangen Daten aus der demdex.net-Domäne. Dies kann so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber dies ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex. net-Aufrufs beschrieben.
seo-description: Audience Manager und der Experience Cloud ID-Dienst senden Aufrufe an die und empfangen Daten aus der demdex.net-Domäne. Dies kann so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber dies ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex. net-Aufrufs beschrieben.
seo-title: 'Aufrufe an die Domäne „demdex.net“ '
solution: Audience Manager
title: 'Aufrufe an die Domäne „demdex.net“ '
uuid: c 06 dae 3 a-f 169-4712-80 fb-d 6 d 448 dce 51 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Aufrufe an die Domäne „demdex.net“ {#understanding-calls-to-the-demdex-domain}

Audience Manager und der Experience Cloud ID-Dienst senden Aufrufe an die und empfangen Daten aus der demdex.net-Domäne. Dies kann so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber dies ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex. net-Aufrufs beschrieben.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Call-Element </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. It reflects <span class="keyword"> Audience Manager</span>'s original, pre-acquisition name (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> hat <span class="keyword"> Demdex</span> im Jahr 2011 erworben und das Unternehmen als <span class="keyword"> Audience Manager neu gestaltet</span>. It is difficult to change this domain because it is entwined deeply with <span class="keyword"> Audience Manager</span>, the <span class="wintitle"> ID service</span>, and our installed user base. See <a href="../overview/aam-overview.md#history-and-background"> History and Background</a>. </p> <p>You may see other prefixes attached to legacy <code> demdex.net</code> calls (e.g., <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>, etc.). Regardless of the prefix, a call to <code><i>something</i>.demdex.net</code> is always a call to <span class="keyword"> Adobe</span> and not to some unknown or suspicious third-party domain. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> ist eine Abkürzung für <span class="wintitle"> Data Provider Match</span>. It tells internal, <span class="keyword"> Adobe</span> systems that a call from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span> is passing in customer data for synchronization or requesting an ID. This is the most common <code> demdex.net</code> call you'll see from <span class="keyword"> Audience Manager</span> or the <span class="wintitle"> ID service</span>. </p> <p><span class="wintitle"> Grundlagen der DPM</span> -Aufrufe: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b><span class="keyword"> Audience Manager</span></b>: Ein <span class="wintitle"> DPM</span> -Aufruf aus <span class="keyword"> Audience Manager</span> sendet Daten an die <span class="wintitle"> Datenerfassungsserver</span> und <span class="wintitle"> Profil-Cache-Server</span>. See <a href="../reference/system-components/components-data-collection.md"> Data Collection Components</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b><span class="wintitle"> ID-Dienst</span></b>: Ein <span class="wintitle"> DPM</span> -Aufruf vom <span class="wintitle"> ID-Dienst</span> ist eine Anforderung einer Besucher-ID. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID Service</a> and <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> How the Experience Cloud ID Service Requests and Sets IDs</a>. </li> 
     </ul> </p> <p> <p>Note:  <span class="wintitle"> ID service</span> customers can change the <span class="wintitle"> DPM</span> prefix in the domain name. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audienceManager Server and audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookies in Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)


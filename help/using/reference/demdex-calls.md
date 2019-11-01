---
description: Audience Manager und der Experience Cloud ID-Dienst senden Aufrufe an die und empfangen Daten aus der demdex.net-Domäne. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-description: Audience Manager und der Experience Cloud ID-Dienst senden Aufrufe an die und empfangen Daten aus der demdex.net-Domäne. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-title: 'Aufrufe an die Domäne „demdex.net“ '
solution: Audience Manager
title: 'Aufrufe an die Domäne „demdex.net“ '
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Aufrufe an die Domäne „demdex.net“ {#understanding-calls-to-the-demdex-domain}

Audience Manager und der Experience Cloud ID-Dienst senden Aufrufe an die und empfangen Daten aus der demdex.net-Domäne. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Es spiegelt den ursprünglichen Namen von <span class="keyword"> Audience Manager</span>vor der Akquise (<span class="keyword"> Demdex</span>) wider. <span class="keyword"> Adobe</span> erwarb 2011 <span class="keyword"> Demdex</span> und stellte das Unternehmen als <span class="keyword"> Audience Manager</span>um. Es ist schwierig, diese Domäne zu ändern, da sie eng mit <span class="keyword"> Audience Manager</span>, dem <span class="wintitle"> ID-Dienst</span>und unserer installierten Benutzerbasis verknüpft ist. Siehe <a href="../overview/aam-overview.md#history-and-background"> Verlauf und Hintergrund</a>. </p> <p>Möglicherweise werden weitere Präfixe an Legacy- <code> demdex.net</code> Aufrufen angehängt (z. B. <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>usw.). Unabhängig vom Präfix <code><i>something</i>.demdex.net</code> ist ein Aufruf an immer ein Aufruf an <span class="keyword"> Adobe</span> und nicht an eine unbekannte oder verdächtige Drittanbieterdomäne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> ist eine Abkürzung für <span class="wintitle"> Data Provider Match</span>. Es teilt internen <span class="keyword"> Adobe</span> -Systemen mit, dass ein Aufruf von <span class="keyword"> Audience Manager</span> oder vom <span class="wintitle"> ID-Dienst</span> Kundendaten zur Synchronisierung weiterleitet oder eine ID anfordert. Dies ist der häufigste <code> demdex.net</code> Aufruf, der von <span class="keyword"> Audience Manager</span> oder vom <span class="wintitle"> ID-Dienst</span>angezeigt wird. </p> <p><span class="wintitle"> Grundlagen zum DPM</span> -Aufruf: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: Ein <span class="wintitle"> DPM</span> -Aufruf von <span class="keyword"> Audience Manager</span> sendet Daten an die Datenerfassungsserver<span class="wintitle"> und </span> Profilcache-Server<span class="wintitle"></span> . Siehe <a href="../reference/system-components/components-data-collection.md"> Datenerfassungskomponenten</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> ID-Dienst</span> </b>: Ein <span class="wintitle"> DPM</span> -Aufruf des <span class="wintitle"> ID-Diensts</span> ist eine Anforderung einer Besucher-ID. Siehe <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies und Experience Cloud ID-Dienst</a> und <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> Anleitung zum Anfordern und Festlegen von IDs</a>durch den Experience Cloud ID-Dienst. </li> 
     </ul> </p> <p> <p>Hinweis:  Kunden des <span class="wintitle"> ID-Diensts</span> können das <span class="wintitle"> DPM</span> -Präfix im Domänennamen ändern. Siehe <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audienceManager Server und audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookies in Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)


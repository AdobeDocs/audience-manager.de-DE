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
   <td colname="col2"> <p>Dies ist eine Legacy-Domäne, die von <span class="keyword"> Adobe kontrolliert</span>wird. Es spiegelt den <span class="keyword"> ursprünglichen Namen des Audience Manager</span>(<span class="keyword"> Demdex</span>) wider. <span class="keyword"> Adobe</span> hat <span class="keyword"> Demdex</span> im Jahr 2011 erworben und das Unternehmen als <span class="keyword"> Audience Manager neu gestaltet</span>. Diese Domäne kann nur schwer geändert werden, da sie tief mit <span class="keyword"> Audience Manager</span>, dem <span class="wintitle"> ID-Dienst</span>und unserer installierten Benutzerbasis entschlüsselt ist. Siehe <a href="../overview/aam-overview.md#history-and-background"> Verlauf und Hintergrund</a>. </p> <p>Möglicherweise werden weitere Präfixe angezeigt, die an ältere <code> demdex. net</code> -Aufrufe angefügt werden (z. B. <code> dcs. demdex. net</code>, <code> fast. demdex. net</code>usw.). Unabhängig vom Präfix ist ein Aufruf von <code><i>some.</i>demdex. net</code> immer ein Aufruf an <span class="keyword"> Adobe</span> und nicht zu unbekannten oder verdächtigen Drittanbieterdomänen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> ist eine Abkürzung für <span class="wintitle"> Data Provider Match</span>. Es teilt interne <span class="keyword"> Adobe</span> -Systeme mit, dass ein Aufruf von <span class="keyword"> Audience Manager</span> oder der <span class="wintitle"> ID-Dienst</span> Kundendaten zur Synchronisierung oder zum Anfordern einer ID weiterleitet. Dies ist der am häufigsten aufgerufene <code> demdex. net</code> -Aufruf aus <span class="keyword"> Audience Manager</span> oder dem <span class="wintitle"> ID-Dienst</span>. </p> <p><span class="wintitle"> Grundlagen der DPM</span> -Aufrufe: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b><span class="keyword"> Audience Manager</span></b>: Ein <span class="wintitle"> DPM</span> -Aufruf aus <span class="keyword"> Audience Manager</span> sendet Daten an die <span class="wintitle"> Datenerfassungsserver</span> und <span class="wintitle"> Profil-Cache-Server</span>. Siehe <a href="../reference/system-components/components-data-collection.md"> Datenerfassungskomponenten</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b><span class="wintitle"> ID-Dienst</span></b>: Ein <span class="wintitle"> DPM</span> -Aufruf vom <span class="wintitle"> ID-Dienst</span> ist eine Anforderung einer Besucher-ID. Weitere Informationen finden Sie unter <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies und Experience Cloud ID-Dienst</a> sowie <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> Anfordern und Festlegen von IDs</a>für Experience Cloud ID-Dienst. </li> 
     </ul> </p> <p> <p>Hinweis: <span class="wintitle"> Kunden des ID-Diensts</span> können das <span class="wintitle"> DPM</span> -Präfix im Domänennamen ändern. Siehe <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> audiencemanager Server und audiencemanagerserversecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookies in Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)


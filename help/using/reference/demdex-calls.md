---
description: Audience Manager und der Identitätsdienst der Adobe Experience Platform rufen Daten von der Domäne demdex.net an und empfangen diese. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-description: Audience Manager und der Identitätsdienst der Adobe Experience Platform rufen Daten von der Domäne demdex.net an und empfangen diese. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-title: 'Aufrufe an die Domäne „demdex.net“ '
solution: Audience Manager
title: 'Aufrufe an die Domäne „demdex.net“ '
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d219f6fa1e2a8396b049f86391142c00e263b629
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 5%

---


# Aufrufe an die Domäne „demdex.net“ {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] und der Identitätsdienst der Adobe Experience Platform ruft Daten von der Domäne demdex.net auf und empfängt sie. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente in einem `demdex.net` Aufruf beschrieben.

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Es spiegelt den ursprünglichen Namen des <span class="keyword"> Audience Managers</span>vor der Akquise (<span class="keyword"> Demdex</span>) wider. <span class="keyword"> Adobe</span> hat <span class="keyword"> Demdex</span> 2011 erworben und die Firma als <span class="keyword"> Audience Manager</span>umbenannt. Es ist schwierig, diese Domäne zu ändern, da sie tief mit <span class="keyword"> Audience Manager</span>, dem <span class="wintitle"> ID-Dienst</span>und unserer installierten Benutzerbasis verknüpft ist. Siehe <a href="../overview/aam-overview.md#history-and-background"> Verlauf und Hintergrund</a>. </p> <p>Möglicherweise werden weitere Präfixe an Legacy- <code> demdex.net</code> Aufrufen angehängt (z. B. <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>usw.). Unabhängig vom Präfix <code><i>something</i>.demdex.net</code> ist ein Aufruf an immer ein Aufruf an <span class="keyword"> Adobe</span> und nicht an eine unbekannte oder verdächtige Drittanbieterdomäne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> ist eine Abkürzung für <span class="wintitle"> Data Provider Match</span>. Es teilt internen <span class="keyword"> Adobe</span> -Systemen mit, dass ein Aufruf von <span class="keyword"> Audience Manager</span> oder dem <span class="wintitle"> ID-Dienst</span> Kundendaten zur Synchronisierung weitergibt oder eine ID anfordert. Dies ist der häufigste <code> demdex.net</code> Aufruf, den Sie vom <span class="keyword"> Audience Manager</span> oder vom <span class="wintitle"> ID-Dienst</span>sehen werden. </p> <p><span class="wintitle"> Grundlagen zum DPM</span> -Aufruf: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: Ein <span class="wintitle"> DPM</span> -Aufruf von <span class="keyword"> Audience Manager</span> sendet Daten an die Datenerfassungsserver <span class="wintitle"> und</span> Profil-Cache-Server <span class="wintitle"></span>. Siehe <a href="../reference/system-components/components-data-collection.md"> Datenerfassungskomponenten</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> ID-Dienst</span> </b>: Ein <span class="wintitle"> DPM</span> -Aufruf des <span class="wintitle"> ID-Diensts</span> ist eine Anforderung einer Besucher-ID. Siehe <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies und den Identitätsdienst</a> für Adobe Experience Platformen und <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="https" scope="external"> So fordert und legt der Identitätsdienst für Adobe Experience Platformen IDs</a>an. </li> 
     </ul> </p> <p> <p>Hinweis:  <span class="wintitle"> Kunden des ID-Diensts</span> können das <span class="wintitle"> DPM</span> -Präfix im Domänennamen ändern. Siehe <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html" format="https" scope="external"> audienceManager Server und audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Identitätsdienst für Adobe Experience Platformen](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies in Audience Manager](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)


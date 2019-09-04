---
seo-title: Server-zu-Server-DCS API-Aufrufe erstellen
solution: Audience Manager
title: Server-zu-Server-DCS API-Aufrufe erstellen
uuid: bdfe 3430-e 27 f -4 a 5 c -88 d 9-ae 164 d 28 f 601
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Server-zu-Server-DCS API-Aufrufe erstellen {#making-server-to-server-dcs-api-calls}

Aufrufe erfordern den Hostnamen des regionalen DCS-Servers und der Benutzer-ID. Wenn Sie nicht über die erforderlichen Benutzer- und Regions-IDs verfügen, lesen [Sie Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) und/oder [Erlebnis-Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Sobald Sie Benutzer- und Regions-IDs haben, können Sie dem DCS Server-zu-Server-Aufrufe hinzufügen. In diesem Abschnitt finden Sie Syntax und Beispiele.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Ersetzen Sie einen echten Wert für den Platzhalter, wenn Sie Server-zu-Server-Aufrufe an den Server [!UICONTROL DCS]senden.

## Syntax und Beispiel aufrufen {#call-syntax-example}

Eine standardmäßige Server-zu-Server-Anforderung, die Daten an die [!UICONTROL DCS] folgende Syntax sendet:

<pre><code>" Host:<i>Domäne.</i>demdex. net "" https://DCS<i>host name.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>.</code></pre>

Ein Beispielaufruf sieht ähnlich wie das folgende Beispiel aus.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Aufrufparameter {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code><i>domain alias</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Dieser Teil des Aufrufs enthält: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Ihr Domänenalias, der von <span class="keyword"> Audience Manager zugewiesen wurde</span> (z. B. <i><code> my_ domain. demdex. net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Die Zieldomäne, die immer <i><code> demdex. net</code></i>lautet. Siehe <a href="../../../reference/demdex-calls.md">Aufrufe an die Domäne „demdex.net“</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>DCS Hostname</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Der HTTP-Header-Host-Parameter, der den Namen des regionalen <span class="wintitle"> DCS</span> -Servers anzeigt. Der Hostname ist an eine Regions-ID gebunden. Daher benötigen Sie dies, bevor Sie diese Aufrufe durchführen. Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Dieser Teil des Aufrufs: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifiziert den Aufruf als Ereignisaufruf. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definiert den Start der URL-Zeichenfolge, die die Daten enthält, die Sie an das DCS senden möchten. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ uuid = <i>Audience Manager-Benutzer-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dies ist der eindeutige Benutzer-ID-Schlüssel, der den Wert <span class="keyword"> des Audience Manager</span> -Benutzers in einem Schlüssel-Wert-Paar enthält. </p> <p>Verwenden <code><i>Sie d_ uuid,</i></code> wenn Sie die Benutzer-ID <span class="keyword"> des Audience Manager</span> weitergeben. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid =<i>Experience Cloud-Benutzer-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dies ist der eindeutige Benutzer-ID-Schlüssel, der den Wert <span class="keyword"> des Experience Cloud</span> -Benutzer-ID in einem Schlüssel-Wert-Paar enthält. Siehe <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> auch Abrufen der Benutzer-ID aus dem ID-Dienst-Cookie</a>. </p> <p>Verwenden <i><code> Sie d_ mid</code></i> , wenn Sie eine <span class="keyword"> aus dem</span> <span class="keyword"> Experience Cloud</span> ID-Dienst erfasste Experience Cloud-ID übergeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb =<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionale Antwortparameter. </p> <p> Zum Senden von Daten an das <span class="wintitle"> DCS</span>sind keine Daten erforderlich. Wenn das <span class="wintitle"> DCS</span> jedoch eine Antwort zurückgeben soll, müssen Sie <i><code> d_ rtbd = json</code></i> in Ihre Anforderung einschließen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielantwort {#sample-response}

Siehe [Daten vom DCS empfangen](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

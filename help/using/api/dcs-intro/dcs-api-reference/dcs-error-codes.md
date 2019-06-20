---
description: Fehlercodes und Meldungen, die von den Datenerfassungsservern (DCS) in numerischer Reihenfolge durch Code-ID generiert wurden.
seo-description: Fehlercodes und Meldungen, die von den Datenerfassungsservern (DCS) in numerischer Reihenfolge durch Code-ID generiert wurden.
seo-title: DCS-Fehlercodes, Nachrichten und Beispiele
solution: Audience Manager
title: DCS-Fehlercodes, Nachrichten und Beispiele
uuid: d 3290038-567 b -4 c 00-bc 95-2 cec 883 da 5 ec
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DCS-Fehlercodes, Nachrichten und Beispiele {#dcs-error-codes-messages-and-examples}

Fehlercodes und Meldungen, die von der [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]) in numerischen Reihenfolge nach Code-ID generiert wurden.

In den unten stehenden Tabellen stellt *kursiv* eine Variable Platzhalter dar.

## Systemfehlercodes {#system-error-codes}

<table id="table_43F4321BEA6A4D1BBDFE2E9FB4402914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code-ID </th> 
   <th colname="col2" class="entry"> Fehlermeldung </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>0 </p> </td> 
   <td colname="col2"> <p>Nicht spezifizierter Fehler </p> </td> 
   <td colname="col3"> <p>Dies ist ein Sammelfehler, der Ereignisse verarbeitet, die nicht von den anderen Fehlerhandlern abgedeckt werden. Fehlerbehebung für diesen Fehler ist schwierig. Dies kann durch eine Vielzahl unbekannter Aktionen oder Ereignisse verursacht werden. </p> <p>Wenn Sie diesen Fehler erhalten, <span class="wintitle"> versuchen</span> Sie es erneut. Wenden Sie sich an Ihren Adobe-Vertreter, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Konfiguration für Hostname konnte nicht gefunden werden: <code><i>hostname</i></code> </p> </td> 
   <td colname="col3"> <p>Der in der Anfrage gesendete Hostname wurde nicht von unserem Partnerbereitstellungsteam eingerichtet. Wenden Sie sich an Ihren Adobe-Vertreter, wenn diese Fehlermeldung angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Ungültiger <code> d_ orgid</code> -Wert (keine Konfiguration für diese Organisations-ID gefunden): <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die Organisations-ID ist falsch. </p> <p>Überprüfen Sie Ihre ID und versuchen Sie es erneut. Wenn Sie Ihre Organisations-ID nicht kennen oder haben, finden Sie im Abschnitt "Administrationsseite" in <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> Experience Cloud Administration</a> weitere Informationen zur Suche. </p> </td> 
  </tr>
 </tbody>
</table>

## Integrationsfehlercodes {#integration-error-codes}

<table id="table_EFF06FB3D045459BA7802872AF22DF79"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code-ID </th> 
   <th colname="col2" class="entry"> Nachricht </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>100 </p> </td> 
   <td colname="col2"> <p>Hostname für die Anforderung konnte nicht abgerufen werden </p> </td> 
   <td colname="col3"> <p>Ein API-Aufruf hat den Host-HTTP-Header nicht in der Anforderung gesendet. </p> <p>Fügen Sie dem Aufruf Hostkopfzeile hinzu und versuchen Sie es erneut. Die meisten Browser und API-Clients führen dies automatisch durch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>Ungültige Experience Cloud-ID, die in <code><i>ID weitergegeben wird</i></code> </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle"> DCS</span> -Aufruf enthält eine ungültige <span class="keyword"> Experience Cloud</span> ID. </p> <p>Überprüfen Sie das <code> Schlüssel-Wert-Paar d_ mid =</code> in der Header-Zeichenfolge. Stellen Sie sicher, dass Sie die richtige <span class="keyword"> Experience Cloud</span> ID weitergeben und die Anforderung erneut versuchen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>Ungültige AAM-ID in Anforderungs <code><i>-ID übergeben</i></code> </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle"> DCS</span> -Aufruf enthält eine ungültige <span class="keyword"> Audience Manager</span> -ID. </p> <p>Überprüfen Sie das <code> Schlüssel-Wert-Paar d_ uuid =</code> in der Header-Zeichenfolge. Stellen Sie sicher, dass Sie die richtige <span class="keyword"> Audience Manager</span> -ID weitergeben und die Anforderung erneut versuchen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>Alle Kunden-ids sind ungültig. </p> </td> 
   <td colname="col3"> <p>Alle Kunden-IDs in Ihrem Aufruf sind ungültig. Überprüfen Sie Ihre IDs und versuchen Sie es erneut. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>Ungültiges <span class="wintitle"> IMS</span> -Token empfangen </p> </td> 
   <td colname="col3"> <p>Für Audience Manager zurückgegeben - Adobe Target-Integrationen. Der Fehler wird ausgegeben, wenn ein Aufruf an das DCS erfolgt, das ein ungültiges IMS-Token enthält. Das Token kann fehlerhaft sein, abgelaufen oder der Benutzer kann nicht für den Zugriff auf die erforderliche Ressource autorisiert werden. </p> </td>
  </tr>
 </tbody>
</table>

## Ausschluss-Fehlercodes {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code-ID </th> 
   <th colname="col2" class="entry"> Nachricht </th> 
   <th colname="col3" class="entry"> Beschreibung </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Abmeldetag für ID <code><i>-ID gefunden</i></code> </p> </td> 
   <td colname="col3"> <p>Ein Kunde hat eine interessensbasierte Werbung abgemeldet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Blockierte Cookies </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn der Browser des Benutzers Drittanbieter-Cookies blockiert.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Vertrauensbeziehung über <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI gefunden</a> </p> </td> 
   <td colname="col3"> <p>Der Benutzer hat einen Ausschluss-Prozess über NAI initiiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Anforderungen aus diesem Land werden vom Partner blockiert </p> </td> 
   <td colname="col3"> <p>Basierend auf der IP-Adresse blockiert der <span class="wintitle"> DCS</span> Anforderungen aus Ländern, in denen der Partner den Traffic bewusst beschränkt hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Anforderungen aus diesem Land sind nicht zulässig. </p> </td> 
   <td colname="col3"> <p>Basierend auf der IP-Adresse blockiert das <span class="wintitle"> DCS</span> Anforderungen aus folgenden Ländern: </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">Kuba (CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">Iran (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">Nordkorea (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">Sudan (SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">Syrien (SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Profilabruffehlercodes {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code-ID </th> 
   <th colname="col2" class="entry"> Nachricht </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> Eigenschaften aus Profilcache für ID können nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn ein Benutzerprofil nicht aus unserem internen Speicher gelesen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Geräte-ids können nicht aus dem Profil-Cache für Kunden-ID gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die <a href="../../../reference/ids-in-aam.md"> Geräte-ID</a> für eine Regel zum Zusammenführen von Profilen nicht abgerufen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Beziehter Kunde kann nicht für Geräte-ID gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die <a href="../../../reference/ids-in-aam.md"> mit einer Geräte-ID</a> verknüpfte Kunden-ID (UUID) für eine Regel für die zuletzt authentifizierte Zusammenführung aus unserem internen Speicher nicht abgerufen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Gerätecluster kann nicht für ID gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die verknüpften Geräte-IDs aus demselben Gerätediagrammcluster können nicht für diese Geräte-ID zurückgegeben werden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Migration konnte nicht durchgeführt werden, da Profil für primäre Geräte fehlgeschlagen ist </p> </td> 
   <td colname="col3"> <p>Wenn dieser Fehler auftritt, treten möglicherweise Skalierungsprobleme bei unserem Datenspeicher (<span class="wintitle"> PCS</span>) auf. Wenden Sie sich an Ihren Adobe-Vertreter, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Migration von <code><i>ID</i></code> zur <code><i>ID konnte nicht durchgeführt werden</i></code>, da Profil für <code><i>ID fehlgeschlagen ist.</i></code> </p> </td>
   <td colname="col3"> <p>Wenn dieser Fehler auftritt, treten möglicherweise Skalierungsprobleme bei unserem Datenspeicher (<span class="wintitle"> PCS</span>) auf. Wenden Sie sich an Ihren Adobe-Vertreter, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Integrationswarnungen {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code-ID </th> 
   <th colname="col2" class="entry"> Nachricht </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>Ungültige Kunden-ID <code><i>-ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die Kunden-ID ist ungültig (fehlende Werte für Datenquelle, fehlende Integrationscodes, ungültige Format für Datenquellen, blockierte Kunden-ID, leere Kunden-ID, unautorisierter Zugriff auf eine Datenquelle, die nicht dem Partner gehört). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Maximale Anzahl der Kunden-ids überschritten. Maximal zulässig ist <code><i>zulässig</i></code>. <code><i>Gefunden</i></code>.</p> </td> 
   <td colname="col3"> <p>Die Anzahl der Kunden-IDs, die mit einer geräteübergreifenden Datenquelle verknüpft sind, überschreitet die zulässige Anzahl geräteübergreifender IDs pro Anforderung. Zu diesen IDs gehören Geräte-, Mobil- oder Cookie-IDs. Der Grenzwert ist derzeit auf 10 eingestellt. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Nicht autorisierte Kunden-ID <code><i>-ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID-Datenquelle nicht der aktuellen Organisations-ID gehört. Wenn Sie Ihre Organisations-ID nicht kennen oder haben, finden Sie im Abschnitt "Suchen Ihrer Organisations-ID" in <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisationen und Kontoverknüpfung</a> Informationen zur Suche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Blockierte Kunden-ID <code><i>-ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID als böswillig identifiziert und in der schwarzen Liste aufgeführt wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Gesperrte Datasource-ID <code><i>-ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Datenquellen-ID als böswillig identifiziert und in der schwarzen Liste aufgeführt wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Blockierte Geräte-ID <code><i>-ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die Geräte-ID wurde als böswillige ID identifiziert und ist in der schwarzen Liste aufgeführt. Dies kann auftreten, wenn wir eine extreme Menge an <span class="wintitle"> DCS</span> -Anforderungen erhalten, die diese Geräte-ID in kurzer Zeit enthalten. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Blockierter Profilvorgang für <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Eine Lese-/Schreibaktion wurde blockiert, da eine ID als böswillig identifiziert und in der schwarzen Liste aufgeführt wurde. Siehe Fehlercode 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Kunden-ID <code><i>-ID</i></code> wurde verworfen, da sie die Beschränkung der deklarierten Kunden-ids pro Anforderung überschritten hat. </p> </td> 
   <td colname="col3"> <p>Zusammenhang mit Fehler 301. Dieser Fehler gibt an, welche Kunden-ID verworfen wurde, da der Grenzwert überschritten wurde. </p> <p>Wenn zum Beispiel im <span class="wintitle"> DCS</span> -Aufruf 12 Kunden-IDs deklariert sind, werden zwei davon verworfen. Um die verworfen zu werden, wird dieser Fehler zweimal in der Antwort angezeigt (einmal für jede verworfen Kunden-ID). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Die Kunden-ID wurde verworfen, da sie die Beschränkung für einen angegebenen Namespace überschritten hat. Namespace ID lautet <code><i>ID</i></code>, Kunden-ID ist <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Dieser Fehlercode wird zurückgegeben, wenn für denselben Namespace (<code> DPID</code>) mehr als 3 Kunden-IDs in einem <span class="wintitle"> DCS</span> -Aufruf deklariert wurden. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In dieser <span class="wintitle"> DCS-Beispielanforderung</span> sind 4 ids für denselben Namespace deklariert (mit dem Integrationscode). Eine der IDs wird verworfen und Fehler 310 wird zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>Anforderung enthält ungültige Parameter </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle"> DCS</span> gibt diesen Fehlercode zurück, wenn mindestens ein URL-Parameter nicht richtig kodiert ist. In diesem Fall ignoriert das <span class="wintitle"> DCS</span> die gesamte Anforderung. </p> <p><code>http (s): // partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp; d_ creative = % ecid!&amp; d_ adgroup = % eaid!&amp; d_ placement = % epid!&amp; d_ campaign = % ebuy!&amp; d_ adsrc = 48123</code> </p> <p>In der obigen Beispielanforderung wird die <code> %</code> Sequenz falsch kodiert. Daher wird es vom <span class="wintitle"> DCS</span> ignoriert. </p> <p>Das korrekt kodierte Beispiel sollte wie folgt aussehen: </p> <p><code>http (s): // partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp; d_ creative = % 25 ecid!&amp; d_ adgroup = % 25 eaid!&amp; d_ placement = % 25 epid!&amp; d_ campaign = % 25 epurchase!&amp; d_ adsrc = 48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>Anforderung enthält eine ungültige globale Geräte-ID </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle">DCS</span> gibt diesen Fehlercode zurück, wenn die Anforderung eine ungültige globale Geräte-ID enthält. DCS ignoriert die ungültige ID und gibt einen 312-Fehler zusammen mit den spezifischen Fehlern der ungültigen ID aus. Ausführliche Informationen zu den richtigen Geräteanzeigen-ID-Formaten und den entsprechenden globalen Datenquellen finden Sie unter <a href="../../../features/global-data-sources.md" format="dita" scope="local">Globale Datenquellen</a> und <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index der IDs in Audience Manager</a> .</p>
   <p>Beispiel eines falschen Aufrufs: <code>" http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z "</code></p>
   <p>Erläuterung: IDFA <span class="keyword">(DPID 20915)</span> muss eine Großbuchstaben-ID sein. Die in der Anforderung angegebene ID ist kleinschreibung.</p>
   </td>
  </tr>

</tbody>
</table>

## Beispiel-Fehlercodemeldungen {#sample-error-codes}

Die [!UICONTROL DCS] Fehlercodes und Meldungen in einem [!DNL JSON] Objekt oder in einem X-Header in der HTTP-Antwortzeichenfolge.

### Beispiel-DCS-Fehlercode und -meldung

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-Error

Error codes captured by the X- header appear in the URL string like this, `X-Error: 101,102`.

[Race Conditions und Fehlerbearbeitung](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
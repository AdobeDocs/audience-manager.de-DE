---
description: Fehlercodes und Meldungen, die von den Datenerfassungsservern (Data Collection Servers, DCS) erzeugt wurden, werden in numerischer Reihenfolge nach Code-ID aufgeführt.
seo-description: Fehlercodes und Meldungen, die von den Datenerfassungsservern (Data Collection Servers, DCS) erzeugt wurden, werden in numerischer Reihenfolge nach Code-ID aufgeführt.
seo-title: DCS-Fehlercodes, Nachrichten und Beispiele
solution: Audience Manager
title: DCS-Fehlercodes, Nachrichten und Beispiele
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
translation-type: tm+mt
source-git-commit: 8478a28cd1b18d878d6938d77ee4f975deb524ef

---


# DCS-Fehlercodes, Nachrichten und Beispiele {#dcs-error-codes-messages-and-examples}

Fehlercodes und Meldungen, die von der [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]) in numerischer Reihenfolge nach Code-ID generiert werden.

In the tables below, *italics* represents a variable placeholder.

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
   <td colname="col3"> <p>Dies ist ein allgemeiner Fehler, der Ereignisse verarbeitet, die nicht von anderen Fehlerhandlern abgedeckt werden. Die Behebung dieses Fehlers ist schwierig. Sie kann durch eine Vielzahl unbekannter Aktionen oder Ereignisse verursacht werden. </p> <p>Wenn Sie diesen Fehler erhalten, versuchen Sie es erneut mit Ihrer <span class="wintitle"> DCS</span> -Anforderung. Wenden Sie sich an Ihren Adobe-Kundenbetreuer, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>config für Hostname konnte nicht gefunden werden: <code><i>hostname</i></code> </p> </td> 
   <td colname="col3"> <p>Der Hostname, der in der Anfrage gesendet wurde, wurde nicht von unserem Partnerbereitstellungsteam eingerichtet. Wenden Sie sich an Ihren Adobe-Kundenbetreuer, wenn diese Fehlermeldung angezeigt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Ungültiger <code> d_orgid</code> Wert (die Konfiguration für diese Organisations-ID konnte nicht gefunden werden): <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die Organisations-ID ist nicht korrekt. </p> <p>Überprüfen Sie Ihre ID und versuchen Sie es erneut. Wenn Sie Ihre Organisations-ID nicht kennen oder noch nicht über eine solche verfügen, finden Sie Informationen dazu, wie Sie diese finden, im Abschnitt "Administrationsseite"in der <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> Experience Cloud-Verwaltung</a> . </p> </td> 
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
   <td colname="col2"> <p>Hostname für Anforderung konnte nicht abgerufen werden </p> </td> 
   <td colname="col3"> <p>Ein API-Aufruf hat den Host-HTTP-Header in der Anforderung nicht gesendet. </p> <p>Fügen Sie dem Aufruf den Host-Header hinzu und versuchen Sie es erneut. Beachten Sie, dass dies in den meisten Browsern und API-Clients automatisch erfolgt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>Ungültige Experience Cloud-ID weitergegeben <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle"> DCS</span> -Aufruf enthält eine ungültige <span class="keyword"> Experience Cloud</span> -ID. </p> <p>Überprüfen Sie das <code> d_mid=</code> Schlüssel-Wert-Paar in der Kopfzeile. Vergewissern Sie sich, dass Sie die richtige <span class="keyword"> Experience Cloud</span> -ID übermitteln, und versuchen Sie es erneut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>Ungültige AAM-ID in Anfrage weitergegeben <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle"> DCS</span> -Aufruf enthält eine ungültige <span class="keyword"> Audience Manager</span> -ID. </p> <p>Überprüfen Sie das <code> d_uuid=</code> Schlüssel-Wert-Paar in der Kopfzeile. Vergewissern Sie sich, dass Sie die richtige <span class="keyword"> Audience Manager</span> -ID übermitteln, und versuchen Sie es erneut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>Alle Kunden-IDs sind ungültig </p> </td> 
   <td colname="col3"> <p>Alle Kunden-IDs in Ihrem Aufruf sind ungültig. Überprüfen Sie Ihre IDs und versuchen Sie es erneut. </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p>109</p> </td> 
   <td colname="col2"> <p>Referrer <code>HTTP referer</code> ist für Partner nicht zulässig <code>Partner ID</code> </p> </td> 
   <td colname="col3"> <p>Der [!DNL HTTP-Referrer]-Header für den Aufruf ist für die Partner-ID im Aufruf nicht zulässig. Überprüfen Sie, ob der [!DNL HTTP-Referrer]-Header korrekt ist.</p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>Ungültiges <span class="wintitle"> IMS</span> -Token erhalten </p> </td> 
   <td colname="col3"> <p>Für Audience Manager - Adobe Target-Integrationen zurückgegeben. Der Fehler wird ausgegeben, wenn ein DCS-Aufruf mit einem ungültigen IMS-Token erfolgt. Das Token ist möglicherweise fehlerhaft, abgelaufen oder der Benutzer ist möglicherweise nicht berechtigt, auf die erforderliche Ressource zuzugreifen. </p> </td>
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
   <td colname="col2"> <p>Tag zum Ausschluss für ID gefunden <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Ein Kunde hat sich gegen den Erhalt von zinsbasierter Werbung entschieden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Blockierte Cookies </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn der Browser des Benutzers Drittanbieter-Cookies blockiert.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Treuhandbeziehung über <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>Der Benutzer hat über NAI einen Ausschluss-Prozess eingeleitet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Anfragen aus diesem Land werden von den Partnern blockiert </p> </td> 
   <td colname="col3"> <p>Basierend auf der IP-Adresse blockiert der <span class="wintitle"> DCS</span> Anfragen aus Ländern, in denen der Partner den Traffic absichtlich begrenzt hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Anfragen aus diesem Land sind nicht zulässig </p> </td> 
   <td colname="col3"> <p>Auf der Grundlage der IP-Adresse blockiert der <span class="wintitle"> DCS</span> Anfragen aus den folgenden Ländern: </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">Kuba (WE) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">Iran (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">Nordkorea (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">Sudan (SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">Syrien (SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fehlercodes beim Abrufen des Profils {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> Eigenschaften können nicht aus Profil-Cache für ID gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn ein Benutzerprofil nicht aus unserem internen Speicher gelesen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Geräte-IDs für Kunden-IDs können nicht aus dem Profil-Cache gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die <a href="../../../reference/ids-in-aam.md"> Geräte-ID</a> für eine Profillink-Zusammenführungsregel nicht abgerufen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Zugehörige Kunden für Geräte-ID können nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die <a href="../../../reference/ids-in-aam.md"> Kunden-ID (UUID)</a> , die einer Geräte-ID zugeordnet ist, nicht für eine Last Authenticated Merge-Regel aus unserem internen Speicher abgerufen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Gerätecluster für ID kann nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die verknüpften Geräte-IDs aus demselben Gerätediagramm-Cluster können für diese Geräte-ID nicht zurückgegeben werden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Migration konnte nicht durchgeführt werden, da das Lesen des Profils für das primäre Gerät fehlgeschlagen ist </p> </td> 
   <td colname="col3"> <p>Wenn Sie diesen Fehler erhalten, treten bei unserem Datenspeicher (<span class="wintitle"> PCS</span>) möglicherweise Skalierungsprobleme auf. Wenden Sie sich an Ihren Adobe-Kundenbetreuer, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Migration von <code><i>ID</i></code> <code><i>ID</i></code>zu konnte nicht durchgeführt werden, da das Lesen des Profils fehlgeschlagen ist für <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Wenn Sie diesen Fehler erhalten, treten bei unserem Datenspeicher (<span class="wintitle"> PCS</span>) möglicherweise Skalierungsprobleme auf. Wenden Sie sich an Ihren Adobe-Kundenbetreuer, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Integrationswarncodes {#integration-warning-codes}

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
   <td colname="col2"> <p>Ungültige Kunden-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die Kunden-ID ist ungültig (fehlende Werte für die Datenquelle, fehlende Integrationscodes, ungültiges Format für Datenquellen, blockierte Kunden-ID, leere Kunden-ID, nicht autorisierter Zugriff auf eine Datenquelle, die nicht zum Partner gehört). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Maximale Anzahl der Kunden-IDs überschritten. Maximal zulässig <code><i>maximum allowed</i></code>. Entdeckt ist <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>Die Anzahl der Kunden-IDs, die mit einer geräteübergreifenden Datenquelle verknüpft sind, überschreitet die zulässige Anzahl geräteübergreifender IDs pro Anforderung. Zu diesen IDs gehören geräteübergreifende, mobile oder Cookie-IDs. Der Grenzwert ist derzeit auf 10 festgelegt. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Unautorisierte Kunden-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID-Datenquelle nicht der aktuellen Organisations-ID gehört. Wenn Sie Ihre Organisations-ID nicht kennen oder Ihre Organisations-ID nicht haben, finden Sie weitere Informationen dazu im Abschnitt " <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisationen suchen und Kontoverknüpfung</a> ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Blockierte Kunden-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID als bösartig identifiziert und auf der schwarzen Liste aufgeführt wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Blockierte Datenquellen-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Datenquellen-ID als bösartig identifiziert wurde und auf der schwarzen Liste steht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Blockierte deklarierte Geräte-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die Geräte-ID wurde als bösartig identifiziert und auf der schwarzen Liste aufgeführt. Dies kann vorkommen, wenn wir in kurzer Zeit eine extreme Anzahl von <span class="wintitle"> DCS</span> -Anfragen mit dieser Geräte-ID erhalten. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Blockierter Profilvorgang für <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Eine Lese-/Schreibaktion wurde blockiert, da eine ID als bösartig erkannt und auf der schwarzen Liste aufgeführt wurde. Siehe Fehlercode 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Die Kunden-ID <code><i>ID</i></code> wurde verworfen, weil sie die Grenze für deklarierte Kunden-IDs pro Anforderung überschritten hat </p> </td> 
   <td colname="col3"> <p>Im Zusammenhang mit Fehler 301. Dieser Fehler gibt an, welche Kunden-ID verworfen wurde, weil die Beschränkung überschritten wurde. </p> <p>Wenn beispielsweise 12 Kunden-IDs beim <span class="wintitle"> DCS</span> -Aufruf deklariert sind, werden zwei davon verworfen. Um zu ermitteln, welche verworfen wurden, erscheint dieser Fehler zweimal in der Antwort (einmal für jede verworfene Kunden-ID). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Kunden-ID wurde verworfen, weil sie die Beschränkung für einen gegebenen Namespace überschritten hat. Namespace-ID ist <code><i>ID</i></code>, Kunden-ID ist <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Dieser Fehlercode wird zurückgegeben, wenn mehr als 3 Kunden-IDs für denselben Namespace (<code> DPID</code>) für einen <span class="wintitle"> DCS</span> -Aufruf deklariert sind. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In dieser Beispiel- <span class="wintitle"> DCS</span> -Anforderung sind 4 IDs für denselben Namespace deklariert (mit dem Integrationscode 1). Eine der IDs wird verworfen und der Fehler 310 wird zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>Anforderung enthält ungültige Parameter </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle"> DCS</span> gibt diesen Fehlercode zurück, wenn mindestens ein URL-Parameter nicht korrekt kodiert wurde. In diesem Fall ignoriert der <span class="wintitle"> DCS</span> die gesamte Anforderung. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>In der obigen Beispielanforderung wird die <code> %</code> Sequenz falsch kodiert. Folglich wird der <span class="wintitle"> DSB</span> ihn ignorieren. </p> <p>Das korrekt kodierte Beispiel sollte wie folgt aussehen: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>Anforderung enthält eine ungültige globale Geräte-ID </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle">DCS</span> gibt diesen Fehlercode zurück, wenn die Anforderung eine ungültige globale Geräte-ID enthält. DCS ignoriert die ungültige ID und gibt einen 312-Fehler zusammen mit den spezifischen Fehlern der ungültigen ID aus. Detaillierte Informationen zu den richtigen ID-Formaten für Gerätewerbung und den entsprechenden globalen Datenquellen finden Sie unter <a href="../../../features/global-data-sources.md" format="dita" scope="local">Globale Datenquellen</a> und <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">ID-Index in Audience Manager</a> .</p>
   <p>Beispiel für einen falschen Aufruf: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Erklärung: Eine <span class="keyword">IDFA (DPID 20915)</span> muss eine Groß-/Kleinschreibung sein. Die in der Anforderung angegebene ID ist klein.</p>
   </td>
  </tr>

</tbody>
</table>

## Beispielfehlermeldungen {#sample-error-codes}

Die [!UICONTROL DCS] gibt Fehlercodes und -meldungen in einem [!DNL JSON] Objekt oder in einem X-Header in der HTTP-Antwort-Zeichenfolge zurück.

### Beispiel-DCS-Fehlercode und -Meldung

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

Fehlercodes, die vom X-Header erfasst werden, werden in der URL-Zeichenfolge wie folgt angezeigt `X-Error: 101,102`.

[Rassenbedingungen und Fehlerbehandlung](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
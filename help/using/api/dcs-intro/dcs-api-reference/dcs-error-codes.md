---
description: Fehlercodes und Meldungen, die von den Datenerfassungsservern (Data Collection Servers, DCS) erzeugt wurden, werden in numerischer Reihenfolge nach Code-ID aufgeführt.
seo-description: Fehlercodes und Meldungen, die von den Datenerfassungsservern (Data Collection Servers, DCS) erzeugt wurden, werden in numerischer Reihenfolge nach Code-ID aufgeführt.
seo-title: DCS-Fehlercodes, Meldungen und Beispiele
solution: Audience Manager
title: DCS-Fehlercodes, Meldungen und Beispiele
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1509'
ht-degree: 3%

---


# DCS-Fehlercodes, Meldungen und Beispiele {#dcs-error-codes-messages-and-examples}

Fehlercodes und Meldungen, die von der [!UICONTROL Data Collection Servers] ([!DNL DCS]) in numerischer Reihenfolge nach Code-ID generiert werden.

In the tables below, *italics* represents a variable placeholder.

## Systemfehlercodes {#system-error-codes}

|Fehlercode|Fehlermeldung|Beschreibung|
|—|—|—|
|0|Nicht angegebener Fehler|Dies ist ein Sammelfehler, der Ereignis verarbeitet, die nicht von den anderen Fehlerhandlern abgedeckt werden. Die Behebung dieses Fehlers ist schwierig. Sie kann durch eine Vielzahl unbekannter Aktionen oder Ereignisse verursacht werden. Wenn Sie diesen Fehler erhalten, versuchen Sie es erneut mit Ihrer [!DNL DCS] Anforderung. Wenden Sie sich an Ihren [!DNL Adobe] Kundenbetreuer, wenn das Problem weiterhin besteht.|
|1|Die Konfiguration für den Hostnamen konnte nicht gefunden werden: `hostname`|Der Hostname, der in der Anfrage gesendet wurde, wurde nicht von unserem Partnerbereitstellungsteam eingerichtet. Wenden Sie sich an Ihren [!DNL Adobe] Kundenbetreuer, wenn diese Fehlermeldung angezeigt wird.|
|2|Ungültiger `d_orgid` Wert (die Konfiguration für diese Organisations-ID konnte nicht gefunden werden): `ID`|Die Organisations-ID ist nicht korrekt. Überprüfen Sie Ihre ID und versuchen Sie es erneut. Wenn Sie Ihre Organisations-ID nicht kennen oder noch nicht über eine solche verfügen, finden Sie weitere Informationen dazu, wie Sie diese finden, im Abschnitt &quot; [Organisationen und Kontoverknüpfungen](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html) &quot;unter &quot;Administrationsseite&quot;.|

## Integrationsfehlercodes {#integration-error-codes}

|Fehlercode|Fehlermeldung|Beschreibung|
|—|—|—|
|100|Der Hostname für die Anforderung konnte nicht abgerufen werden|Ein [!DNL API] Aufruf hat den Host- [!DNL HTTP] Header in der Anforderung nicht gesendet. Hinzufügen Sie den Host-Header auf den Aufruf und versuchen Sie es erneut. Die meisten Browser und [!DNL API] Clients tun dies automatisch. |
|101|Ungültige [!DNL Experience Cloud] ID übergeben `ID`|Der [!DNL DCS] Aufruf enthält eine ungültige [!DNL Experience Cloud] ID. Überprüfen Sie das `d_mid=` Schlüssel-Wert-Paar in der Kopfzeile. Vergewissern Sie sich, dass Sie die richtige [!DNL Experience Cloud] ID übergeben, und versuchen Sie es erneut. |
|102|Ungültige [!DNL AAM ID] weitergeleitete Anforderung `ID`|Der [!DNL DCS] Aufruf enthält eine ungültige [!DNL Audience Manager] ID. Überprüfen Sie das `d_uuid=` Schlüssel-Wert-Paar in der Kopfzeile. Vergewissern Sie sich, dass Sie die richtige [!DNL Audience Manager] ID übergeben, und versuchen Sie es erneut. |
|104|Alle Kunden-IDs sind ungültig | Alle Kunden-IDs in Ihrem Aufruf sind ungültig. Überprüfen Sie Ihre IDs und versuchen Sie es erneut.|
|109|Referrer `HTTP referer` ist für Partner nicht zulässig `Partner ID`|Die `HTTP referer` Kopfzeile im Aufruf ist für die Partner-ID im Aufruf nicht zulässig. Überprüfen Sie, ob die `HTTP referer` Kopfzeile korrekt ist.|
|111|Ungültiger `IMS` Token erhalten|Zurückgegeben für [!DNL Audience Manager] - [!DNL Adobe Target] Integrationen. Der Fehler wird ausgegeben, wenn ein Aufruf an die [!DNL DCS]Seite mit einem ungültigen [!DNL IMS] Token erfolgt. Das Token ist möglicherweise fehlerhaft, abgelaufen oder der Benutzer ist möglicherweise nicht berechtigt, auf die erforderliche Ressource zuzugreifen.|

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
   <td colname="col2"> <p>Opt-out Tag für ID <code><i>ID</i></code> </p> </td> 
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

## Fehlercodes beim Abrufen von Profilen {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> Eigenschaften können nicht aus dem Profil-Cache für ID gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn ein Profil des Benutzers nicht aus unserer internen Datenspeicherung gelesen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Geräte-IDs für Kunden-IDs können nicht aus dem Profil-Cache gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die <a href="../../../reference/ids-in-aam.md"> Geräte-ID</a> für eine Profil Link-Zusammenführungsregel nicht abgerufen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Zugehörige Kunden für Geräte-ID können nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die einer Geräte-ID zugeordnete <a href="../../../reference/ids-in-aam.md"> Kunden-ID (UUID)</a> nicht für eine "Zuletzt authentifizierte"Mergeregel aus unserer internen Datenspeicherung abgerufen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Gerätecluster für ID kann nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die verknüpften Geräte-IDs aus demselben Gerätediagramm-Cluster können für diese Geräte-ID nicht zurückgegeben werden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Migration konnte nicht durchgeführt werden, da das Profil für das Primärgerät nicht gelesen werden konnte. </p> </td> 
   <td colname="col3"> <p>Wenn Sie diesen Fehler erhalten, treten bei unserem Datenspeicher (<span class="wintitle"> PCS</span>) möglicherweise Skalierungsprobleme auf. Wenden Sie sich an Ihren Adobe-Kundenbetreuer, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Die Migration von <code><i>ID</i></code> <code><i>ID</i></code>zu konnte nicht durchgeführt werden, da das Lesen des Profils fehlgeschlagen ist für <code><i>ID</i></code> </p> </td>
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
   <td colname="col2"> <p>Maximale Anzahl der Kunden-IDs überschritten. Maximal zulässig ist <code><i>maximum allowed</i></code>. Entdeckt ist <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>Die Anzahl der Kunden-IDs, die mit einer geräteübergreifenden Datenquelle verknüpft sind, überschreitet die zulässige Anzahl geräteübergreifender IDs pro Anforderung. Zu diesen IDs gehören geräteübergreifende, mobile oder Cookie-IDs. Der Grenzwert ist derzeit auf 10 gesetzt. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Unautorisierte Kunden-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID-Datenquelle nicht im Besitz der aktuellen Organisations-ID ist. Wenn Sie Ihre Organisations-ID nicht kennen oder Ihre Organisations-ID nicht haben, finden Sie weitere Informationen dazu im Abschnitt " <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisationen suchen und Kontoverknüpfung</a> ". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Blockierte Kunden-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID als bösartig identifiziert und einer Blockierungsliste hinzugefügt wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Blockierte Datenquellen-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Datenquellen-ID als bösartig identifiziert und einer Blockierungsliste hinzugefügt wurde </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Blockierte deklarierte Geräte-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die Geräte-ID wurde als bösartig identifiziert und zu einer Blockierungsliste hinzugefügt. Dies kann vorkommen, wenn wir eine extreme Anzahl von <span class="wintitle"> DCS</span> -Anforderungen mit dieser Geräte-ID in kurzer Zeit erhalten. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Blockierter Profil für <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Eine Lese-/Schreibaktion wurde blockiert, da eine ID als bösartig erkannt und einer Blockierungsliste hinzugefügt wurde Siehe Fehlercode 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Die Kunden-ID <code><i>ID</i></code> wurde verworfen, weil sie die Grenze für deklarierte Kunden-IDs pro Anforderung überschritten hat </p> </td> 
   <td colname="col3"> <p>Im Zusammenhang mit Fehler 301. Dieser Fehler gibt an, welche Kunden-ID verworfen wurde, weil die Beschränkung überschritten wurde. </p> <p>Wenn beispielsweise 12 Kunden-IDs beim <span class="wintitle"> DCS</span> -Aufruf deklariert sind, werden zwei davon verworfen. Um zu ermitteln, welche verworfen wurden, erscheint dieser Fehler zweimal in der Antwort (einmal für jede verworfene Kunden-ID). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Die Kunden-ID wurde verworfen, weil sie die Grenze für einen bestimmten Namensraum überschritten hat. Namensraum-ID ist <code><i>ID</i></code>, Kunden-ID ist <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Dieser Fehlercode wird zurückgegeben, wenn mehr als 3 Kunden-IDs für denselben Namensraum (<code> DPID</code>) für einen <span class="wintitle"> DCS</span> -Aufruf deklariert sind. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In dieser Beispiel- <span class="wintitle"> DCS</span> -Anforderung sind 4 IDs für denselben Namensraum deklariert (mit dem Integrationscode 1). Eine der IDs wird verworfen und der Fehler 310 wird zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>Anforderung enthält ungültige Parameter </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle"> DCS</span> gibt diesen Fehlercode zurück, wenn mindestens ein URL-Parameter nicht korrekt kodiert wurde. In diesem Fall ignoriert der <span class="wintitle"> DCS</span> die gesamte Anforderung. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>In der obigen Beispielanforderung wird die <code> %</code> Sequenz falsch kodiert. Folglich wird der <span class="wintitle"> DSB</span> ihn ignorieren. </p> <p>Das korrekt kodierte Beispiel sollte wie folgt aussehen: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>Anforderung enthält eine ungültige globale Geräte-ID </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle">DCS</span> gibt diesen Fehlercode zurück, wenn die Anforderung eine ungültige globale Geräte-ID enthält. DCS ignoriert die ungültige ID und gibt einen 312-Fehler zusammen mit den spezifischen Fehlern der ungültigen ID aus. Detaillierte Informationen zu den richtigen <a href="../../../features/global-data-sources.md" format="dita" scope="local">Anzeigen-ID-Formaten und den entsprechenden globalen Datenquellen finden Sie im Audience Manager</a> unter "Globale Datenquellen <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">und</a> ID-Index"unter den entsprechenden globalen Datenquellen.</p>
   <p>Beispiel für einen falschen Aufruf: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Erklärung: Eine <span class="keyword">IDFA (DPID 20915)</span> muss eine Groß-/Kleinschreibung sein. Die in der Anforderung angegebene ID ist klein.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>CMP-ID ist in GCL nicht vorhanden</p> </td> 
   <td colname="col3"> <p>Wenn <code>gdpr=1</code> und die IAB-TC-Zeichenfolge durch eine CMP-ID generiert wird, die zum Zeitpunkt der Auswertung nicht in der zwischengespeicherten Version der Global CMP-Liste des Audience Managers vorhanden ist, verwirft das Audience Manager-Plug-in für die IAB-TCF die IAB-TC-Zeichenfolge und verarbeitet die Anforderung wie gewohnt. Das IAB TCF v2.0 ${GDPR} Makro ist auf 0 gesetzt und das ${GDPR_CONSENT_XXX} Makro ist leer.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP-ID wird als in GCL gelöscht gekennzeichnet</p> </td> 
   <td colname="col3"> <p>Wenn <code>gdpr=1</code> und die IAB-TC-Zeichenfolge von einem CMP generiert wird, der in unserer zwischengespeicherten Version der Global CMP-Liste als gelöscht gekennzeichnet ist, verwirft das Audience Manager-Plug-in für die IAB-TCF die TC-Zeichenfolge und verarbeitet die Anforderung wie gewohnt, wenn die Bewertungszeit über die Löschzeit aus der Global CMP-Liste hinausgeht. Das IAB TCF v2.0 ${GDPR} Makro ist auf 0 gesetzt und das ${GDPR_CONSENT_XXX} Makro ist leer.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>Die Zeichenfolge für die Zustimmung gibt keine Zustimmung</p> </td> 
   <td colname="col3"> <p>Wenn keine Zustimmung erteilt wird, schließt das Audience Manager-Plug-in für die IAB-TCF den Benutzer von der weiteren Datenerfassung ab oder löscht den Aufruf vollständig, wenn kein Partnerkontext erkannt wurde.</p>
   </td>
  </tr>

</tbody>
</table>

## Beispielfehlermeldungen {#sample-error-codes}

Die [!DNL DCS] gibt Fehlercodes und -meldungen in einem [!DNL JSON] Objekt oder in einem X-Header in der HTTP-Antwort-Zeichenfolge zurück.

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

[Wettlaufsituationen (Race Conditions) und Fehlerbehandlung](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
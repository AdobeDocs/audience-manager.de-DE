---
description: Von Datenerfassungsservern (Data Collection Servers, DCS) generierte Fehlercodes und Meldungen werden in numerischer Reihenfolge nach Code-ID aufgelistet.
title: DCS-Fehlercodes, Meldungen und Beispiele
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 4%

---

# DCS-Fehlercodes, Meldungen und Beispiele {#dcs-error-codes-messages-and-examples}

Von der [!UICONTROL Data Collection Servers] ([!DNL DCS]) in numerischer Reihenfolge nach Code-ID aufgeführt.

In den unten stehenden Tabellen *kursiv* stellt einen Variablenplatzhalter dar.

## Systemfehlercodes {#system-error-codes}

| Fehler-Code | Fehlermeldung | Beschreibung |
|---|---|---|
| 0 | Nicht angegebener Fehler | Dies ist ein Sammelfehler, der Ereignisse verarbeitet, die nicht von den anderen Fehler-Handlern abgedeckt werden. Die Fehlerbehebung ist schwierig. Sie kann durch eine Vielzahl unbekannter Aktionen oder Ereignisse verursacht werden. Wenn dieser Fehler angezeigt wird, versuchen Sie Ihre [!DNL DCS] erneut anfordern. Wenden Sie sich an [!DNL Adobe] angezeigt, wenn das Problem weiterhin besteht. |
| 1 | Die Konfiguration für den Hostnamen konnte nicht gefunden werden: `hostname` | Der in der Anfrage gesendete Hostname wurde nicht von unserem Partner-Bereitstellungsteam eingerichtet. Wenden Sie sich an [!DNL Adobe] angezeigt, wenn diese Fehlermeldung angezeigt wird. |
| 2 | Ungültig `d_orgid` -Wert (konnte keine Konfiguration für diese Organisations-ID finden): `ID` | Die Organisations-ID ist falsch. Überprüfen Sie Ihre ID und versuchen Sie die Anfrage erneut. Wenn Sie Ihre Organisations-ID nicht kennen oder noch nicht über eine solche verfügen, lesen Sie den Abschnitt &quot;Administrationsseite&quot; [Organisationen und Kontoverknüpfung](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) für Informationen darüber, wie Sie sie finden. |
| 10 | Eigenschaften können nicht ausgewertet werden | Die Eigenschaften der Anforderung wurden entweder teilweise bewertet oder gar nicht bewertet. Wenden Sie sich an [!DNL Adobe] angezeigt, wenn das Problem weiterhin besteht. |

## Integrationsfehlercodes {#integration-error-codes}

| Fehler-Code | Fehlermeldung | Beschreibung |
|---|---|---|
| 100 | Hostname für Anfrage konnte nicht abgerufen werden | Ein [!DNL API] -Aufruf hat den Host nicht gesendet [!DNL HTTP] -Kopfzeile in der Anfrage. Fügen Sie den Host-Header zum -Aufruf hinzu und versuchen Sie es erneut. Die meisten Browser und [!DNL API] -Clients tun dies automatisch. |
| 101 | Ungültig [!DNL Experience Cloud] ID weitergegeben `ID` | Die [!DNL DCS] -Aufruf enthält einen ungültigen [!DNL Experience Cloud] Kennung. Überprüfen Sie die `d_mid=` Schlüssel-Wert-Paar in der Kopfzeile. Vergewissern Sie sich, dass Sie die richtige [!DNL Experience Cloud] Kennung und versuchen Sie es erneut. |
| 102 | Ungültig [!DNL AAM ID] übergebene Anfrage `ID` | Die [!DNL DCS] -Aufruf enthält einen ungültigen [!DNL Audience Manager] Kennung. Überprüfen Sie die `d_uuid=` Schlüssel-Wert-Paar in der Kopfzeile. Vergewissern Sie sich, dass Sie die richtige [!DNL Audience Manager] Kennung und versuchen Sie es erneut. |
| 104 | Alle Kunden-IDs sind ungültig | Alle Kunden-IDs in Ihrem Aufruf sind ungültig. Überprüfen Sie Ihre IDs und versuchen Sie es erneut. |
| 109 | Referrer `HTTP referer` ist für Partner nicht zulässig `Partner ID` | Die `HTTP referer` -Kopfzeile im -Aufruf ist für die Partner-ID im -Aufruf nicht zulässig. Stellen Sie sicher, dass die `HTTP referer` -Kopfzeile korrekt ist. |
| 111 | Ungültig `IMS` Token empfangen | Zurückgegeben für [!DNL Audience Manager] - [!DNL Adobe Target] Integrationen. Der Fehler wird ausgelöst, wenn ein Aufruf an die [!DNL DCS], die einen ungültigen enthält [!DNL IMS] Token. Das Token kann fehlerhaft sein, abgelaufen sein oder der Benutzer kann nicht berechtigt sein, auf die erforderliche Ressource zuzugreifen. |

## Opt-out-Fehlercodes {#opt-out-error-codes}

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
   <td colname="col2"> <p>Opt-out-Tag für ID gefunden <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Ein Kunde hat sich vom Erhalt einer zinsbasierten Werbung abgemeldet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Blockierte Cookies </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn der Browser des Benutzers Drittanbieter-Cookies blockiert.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Treuebeziehung über <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>Der Benutzer hat über NAI einen Opt-out-Prozess eingeleitet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Anträge dieses Landes werden von einem Partner blockiert </p> </td> 
   <td colname="col3"> <p>Basierend auf der IP-Adresse wird die <span class="wintitle"> DCS</span> blockiert Anforderungen aus Ländern, in denen der Partner den Traffic absichtlich begrenzt hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Anfragen aus diesem Land sind nicht zulässig </p> </td> 
   <td colname="col3"> <p>Basierend auf der IP-Adresse wird die <span class="wintitle"> DCS</span> blockiert Anforderungen aus den folgenden Ländern: </p> <p> 
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

## Fehler-Codes beim Abrufen von Profilen {#profile-retrieval-error-codes}

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
   <td colname="col3"> <p>Wird zurückgegeben, wenn ein Benutzerprofil nicht aus unserem internen Speicher gelesen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Geräte-IDs können nicht aus dem Profil-Cache für Kunden-ID gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die <a href="../../../reference/ids-in-aam.md"> Geräte-ID</a> kann nicht für eine Profillink-Zusammenführungsregel abgerufen werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Zugehörige Kunden für Geräte-ID können nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die <a href="../../../reference/ids-in-aam.md"> Kunden-ID (UUID)</a> mit einer Geräte-ID verknüpft ist, kann nicht für eine Zusammenführungsregel mit der Bezeichnung "Zuletzt authentifiziert"aus unserem internen Speicher abgerufen werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Gerätecluster für ID kann nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die verknüpften Geräte-IDs desselben Gerätediagramm-Clusters können für diese Geräte-ID nicht zurückgegeben werden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Migration konnte nicht durchgeführt werden, da das Lesen des Profils für das primäre Gerät fehlgeschlagen ist </p> </td> 
   <td colname="col3"> <p>Wenn dieser Fehler bei Ihnen auftritt, kann es bei unserem Datenspeicher (<span class="wintitle"> PCS</span>). Wenden Sie sich an Ihren Kundenbetreuer, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Migration von konnte nicht durchgeführt werden <code><i>ID</i></code> nach <code><i>ID</i></code>, da der Profillesen für <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Wenn dieser Fehler bei Ihnen auftritt, kann es bei unserem Datenspeicher (<span class="wintitle"> PCS</span>). Wenden Sie sich an Ihren Kundenbetreuer, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Integrationswarnungscodes {#integration-warning-codes}

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
   <td colname="col3"> <p>Die Kunden-ID ist ungültig (fehlende Werte für die Datenquelle, fehlende Integrationscodes, ungültiges Format für Datenquellen, blockierte Kunden-ID, leere Kunden-ID, nicht autorisierter Zugriffsversuch auf eine Datenquelle, die nicht zum Partner gehört). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Maximale Anzahl der Kunden-IDs überschritten. Maximal zulässig <code><i>maximum allowed</i></code>. gefunden <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>Die Anzahl der Kunden-IDs, die mit einer geräteübergreifenden Datenquelle verknüpft sind, überschreitet die zulässige Anzahl geräteübergreifender IDs pro Anfrage. Zu diesen IDs gehören geräteübergreifende, mobile oder Cookie-IDs. Der Grenzwert ist derzeit auf 10 festgelegt. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Unberechtigte Kunden-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID-Datenquelle nicht der aktuellen Organisations-ID gehört. Wenn Sie Ihre Organisations-ID nicht kennen oder noch nicht über eine solche verfügen, finden Sie weitere Informationen im Abschnitt "Organisations-ID ermitteln"unter <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisationen und Kontoverknüpfung</a> für Informationen darüber, wie Sie sie finden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Blockierte Kunden-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID als bösartig identifiziert und einer Blockierungsliste hinzugefügt wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Kennung der blockierten Datenquelle <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Datenquellen-ID als bösartig identifiziert und einer Blockierungsliste hinzugefügt wurde </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Blockierte deklarierte Geräte-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die Geräte-ID wurde als bösartig identifiziert und zu einer Blockierungsliste hinzugefügt. Dies kann passieren, wenn eine extreme Anzahl von <span class="wintitle"> DCS</span> -Anfragen, die diese Geräte-ID enthalten, in kurzer Zeit. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Vorgang "Blocked profile"für <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Eine Lese-/Schreibaktion wurde blockiert, da eine ID als bösartig identifiziert und zu einer Blockierungsliste hinzugefügt wurde Siehe Fehlercode 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Kunden-ID <code><i>ID</i></code> wurde verworfen, weil es die Grenze der deklarierten Kunden-IDs pro Anfrage überschritten hat </p> </td> 
   <td colname="col3"> <p>Zusammenhang mit Fehler 301. Dieser Fehler gibt an, welche Kunden-ID verworfen wurde, weil die Grenze überschritten wurde. </p> <p>Wenn beispielsweise 12 Kunden-IDs auf der <span class="wintitle"> DCS</span> -Aufruf, werden zwei davon verworfen. Um die verworfenen weiterzuleiten, wird dieser Fehler in der Antwort zweimal angezeigt (einmal für jede verworfene Kunden-ID ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Kunden-ID wurde verworfen, da sie die Beschränkung für einen bestimmten Namespace überschritten hat. Namespace-ID ist <code><i>ID</i></code>, lautet die Kunden-ID <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Dieser Fehlercode wird zurückgegeben, wenn mehr als 3 Kunden-IDs für denselben Namespace deklariert sind (<code> DPID</code>) auf <span class="wintitle"> DCS</span> aufrufen. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In diesem Beispiel <span class="wintitle"> DCS</span> -Anfrage gibt es 4 IDs, die für denselben Namespace deklariert sind (mit dem Integrationscode 1). Eine der IDs wird verworfen und der Fehler 310 wird zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>Anfrage enthält ungültige Parameter </p> </td> 
   <td colname="col3"> <p>Die <span class="wintitle"> DCS</span> gibt diesen Fehlercode zurück, wenn mindestens ein URL-Parameter nicht ordnungsgemäß kodiert ist. In diesem Fall wird die <span class="wintitle"> DCS</span> die gesamte Anfrage ignoriert. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>In der obigen Beispielanfrage wird die <code> %</code> Sequenz ist falsch kodiert. Folglich <span class="wintitle"> DCS</span> wird es ignorieren. </p> <p>Das korrekt kodierte Beispiel sollte wie folgt aussehen: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>Anfrage enthält eine ungültige globale Geräte-ID </p> </td> 
   <td colname="col3"> <p>Die <span class="wintitle">DCS</span> gibt diesen Fehlercode zurück, wenn die Anfrage eine ungültige globale Geräte-ID enthält. Der DES ignoriert die ungültige ID und gibt einen 312-Fehler zusammen mit den spezifischen Fehlern der ungültigen ID aus. Siehe <a href="../../../features/global-data-sources.md" format="dita" scope="local">Globale Data Sources</a> und <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index der IDs in Audience Manager</a> für detaillierte Informationen zu den richtigen Geräte-Werbe-ID-Formaten und den entsprechenden globalen Datenquellen.</p>
   <p>Beispiel eines falschen Aufrufs: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Erklärung: Ein <span class="keyword">IDFA (DPID 20915)</span> muss eine ID in Großbuchstaben sein. Die in der Anfrage angegebene ID ist in Kleinbuchstaben.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>Die CMP-ID ist nicht in GCL enthalten.</p> </td> 
   <td colname="col3"> <p>Wann <code>gdpr=1</code> und die IAB-TC-Zeichenfolge von einer CMP-ID generiert wird, die zum Zeitpunkt der Auswertung nicht in der zwischengespeicherten Version der globalen CMP-Liste von Audience Manager vorhanden ist, verwirft das Audience Manager-Plug-in für IAB TCF die IAB-TC-Zeichenfolge und verarbeitet die Anforderung wie gewohnt. Das IAB TCF v2.0 ${GDPR} -Makro ist auf 0 gesetzt und das Makro ${GDPR_CONSENT_XXX} ist leer.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP-ID wird als in GCL als gelöscht markiert</p> </td> 
   <td colname="col3"> <p>Wann <code>gdpr=1</code> und die IAB-TC-Zeichenfolge von einem CMP generiert wird, der in unserer zwischengespeicherten Version der globalen CMP-Liste als gelöscht markiert ist, verwirft das Audience Manager-Plug-in für IAB TCF die TC-Zeichenfolge und verarbeitet die Anforderung wie gewohnt, wenn die Auswertungszeit nach der Löschzeit aus der globalen CMP-Liste liegt. Das IAB TCF v2.0 ${GDPR} -Makro ist auf 0 gesetzt und das Makro ${GDPR_CONSENT_XXX} ist leer.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>Zustimmungszeichenfolge gibt keine Zustimmung an</p> </td> 
   <td colname="col3"> <p>Wenn keine Zustimmung erteilt wird, lehnt das Audience Manager-Plug-in für IAB TCF die weitere Datenerfassung ab oder bricht den Aufruf vollständig ab, wenn kein Partnerkontext erkannt wird.</p>
   </td>
  </tr>

</tbody>
</table>

## Beispiel-Fehlercode-Meldungen {#sample-error-codes}

Die [!DNL DCS] gibt Fehlercodes und -nachrichten in einer [!DNL JSON] -Objekt oder in einem X-Header in der HTTP-Antwortzeichenfolge.

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

### X-Fehler

Vom X-Header erfasste Fehlercodes werden in der URL-Zeichenfolge wie folgt angezeigt: `X-Error: 101,102`.

[Wettlaufsituationen (Race Conditions) und Fehlerbehandlung](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

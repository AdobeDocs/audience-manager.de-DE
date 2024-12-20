---
description: Fehlercodes und Meldungen, die von den Datenerfassungs-Servern (DCS) generiert werden und in numerischer Reihenfolge nach Code-ID aufgeführt sind.
title: DCS-Fehler-Codes, Meldungen und Beispiele
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '1517'
ht-degree: 3%

---

# DCS-Fehler-Codes, Meldungen und Beispiele {#dcs-error-codes-messages-and-examples}

Fehlercodes und Meldungen, die von der [!UICONTROL Data Collection Servers] ([!DNL DCS]) generiert wurden und in numerischer Reihenfolge nach Code-ID aufgelistet sind.

In den folgenden Tabellen steht *kursiv* für einen Variablenplatzhalter.

## Systemfehlercodes {#system-error-codes}

| Fehlercode | Fehlermeldung | Beschreibung |
|---|---|---|
| 0 | Nicht spezifizierter Fehler | Dies ist ein Fehler, der alle Fehler erfasst und Ereignisse behandelt, die nicht von den anderen Fehler-Handlern abgedeckt werden. Die Fehlerbehebung für diesen Fehler ist schwierig. Sie kann durch eine Vielzahl von unbekannten Aktionen oder Ereignissen verursacht werden. Wenn Sie diesen Fehler erhalten, versuchen Sie Ihre [!DNL DCS] erneut. Wenden Sie sich an den [!DNL Adobe], wenn das Problem weiterhin besteht. |
| 1 | Konfiguration für Host-Namen wurde nicht gefunden: `hostname` | Der in der Anfrage gesendete Hostname wurde nicht von unserem Partner-Bereitstellungs-Team eingerichtet. Wenden Sie sich an den [!DNL Adobe], wenn diese Fehlermeldung angezeigt wird. |
| 2 | Ungültiger `d_orgid` (für diese Organisations-ID wurde keine Konfiguration gefunden): `ID` | Die Organisations-ID ist falsch. Überprüfen Sie Ihre ID und versuchen Sie die Anfrage erneut. Wenn Sie Ihre Organisations-ID nicht kennen oder haben, finden Sie im Abschnitt „Administrationsseite“ [Organisationen und Kontoverknüpfung](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) Informationen dazu, wie Sie sie finden. |
| 10 | Eigenschaften können nicht ausgewertet werden | Die Eigenschaften in der Anfrage wurden entweder teilweise oder gar nicht ausgewertet. Wenden Sie sich an den [!DNL Adobe], wenn das Problem weiterhin besteht. |

## Fehler-Codes für die Integration {#integration-error-codes}

| Fehlercode | Fehlermeldung | Beschreibung |
|---|---|---|
| 100 | Der Hostname für die Anfrage konnte nicht abgerufen werden | Ein [!DNL API]-Aufruf hat die [!DNL HTTP]-Kopfzeile des Hosts in der Anfrage nicht gesendet. Fügen Sie die Host-Kopfzeile zum Aufruf hinzu und versuchen Sie es erneut. Die meisten Browser und [!DNL API] Clients tun dies automatisch. |
| 101 | Ungültige [!DNL Experience Cloud]-ID in `ID` übergeben | Der [!DNL DCS]-Aufruf enthält eine ungültige [!DNL Experience Cloud]-ID. Überprüfen Sie das `d_mid=` Schlüssel-Wert-Paar in der Kopfzeilen-Zeichenfolge. Stellen Sie sicher, dass Sie die richtige [!DNL Experience Cloud]-ID übergeben, und wiederholen Sie die Anfrage. |
| 102 | Ungültige [!DNL AAM ID] in Anfrage `ID` übergeben | Der [!DNL DCS]-Aufruf enthält eine ungültige [!DNL Audience Manager]-ID. Überprüfen Sie das `d_uuid=` Schlüssel-Wert-Paar in der Kopfzeilen-Zeichenfolge. Stellen Sie sicher, dass Sie die richtige [!DNL Audience Manager]-ID übergeben, und wiederholen Sie die Anfrage. |
| 104 | Alle Kunden-IDs sind ungültig | Alle Kunden-IDs in Ihrem -Aufruf sind ungültig. Überprüfen Sie Ihre IDs und versuchen Sie es erneut. |
| 109 | Referrer `HTTP referer` ist für Partner-`Partner ID` nicht zulässig | Die `HTTP referer`-Kopfzeile des -Aufrufs ist für die Partner-ID des -Aufrufs nicht zulässig. Überprüfen Sie, ob die `HTTP referer`-Kopfzeile korrekt ist. |
| 111 | Ungültiges `IMS` empfangen | Zurückgegeben für [!DNL Audience Manager] - [!DNL Adobe Target]. Der Fehler wird ausgelöst, wenn ein Aufruf an die [!DNL DCS] erfolgt, die ein ungültiges [!DNL IMS]-Token enthält. Das Token ist möglicherweise fehlerhaft oder abgelaufen oder der Benutzer ist möglicherweise nicht berechtigt, auf die erforderliche Ressource zuzugreifen. |

## Fehler-Codes für Opt-out {#opt-out-error-codes}

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
   <td colname="col2"> <p>Opt-out-Tag für ID <code><i>ID</i></code> aufgetreten </p> </td> 
   <td colname="col3"> <p>Ein Kunde hat sich gegen den Erhalt von interessenbasierter Werbung entschieden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Blockierte Cookies </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn der Browser des Benutzers Drittanbieter-Cookies blockiert.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Auf Vertrauensbeziehung über <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI gestoßen</a> </p> </td> 
   <td colname="col3"> <p>Der Benutzer hat über NAI einen Opt-out-Prozess initiiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Anfragen aus diesem Land werden von dem Partner blockiert </p> </td> 
   <td colname="col3"> <p>Basierend auf der IP-Adresse blockiert <span class="wintitle"> DCS</span> Anfragen aus Ländern, in denen der Partner den Traffic bewusst beschränkt hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Anfragen aus diesem Land sind nicht zulässig </p> </td> 
   <td colname="col3"> <p>Basierend auf der IP-Adresse blockiert der <span class="wintitle"> DCS</span> Anfragen aus den folgenden Ländern: </p> <p> 
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

## Fehlercodes für den Profilabruf {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> Eigenschaften aus dem Profil-Cache für ID können nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn ein Benutzerprofil nicht aus unserem internen Speicher gelesen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Geräte-IDs können nicht aus dem Profil-Cache für Kunden-ID gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die <a href="../../../reference/ids-in-aam.md">-Geräte</a>ID für eine Profilverknüpfungs-Zusammenführungsregel nicht abgerufen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Der zugehörige Kunde für Geräte-ID kann nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die <a href="../../../reference/ids-in-aam.md"> Kunden-ID (UUID</a>, die einer Geräte-ID zugeordnet ist, nicht für eine Regel zur letzten authentifizierten Zusammenführung aus unserem internen Speicher abgerufen werden kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Gerätecluster für ID kann nicht gelesen werden: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die verknüpften Geräte-IDs aus demselben Gerätediagramm-Cluster können für diese Geräte-ID nicht zurückgegeben werden. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Migration konnte nicht durchgeführt werden, da das Lesen des Profils für das Primärgerät fehlgeschlagen ist. </p> </td> 
   <td colname="col3"> <p>Wenn Sie diesen Fehler erhalten, können Skalierbarkeitsprobleme bei unserem Datenspeicher (<span class="wintitle"> PCS) </span>. Wenden Sie sich an den Adobe-Support, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Migration von <code><i>ID</i></code> nach <code><i>ID</i></code> konnte nicht durchgeführt werden, da das Lesen des Profils für <code><i>ID</i></code> fehlgeschlagen ist </p> </td>
   <td colname="col3"> <p>Wenn Sie diesen Fehler erhalten, können Skalierbarkeitsprobleme bei unserem Datenspeicher (<span class="wintitle"> PCS) </span>. Wenden Sie sich an den Adobe-Support, wenn das Problem weiterhin besteht. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Warncodes für die Integration {#integration-warning-codes}

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
   <td colname="col3"> <p>Die Kunden-ID ist ungültig (fehlende Werte für die Datenquelle, fehlende Integrations-Codes, ungültiges Format für Datenquellen, blockierte Kunden-ID, leere Kunden-ID, nicht autorisierter Zugriffsversuch auf eine Datenquelle, die nicht zum Partner gehört). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Maximale Anzahl von Kunden-IDs überschritten. Maximal zulässig ist <code><i>maximum allowed</i></code>. Gefunden wurde <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>Die Anzahl der mit einer geräteübergreifenden Datenquelle verknüpften Kunden-IDs überschreitet die zulässige Anzahl geräteübergreifender IDs pro Anfrage. Zu diesen IDs gehören geräteübergreifende, mobile oder Cookie-IDs. Das Limit ist derzeit auf 10 festgelegt. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Nicht autorisierte Kunden-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID-Datenquelle nicht der aktuellen Organisations-ID gehört. Wenn Sie Ihre Organisations-ID nicht kennen oder haben, finden Sie im Abschnitt „Suchen Ihrer Organisations-ID“ in <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisations- und </a> Informationen darüber, wie Sie sie finden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Blockierte Kunden-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Kunden-ID als bösartig identifiziert und einer Blockierungsliste hinzugefügt wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Blockierte Datenquelle-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Wird zurückgegeben, wenn die Datenquellen-ID als bösartig identifiziert und einer Blockierungsliste hinzugefügt wurde </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Blockierte deklarierte Geräte-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Die Geräte-ID wurde als bösartig identifiziert und einer Blockierungsliste hinzugefügt. Dies kann passieren, wenn wir in kurzer Zeit extrem viele <span class="wintitle"> DCS</span>-Anfragen mit dieser Geräte-ID erhalten. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Blockierter Profilvorgang für <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Eine Lese-/Schreibaktion wurde blockiert, da eine ID als bösartig erkannt und einer Blockierungsliste hinzugefügt wurde. Siehe Fehlercode 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Kunden-ID <code><i>ID</i></code> wurde verworfen, da sie das Limit von deklarierten Kunden-IDs pro Anfrage überschritten hat </p> </td> 
   <td colname="col3"> <p>Bezieht sich auf Fehler 301. Dieser Fehler gibt an, welche Kunden-ID verworfen wurde, da das Limit überschritten wurde. </p> <p>Wenn beispielsweise 12 Kunden-IDs im Aufruf <span class="wintitle"> DCS</span> deklariert sind, werden zwei von ihnen verworfen. Um weiterzuleiten, welche verworfen wurden, wird dieser Fehler zweimal in der Antwort angezeigt (einmal für jede verworfene Kunden-ID ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Kunden-ID wurde verworfen, da sie das Limit für einen bestimmten Namespace überschritten hat. Namespace-ID ist <code><i>ID</i></code>, Kunden-ID ist <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Dieser Fehler-Code wird zurückgegeben, wenn bei einem <span class="wintitle"> DCS</span>-Aufruf mehr als 3 Kunden-IDs für denselben Namespace (<code> DPID</code>) deklariert sind. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>In diesem Beispiel <span class="wintitle"> DCS</span>-Anfrage gibt es vier IDs, die für denselben Namespace deklariert wurden (mit dem Integrations-Code eins). Eine der IDs wird verworfen und der Fehler 310 wird zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>Anfrage enthält ungültige Parameter </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle"> DCS</span> gibt diesen Fehlercode zurück, wenn mindestens ein URL-Parameter nicht ordnungsgemäß codiert ist. In diesem Fall ignoriert der <span class="wintitle"> DCS</span> die gesamte Anfrage. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>In der obigen Beispielanfrage ist die <code> %</code> falsch codiert. Folglich wird das <span class="wintitle"> DCS</span> sie ignorieren. </p> <p>Das korrekt codierte Beispiel sollte wie folgt aussehen: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>Anfrage enthält eine ungültige globale Geräte-ID </p> </td> 
   <td colname="col3"> <p>Der <span class="wintitle">DCS</span> gibt diesen Fehlercode zurück, wenn die Anfrage eine ungültige globale Geräte-ID enthält. DCS ignoriert die ungültige ID und gibt einen 312-Fehler zusammen mit den spezifischen Fehlern der ungültigen ID aus. Unter <a href="../../../features/global-data-sources.md" format="dita" scope="local">Globale Datenquellen</a> und <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index der IDs im Audience Manager </a> finden Sie detaillierte Informationen zu den richtigen Formaten für Geräteanzeigen und den entsprechenden globalen Datenquellen.</p>
   <p>Beispiel für einen falschen Aufruf: <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Erklärung: Eine <span class="keyword">IDFA (DPID 20915)</span> muss eine ID in Großbuchstaben sein. Die in der Anfrage angegebene ID ist Kleinbuchstaben.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>CMP-ID ist in GCL nicht vorhanden</p> </td> 
   <td colname="col3"> <p>Wenn <code>gdpr=1</code> und die IAB-TC-Zeichenfolge von einer CMP-ID generiert werden, die zum Zeitpunkt der Auswertung nicht in der zwischengespeicherten Version der globalen CMP-Liste von Audience Manager vorhanden ist, verwirft das Audience Manager-Plug-in für IAB TCF die IAB-TC-Zeichenfolge und verarbeitet die Anfrage wie gewohnt. Das IAB TCF v2.2 ${GDPR}-Makro ist auf 0 gesetzt und das ${GDPR_CONSENT_XXX}-Makro ist leer.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP-ID wird in GCL als gelöscht markiert</p> </td> 
   <td colname="col3"> <p>Wenn <code>gdpr=1</code> und die IAB-TC-Zeichenfolge von einer CMP generiert werden, die in der zwischengespeicherten Version der globalen CMP-Liste als gelöscht markiert ist, verwirft das Audience Manager-Plug-in für IAB TCF die TC-Zeichenfolge und verarbeitet die Anfrage wie gewohnt, wenn die Auswertungszeit nach der Löschzeit aus der globalen CMP-Liste liegt. Das IAB TCF v2.2 ${GDPR}-Makro ist auf 0 gesetzt und das ${GDPR_CONSENT_XXX}-Makro ist leer.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>Einverständniszeichenfolge gibt kein Einverständnis an</p> </td> 
   <td colname="col3"> <p>Wenn kein Einverständnis erteilt wird, verhindert das Audience Manager-Plug-in für IAB TCF, dass der Benutzer weitere Daten erfasst, oder löscht den Aufruf vollständig, wenn kein Partnerkontext erkannt wurde.</p>
   </td>
  </tr>

</tbody>
</table>

## Beispiele für Fehlercode-Meldungen {#sample-error-codes}

Die [!DNL DCS] gibt Fehler-Codes und Meldungen in einem [!DNL JSON]-Objekt oder in einer X- -Kopfzeile in der HTTP-Antwortzeichenfolge zurück.

### Beispiel-DCS-Fehler-Code und -Nachricht

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

Vom X- -Header erfasste Fehler-Codes werden `X-Error: 101,102` wie folgt in der URL-Zeichenfolge angezeigt.

[Wettlaufbedingungen und Fehlerbehandlung](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

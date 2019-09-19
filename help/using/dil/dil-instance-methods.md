---
description: Mit den DIL-APIs auf Instanzebene können Sie Audience Manager-Objekte programmgesteuert erstellen und verwenden. Die Methoden auf Instanzebene verbessern die API-Funktionalität, die durch Methoden auf Klassenebene festgelegt wird.
keywords: Eigenschaften erstellen;Eigenschaften erstellen
seo-description: Mit den DIL-APIs auf Instanzebene können Sie Audience Manager-Objekte programmgesteuert erstellen und verwenden. Die Methoden auf Instanzebene verbessern die API-Funktionalität, die durch Methoden auf Klassenebene festgelegt wird.
seo-title: DIL-Methoden auf Instanzebene
solution: Audience Manager
title: DIL-Methoden auf Instanzebene
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL-Methoden auf Instanzebene{#instance-level-dil-methods}

Mit den [!UICONTROL DIL] APIs auf Instanzebene können Sie Audience Manager-Objekte programmgesteuert erstellen und verwenden. Die Methoden auf Instanzebene verbessern die API-Funktionalität, die durch Methoden auf Klassenebene festgelegt wird.

## Erste Schritte mit DIL-Methoden auf Instanzebene {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Beim Arbeiten mit [!UICONTROL DIL] APIs auf Instanzebene:

* Für den Zugriff sind ein Name des Partners und eine Container-Namespace-ID (NSID) erforderlich. Wenden Sie sich an Ihren Audience Manager-Kundenbetreuer, um diese Informationen zu erhalten.
* Ersetzen Sie den *kursiv* formatierten Beispieltext in der API-Dokumentation durch Wert, ID oder andere Variable, die von der verwendeten Methode benötigt werden.

<!-- 

c_instance_start.xml

 -->

## signale {#signals}

Fügt der Abfragezeichenfolge einer ausstehenden Anforderung Zuordnungen auf Kunden- und Plattformebene hinzu.

<!-- 

r_dil_signals.xml

 -->

**** Funktionssignatur: `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Sie können andere API-Aufrufe mit dieser Methode verketten.
>* Wenn sich die Adobe Experience Cloud-JavaScript-Bibliothek auf der Seite befindet, `submit()` wartet darauf, dass die Cloud ein Cookie setzt, bevor eine Anforderung gesendet wird.


**Reservierte Anforderungsschlüssel**

Die folgenden Anforderungsschlüssel sind reserviert und können mit dieser Methode nicht überschrieben werden:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `obj` | Objekt | Ein Objekt, das die Schlüssel-Wert-Paare für Zuordnungen auf Plattformebene darstellt. Parameter akzeptiert Zeichenfolgen und Arrays als Eigenschaftswerte im Objekt. |
| `prefix` | Zeichenfolge | Optional. Der Zeichenfolgenwert, der jedem Objektschlüssel als Präfix vorangestellt wird (ersetzt den Originalschlüssel). |
| `return` | DIL.api | Gibt das API-Objekt der aktuellen DIL-Instanz zurück. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner: '<i>partnerName</i>' containerNSID: <i>containerNSID</i> }); 
 
// Methode 1 var obj = { key1 : 1, key2: 2 }; 
dataLib.api.Signals(obj, 'c_').submit(); 
 
// Methode 2 dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Methode 3 // wird 'c_key=a&amp;c_key=2&amp;c_key=3' an Audience Manager var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.Signals(obj, 'c_').submit(); 
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [Namensanforderungen für Schlüsselvariablen](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

Fügt der Abfragezeichenfolge einer ausstehenden Anforderung SIDs hinzu.

<!-- 

r_dil_traits.xml

 -->

**** Funktionsunterschrift: `traits:function (sids){}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `sids` | Array | Eigenschaftensegment-IDs in einem Array. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>
var partnerObject = DIL.create({ partner: '<i>Name</i>des Partners', containerNSID: <i>NSID</i> }); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Fügen Sie Daten zu Protokolldateien in der ausstehenden Anforderung hinzu.

<!-- 

r_dil_logs.xml

 -->

**** Funktionsunterschrift: `logs: function {key1:value1, key2:value2}`

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>
var partnerObject = DIL.create({ partner: '<i>partner</i>', containerNSID: <i>NSID</i> }); 
partnerObject.api.logs({ file: "dil.js", Meldung: 'Dies ist die erste Anforderung' });
</code></pre>

## submit {#submit}

Sendet alle ausstehenden Daten an Audience Manager für die [!UICONTROL DIL] Instanz.

<!-- 

r_dil_submit.xml

 -->

**** Funktionssignatur: `submit: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten. Schreibt auch kodierte Daten in ein Ziel-Cookie. [!UICONTROL DIL] Leerzeichen werden beispielsweise als `%20` und Semikolons als `%3B`kodiert.

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ file: "dil.js", Meldung: 'Dies ist die erste Anforderung' }).signals({ c_zdid: <i>111</i> d_dma: '<i>default</i>' }).submit();
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [Voraussetzungen für das Präfix für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

Eine Funktion, die nach dem Rückruf beim Veröffentlichen des Standardziels ausgeführt wird.

<!-- 

r_dil_after_result.xml

 -->

**** Funktionssignatur: `afterResult: function (fn) {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `fn` | Funktion | Die Funktion, die nach der Verarbeitung von JSON ausgeführt werden soll, wird durch den standardmäßigen Rückruf verarbeitet, der die Zielveröffentlichung verarbeitet. |

**Antwort**

Gibt ein API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.signals({ c_zdid: <i>54321</i> d_dma: '<i>default</i>' }).afterResult(function(json){ //Tun Sie etwas mit den JSON-Daten, die vom Server zurückgegeben werden. 
}).submit();
</code></pre>

## clearData {#cleardata}

Löscht alle Daten in einer ausstehenden Anforderung.

<!-- 

r_dil_clear_data.xml

 -->

**** Funktionssignatur: `clearData: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ file: Meldung "dil.js": 'Dies ist die erste Anforderung' }).signals({ c_zdid: <i>111</i> d_dma: '<i>default</i>' }); 
 
//Zurücksetzen der ausstehenden dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Fügt benutzerdefinierte Abfrageparameter hinzu, die nicht explizit vom Datenerfassungsserver zu einer ausstehenden Anforderung definiert wurden.

<!-- 

r_dil_custom_query_params.xml

 -->

**** Funktionssignatur: `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Reservierte Anforderungsschlüssel**

Die folgenden Anforderungsschlüssel sind reserviert und können mit dieser Methode nicht überschrieben werden:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Antwort**

Gibt das API-Objekt der aktuellen DIL-Instanz zurück.

**Beispielcode**

<pre><code>
var partnerObject = DIL.create({ partner: '<i>partner</i>', containerNSID: <i>NSID</i> }); 
partnerObject.api.customQueryParams({ nid: 54231, Typ: 'default' }); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Gibt den Wert der Container-NSID für die [!UICONTROL DIL] Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_container_nsid.xml

 -->

**** Funktionssignatur: `dil.api.getContainerNSID: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
//Container NSID var nsid = dataLib.api.getContainerNSID() überprüfen;
</code></pre>

## getEventLog {#geteventlog}

Gibt chronologisch sortierte Ereignisprotokolldaten als Zeichenfolgen-Array zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_event_log.xml

 -->

**** Funktionssignatur: `dil.api.getEventLog: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ file: "dil.js", Meldung: 'Dies ist die erste Anforderung' });.signals({ c_zdid: <i>111</i> d_dma: '<i>default</i>' });.submit(); 
 
//Protokoll für Meldungen überprüfen var log = dataLib.api.getEventLog(); 
if (log &amp;&amp; log.length) { alert(log.join('\n')); 
else{ alert('Keine Protokollmeldungen'); 
}</code></pre>

## getPartner {#getpartner}

Gibt den Partnernamen für eine [!UICONTROL DIL] Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_partner.xml

 -->

**** Funktionssignatur: `dil.api.getPartner: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner: '<i>partnerName</i>' containerNSID: <i>containerNSID</i> }); 
 
//Überprüfen Sie den Partnernamen var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Gibt den Status der aktuellen [!UICONTROL DIL] Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_state.xml

 -->

**** Funktionssignatur: `dil.api.getState: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ file: 'dil.js', message:'Dies ist die erste Anforderung' });.signals({ c.zdid: <i>111</i> d_dma: '<i>default</i>' });.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Objektbeschreibung des Status = { pendingRequest: {<i>ausstehende Daten für den Aufruf an den Server</i>}, otherRequestInfo:{ fireQueue: [], ausgelöst: [], ausgelöst: false, Fehler: [], reservedKeys: { sids: true, pdata: true, logdata: true, callback: true, postCallbackFn: true, useImageRequest: true, }, firstRequestHasFired: false, num_of_jsonp_response: 0, num_of_jsonp_errors: 0, num_of_img_response: 0, num_of_img_errors: 0 }, destinationPublishingInfo: { THROTTLE_START: 3000, throttleTimerSet: false, id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, url: (constants.isHTTPS ? https://' : "https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' + containerNSID + '#' + encodeURIComponent(document.location.href), iframe: null, iframeHasLoaded: false, sendMessages: false, Meldungen: [], messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, //100 ms für IE 6 und 7 empfehlen, 15 ms für andere Browser jsonVerarbeitete: [] } } */</code></pre>

## idSync {#idsync}

Besteht aus zwei Funktionen, mit denen Datenpartner Benutzer-IDs untereinander und mit Audience Manager austauschen und synchronisieren können.

<!-- 

r_dil_idsync.xml

 -->

**Funktionssignatur:**

Funktioniert mit [!UICONTROL DIL] Versionen 2.10 und 3.1 oder höher.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code </th> 
   <th colname="col2" class="entry"> Synchronisiert Benutzer-IDs </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Zwischen verschiedenen Datenpartnern und Audience Manager. Partner x würde dies beispielsweise verwenden, um eine Benutzer-ID mit Partner y zu synchronisieren und diese dann an Audience Manager zu senden. </p> <p> <p><b></b> Wichtig:  Diese Methode ist veraltet. Bitte verwenden Sie die <code> idSyncByURL- </code> Methode der Experience Cloud ID-Dienstinstanz. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Wenn Sie die Benutzer-ID bereits kennen und sie an Audience Manager senden möchten. </p> <p> <p><b></b> Wichtig:  Diese Methode ist veraltet. Bitte verwenden Sie die <code> idSyncByDataSource- </code> Methode der Experience Cloud ID-Dienstinstanz. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync-Elemente**

`idSync` kann Folgendes umfassen:

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>Durch Audience Manager zugewiesene Datenanbieter-ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>Die eindeutige Datenanbieter-ID für den Benutzer. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> Nummer </td> 
   <td colname="col3"> <p><i>(Optional)</i> Legt die Cookie-Ablaufzeit fest. Hierbei muss es sich um eine Ganzzahl handeln. Der Standardwert lautet 20.160 Minuten (14 Tage). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>Ziel-URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Makros**

`idSync` akzeptiert die folgenden Makros:

* **`%TIMESTAMP%`:** Generiert einen Zeitstempel (in Millisekunden). Wird für das Cache-Busting verwendet.
* **`%DID%`:** Fügt die Audience Manager-ID für den Benutzer ein.
* **`%HTTP_PROTO%`** : Legt das Seitenprotokoll fest ( `http` oder `https`).

**Antwort**

Beide Funktionen werden `Successfully queued` bei erfolgreichem Abschluss zurückgegeben. Falls nicht, wird eine Fehlermeldungszeichenfolge zurückgegeben.

**Beispielcode**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// URL mit Makros ersetzen dilInstance.api.idSync({ dpid: '23', // muss eine String-URL sein: '//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net %2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', Minuten Live: 20160 // optional, standardmäßig 20160 Minuten (14 Tage) });
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fehlerbehebungen 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&amp;dpuuid=&lt;dpuuid&gt;' dilInstance.api.aamIdSync({ dpid: '23', // muss eine Zeichenfolge sein: '98765', // muss eine Zeichenfolge minToLive sein: 20160 // optional, standardmäßig 20160 Minuten (14 Tage) });
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [Synchronisierungsfunktionen im Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

Fügt der ausstehenden Anforderung einen Rückruf (der JSON erhält) hinzu.

<!-- 

r_dil_result.xml

 -->

**** Funktionssignatur: `result: function (callback) {}`

Dieser Rückruf ersetzt den Standard-Rückruf, der die Zielveröffentlichung behandelt.

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `callback` | Funktion | JavaScript-Funktion, die vom JSONP-Rückruf ausgeführt wird. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner: '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ //Tun Sie etwas, möglicherweise mit den JSON-Daten, die vom Server zurückgegeben werden. 
});.submit();
</code></pre>

##  secureDataCollection {#securedatacollection}

`secureDataCollection` ist ein boolescher Parameter, der steuert, wie [!UICONTROL DIL] Aufrufe an die [!UICONTROL Data Collection Servers (DCS)] und Akamai gesendet werden.

<!-- 

dil-secure-data-collection.xml

 -->

* Wenn `secureDataCollection= true` (Standard), erfolgt [!UICONTROL DIL] immer ein sicherer HTTPS-Aufruf.

* Wenn `secureDataCollection= false`erfolgt [!UICONTROL DIL] entweder HTTP- oder HTTPS-Aufrufe gemäß dem von der Seite festgelegten Sicherheitsprotokoll.

>[!IMPORTANT]
>
>Wird eingestellt, `secureDataCollection= false` wenn Sie visitorAPI.js und [!UICONTROL DIL] auf derselben Seite verwenden. Siehe Codebeispiel unten.

<pre><code class="js">
var dilInstance = DIL.create({ ... 
     secureDataCollection: false });
</code></pre>

>[!MORE_LIKE_THIS]
>
>* [DIL erstellen](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` ist ein boolescher true/false-Parameter, der steuert, wie der Browser Ressourcen von anderen Domänen anfordert.

<!-- 

dil-use-cors-only.xml

 -->

**Übersicht**

`useCORSOnly` ist standardmäßig false. False bedeutet, dass der Browser Ressourcenprüfungen mit CORS oder JSONP durchführen kann. Es wird jedoch [!UICONTROL DIL] immer versucht, zunächst Ressourcen mit CORS anzufordern. Bei älteren Browsern, die CORS nicht unterstützen, wird auf JSONP zurückgegriffen. Wenn Sie den Browser zwingen müssen, nur CORS zu verwenden, z. B. bei Sites mit hohen Sicherheitsanforderungen, setzen Sie `useCORSOnly:true`.

**Codebeispiel**

<pre><code class="js">
var dilInstance = DIL.create({ ... 
     useCORSOnly: true });
</code></pre>

>[!IMPORTANT]
>
>* Es wird empfohlen, diese Einstellung `useCORSOnly: true` nur dann vorzunehmen, wenn Sie sicher sind, dass Ihre Site-Besucher Browser haben, die diese Funktion unterstützen.
>* Ab `useCORSOnly: true`diesem Zeitpunkt [!UICONTROL DIL] werden keine ID-Aufrufe von Internet Explorer Version 9 oder älter durchgeführt.
>



>[!MORE_LIKE_THIS]
>
>* [DIL erstellen](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID-Dienst: UseCORSOnly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [CORS-Unterstützung im Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

Ändert den Anforderungstyp in Bild `<img>` aus Skript `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**** Funktionssignatur: `useImageRequest: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Antwort**

Gibt ein API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>


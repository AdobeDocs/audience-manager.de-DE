---
description: Mit den DIL-APIs auf Instanzebene können Sie Audience Manager-Objekte programmgesteuert erstellen und damit arbeiten. Die Methoden auf Instanzebene verbessern die API-Funktionalität, die von den Methoden auf Klassenebene eingerichtet wird.
keywords: Eigenschaften erstellen;Eigenschaft erstellen
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: DIL-Methoden auf Instanzebene
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 13%

---

# DIL-Methoden auf Instanzebene{#instance-level-dil-methods}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung des [!DNL Data Integration Library (DIL)] und der [!DNL DIL] eingestellt.
>
>Bestehende Kundinnen und Kunden können ihre [!DNL DIL] Implementierung weiterhin nutzen. Allerdings wird sich Adobe nicht über diesen Punkt hinaus [!DNL DIL] entwickeln. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) auf ihre langfristige Datenerfassungsstrategie hin zu überprüfen.
>
>Kunden, die nach Juli 2023 neue Datenerfassungsintegrationen implementieren möchten, sollten stattdessen [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

Mit den [!UICONTROL DIL]-APIs auf Instanzebene können Sie Audience Manager-Objekte programmgesteuert erstellen und mit ihnen arbeiten. Die Methoden auf Instanzebene verbessern die API-Funktionalität, die von den Methoden auf Klassenebene eingerichtet wird.

## Erste Schritte mit DIL-Methoden auf Instanzebene {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Beim Arbeiten mit [!UICONTROL DIL]-APIs auf Instanzebene:

* Für den Zugriff sind ein Partnername und eine Container-Namespace-ID (NSID) erforderlich. Wenden Sie sich an Ihren Audience Manager Account Manager, um diese Informationen zu erhalten.
* Ersetzen Sie einen *(kursiv*) Beispieltext in der API-Dokumentation durch den Wert, die ID oder eine andere Variable, wie von der Methode benötigt, mit der Sie arbeiten.

<!-- 

c_instance_start.xml

 -->

## Signale {#signals}

Fügt der Abfragezeichenfolge einer ausstehenden Anfrage Zuordnungen auf Kunden- und Plattformebene hinzu.

<!-- 

r_dil_signals.xml

 -->

**Funktionssignatur:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Sie können andere API-Aufrufe an diese Methode verketten.
>* Wenn sich die Adobe Experience Cloud JavaScript-Bibliothek auf der Seite befindet, wartet `submit()`, bis die Cloud ein Cookie setzt, bevor eine Anfrage gesendet wird.

**Reservierte Anforderungsschlüssel**

Die folgenden Anfrageschlüssel sind reserviert und können von dieser Methode nicht überschrieben werden:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `obj` | Objekt | Ein Objekt, das die Schlüssel-Wert-Paare für Zuordnungen auf Plattformebene darstellt. Der Parameter akzeptiert Zeichenfolgen und Arrays als Eigenschaftswerte im -Objekt. |
| `prefix` | Zeichenfolge | Optional. Der Zeichenfolgenwert, der jedem Objektschlüssel vorangestellt ist (ersetzt den Originalschlüssel). |
| `return` | DIL.api | Gibt das API-Objekt der aktuellen DIL-Instanz zurück. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

Fügt SIDs zur Abfragezeichenfolge einer ausstehenden Anfrage hinzu.

<!-- 

r_dil_traits.xml

 -->

**Funktionssignatur:** `traits:function (sids){}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `sids` | Array | Trait-Segment-IDs in einem Array. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] zurück.

**Beispielcode**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## Protokolle {#logs}

Fügen Sie in der ausstehenden Anfrage Daten zu den Protokolldateien hinzu.

<!-- 

r_dil_logs.xml

 -->

**Funktionssignatur:** `logs: function {key1:value1, key2:value2}`

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] zurück.

**Beispielcode**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);
</code></pre>

## submit {#submit}

Übermittelt alle ausstehenden Daten an den Audience Manager für die [!UICONTROL DIL].

<!-- 

r_dil_submit.xml

 -->

**Funktionssignatur:** `submit: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten. Außerdem schreibt [!UICONTROL DIL] kodierte Daten in ein Ziel-Cookie. Leerzeichen werden beispielsweise als `%20` und Semikolons als `%3B` codiert.

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits(&lbrack; 
<i>123,456, 789</i>&rbrack;).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;).submit();
</code></pre>

## afterresult {#afterresult}

Eine Funktion, die nach dem Standardrückruf für die Zielveröffentlichung ausgeführt wird.

<!-- 

r_dil_after_result.xml

 -->

**Funktionssignatur:** `afterResult: function (fn) {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `fn` | Funktion | Die Funktion, die nach der JSON-Veröffentlichung ausgeführt werden soll, wird durch den Standardrückruf verarbeitet, der die Zielveröffentlichung handhabt. |

**Antwort**

Gibt ein API-Objekt der aktuellen [!UICONTROL DIL] zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.signals(&lbrace; 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
&rbrace;).afterResult(function(json)&lbrace; 
     //Do something with the JSON data returned from the server. 
&rbrace;).submit();
</code></pre>

## clearData {#cleardata}

Löscht alle Daten in einer ausstehenden Anfrage.

<!-- 

r_dil_clear_data.xml

 -->

**Funktionssignatur:** `clearData: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs(&lbrace; 
     file: 'dil.js' 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Fügt einer ausstehenden Anfrage benutzerdefinierte Abfrageparameter hinzu, die vom Datenerfassungs-Server nicht explizit definiert sind.

<!-- 

r_dil_custom_query_params.xml

 -->

**Funktionssignatur:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Reservierte Anforderungsschlüssel**

Die folgenden Anfrageschlüssel sind reserviert und können von dieser Methode nicht überschrieben werden:

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
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.customQueryParams(&lbrace; 
     nid: 54231, 
     ntype: 'default' 
&rbrace;); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Gibt den Wert der Container-NSID für die [!UICONTROL DIL]-Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Funktionssignatur:** `dil.api.getContainerNSID: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Gibt chronologisch sortierte Ereignisprotokolldaten als Zeichenfolgen-Array zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_event_log.xml

 -->

**Funktionssignatur:** `dil.api.getEventLog: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) &lbrace; 
     alert(log.join('\n')); 
&rbrace;else&lbrace; 
     alert('No log messages'); 
&rbrace;
</code></pre>

## getPartner {#getpartner}

Gibt den Partnernamen für eine [!UICONTROL DIL] Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_partner.xml

 -->

**Funktionssignatur:** `dil.api.getPartner: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Gibt den Status der aktuellen [!UICONTROL DIL] zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_state.xml

 -->

**Funktionssignatur:** `dil.api.getState: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message:'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = &lbrace; 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:&lbrace; 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: &lbrace; 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          &rbrace;, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     &rbrace;, 
     destinationPublishingInfo: &lbrace; 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          &#x200B;+ containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     &rbrace; 
&rbrace; 
*/
</code></pre>

## idSync {#idsync}

Besteht aus zwei Funktionen, mit denen Datenpartner Benutzer-IDs untereinander und mit dem Audience Manager austauschen und synchronisieren können.

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
   <td colname="col2"> <p>Zwischen verschiedenen Datenpartnern und Audience Managern. Beispielsweise würde Partner X dies verwenden, um eine Benutzer-ID mit Partner Y zu synchronisieren und diese dann an den Audience Manager zu senden. </p> <p> <p><b>Wichtig:</b> Diese Methode ist veraltet. Verwenden Sie die <code> idSyncByURL </code> der Adobe Experience Platform Identity Service-Instanz. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Wenn Sie die Benutzer-ID bereits kennen und an den Audience Manager senden möchten. </p> <p> <p><b>Wichtig:</b> Diese Methode ist veraltet. Verwenden Sie die <code> idSyncByDataSource </code> der Adobe Experience Platform Identity Service-Instanz. </p> </p> </td> 
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

* **`%TIMESTAMP%`:** Erstellt einen Zeitstempel (in Millisekunden). Wird für das Cache-Busting verwendet.
* **`%DID%`:** Fügt die Audience Manager-ID für den Benutzer ein.
* **`%HTTP_PROTO%`:** Legt das Seitenprotokoll fest ( `http` oder `https`).

**Antwort**

Beide Funktionen geben bei Erfolg `Successfully queued` zurück. Falls nicht, wird eine Fehlermeldungszeichenfolge zurückgegeben.

**Beispielcode**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync(&lbrace; 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync(&lbrace; 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

## Ergebnis {#result}

Fügt der ausstehenden Anfrage einen Callback (der JSON erhält) hinzu.

<!-- 

r_dil_result.xml

 -->

**Funktionssignatur:** `result: function (callback) {}`

Dieser Rückruf ersetzt den standardmäßigen Rückruf, der die Zielveröffentlichung handhabt.

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `callback` | Funktion | Vom JSONP-Callback ausgeführte JavaScript-Funktion. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json)&lbrace; 
     //Do something, possibly with the JSON data returned from the server. 
&rbrace;);.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` ist ein boolescher Parameter, der steuert, wie [!UICONTROL DIL] Aufrufe an die [!UICONTROL Data Collection Servers (DCS)] und Akamai sendet.

<!-- 

dil-secure-data-collection.xml

 -->

* Wenn `secureDataCollection= true` (Standard), führt [!UICONTROL DIL] immer sichere HTTPS-Aufrufe durch.

* Bei der `secureDataCollection= false` führt [!UICONTROL DIL] entweder HTTP- oder HTTPS-Aufrufe durch, indem das von der Seite festgelegte Sicherheitsprotokoll befolgt wird.

>[!IMPORTANT]
>
>Legen Sie `secureDataCollection= false` fest, wenn Sie visitorAPI.js und [!UICONTROL DIL] auf derselben Seite verwenden. Siehe Code-Beispiel unten.

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     secureDataCollection: false 
&rbrace;);
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` ist ein boolescher „true/false“-Parameter, der steuert, wie der Browser Ressourcen von anderen Domains anfordert.

<!-- 

dil-use-cors-only.xml

 -->

**Überblick**

`useCORSOnly` ist standardmäßig false. „False“ bedeutet, dass der Browser Ressourcenprüfungen mit CORS oder JSONP durchführen kann. [!UICONTROL DIL] versucht jedoch immer zuerst, Ressourcen mit CORS anzufordern. Bei älteren Browsern, die CORS nicht unterstützen, wird auf JSONP zurückgegriffen. Wenn Sie den Browser zwingen müssen, nur CORS zu verwenden, wie etwa bei Sites mit hohen Sicherheitsanforderungen, legen Sie `useCORSOnly:true` fest.

**Codebeispiel**

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     useCORSOnly: true 
&rbrace;);
</code></pre>

>[!IMPORTANT]
>
>* Es wird empfohlen, `useCORSOnly: true` nur dann festzulegen, wenn Sie sicher sind, dass Ihre Site-Besucher Browser haben, die diese Funktion unterstützen.
>* Wenn `useCORSOnly: true`, führt [!UICONTROL DIL] keine ID-Aufrufe von Internet Explorer ab Version 9 durch.
>

## useImageRequest {#useimagerequest}

Ändert den Anfragetyp von Skript-`<src>` in `<img>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Funktionssignatur:** `useImageRequest: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Antwort**

Gibt ein API-Objekt der aktuellen [!UICONTROL DIL] zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Anforderungen an Namen für Schlüsselvariablen](../features/traits/trait-key-name-requirements.md)
>* [Anforderungen an Präfixe für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)
>* [Synchronisierungsfunktionen im Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [Erstellen einer DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform Identity Service: useCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [CORS-Unterstützung im Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)

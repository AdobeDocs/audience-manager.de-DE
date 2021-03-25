---
description: Mit DIL-APIs auf Instanzebene können Sie Audience Manager-Objekte programmgesteuert erstellen und verwenden. Die Methoden auf Instanzebene erweitern die API-Funktionalität, die durch Methoden auf Klassenebene festgelegt wird.
keywords: Eigenschaften erstellen;Eigenschaften erstellen
seo-description: Mit DIL-APIs auf Instanzebene können Sie Audience Manager-Objekte programmgesteuert erstellen und verwenden. Die Methoden auf Instanzebene erweitern die API-Funktionalität, die durch Methoden auf Klassenebene festgelegt wird.
seo-title: DIL-Methoden auf Instanzebene
solution: Audience Manager
title: DIL-Methoden auf Instanzebene
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL-Implementierung
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 15%

---


# DIL-Methoden auf Instanzebene{#instance-level-dil-methods}

Mit den APIs auf Instanzebene [!UICONTROL DIL] können Sie Audience Manager-Objekte programmgesteuert erstellen und bearbeiten. Die Methoden auf Instanzebene erweitern die API-Funktionalität, die durch Methoden auf Klassenebene festgelegt wird.

## Erste Schritte mit DIL-Methoden auf Instanzebene {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Beim Arbeiten mit den APIs auf Instanzebene [!UICONTROL DIL]:

* Für den Zugriff sind ein Partnername und eine Container-Namensraum-ID (NSID) erforderlich. Wenden Sie sich an Ihren Kundenbetreuer, um diese Informationen zu erhalten.
* Ersetzen Sie jeden Beispieltext *kursiv* in der API-Dokumentation durch Wert, ID oder andere Variable, die von der Methode, mit der Sie arbeiten, benötigt werden.

<!-- 

c_instance_start.xml

 -->

## signale {#signals}

Fügt der Zeichenfolge einer ausstehenden Anforderung eine Zuordnung auf Kunden- und Plattformebene hinzu.

<!-- 

r_dil_signals.xml

 -->

**Funktionssignatur:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Sie können andere API-Aufrufe mit dieser Methode verketten.
>* Wenn sich die Adobe Experience Cloud JavaScript-Bibliothek auf der Seite befindet, wartet `submit()` darauf, dass die Cloud ein Cookie setzt, bevor eine Anforderung gesendet wird.


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

Gibt das API-Objekt der aktuellen [!UICONTROL DIL]-Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
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

Fügt der Abfrage-Zeichenfolge einer ausstehenden Anforderung SIDs hinzu.

<!-- 

r_dil_traits.xml

 -->

**Funktionsunterschrift:** `traits:function (sids){}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `sids` | Array | Eigenschaftensegment-IDs in einem Array. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL]-Instanz zurück.

**Beispielcode**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

hinzufügen Daten, um Dateien in der ausstehenden Anforderung zu protokollieren.

<!-- 

r_dil_logs.xml

 -->

**Funktionsunterschrift:** `logs: function {key1:value1, key2:value2}`

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL]-Instanz zurück.

**Beispielcode**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## submit {#submit}

Sendet alle ausstehenden Daten an Audience Manager für die Instanz [!UICONTROL DIL].

<!-- 

r_dil_submit.xml

 -->

**Funktionssignatur:** `submit: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten. Außerdem schreibt [!UICONTROL DIL] kodierte Daten in ein Ziel-Cookie. Leerzeichen werden beispielsweise als `%20` und Semikolons als `%3B` kodiert.

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL]-Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
</code></pre>

## afterResult {#afterresult}

Eine Funktion, die nach dem Rückruf beim Veröffentlichen des Standardziels ausgeführt wird.

<!-- 

r_dil_after_result.xml

 -->

**Funktionssignatur:** `afterResult: function (fn) {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `fn` | Funktion | Die Funktion, die nach der Verarbeitung von JSON ausgeführt werden soll, wird durch den standardmäßigen Rückruf verarbeitet, der die Zielveröffentlichung verarbeitet. |

**Antwort**

Gibt ein API-Objekt der aktuellen [!UICONTROL DIL]-Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
</code></pre>

## clearData {#cleardata}

Löscht alle Daten in einer ausstehenden Anforderung.

<!-- 

r_dil_clear_data.xml

 -->

**Funktionssignatur:** `clearData: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL]-Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Fügt einer ausstehenden Anforderung benutzerdefinierte Abfragen hinzu, die nicht explizit vom Datenerfassungsserver definiert wurden.

<!-- 

r_dil_custom_query_params.xml

 -->

**Funktionssignatur:** `customQueryParams: function (obj) {}`

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
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Gibt den Wert der NSID des Containers für die [!UICONTROL DIL]-Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Funktionssignatur:** `dil.api.getContainerNSID: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Gibt chronologisch sortierte Ereignis-Protokolldaten als Zeichenfolgen-Array zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_event_log.xml

 -->

**Funktionssignatur:** `dil.api.getEventLog: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

Gibt den Partnernamen für eine [!UICONTROL DIL]-Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_partner.xml

 -->

**Funktionssignatur:** `dil.api.getPartner: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Gibt den Status der aktuellen [!UICONTROL DIL]-Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_state.xml

 -->

**Funktionssignatur:** `dil.api.getState: function () {}`

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

Besteht aus zwei Funktionen, mit denen Datenpartner Benutzer-IDs untereinander und mit Audience Manager austauschen und synchronisieren können.

<!-- 

r_dil_idsync.xml

 -->

**Funktionssignatur:**

Funktioniert mit den Versionen 2.10 und 3.1 oder höher.[!UICONTROL DIL]

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
   <td colname="col2"> <p>Zwischen verschiedenen Datenpartnern und Audience Manager. Partner x würde dies beispielsweise verwenden, um eine Benutzer-ID mit Partner y zu synchronisieren und diese dann an Audience Manager zu senden. </p> <p> <p><b>Wichtig: </b>  Diese Methode wird nicht mehr unterstützt. Bitte verwenden Sie die <code> idSyncByURL </code>-Methode der Adobe Experience Platform Identity Service-Instanz. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Wenn Sie die Benutzer-ID bereits kennen und sie an Audience Manager senden möchten. </p> <p> <p><b>Wichtig: </b>  Diese Methode wird nicht mehr unterstützt. Bitte verwenden Sie die <code> idSyncByDataSource </code>-Methode der Adobe Experience Platform Identity Service-Instanz. </p> </p> </td> 
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
* **`%HTTP_PROTO%`:** Legt das Seitenprotokoll fest (  `http` oder  `https`).

**Antwort**

Beide Funktionen geben bei erfolgreichem Abschluss `Successfully queued` zurück. Falls nicht, wird eine Fehlermeldungszeichenfolge zurückgegeben.

**Beispielcode**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

## result {#result}

Fügt der ausstehenden Anforderung einen Rückruf (der JSON erhält) hinzu.

<!-- 

r_dil_result.xml

 -->

**Funktionssignatur:** `result: function (callback) {}`

Dieser Rückruf ersetzt den Standard-Rückruf, der die Zielveröffentlichung behandelt.

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `callback` | Funktion | JavaScript-Funktion, die vom JSONP-Rückruf ausgeführt wird. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL]-Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` ist ein boolescher Parameter, der steuert, wie  [!UICONTROL DIL] Aufrufe an Akamai  [!UICONTROL Data Collection Servers (DCS)] und Akamai ausgeführt werden.

<!-- 

dil-secure-data-collection.xml

 -->

* Wenn `secureDataCollection= true` (Standard), [!UICONTROL DIL] immer sichere HTTPS-Aufrufe durchführt.

* Wenn `secureDataCollection= false` [!UICONTROL DIL] HTTP- oder HTTPS-Aufrufe nach dem von der Seite festgelegten Sicherheitsprotokoll durchführt.

>[!IMPORTANT]
>
>Legen Sie `secureDataCollection= false` fest, wenn Sie visitorAPI.js und [!UICONTROL DIL] auf derselben Seite verwenden. Siehe Codebeispiel unten.

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` ist ein boolescher true/false-Parameter, der steuert, wie der Browser Ressourcen von anderen Domänen anfordert.

<!-- 

dil-use-cors-only.xml

 -->

**Überblick**

`useCORSOnly` ist standardmäßig false. False bedeutet, dass der Browser Ressourcenprüfungen mit CORS oder JSONP durchführen kann. [!UICONTROL DIL] versucht jedoch immer, Ressourcen zuerst mit CORS anzufordern. Bei älteren Browsern, die CORS nicht unterstützen, wird auf JSONP zurückgegriffen. Wenn Sie den Browser zwingen müssen, nur CORS zu verwenden, z. B. bei Sites mit hohen Sicherheitsanforderungen, setzen Sie `useCORSOnly:true`.

**Code-Beispiel**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* Es wird empfohlen, `useCORSOnly: true` nur dann einzustellen, wenn Sie sicher sind, dass Ihre Site-Besucher Browser haben, die diese Funktion unterstützen.
>* Wenn `useCORSOnly: true` [!UICONTROL DIL] keine ID-Aufrufe von Internet Explorer Version 9 oder älter ausführt.

>



## useImageRequest {#useimagerequest}

Ändert den Anforderungstyp in image `<img>` von script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Funktionssignatur:** `useImageRequest: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe mit dieser Methode verketten.

**Antwort**

Gibt ein API-Objekt der aktuellen [!UICONTROL DIL]-Instanz zurück.

**Beispielcode**

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Anforderungen an Namen für Schlüsselvariablen](../features/traits/trait-key-name-requirements.md)
>* [Anforderungen an Präfixe für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)
>* [Synchronisierungsfunktionen im Adobe Experience Platform-Identitätsdienst](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/idsync.html)
>* [Erstellen einer DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform-Identitätsdienst: UseCORSOnly](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [CORS-Unterstützung im Adobe Experience Platform-Identitätsdienst](https://docs.adobe.com/content/help/en/id-service/using/reference/cors.html)


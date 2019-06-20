---
description: Mit DIL-apis auf Instanzebene können Sie Audience Manager-Objekte programmatisch erstellen und bearbeiten. Die Methoden auf Instanzebene verbessern die API-Funktionalität, die von den Methoden auf Klassenebene bestimmt wird.
keywords: Eigenschaften erstellen; Eigenschaft erstellen
seo-description: Mit DIL-apis auf Instanzebene können Sie Audience Manager-Objekte programmatisch erstellen und bearbeiten. Die Methoden auf Instanzebene verbessern die API-Funktionalität, die von den Methoden auf Klassenebene bestimmt wird.
seo-title: DIL-Methoden auf Instanzebene
solution: Audience Manager
title: DIL-Methoden auf Instanzebene
uuid: aa 5147 bb -51 d 5-41 d 4-a 78 a-e 550 f 7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL-Methoden auf Instanzebene{#instance-level-dil-methods}

Mit apis auf Instanzebene [!UICONTROL DIL] können Sie Audience Manager-Objekte programmatisch erstellen und bearbeiten. Die Methoden auf Instanzebene verbessern die API-Funktionalität, die von den Methoden auf Klassenebene bestimmt wird.

## Erste Schritte mit DIL-Methoden auf Instanzebene {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Bei Verwendung der [!UICONTROL DIL] apis auf Instanzebene:

* Zugriff erfordert einen Partner- und Container-Namespace-ID (NSID). Wenden Sie sich an Ihren Audience Manager-Kundenbetreuer, um diese Informationen abzurufen.
* Ersetzen Sie beliebige *kursiv gedruckte* Texte in der API-Dokumentation durch den Wert, die ID oder andere Variable, die für die verwendete Methode erforderlich sind.

<!-- 

c_instance_start.xml

 -->

## signalisiert {#signals}

Fügt der Abfragezeichenfolge einer ausstehenden Anforderung Kunden- und Plattformzuordnungen hinzu.

<!-- 

r_dil_signals.xml

 -->

**Funktionssignatur:**`signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Sie können andere API-Aufrufe an diese Methode verketten.
>* Wenn sich die Adobe Experience Cloud-javascript-Bibliothek auf der Seite befindet, `submit()` wartet die Cloud, um ein Cookie festzulegen, bevor eine Anforderung gesendet wird.


**Reservierte Anforderungsschlüssel**

Die folgenden Anforderungs-Schlüssel sind reserviert und können von dieser Methode nicht überschrieben werden:

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
| `prefix` | Zeichenfolge | Optional. Der Zeichenfolgenwert für die einzelnen Objektschlüssel (ersetzt den ursprünglichen Schlüssel). |
| `return` | DIL. api | Gibt das API-Objekt der aktuellen DIL-Instanz zurück. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>' 
 Containernsid: <i>Containernsid</i> }); 
 
// Method 1 
var obj = {key 1: 1, Schlüssel 2: 2}; 
Datalib. api. sign(obj,' c_'). submit (); 
 
// Method 2 
datalib. api. sign({c_ zdid: 44321}). submit (); 
 
// Methode 3 
// sendet'c_ key = a &amp; c_ key = 2 &amp; c_ key = 3 ' in Audience manager 
var obj = {key: [' a ',' b ',' c ']}; 
Datalib. api. sign(obj,' c_'). submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Namensanforderungen für Schlüsselvariablen](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

Fügt der Abfragezeichenfolge einer ausstehenden Anforderung sids hinzu.

<!-- 

r_dil_traits.xml

 -->

**Funktionssignatur:**`traits:function (sids){}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `sids` | Array | Eigenschaftssegment-IDs in einem Array. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>var partnerobject = DIL. create ({ 
 Partner: '<i>Name des Partners</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. properties (<i>[123, 456, 789]</i>);</code>
</pre>

## Protokolle {#logs}

Fügen Sie Daten zu Protokolldateien in der ausstehenden Anforderung hinzu.

<!-- 

r_dil_logs.xml

 -->

**Funktionssignatur:**`logs: function {key1:value1, key2:value2}`

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>var partnerobject = DIL. create ({ 
 Partner: '<i>partner</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. logs ({ 
 Datei: ' dil. js ', 
 message: ' Dies ist die erste Anforderung '});</code>
</pre>

## submit {#submit}

Sendet alle ausstehenden Daten an Audience Manager für die [!UICONTROL DIL] Instanz.

<!-- 

r_dil_submit.xml

 -->

**Funktionssignatur:**`submit: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten. [!UICONTROL DIL] Schreibt außerdem kodierte Daten in ein Zielcookie. Beispielsweise werden Leerzeichen als `%20` und Semikolons kodiert `%3B`.

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. properties ([<i>123.456, 
789</i>]). logs ({ 
 Datei: ' dil. js ', 
 message: Dies ist die erste Anforderung}}). 
sign({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}). 
submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Präfix für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)


## Afterresult {#afterresult}

Eine Funktion, die nach dem Rückruf für die Standardzielveröffentlichung ausgeführt wird.

<!-- 

r_dil_after_result.xml

 -->

**Funktionssignatur:**`afterResult: function (fn) {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `fn` | Funktion | Die Funktion, die Sie ausführen möchten, nachdem JSON ausgeführt wurde, wird vom Standardrückruf verarbeitet, der die Zielveröffentlichung verarbeitet. |

**Antwort**

Gibt ein API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. signs ({ 
 c_ zdid: <i>54321</i> 
 d_ dma: '<i>default</i>'}). 
afterresult (function (json) { 
 //Do Sie etwas mit den JSON-Daten, die vom Server zurückgegeben werden. 
}).submit();
</code></pre>

## Cleardata {#cleardata}

Löscht alle Daten in einer ausstehenden Anforderung.

<!-- 

r_dil_clear_data.xml

 -->

**Funktionssignatur:**`clearData: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. properties ([<i>123.456, 789</i>]). logs ({ 
 Datei: ' dil. js ' 
 message: Dies ist die erste Anforderung}}). 
sign({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); 
 
//Reset the ausstehende data 
datalib. cleardata ();</code>
</pre>

## Customqueryparams {#customqueryparams}

Fügt benutzerdefinierte Abfrageparameter hinzu, die nicht explizit vom Datenerfassungsserver einer ausstehenden Anforderung definiert werden.

<!-- 

r_dil_custom_query_params.xml

 -->

**Funktionssignatur:**`customQueryParams: function (obj) {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Reservierte Anforderungsschlüssel**

Die folgenden Anforderungs-Schlüssel sind reserviert und können von dieser Methode nicht überschrieben werden:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Antwort**

Gibt das API-Objekt der aktuellen DIL-Instanz zurück.

**Beispielcode**

<pre><code>var partnerobject = DIL. create ({ 
 Partner: '<i>partner</i>', 
 Containernsid: <i>NSID</i> }); 
Partnerobject. api. customqueryparams ({ 
 nid: 54231, 
 ntype: ' default '});</code>
</pre>

## Getcontainernsid {#getcontainernsid}

Gibt den Wert der Containernsid für die [!UICONTROL DIL] Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Funktionssignatur:**`dil.api.getContainerNSID: function () {}`

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
//Verify the container NSID 
var nsid = datalib. api. getcontainernsid ();</code>
</pre>

## Geteventlog {#geteventlog}

Gibt chronologisch sortierte Ereignisprotokolldaten als Array von Zeichenfolgen zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_event_log.xml

 -->

**Funktionssignatur:**`dil.api.getEventLog: function () {}`

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. properties ([<i>123, 456, 789</i>]). logs ({ 
 Datei: ' dil. js ', 
 message: ' Dies ist die erste Anforderung '}); . sign ({ 
 c_ zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); . submit (); 
 
//Check log for messages 
var log = datalib. api. geteventlog (); 
if (log &amp; &amp; log. length) { 
 alert (log. join ('\ n ')); 
} else { 
 alert (' No log messages '); 
}</code>
</pre>

## Getpartner {#getpartner}

Gibt den Namen des Partners für eine [!UICONTROL DIL] Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_partner.xml

 -->

**Funktionssignatur:**`dil.api.getPartner: function () {}`

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>' 
 Containernsid: <i>Containernsid</i> }); 
 
//Verify the partner name 
var partner = datalib. api. getpartner ();</code>
</pre>

## Getstate {#getstate}

Gibt den Status der aktuellen [!UICONTROL DIL] Instanz zurück. Nützlich für Debugging und Fehlerbehebung.

<!-- 

r_dil_get_state.xml

 -->

**Funktionssignatur:**`dil.api.getState: function () {}`

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. properties ([<i>123, 456, 789</i>]). logs ({ 
 Datei: ' dil. js ', 
 message: ' Dies ist die erste Anforderung '}); . sign ({ 
 c. zdid: <i>1111</i> 
 d_ dma: '<i>default</i>'}); . submit (); 
 
var state = datalib. api. getstate (); 
 
/* Objektgliederung von Bundesstaat 
= {{ 
 Pendingrequest: {<i>ausstehende Daten für den Aufruf an server</i>}, 
 Otherrequestinfo: { 
 Firingqueue: [], 
 ausgelöst: [], 
 Auslösen: false, 
 errored: [], 
 Reservedkeys: { 
 Sids: true, 
 pdata: true, 
 logdata: true, 
 callback: true, 
 Postcallbackfn: true, 
 Useideparequest: true, 
 }, 
 Firstrequesthasausgelöst: false, 
 num_ of_ jsonp_ responses: 0, 
 num_ of_ jsonp_ errors: 0, 
 num_ of_ img_ responses: 0, 
 num_ of_ img_ errors: 0 
 }, 
 Destinationpublishinginfo: { 
 THROTTLE_ START: 3000, 
 Throttletimerset: false, 
 id: " destination_ publishing_ iframe_' + partner +'_' + containernsid, 
 url: (Konstanten. ishttps? ' https://': ' https://fast.') + partner +' .demdex.net/dest3.html?d_nsid=' 
 + Containernsid +' #' + encodeuricomponent (document. location. href), 
 iframe: null, 
 Iframehasloaded: false, 
 Sendingmessages: false, 
 Nachrichten: [], 
 Messagesendinginterval: konstanten. POST_ MESSAGE_ ENABLED? 15: 100, 
 //Recommend 100 ms für IE 6 &amp; 7, 15 ms für andere Browser 
 Jsonprocessed: [] 
 }} 
*/</code>
</pre>

## Idsync {#idsync}

Besteht aus zwei Funktionen, mit denen Datenpartner Benutzer-IDs zwischen sich selbst und Audience Manager austauschen und synchronisieren können.

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
   <td colname="col1"> <code> dil. Instance. api. idsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Zwischen verschiedenen Datenpartnern und Audience Manager. Beispiel: Partner X verwendet dies zur Synchronisierung einer Benutzer-ID mit Partner Y und sendet diese dann an Audience Manager. </p> <p> <p><b>Wichtig:</b> Diese Methode wird nicht mehr unterstützt. Bitte verwenden Sie die <code> idsyncbyurl </code> -Methode der Experience Cloud ID-Dienstinstanz. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. aamidsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Wenn Sie die Benutzer-ID bereits kennen und sie an Audience Manager senden möchten. </p> <p> <p><b>Wichtig:</b> Diese Methode wird nicht mehr unterstützt. Bitte verwenden Sie die <code> idsyncbydatasource </code> -Methode der Experience Cloud ID-Dienstinstanz. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Idsync Elements**

`idSync` kann aus Folgendem bestehen:

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
* **`%HTTP_PROTO%`:** Legt das Seitenprotokoll ( `http` oder `https`) fest.

**Antwort**

Beide Funktionen kehren bei `Successfully queued` Erfolg zurück. Falls nicht, wird eine Fehlermeldungszeichenfolge zurückgegeben.

**Beispielcode**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">// URL Fires with macros replaced 
dilinstance. api. idsync ({ 
 dpid: ' 23 ', // muss eine Zeichenfolge sein 
 url: '//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
% 2 Fibs % 3 Adpid % 3 D 420% 26 dpuuid % 3 D % 7 B % 7 Buid % 7 D % 7 D ', 
 Minutestolive: 20160 // optional, Standard auf 20160 Minuten (14 Tage)});</code>
</pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">// Fires ' https:/https:' +'//dpm.demdex.net/ibs:dpid= &lt; dpid &gt; &amp; dpuuid = &lt; dpuuid &gt;' 
dilinstance. api. aamidsync ({ 
 dpid: ' 23 ', // muss eine Zeichenfolge sein 
 dpuuid: ' 98765 ', // muss eine Zeichenfolge sein 
 Minutestolive: 20160 // optional, Standard auf 20160 Minuten (14 Tage)});</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Synchronisierungsfunktionen im Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## Ergebnis {#result}

Fügt der ausstehenden Anforderung einen Rückruf (der JSON erhält) hinzu.

<!-- 

r_dil_result.xml

 -->

**Funktionssignatur:**`result: function (callback) {}`

Dieser Rückruf ersetzt den Standardrückruf, der die Zielveröffentlichung verarbeitet.

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `callback` | Funktion | Javascript-Funktion, die vom JSONP-Rückruf ausgeführt wird. |

**Antwort**

Gibt das API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. properties ([<i>123, 456, 789</i>]). result (function (json) { 
 //Do Sie etwas, möglicherweise mit den JSON-Daten, die vom Server zurückgegeben werden. 
});.submit();
</code></pre>

## Securedatacollection {#securedatacollection}

`secureDataCollection` ein boolescher Parameter, der steuert, wie [!UICONTROL DIL] Aufrufe an [!UICONTROL Data Collection Servers (DCS)] und Akamai gesendet werden.

<!-- 

dil-secure-data-collection.xml

 -->

* Wenn `secureDataCollection= true` (Standard), werden sichere HTTPS-Aufrufe [!UICONTROL DIL] immer ausgeführt.

* Wenn `secureDataCollection= false`Sie [!UICONTROL DIL] HTTP- oder HTTPS-Aufrufe befolgen, indem Sie das von der Seite festgelegte Sicherheitsprotokoll befolgen.

>[!IMPORTANT]
>
>Legen Sie fest `secureDataCollection= false` , ob Sie visitorapi. js und [!UICONTROL DIL] auf derselben Seite verwenden. Siehe Codebeispiel unten.

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Securedatacollection: false});</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [DIL create](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` ist ein boolescher true/false-Parameter, der steuert, wie der Browser Ressourcen aus anderen Domänen anfordert.

<!-- 

dil-use-cors-only.xml

 -->

**Übersicht**

`useCORSOnly` ist standardmäßig falsch. False bedeutet, dass der Browser Ressourcenprüfungen mit CORS oder JSONP durchführen kann. Versucht [!UICONTROL DIL] jedoch immer, zunächst Ressourcen mit CORS anzufordern. Bei älteren Browsern, die CORS nicht unterstützen, wird auf JSONP zurückgegriffen. Wenn Sie erzwingen müssen, dass der Browser nur CORS verwendet, z. B. mit Sites mit hohen Sicherheitsanforderungen, legen `useCORSOnly:true`Sie fest.

**Codebeispiel**

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Usecorsonly: true});</code>
</pre>

>[!IMPORTANT]
>
>* Wir empfehlen Ihnen, nur festzulegen `useCORSOnly: true` , wenn die Besucher Ihrer Site über Browser verfügen, die diese Funktion unterstützen.
>* Wenn `useCORSOnly: true`[!UICONTROL DIL] keine ID-Aufrufe aus Internet Explorer Version 9 oder älter erfolgen.
>



>[!MORE_ LIKE_ THIS]
>
>* [DIL create](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID-Dienst: Usecorsonly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [CORS-Unterstützung im Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## Useideparequest {#useimagerequest}

Ändert den Anforderungstyp `<img>` aus dem Skript `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Funktionssignatur:**`useImageRequest: function () {}`

>[!NOTE]
>
>Sie können andere API-Aufrufe an diese Methode verketten.

**Antwort**

Gibt ein API-Objekt der aktuellen [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername</i>', 
 Containernsid: <i>Containernsid</i> }); 
 
Datalib. api. properties ([<i>123, 456, 789</i>]). useideparequest (). submit ();</code>
</pre>


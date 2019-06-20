---
description: Beschreibt Methoden im Namespace DIL. tool. Diese Dienstprogrammfunktionen helfen Ihnen bei der Durchführung bestimmter Aufgaben.
seo-description: Beschreibt Methoden im Namespace DIL. tool. Diese Dienstprogrammfunktionen helfen Ihnen bei der Durchführung bestimmter Aufgaben.
seo-title: DIL-Werkzeuge
solution: Audience Manager
title: DIL-Werkzeuge
uuid: 2 bc 62 ce 2-16 bd -4 e 80-b 493-c 816 ba 643 b 59
translation-type: tm+mt
source-git-commit: ac9e4f24a896ecae2ebf36dcf34a4ac8fab00cd8

---


# DIL-Werkzeuge

Beschreibt Methoden im `DIL.tools` Namespace. Diese Dienstprogrammfunktionen helfen Ihnen bei der Durchführung bestimmter Aufgaben.

<!-- 

c_dil_functions.xml

 -->

## Getsearchreferrer

Gibt Suchbegriffe zurück, die zum Erreichen der aktuellen Seite verwendet werden.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Zweck von `getSearchReferrer`

Gibt in DIL Suchergebnisse (Namen und Schlüsselwörter) `getSearchReferrer` zurück, die zum Erreichen Ihrer Site verwendet werden. Sie können spezifische Suchbegriffe an diese Funktion weitergeben oder die unterstützten Suchmaschinen ( [!DNL AOL][!DNL Ask][!DNL Bing], [!DNL Google]und [!DNL Yahoo]) `document.referrer` standardmäßig durchsuchen.

### Funktionssignatur

Funktionssignatur: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Funktionsparameter

`getSearchReferrer` akzeptiert:

* *`{string}`*: *(Optional)* Eine Zeichenfolge, die die Suchurl enthält (verwendet `document.referrer` wenn nicht definiert).
* *`{object}`*: *(Optional)* Ein Objekt, das die Konfiguration für die `hostPattern``queryParam`, `queryPattern`oder.

Und gibt Folgendes zurück:

* `{object}` Ein Objekt, das gültige Namen und Suchbegriffe enthält.

### Beispiele

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Suchtyp </th> 
   <th> Beschreibung </th> 
   <th> Codebeispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Standardsuche</td> 
   <td> Gibt Suchbegriffe zurück, die von den Suchmaschinen AOL, Ask, Bing, Google und Yahoo verwendet werden. </td> 
   <td>
      <code>var &amp; amp; nbsp; results &amp; amp; nbsp; = &amp; amp; nbsp; DIL. tools. getsearchreferrer ();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Benutzerdefinierte URL übermitteln</td> 
   <td>Gibt den Suchverweis basierend auf einer benutzerdefinierten URL zurück.</td> 
   <td> 
  <code>
        var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Match URL Hostname with a Custom Regex</b></td> 
   <td> Übermitteln Sie einen benutzerdefinierten Regex an den Hostnamen der verweisenden URL. </td> 
   <td> 
  <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/
    search.aspx?q=adobe+rules",{ 
       hostPattern:/ehow\./, 
         queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Suchmuster mit einem benutzerspezifischen Regex abgleichen</b> </td> 
   <td> Übergeben Sie einen benutzerdefinierten Regex, um eine benutzerdefinierte Suche durchzuführen. </td> 
   <td> 
    <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
    {
       hostPattern:/ehow\./, 
           search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## Decomposeuri

Entpackt einen einheitlichen Ressourcenbezeichner ( [!DNL URI]) in seine Komponenten: `hash``host``href``pathname``protocol`, `search`und `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Funktionssignatur: `DIL.tools.decomposeURI`

### Funktionsparameter

`decomposeURI` akzeptiert:

* *`uri {string}`*: *(Optional)* Eine Zeichenfolge, die den URI enthält. Wird standardmäßig `document.location.href` nicht angegeben.

Und gibt Folgendes zurück:

* *`{object}`*: Ein Objekt, das gültige Namen und Suchbegriffe enthält.

### Beispielcode


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## Getmetatags

Sucht nach spezifischen Inhalten, die in den Meta-Tags auf einer Webseite definiert sind, und gibt diese Daten in einem Objekt zurück.

<!-- 

r_dil_get_metatags.xml

 -->

### Funktionssignatur

Funktionssignatur: `DIL.tools.getMetaTags( 1 or more parameters)`

### Funktionsparameter

`getMetaTags` akzeptiert einen oder mehrere Namensparameter (Zeichenfolgentyp), nach denen gesucht werden soll. Gibt ein Objekt zurück, das aus Schlüssel/Wert-Paaren besteht.

### Beispielcode

<pre class="&ldquo;javascript&rdquo;"><code>var datalib = DIL. create ({ 
 Partner: '<i>Partnername '</i>, 
 Containernsid: <i>Containernsid</i> }); 
Datalib. api. signals (DIL. tools. getmetatags ('<i>anwendung</i>','<i>keywords</i>','<i>description</i>'),' c_'). submit ();</code>
</pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 
dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>

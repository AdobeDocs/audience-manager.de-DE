---
description: Beschreibt Methoden im Namensraum DIL.tools. Mit diesen Dienstprogrammfunktionen können Sie bestimmte Aufgaben ausführen.
seo-description: Beschreibt Methoden im Namensraum DIL.tools. Mit diesen Dienstprogrammfunktionen können Sie bestimmte Aufgaben ausführen.
seo-title: DIL-Tools
solution: Audience Manager
title: DIL-Tools
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 5%

---


# DIL-Tools

Beschreibt Methoden im `DIL.tools` Namensraum. Mit diesen Dienstprogrammfunktionen können Sie bestimmte Aufgaben ausführen.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Gibt Suchbegriffe zurück, die zum Erreichen der aktuellen Seite verwendet werden.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Zweck `getSearchReferrer`

In DIL gibt `getSearchReferrer` die Suchergebnisse (Namen und Schlüsselwörter) zurück, die zum Erreichen Ihrer Site verwendet wurden. Sie können bestimmte Suchbegriffe an diese Funktion übergeben oder die unterstützten Suchmaschinen ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google]und [!DNL Yahoo]) `document.referrer` standardmäßig suchen lassen.

### Funktionsunterschrift

Funktionsunterschrift: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Funktionsparameter

`getSearchReferrer` akzeptiert:

* *`{string}`*: *(Optional)* Eine Zeichenfolge, die die Such-URL enthält (wird verwendet, `document.referrer` wenn sie nicht definiert ist).
* *`{object}`*: *(Optional)* Ein Objekt, das die Konfiguration für die `hostPattern`, `queryParam`oder `queryPattern`.

Und gibt zurück:

* `{object}` Ein Objekt, das gültige Namen und Suchbegriffe enthält.

### Beispiele

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Suchtyp </th> 
   <th> Beschreibung </th> 
   <th> Code-Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Standardsuche</td> 
   <td> Gibt Suchbegriffe zurück, die von den Suchmaschinen AOL, Ask, Bing, Google und Yahoo verwendet werden. </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Übergeben einer benutzerspezifischen URL</td> 
   <td>Gibt den Werber für die Suche basierend auf einer benutzerdefinierten URL zurück.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>URL-Hostnamen mit benutzerdefiniertem Regex abgleichen</b></td> 
   <td> Geben Sie einen benutzerdefinierten Regex ein, um dem Hostnamen der verweisenden URL zu entsprechen. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Suchmuster mit einem benutzerspezifischen Regex abgleichen</b> </td> 
   <td> Übergeben Sie einen benutzerdefinierten Regex, um eine benutzerdefinierte Suche durchzuführen. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decompseURI

Demonstriert eine Uniform Resource Identifier ( [!DNL URI]) in ihre Komponenten: `hash`, `host`, `href`, `pathname`, `protocol`, `search`und `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Funktionsunterschrift: `DIL.tools.decomposeURI`

### Funktionsparameter

`decomposeURI` akzeptiert:

* *`uri {string}`*: *(Optional)* Eine Zeichenfolge, die den URI enthält. Defaults to `document.location.href` if not specified.

Und gibt zurück:

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

## getMetaTags

Sucht nach bestimmten Inhalten, die in den Meta-Tags auf einer Webseite definiert sind, und gibt diese Daten in einem Objekt zurück.

<!-- 

r_dil_get_metatags.xml

 -->

### Funktionsunterschrift

Funktionsunterschrift: `DIL.tools.getMetaTags( 1 or more parameters)`

### Funktionsparameter

`getMetaTags` akzeptiert einen oder mehrere Namensparameter (Zeichenfolgen-Typ), nach denen gesucht werden soll. Gibt ein Objekt zurück, das aus Schlüssel-Wert-Paaren besteht.

### Beispielcode

```js
var dataLib = DIL.create({ 
     partner: 'partnerName', 
     containerNSID: containerNSID 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('application', 'keywords',  'description'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: `partnerName', 
     containerNSID: containerNSID 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('application','keywords', 'description'), 'c_').submit();
```

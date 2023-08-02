---
description: Beschreibt Methoden im DIL.tools-Namespace. Mithilfe dieser Dienstprogrammfunktionen können Sie bestimmte Aufgaben ausführen.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL-Tools
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 3%

---

# DIL-Tools

>[!WARNING]
>
>Ab Juli 2023 hat die Adobe die Entwicklung der [!DNL Data Integration Library (DIL)] und [!DNL DIL] -Erweiterung.
>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] Implementierung. Die Adobe wird sich jedoch nicht entwickeln [!DNL DIL] über diesen Punkt hinaus. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie.
>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) anstatt.

Beschreibt Methoden im Abschnitt `DIL.tools` Namespace. Mithilfe dieser Dienstprogrammfunktionen können Sie bestimmte Aufgaben ausführen.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Gibt Suchbegriffe zurück, die zum Erreichen der aktuellen Seite verwendet werden.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Zweck `getSearchReferrer`

DIL: `getSearchReferrer` gibt Suchergebnisse (Namen und Schlüsselwörter) zurück, die zum Erreichen Ihrer Site verwendet werden. Sie können bestimmte Suchbegriffe an diese Funktion übergeben oder sie nach unterstützten Suchmaschinen durchsuchen ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], und [!DNL Yahoo]) gegen `document.referrer` Standardmäßig.

### Funktionsunterschrift

Funktionsunterschrift: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Funktionsparameter

`getSearchReferrer` akzeptiert:

* *`{string}`*: *(Optional)* Eine Zeichenfolge, die die Such-URL enthält (verwendet `document.referrer` wenn nicht definiert).
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
   <td>Übergeben einer benutzerdefinierten URL</td> 
   <td>Gibt die verweisende Stelle basierend auf einer benutzerdefinierten URL zurück.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>URL-Hostname mit benutzerdefiniertem Regex abgleichen</b></td> 
   <td> Übergeben Sie einen benutzerdefinierten Regex, um den Hostnamen der verweisenden URL abzugleichen. </td> 
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
   <td> <b>Suchmuster mit benutzerdefiniertem Regex abgleichen</b> </td> 
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

## dekomposseURI

Deassembliert eine Uniform Resource Identifier ( [!DNL URI]) in die Komponenten der Komponente: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, und `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Funktionsunterschrift: `DIL.tools.decomposeURI`

### Funktionsparameter

`decomposeURI` akzeptiert:

* *`uri {string}`*: *(Optional)* Eine Zeichenfolge, die den URI enthält. Standardwert ist `document.location.href` falls nicht angegeben.

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

`getMetaTags` akzeptiert einen oder mehrere Namensparameter (Zeichenfolgentyp) für die Suche. Es wird ein Objekt zurückgegeben, das aus Schlüssel-Wert-Paaren besteht.

### Beispielcode

<pre class="javascript"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>

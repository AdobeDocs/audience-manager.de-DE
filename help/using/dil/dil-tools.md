---
description: Beschreibt Methoden im DIL.tools-Namespace. Mit diesen Dienstprogrammfunktionen können Sie bestimmte Aufgaben ausführen.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL-Tools
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 2%

---

# DIL-Tools

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung des [!DNL Data Integration Library (DIL)] und der [!DNL DIL] eingestellt.
>
>Bestehende Kundinnen und Kunden können ihre [!DNL DIL] Implementierung weiterhin nutzen. Adobe wird jedoch keine [!DNL DIL] über diesen Punkt hinaus entwickeln. Kundinnen und Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) auf ihre langfristige Datenerfassungsstrategie hin zu überprüfen.
>
>Kunden, die nach Juli 2023 neue Datenerfassungsintegrationen implementieren möchten, sollten stattdessen [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

Beschreibt die Methoden im `DIL.tools` Namespace. Mit diesen Dienstprogrammfunktionen können Sie bestimmte Aufgaben ausführen.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Gibt Suchbegriffe zurück, die zum Aufrufen der aktuellen Seite verwendet werden.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Zweck der `getSearchReferrer`

In DIL gibt `getSearchReferrer` Suchergebnisse (Namen und Schlüsselwörter) zurück, die zum Erreichen Ihrer Site verwendet werden. Sie können bestimmte Suchbegriffe an diese Funktion übergeben oder sie die unterstützten Suchmaschinen ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google] und [!DNL Yahoo]) standardmäßig nach `document.referrer` durchsuchen lassen.

### Funktionssignatur

Funktionssignatur: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Funktionsparameter

`getSearchReferrer` akzeptiert:

* *`{string}`*: *(Optional)* Eine Zeichenfolge, die die Such-URL enthält (verwendet `document.referrer`, wenn nicht definiert).
* *`{object}`*: *(Optional)* Ein Objekt, das die Konfiguration für die `hostPattern`, `queryParam` oder `queryPattern` enthält.

Und gibt zurück:

* `{object}` Ein -Objekt, das gültige Namen und Schlüsselwörter enthält.

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
   <td> Gibt Keyword-Suchbegriffe zurück, die von den Suchmaschinen AOL, Ask, Bing, Google und Yahoo verwendet werden. </td> 
   <td>
      <code>var&nbsp;results&nbsp;=&nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>In einer benutzerdefinierten URL übergeben</td> 
   <td>Gibt den Such-Referrer basierend auf einer benutzerdefinierten URL zurück.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>URL-Hostname mit einer benutzerdefinierten Regex abgleichen</b></td> 
   <td> Übergeben Sie einen benutzerdefinierten Regex, damit er mit dem Host-Namen der verweisenden URL übereinstimmt. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",&lbrace; 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      &rbrace;); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Suchmuster mit einem benutzerdefinierten Regex abgleichen</b> </td> 
   <td> Übergeben Sie einen benutzerdefinierten Regex, um eine benutzerdefinierte Suche durchzuführen. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      &lbrace;
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      &rbrace;);
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## zerlegenURI

Teilt eine Uniform Resource Identifier ([!DNL URI]) in seine einzelnen Komponenten auf: `hash`, `host`, `href`, `pathname`, `protocol`, `search` und `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Funktionssignatur: `DIL.tools.decomposeURI`

### Funktionsparameter

`decomposeURI` akzeptiert:

* *`uri {string}`*: *(Optional)* Eine Zeichenfolge, die den URI enthält. Die Standardeinstellung ist `document.location.href`, wenn nicht anders angegeben.

Und gibt zurück:

* *`{object}`*: Ein Objekt, das gültige Namen und Schlüsselwörter enthält.

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

Sucht nach bestimmten Inhalten, die in den Meta-Tags auf einer Web-Seite definiert sind, und gibt diese Daten in einem -Objekt zurück.

<!-- 

r_dil_get_metatags.xml

 -->

### Funktionssignatur

Funktionssignatur: `DIL.tools.getMetaTags( 1 or more parameters)`

### Funktionsparameter

`getMetaTags` akzeptiert einen oder mehrere Namensparameter (vom Typ Zeichenfolge), nach denen gesucht werden soll. Sie gibt ein -Objekt zurück, das aus Schlüssel-Wert-Paaren besteht.

### Beispielcode

<pre class="javascript"><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: <i>&grave;partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>

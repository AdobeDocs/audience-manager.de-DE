---
description: Beschreibt Methoden im Namespace DIL.modules. Mit diesen Modulen können Sie Daten programmgesteuert erfassen und mit Audience Manager-Objekten arbeiten.
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: DIL-Module
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 4%

---

# DIL-Module{#dil-modules}

>[!WARNING]
>
>Ab Juli 2023 hat die Adobe die Entwicklung der [!DNL Data Integration Library (DIL)] und [!DNL DIL] -Erweiterung.
><br>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] Implementierung. Die Adobe wird sich jedoch nicht entwickeln [!DNL DIL] über diesen Punkt hinaus. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie.
><br>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) anstatt.

Beschreibt Methoden im `DIL.modules` Namespace. Mit diesen Modulen können Sie Daten programmgesteuert erfassen und mit Audience Manager-Objekten arbeiten.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Funktioniert mit [!UICONTROL DIL] zum Senden [!DNL Analytics] Tag-Elemente (Variablen, Props, eVars usw.) auf Audience Manager. Gibt Daten in einer kommagetrennten Liste zurück. Verfügbar in Version 2.6.

**Funktionssignatur:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Sie müssen diesen Code auf der Seite platzieren *before* die `s.t();` -Funktion.

<!-- 

r_dil_sc_init.xml

 -->

**Parameter**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variablen </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>Ein Array von Zeichenfolgen, die eine unnummerierte <span class="keyword"> Analytics </span> Variablen wie <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, usw. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ein Array von Objekten, die Aufzählungen enthalten <span class="keyword"> Analytics </span> Variablen wie Props und eVars (z. B. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Ganzzahl </td> 
   <td colname="col3"> <p>Gibt an, wie viele iterierte Namen Sie zurückgeben möchten. Um beispielsweise zwei Props oder eVars zurückzugeben, legen Sie <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ein Objekt, das die <span class="keyword"> Analytics </span> -Objekt. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ein Objekt, das <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Zusätzliche Optionen: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Wenn Sie nichts anderes angeben, werden Punkte durch den standardmäßigen Unterstrich ( _ ) ersetzt. </p> <p>Beispiel <code> s.contextData = {abc.def = '123'} </code>würde zu <code> c_contextData_abc_def=123 </code> in der Abfragezeichenfolge des Ereignisaufrufs. </p> <p>Diese Option ist nur in <span class="wintitle"> DIL </span> Version 5.0 oder höher. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>Beispiel: <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> würde dazu führen, dass das Array von Zeichenfolgen aus der Datenerfassung von Kontextdaten gefiltert wird. Bei dieser Option werden personenbezogene Daten (PII) ausgeschlossen. </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Von SiteCatalyst.init erfasste Daten**

Diese Funktion gibt Details zu folgenden Elementen zurück: [!DNL Analytics] properties:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1 - 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**Beispielcode**

Dieser Code erstellt eine kommagetrennte Liste von [!DNL Analytics] Ereignisse (Props, eVars usw.) , wenn Werte für sie vorhanden sind.

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

So verfolgen Sie alle überwachten [!DNL Analytics] Datenpunkte ohne die oben dargestellte zusätzliche Funktion aufrufen `siteCatalyst.init` wie folgt:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

Die `GA.submitUniversalAnalytics();` -Funktion sendet Daten von Google [!DNL Universal Analytics] auf Audience Manager. Diese [!UICONTROL DIL] -Funktion ist für die Verwendung mit `analytics.js`, die neueste Codebibliothek für Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] hat keine Einblicke in oder Kontrolle über Google `analytics.js` Code-Bibliothek. Sie sollten sicherstellen, dass [!UICONTROL DIL] Die Datenerfassung funktioniert weiterhin, wenn oder wenn Google neue Versionen von `analytics.js`.
>
>* Sie können `GA.submitUniversalAnalytics();` Wenn Sie weiterhin mit dem alten Analytics-Trackingcode von Google arbeiten (z. B. `ga.js` oder `dc.js`). Siehe [GA.init](../dil/dil-modules.md#ga-init) anstatt.
>

**Funktionssignatur:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Eigenschaften**

Die `GA.submitUniversalAnalytics();` -Funktion akzeptiert die folgenden Eigenschaften.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Eigenschaft </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p>Die globale Variable für Ihre Instanz von <span class="keyword"> Google Analytics </span>. Dies ist normalerweise <code> ga </code> , sofern Sie Ihre <span class="keyword"> Google Analytics </span> Code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>Die -Variable, die Ihre Instanz von <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Optional)</i> Im <code> analytics.js </code> Bibliothek, ist die interne Eigenschaft die minimierte Variable <code> 'b' </code>. Diese Variable enthält <span class="keyword"> Google Analytics </span> Daten. </p> <p>Diese Eigenschaft ist optional, da Sie sie nur festlegen müssen, wenn Google den Namen der internen Variablen ändert. Wenn diese minimierte Variable beispielsweise in <code> 'a' </code>aufrufen <code> GA.submitUniversalAnalytics(); </code> wie folgt: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel**

Denken Sie daran, die [!DNL Google Analytics] `ga` -Objekt zuerst, bevor [!UICONTROL DIL] und `GA.submitUniversalAnalytics();`. Ihr Code könnte in etwa wie folgt aussehen:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

Die `GA.init()` sendet Daten aus der veralteten/veralteten Version von [!DNL Google Analytics] auf Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` funktioniert nur mit dem alten Analytics-Trackingcode von Google, `ga.js` oder `dc.js`. Sie können dies nicht aufrufen [!UICONTROL DIL] Funktion verwenden, wenn Sie `analytics.js`, die neueste Codebibliothek für Google [!DNL Universal Analytics]. [!DNL Audience Manager] Kunden, die [!UICONTROL DIL] und [!DNL Universal Analytics] sollte [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Funktionssignatur:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `_gaq` | Array | Ein Array, das GA-Befehle enthält. |
| `dilInstance` | Objekt | Ein Objekt, das die DIL-Instanz enthält. |
| `trackVars` | Objekt | *(Optional)* Ein Objekt, das aus dem `names` -Eigenschaft. Diese Eigenschaft ist ein Array von GA-Befehlsnamen, die Sie verfolgen möchten. |

**Unterstützte GA-Funktionsaufrufe**

Standardmäßig `GA.init` erfasst Daten aus den folgenden Funktionen:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL erstellt Schlüssel für GA-Daten**

Audience Manager akzeptiert Daten in Form von Schlüssel-Wert-Paaren, während GA mit Elementen in einem Array funktioniert. So arbeiten Sie mit GA-Daten: [!UICONTROL DIL] erstellt automatisch ein Schlüssel-Wert-Paar und bildet einen Schlüssel wie den folgenden: `c_ <key name>`. Außerdem werden Elemente in GA-Arrays in einer bestimmten Reihenfolge angezeigt. Daher müssen Sie alle Parameter in dieser Reihenfolge angeben, auch wenn sie keine Daten enthalten. [!UICONTROL DIL] ordnet Schlüssel für die folgenden GA-Methoden zu:

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**Beispielcode**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

Rufen Sie auf, um alle überwachten GA-Metriken ohne die oben dargestellte zusätzliche Funktion zu verfolgen. `GA.init` wie folgt:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Beispielereignisaufruf**

Der URL-Ereignisaufruf an Audience Manager könnte in etwa wie folgt aussehen:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics-Trackingcode](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Vollständige Webaktualisierung: ga.js/dc.js to analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Hinzufügen von analytics.js zu Ihrer Site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [ga-Objektmethoden-Referenz](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

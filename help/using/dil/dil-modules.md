---
description: Beschreibt Methoden im Namespace DIL. module. Mit diesen Modulen können Sie programmgesteuert Daten sammeln und mit Audience Manager-Objekten arbeiten.
seo-description: Beschreibt Methoden im Namespace DIL. module. Mit diesen Modulen können Sie programmgesteuert Daten sammeln und mit Audience Manager-Objekten arbeiten.
seo-title: DIL-Module
solution: Audience Manager
title: DIL-Module
uuid: d 4 c 0 d 8 dd -79 f 8-448 e-b 17 c-c 935415 dd 449
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# DIL Modules{#dil-modules}

Describes methods in the `DIL.modules` namespace. Mit diesen Modulen können Sie programmgesteuert Daten sammeln und mit Audience Manager-Objekten arbeiten.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Works with [!UICONTROL DIL] to send [!DNL Analytics] tag elements (variables, props, eVars, etc.) in Audience Manager. Gibt Daten in einer durch Kommata getrennten Liste zurück. Verfügbar in Version 2.6.

**Funktionssignatur:**`DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>You must place this code on the page *before* the `s.t();` function.

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
   <td colname="col1"> <code> Namen </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>An array of strings that contains un-enumerated <span class="keyword"> Analytics </span> variables like <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Iteratednames </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>An array of objects that contains enumerated <span class="keyword"> Analytics </span> variables like props and evars (e.g. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Maxindex </code> </td> 
   <td colname="col2"> Ganzzahl </td> 
   <td colname="col3"> <p>Gibt an, wie viele iterierte Namen zurückgegeben werden sollen. For example, to return two props or evars, set <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Sitecatalystreportingsuite </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>An object that represents the <span class="keyword"> Analytics </span> object. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Dilinstance </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>An object that represents <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Weitere Optionen: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> Replacecontextdataperiodswith </code> </p> <p>Wenn Sie keine andere Angabe vornehmen, werden die Punkte durch den Unterstrich (_) ersetzt. </p> <p>For example <code> s.contextData = {abc.def = '123'} </code>would result in <code> c_contextData_abc_def=123 </code> in the event call query string. </p> <p>This option is available only in <span class="wintitle"> DIL </span> version 5.0 or later. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> Filterfromcontextvariables </code> </p> <p>For example, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> would result in the array of strings being filtered from the data collection of context data. Diese Option schließt personenbezogene Informationen (PII) aus. </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Von sitecatalyst. init erfasste Daten**

This function returns details on the following [!DNL Analytics] properties:

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

This code creates a comma separated list of [!DNL Analytics] events (props, eVars, etc.) wenn Werte vorhanden sind.

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

To track all the monitored [!DNL Analytics] data points without the additional function shown above, invoke `siteCatalyst.init` by itself like this:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

The `GA.submitUniversalAnalytics();` function sends data from Google's [!DNL Universal Analytics] to Audience Manager. This [!UICONTROL DIL] function is designed to work with `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] verfügt über keine Einblicke in die Google `analytics.js` -Codebibliothek. You should verify that [!UICONTROL DIL] data collection is still working if or when Google releases new versions of `analytics.js`.
   >
   >
* You cannot use `GA.submitUniversalAnalytics();` if you're still working with Google's legacy analytics tracking code (e.g., `ga.js` or `dc.js`). See [GA.init](../dil/dil-modules.md#ga-init) instead.
>



**Funktionssignatur:**`DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Eigenschaften**

The `GA.submitUniversalAnalytics();` function accepts the following properties.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Eigenschaft </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Gaobject </code> </p> </td> 
   <td colname="col2"> <p>The global variable for your instance of <span class="keyword"> Google Analytics </span>. This is usually <code> ga </code> by default, unless you've customized your <span class="keyword"> Google Analytics </span> code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dilinstance </code> </p> </td> 
   <td colname="col2"> <p>The variable that represents your instance of <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Internalpropertyname </code> </p> </td> 
   <td colname="col2"> <p> <i>(Optional)</i> In der <code> Analytics. js-Bibliothek </code> ist die interne Eigenschaft die minimierte Variable <code> 'b ' </code>. This variable holds <span class="keyword"> Google Analytics </span> data. </p> <p>Diese Eigenschaft ist optional, da sie sie nur festlegen muss, wenn Google den Namen ihrer internen Variablen ändert. For example, if this minified variable changed to <code> 'a' </code>, you would call <code> GA.submitUniversalAnalytics(); </code> like this: </p> <p> <code> DIL. modules. gasubmituniversalanalytics (ga, dilinstance,' a '); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel**

Remember to define the [!DNL Google Analytics] `ga` object first, before calling [!UICONTROL DIL] and `GA.submitUniversalAnalytics();`. Ihr Code könnte wie folgt aussehen:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

>[!MORE_ LIKE_ THIS]
>
>* [GA-Objektmethodenreferenz](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)


## GA.init {#ga-init}

The `GA.init()` function sends data from the legacy/deprecated version of [!DNL Google Analytics] to Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` funktioniert nur mit dem alten Analytics-Trackingcode von Google `ga.js``dc.js`oder You cannot invoke this [!UICONTROL DIL] function if you use `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics]. [!DNL Audience Manager] Kunden, die [!UICONTROL DIL][!DNL Universal Analytics][GA. submituniversalanalytics verwenden](../dil/dil-modules.md#ga-submit-universal-analytics).

**Funktionssignatur:**`DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `_gaq` | Array | Ein Array mit GA-Befehlen. |
| `dilInstance` | Objekt | Ein Objekt, das die DIL-Instanz enthält. |
| `trackVars` | Objekt | *(Optional)* Ein Objekt, das aus der `names` Eigenschaft besteht. Diese Eigenschaft ist ein Array von GA-Befehlsnamen, die Sie verfolgen möchten. |

**Unterstützte GA-Funktionsaufrufe**

By default, `GA.init` captures data from the following functions:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL Erstellt Schlüssel für GA-Daten**

Audience Manager akzeptiert Daten in Form von Schlüssel/Wert-Paaren, während GA mit Elementen in einem Array arbeitet. To work with GA data, [!UICONTROL DIL] creates a key-value pair automatically and forms a key like this: `c_ <key name>`. Außerdem werden Elemente in GA-Arrays in einer bestimmten Reihenfolge angezeigt. Daher müssen Sie alle Parameter in dieser Reihenfolge bereitstellen, auch wenn sie keine Daten enthalten. [!UICONTROL DIL] ordnet Schlüssel für die folgenden GA-Methoden zu:

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

To track all the monitored GA metrics without the additional function shown above, invoke `GA.init` by itself like this:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Beispielereignisaufruf**

Der URL-Ereignisaufruf an Audience Manager könnte wie folgt aussehen:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORE_ LIKE_ THIS]
>
>* [Google Analytics-Trackingcode](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Vollständiges Web-Upgrade: ga.js/dc.js auf analytics. js](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [Hinzufügen von Analytics. js zu Ihrer Site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)


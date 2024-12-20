---
description: Beschreibt Methoden im DIL.modules-Namespace. Mit diesen Modulen können Sie Daten programmgesteuert erfassen und mit Audience Manager-Objekten arbeiten.
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: DIL-Module
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 3%

---

# DIL-Module{#dil-modules}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung des [!DNL Data Integration Library (DIL)] und der [!DNL DIL] eingestellt.
>
>Bestehende Kundinnen und Kunden können ihre [!DNL DIL] Implementierung weiterhin nutzen. Allerdings wird sich Adobe nicht über diesen Punkt hinaus [!DNL DIL] entwickeln. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) auf ihre langfristige Datenerfassungsstrategie hin zu überprüfen.
>
>Kunden, die nach Juli 2023 neue Datenerfassungsintegrationen implementieren möchten, sollten stattdessen [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

Beschreibt die Methoden im `DIL.modules` Namespace. Mit diesen Modulen können Sie Daten programmgesteuert erfassen und mit Audience Manager-Objekten arbeiten.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Funktioniert mit [!UICONTROL DIL], um [!DNL Analytics] Tag-Elemente (Variablen, Props, eVars usw.) an den Audience Manager zu senden. Gibt Daten in einer kommagetrennten Liste zurück. Verfügbar in Version 2.6.

**Funktionssignatur:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Sie müssen diesen Code auf der Seite (*)* der `s.t();` platzieren.

<!-- 

r_dil_sc_init.xml

 -->

**Parameter**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namen </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>Ein Array von Zeichenfolgen, das nicht aufgezählte <span class="keyword"> Analytics-</span> wie <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code> usw. enthält. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ein Array von Objekten, das Aufzählungen <span class="keyword"> Analytics </span> Variablen wie Props und eVars enthält (z. B. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Ganzzahl </td> 
   <td colname="col3"> <p>Gibt an, wie viele iterierte Namen Sie zurückgeben möchten. Um beispielsweise zwei Props oder eVars zurückzugeben, setzen Sie <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ein -Objekt, das das <span class="keyword"> Analytics-</span> darstellt. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ein -Objekt, das <span class="wintitle"> DIL-</span> darstellt. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Zusätzliche Optionen: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Wenn Sie nichts anderes angeben, werden Punkte durch den standardmäßigen Unterstrich ( _ ) ersetzt. </p> <p>Beispielsweise würde <code> s.contextData = {abc.def = '123'} </code>zu einer <code> c_contextData_abc_def=123 </code> in der Abfragezeichenfolge des Ereignisaufrufs führen. </p> <p>Diese Option ist nur in <span class="wintitle"> DIL </span> Version 5.0 oder höher verfügbar. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p><code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> würde beispielsweise dazu führen, dass das Zeichenfolgen-Array aus der Datenerfassung der Kontextdaten gefiltert würde. Diese Option schließt personenbezogene Daten (PII) aus. </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Von siteCatalyst.init erfasste Daten**

Diese Funktion gibt Details zu den folgenden [!DNL Analytics] zurück:

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

Dieser Code erstellt eine kommagetrennte Liste von [!DNL Analytics]-Ereignissen (Props, eVars usw.), wenn Werte für sie vorhanden sind.

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

Um alle überwachten [!DNL Analytics] ohne die oben dargestellte zusätzliche Funktion zu verfolgen, rufen Sie `siteCatalyst.init` wie folgt selbst auf:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

Die `GA.submitUniversalAnalytics();` sendet Daten aus der [!DNL Universal Analytics] von Google an den Audience Manager. Diese [!UICONTROL DIL]-Funktion wurde für die Verwendung mit `analytics.js` entwickelt, der neuesten Code-Bibliothek für Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] hat keinen Einblick in die Google `analytics.js`-Code-Bibliothek und keine Kontrolle über diese. Sie sollten sicherstellen, dass [!UICONTROL DIL] Datenerfassung weiterhin funktioniert, wenn oder wenn Google neue Versionen von `analytics.js` veröffentlicht.
>
>* Sie können `GA.submitUniversalAnalytics();` nicht verwenden, wenn Sie noch immer mit dem veralteten Analytics-Trackingcode von Google arbeiten (z. B. `ga.js` oder `dc.js`). Siehe [GA.init](../dil/dil-modules.md#ga-init).
>

**Funktionssignatur:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Eigenschaften**

Die `GA.submitUniversalAnalytics();`-Funktion akzeptiert die folgenden Eigenschaften.

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
   <td colname="col2"> <p>Die globale Variable für Ihre Instanz <span class="keyword"> Google Analytics-</span>. Dies ist in der Regel standardmäßig <code> ga </code>, es sei denn, Sie haben Ihren <span class="keyword"> Google Analytics-</span> angepasst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>Die Variable, die Ihre Instanz <span class="wintitle"> DIL-</span> darstellt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Optional)</i> In der <code> analytics.js </code>-Bibliothek ist die interne Eigenschaft die minimierte Variable <code> 'b' </code>. Diese Variable enthält <span class="keyword"> Google Analytics-</span>. </p> <p>Diese Eigenschaft ist optional, da Sie sie nicht festlegen müssen, es sei denn, Google ändert den Namen seiner internen Variablen. Wenn diese minimierte Variable beispielsweise in <code> 'a' </code> geändert wird, würden Sie <code> GA.submitUniversalAnalytics(); </code> wie folgt aufrufen: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel**

Denken Sie daran, zunächst das [!DNL Google Analytics] `ga`-Objekt zu definieren, bevor Sie [!UICONTROL DIL] und `GA.submitUniversalAnalytics();` aufrufen. Ihr Code könnte in etwa wie folgt aussehen:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

Die `GA.init()` sendet Daten aus der veralteten/veralteten Version von [!DNL Google Analytics] an den -Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` funktioniert nur mit dem alten Analytics-Trackingcode von Google, `ga.js` oder `dc.js`. Sie können diese [!UICONTROL DIL] nicht aufrufen, wenn Sie `analytics.js` verwenden, die die neueste Code-Bibliothek für Google [!DNL Universal Analytics] ist. [!DNL Audience Manager] Kunden, die [!UICONTROL DIL] und [!DNL Universal Analytics] verwenden, sollten [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics) sehen.

**Funktionssignatur:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `_gaq` | Array | Ein Array, das GA-Befehle enthält. |
| `dilInstance` | Objekt | Ein -Objekt, das die DIL-Instanz enthält. |
| `trackVars` | Objekt | *(Optional)* Ein Objekt, das aus der `names` besteht. Diese Eigenschaft ist ein Array von GA-Befehlsnamen, die Sie verfolgen möchten. |

**Unterstützte GA-Funktionsaufrufe**

Standardmäßig erfasst `GA.init` Daten aus den folgenden Funktionen:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL erstellt Schlüssel für GA-Daten**

Audience Manager akzeptiert Daten in Form von Schlüssel-Wert-Paaren, während GA mit Elementen in einem Array arbeitet. Um mit GA-Daten zu arbeiten, erstellt [!UICONTROL DIL] automatisch ein Schlüssel-Wert-Paar und bildet einen Schlüssel wie den folgenden: `c_ <key name>`. Außerdem erscheinen Elemente in GA-Arrays in einer bestimmten Reihenfolge. Daher müssen Sie alle Parameter in dieser Reihenfolge angeben, auch wenn sie keine Daten enthalten. [!UICONTROL DIL] ordnet Schlüssel für die folgenden GA-Methoden zu:

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

Um alle überwachten GA-Metriken ohne die oben dargestellte zusätzliche Funktion zu verfolgen, rufen Sie `GA.init` wie folgt selbst auf:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Beispielereignisaufruf**

Der URL-Ereignisaufruf an den Audience Manager könnte in etwa wie folgt aussehen:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics-Trackingcode](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Vollständiges Web-Upgrade: ga.js/dc.js auf analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Hinzufügen von analytics.js zu Ihrer Site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [GA-Objektmethoden-Referenz](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

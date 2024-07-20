---
description: Beschreibt Methoden im Namespace DIL.modules. Mit diesen Modulen können Sie Daten programmgesteuert erfassen und mit Audience Manager-Objekten arbeiten.
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
>Ab Juli 2023 hat Adobe die Entwicklung der Erweiterung [!DNL Data Integration Library (DIL)] und der Erweiterung [!DNL DIL] eingestellt.
>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] -Implementierung verwenden. Adobe wird jedoch nicht mehr [!DNL DIL] als bisher entwickeln. Kunden wird empfohlen, das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie zu bewerten.
>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten stattdessen das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

Beschreibt Methoden im Namespace `DIL.modules` . Mit diesen Modulen können Sie Daten programmgesteuert erfassen und mit Audience Manager-Objekten arbeiten.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Funktioniert mit [!UICONTROL DIL] , um [!DNL Analytics] -Tag-Elemente (Variablen, Props, eVars usw.) zu senden. auf Audience Manager. Gibt Daten in einer kommagetrennten Liste zurück. Verfügbar in Version 2.6.

**Funktionssignatur:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Sie müssen diesen Code auf der Seite *vor* der Funktion `s.t();` platzieren.

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
   <td colname="col3"> <p>Ein Array von Zeichenfolgen, die nicht aufgezählte <span class="keyword"> Analytics </span>-Variablen wie <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code> usw. enthalten. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ein Array von Objekten, die Aufzählungsvariablen <span class="keyword"> Analytics </span> enthalten, wie Props und eVars (z. B. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Ganzzahl </td> 
   <td colname="col3"> <p>Gibt an, wie viele iterierte Namen Sie zurückgeben möchten. Wenn Sie beispielsweise zwei Eigenschaften oder eVars zurückgeben möchten, legen Sie <code> maxIndex:2 </code> fest. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ein Objekt, das das Objekt <span class="keyword"> Analytics </span> darstellt. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ein Objekt, das <span class="wintitle"> DIL </span> darstellt. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Zusätzliche Optionen: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Wenn Sie nichts anderes angeben, werden Punkte durch den standardmäßigen Unterstrich ( _ ) ersetzt. </p> <p>Beispiel: <code> s.contextData = {abc.def = '123'} </code>würde in der Abfragezeichenfolge des Ereignisaufrufs zu <code> c_contextData_abc_def=123 </code> führen. </p> <p>Diese Option ist nur in <span class="wintitle"> DIL </span> Version 5.0 oder neuer verfügbar. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>Beispiel: <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> würde dazu führen, dass das Array von Zeichenfolgen aus der Datenerfassung von Kontextdaten gefiltert wird. Bei dieser Option werden personenbezogene Daten (PII) ausgeschlossen. </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Von SiteCatalyst.init erfasste Daten**

Diese Funktion gibt Details zu den folgenden [!DNL Analytics] -Eigenschaften zurück:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1-75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**Beispielcode**

Dieser Code erstellt eine kommagetrennte Liste von [!DNL Analytics] -Ereignissen (Props, eVars usw.) , wenn Werte für sie vorhanden sind.

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

Um alle überwachten [!DNL Analytics] -Datenpunkte ohne die oben dargestellte zusätzliche Funktion zu verfolgen, rufen Sie `siteCatalyst.init` allein wie folgt auf:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

Die Funktion `GA.submitUniversalAnalytics();` sendet Daten von Google [!DNL Universal Analytics] an Audience Manager. Diese [!UICONTROL DIL] -Funktion wurde für die Verwendung mit `analytics.js` entwickelt, der neuesten Codebibliothek für Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] hat keine Einblicke in die Google `analytics.js`-Codebibliothek und hat keine Kontrolle darüber. Sie sollten sicherstellen, dass die [!UICONTROL DIL]-Datenerfassung weiterhin funktioniert, wenn oder wenn Google neue Versionen von `analytics.js` veröffentlicht.
>
>* Sie können `GA.submitUniversalAnalytics();` nicht verwenden, wenn Sie weiterhin mit dem alten Analytics-Trackingcode von Google arbeiten (z. B. `ga.js` oder `dc.js`). Siehe stattdessen [GA.init](../dil/dil-modules.md#ga-init) .
>

**Funktionssignatur:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Eigenschaften**

Die Funktion `GA.submitUniversalAnalytics();` akzeptiert die folgenden Eigenschaften.

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
   <td colname="col2"> <p>Die globale Variable für Ihre Instanz von <span class="keyword"> Google Analytics </span>. Dies ist normalerweise standardmäßig <code> ga </code>, es sei denn, Sie haben Ihren <span class="keyword"> Google Analytics </span> -Code angepasst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>Die Variable, die Ihre Instanz von <span class="wintitle"> DIL </span> darstellt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Optional)</i> In der Bibliothek <code> analytics.js </code> ist die interne Eigenschaft die minimierte Variable <code> 'b' </code>. Diese Variable enthält <span class="keyword"> Google Analytics </span> -Daten. </p> <p>Diese Eigenschaft ist optional, da Sie sie nur festlegen müssen, wenn Google den Namen der internen Variablen ändert. Wenn diese minimierte Variable beispielsweise zu <code> 'a' </code> geändert wird, rufen Sie <code> GA.submitUniversalAnalytics(); </code> wie folgt auf: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel**

Denken Sie daran, zuerst das Objekt [!DNL Google Analytics] `ga` zu definieren, bevor Sie [!UICONTROL DIL] und `GA.submitUniversalAnalytics();` aufrufen. Ihr Code könnte in etwa wie folgt aussehen:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

Die Funktion `GA.init()` sendet Daten aus der veralteten/veralteten Version von [!DNL Google Analytics] an Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` funktioniert nur mit dem alten Analytics-Trackingcode von Google, `ga.js` oder `dc.js`. Sie können diese [!UICONTROL DIL] -Funktion nicht aufrufen, wenn Sie `analytics.js` verwenden, die die neueste Codebibliothek für Google [!DNL Universal Analytics] ist. [!DNL Audience Manager] -Kunden, die [!UICONTROL DIL] und [!DNL Universal Analytics] verwenden, sollten [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics) sehen.

**Funktionssignatur:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `_gaq` | Array | Ein Array, das GA-Befehle enthält. |
| `dilInstance` | Objekt | Ein Objekt, das die DIL-Instanz enthält. |
| `trackVars` | Objekt | *(Optional)* Ein Objekt, das aus der Eigenschaft `names` besteht. Diese Eigenschaft ist ein Array von GA-Befehlsnamen, die Sie verfolgen möchten. |

**Unterstützte GA-Funktionsaufrufe**

Standardmäßig erfasst `GA.init` Daten aus den folgenden Funktionen:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL Erstellt Schlüssel für GA Data**

Audience Manager akzeptiert Daten in Form von Schlüssel-Wert-Paaren, während GA mit Elementen in einem Array funktioniert. Um mit GA-Daten zu arbeiten, erstellt [!UICONTROL DIL] automatisch ein Schlüssel-Wert-Paar und bildet einen Schlüssel wie den folgenden: `c_ <key name>`. Außerdem werden Elemente in GA-Arrays in einer bestimmten Reihenfolge angezeigt. Daher müssen Sie alle Parameter in dieser Reihenfolge angeben, auch wenn sie keine Daten enthalten. [!UICONTROL DIL] ordnet Schlüssel für die folgenden GA-Methoden zu:

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

Um alle überwachten GA-Metriken ohne die oben dargestellte zusätzliche Funktion zu verfolgen, rufen Sie `GA.init` allein wie folgt auf:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Beispielereignisaufruf**

Der URL-Ereignisaufruf an Audience Manager könnte in etwa wie folgt aussehen:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics-Trackingcode](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Abschließen der Web-Aktualisierung: ga.js/dc.js to analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Hinzufügen von analytics.js zu Ihrer Site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [ga-Objektmethoden-Referenz](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

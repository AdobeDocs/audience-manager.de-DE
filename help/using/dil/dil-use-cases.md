---
description: Codebeispiele und Beschreibungen für spezifische DIL-Verwendungen.
seo-description: Codebeispiele und Beschreibungen für spezifische DIL-Verwendungen.
seo-title: DIL-Anwendungsfälle und Codebeispiele
solution: Audience Manager
title: DIL-Anwendungsfälle und Codebeispiele
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL Use Cases and Code Samples{#dil-use-cases-and-code-samples}

Codebeispiele und Beschreibungen für spezifische DIL-Verwendungen.

<!-- 

c_dil_use_case.xml

 -->

## Send Data Elements to Audience Manager with DIL {#send-data-elements-dil}

Erstellen Sie eine Objektvariable, die Informationen zu Seitenelementen an Audience Manager sendet. Dies ist für allgemeine Datenerfassung oder als Alternative zur Datenerfassung mit Analytics-Variablen nützlich.

<!-- 

c_dil_send_page_objects.xml

 -->

**Beschreibung**

The following code demonstrates how to collect page data and send it to Audience Manager with [!UICONTROL DIL]. Diese Beispiele verwenden eine Variable, um Datenelemente in einer einfachen Liste oder in einem Array festzuhalten. Remember, pass in variables as [key-value pairs](../reference/key-value-pairs-explained.md). Also, note the `c_` prefix before the key in the key-value pair. This [required prefix](../features/traits/trait-variable-prefixes.md) identifies information as user-defined data. In the first example, you need to manually append `c_` to the key. In the second example, [!UICONTROL DIL] does this for you automatically.

**Werteigenschaften konsistent beibehalten**

Denken Sie daran, die Werteigenschaften beim Übergeben von Daten unverändert beizubehalten. Wenn Sie beispielsweise zwei identische Schlüssel mit unterschiedlichen Werten haben, hat der Wert des letzten Schlüssel-Wert-Paars Vorrang vor den vorhergehenden Wertobjekten. For example, passing in `color:blue` and `color:red` sets the returned value to red (overwrites blue).

**Beispiel 1: Daten als Schlüssel-Wert-Paare senden**

Dieses Basisbeispiel sendet Farb- und Preisdaten in Form von Schlüssel/Wert-Paaren an Audience Manager. Ihr Code könnte wie folgt aussehen:

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
sample_ dil. api. signs ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**Beispiel 2: Daten in einem Objekt senden**

Dieses erweiterte Beispiel zeigt, wie Daten in einem Objekt an Audience Manager gesendet werden. When working with this method, [!UICONTROL DIL] lets you pass an object as a function parameter into the [!DNL signals()] method. [!UICONTROL DIL] Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>var my_ object = { 
 color: " blue ", 
 Preis: " 900 "}; 
 
var sample_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
//Load Sie das Objekt und hängen Sie "c_" an alle Schlüssel in den Schlüssel/Wert-Paaren an und senden Sie Daten an audiencemanager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Beispiel 3: Senden von Seitendaten in einem Array**

In this case, the variable `my_object` uses an array to hold data. Dieses Beispiel baut auf den Informationen auf, die von der oben genannten Methode übergeben wurden, fügt jedoch eine zusätzliche Ebene hinzu, um einen Produkttyp und ein Modell aufzunehmen. Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>var my_ objects = [{ 
 color: " blue ", 
 Preis: " 900 "}, 
{ 
 type: " acura ", 
 Modell: " tl "}]; 
 
var sample_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
 
for (var i = 0; i &lt; my_ objects. length; i + +) 
//Load Sie das Objekt und hängen Sie "c_" an alle Schlüssel in den Schlüsselwertpaaren an. 
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

>[!MORE_ LIKE_ THIS]
>
>* [signalisiert](../dil/dil-instance-methods.md#signals)


## Capture Referring URL {#capture-referring-url}

Erfassen und senden Sie eine verweisende URL an den Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Diese Methode funktioniert nur, wenn Benutzer zwischen Seiten mit ähnlichen Protokollen (HTTP vs. HTTPS) wechseln. Beispielsweise behält der Browser eine verweisende URL bei, wenn Sie von einer sicheren Site zu einer anderen sicheren Site navigieren. Browser behalten die verweisende URL nicht bei, wenn Sie zwischen sicheren und nicht sicheren Sites wechseln. This behavior is normal browser functionality and cannot be circumvented by [!UICONTROL DIL].

**Codebeispiel**

Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
adobe_ dil. api. sign({d_ referer: document. referrer}). submit ();</code>
</pre>

## Capture Search Engine Types and Keyword Search Terms {#capture-search-engine-types}

Senden Sie Informationen über Suchmaschinentypen und Suchbegriffssuchen in Audience Manager.

<!-- 

c_dil_search_engine_valid.xml

 -->

**Unterstützte Suchmaschinen**

`DIL.getSearchReferrer` Erkennt standardmäßig Suchvorgänge aus diesen Suchmaschinen (einschließlich internationale Variationen):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Beschreibung**

Der folgende Code zeigt, wie der Suchreferrer für alle unterstützten Suchmaschinen abgerufen wird. In this case, let's assume a user searched on the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Dieser Code hilft Ihnen dabei, diese Suchbegriffe zu erfassen und an Audience Manager zu senden.

**Einfacher Code**

Basic code for getting the search referrer (from `google.com`, for example) looks like this:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Beispiel für eine Liste der Suchmaschinen-Codebeispiele**

In this case, let's assume that a user searched for the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Note how the code prefixes the required `c_` parameter to search engine ( `c_se`) and search term ( `c_st`). `c_` ist ein [erforderliches Präfix](../features/traits/trait-variable-prefixes.md) , das diese als kundendefinierte Variablen in Audience Manager bezeichnet.

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signs ({ 
 c_ se: se. name, 
 c_ st: se. keywords 
 }). submit (); 
}</code>
</pre>

**Beispiel für nicht aufgelistete Suchmaschinen-Codebeispiele**

In this case, let's assume that a user searched for the term "homes" from `dogpile.com`. Because [!DNL Dogpile] is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Map Key Values to Other Keys {#map-key-values}

Verknüpfen Sie den Wert von einem Schlüssel-Wert-Paar mit einem anderen Schlüssel.

<!-- 

c_dil_map_keys.xml

 -->

**Beschreibung**

In a key-value pair, the `c_` prefix appended to the key identifies the signal as customer-defined data. Kundendefinierte Daten werden für das Targeting auf der spezifischen Site verwendet, die Daten an einen Ereignisaufruf übergeben hat. Manchmal möchten Sie diese Informationen jedoch auch für alle Eigenschaften in Ihrem Audience Manager-Konto verfügbar machen. To do this, map the value in a `c_` key-value pair to a platform level key. A platform level key is prefixed with `d_` and makes the signal available for targeting across all properties in your account.

Beispiel: Sie erfassen ZIP-Codedaten aus einer bestimmten Site, möchten sie jedoch allen Ihren Audience Manager-Eigenschaften zuordnen. To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. `c_zip`) to a platform defined key as shown below.

**Codebeispiel**

Ihr Code könnte wie folgt aussehen:

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

>[!MORE_ LIKE_ THIS]
>
>* [Präfix für Schlüsselvariablen](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

Richten Sie DIL mit einem GTM-Tag ein und stellen Sie es bereit.

<!-- 

t_dil_google_tagmanager.xml

 -->

This procedure assumes you have a [!DNL Google Tag Manager] account, some working knowledge of that product, and your Audience Manager `dil.js` file.

To traffic the `dil.js` file in GTM:

1. Erstellen Sie einen neuen Container oder öffnen Sie einen vorhandenen Container.
1. Fügen Sie dem Container ein neues Tag hinzu.
1. Öffnen Sie das Tag, um es zu bearbeiten und zu bearbeiten:

   * Geben Sie dem Tag einen Namen.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * In the HTML field, place the [!UICONTROL DIL] code (library + the custom code) within script tags `<script>DIL code</script>`.
   * Klicken Sie auf **[!UICONTROL Save]**.

1. Veröffentlichen Sie den Behälter.
1. Erstellen Sie Container-Tag-Code und platzieren Sie ihn in Ihrem Bestand.

>[!MORE_ LIKE_ THIS]
>
>* [Hilfe Center für Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)


---
description: Codebeispiele und Beschreibungen für spezifische Anwendungsfälle von DIL.
seo-description: Codebeispiele und Beschreibungen für spezifische Anwendungsfälle von DIL.
seo-title: DIL-Anwendungsfälle und Code-Beispiele
solution: Audience Manager
title: DIL-Anwendungsfälle und Code-Beispiele
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---


# DIL-Anwendungsfälle und Code-Beispiele{#dil-use-cases-and-code-samples}

Codebeispiele und Beschreibungen für spezifische Anwendungsfälle von DIL.

<!-- 

c_dil_use_case.xml

 -->

## Datenelemente mit DIL {#send-data-elements-dil} an Audience Manager senden

Erstellen Sie eine Objektvariable, die Informationen zu Seitenelementen an Audience Manager sendet. Dies ist nützlich für die allgemeine Datenerfassung oder als Alternative zur Datenerfassung mit Analytics-Variablen.

<!-- 

c_dil_send_page_objects.xml

 -->

**Beschreibung**

Der folgende Code zeigt, wie Sie Seitendaten erfassen und mit [!UICONTROL DIL] an Audience Manager senden. Diese Beispiele verwenden eine Variable, um Datenelemente in einer flachen Liste oder in einem Array zu speichern. Denken Sie daran, Variablen als [Schlüssel-Wert-Paare](../reference/key-value-pairs-explained.md) zu übergeben. Beachten Sie auch das Präfix `c_` vor dem Schlüssel im Schlüssel-Wert-Paar. Dieses [erforderliche Präfix](../features/traits/trait-variable-prefixes.md) identifiziert Informationen als benutzerdefinierte Daten. Im ersten Beispiel müssen Sie `c_` manuell an den Schlüssel anhängen. Im zweiten Beispiel führt [!UICONTROL DIL] dies automatisch für Sie aus.

**Konstante Werteigenschaften beibehalten**

Denken Sie daran, die Werteigenschaften beim Übergeben von Daten gleich zu halten. Wenn Sie beispielsweise zwei identische Schlüssel mit unterschiedlichen Werten haben, hat der Wert des letzten Schlüssel-Wert-Paars Vorrang vor den vorhergehenden Wertobjekten. Wenn Sie beispielsweise `color:blue` und `color:red` übergeben, wird der zurückgegebene Wert auf rot gesetzt (überschreibt Blau).

**Beispiel 1: Daten als Schlüssel-Wert-Paare senden**

Dieses Basisbeispiel sendet Farb- und Preisdaten in Form von Schlüssel-Wert-Paaren an Audience Manager. Ihr Code könnte wie folgt aussehen:

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Beispiel 2: Daten in einem Objekt senden**

Dieses erweiterte Beispiel zeigt, wie Daten in einem Objekt an Audience Manager gesendet werden. Wenn Sie mit dieser Methode arbeiten, können Sie mit [!UICONTROL DIL] ein Objekt als Funktionsparameter an die [!DNL signals()]-Methode übergeben. [!UICONTROL DIL] Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Beispiel 3: Senden von Seitendaten in einem Array**

In diesem Fall verwendet die Variable `my_object` ein Array, um Daten zu speichern. Dieses Beispiel baut auf den Informationen auf, die von der oben empfohlenen Methode weitergegeben wurden, fügt jedoch eine zusätzliche Ebene hinzu, um einen Produkttyp und ein Modell aufzunehmen. Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## Verweisende URL erfassen {#capture-referring-url}

Erfassen und senden Sie eine verweisende URL an Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Diese Methode funktioniert nur, wenn Benutzer zwischen Seiten mit ähnlichen Protokollen (HTTP oder HTTPS) wechseln. Beispielsweise behält der Browser eine verweisende URL bei, wenn Sie von einer sicheren Site zu einer anderen sicheren Site navigieren. Browser behalten die verweisende URL nicht bei, wenn Sie zwischen sicheren und unsicheren Sites wechseln. Dieses Verhalten ist eine normale Browserfunktionalität und kann nicht durch [!UICONTROL DIL] umgangen werden.

**Code-Beispiel**

Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Suchmaschinentypen und Suchbegriffe erfassen {#capture-search-engine-types}

Senden Sie Informationen über Suchmaschinentypen und Suchbegriffe an Audience Manager.

>[!IMPORTANT]
>
>In diesem Abschnitt werden ältere Funktionen beschrieben, die in den neuesten Versionen von DIL nicht unterstützt werden.

**Unterstützte Suchmaschinen**

Standardmäßig erkennt `DIL.getSearchReferrer` Suchen aus diesen Suchmaschinen (einschließlich internationaler Variationen):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Beschreibung**

Der folgende Code zeigt, wie Sie den Werber für die Suche nach einer der unterstützten Suchmaschinen abrufen. In diesem Fall nehmen wir an, dass ein Benutzer nach dem Begriff &quot;home&quot;aus [!DNL Google] Kanada ( `www.google.ca`) gesucht hat. Dieser Code hilft Ihnen, diese Suchbegriffe zu erfassen und an den Audience Manager zu senden.

**Einfacher Code**

Der Basiscode zum Abrufen des Werbers für die Suche (z. B. von `google.com`) sieht wie folgt aus:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Beispiel für aufgelisteten Suchmaschinencode**

In diesem Fall nehmen wir an, dass ein Benutzer nach dem Begriff &quot;home&quot;aus [!DNL Google] Kanada ( `www.google.ca`) gesucht hat. Beachten Sie, wie der Code den erforderlichen Parameter `c_` für die Suchmaschine ( `c_se`) und den Suchbegriff ( `c_st`) präfixiert. `c_` ist ein  [erforderliches ](../features/traits/trait-variable-prefixes.md) Präfix, das diese als kundendefinierte Variablen für Audience Manager identifiziert.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**Beispiel für nicht aufgelisteten Suchmaschinencode**

In diesem Fall nehmen wir an, dass ein Benutzer nach dem Begriff &quot;home&quot;von `dogpile.com` gesucht hat. Da [!DNL Dogpile] nicht standardmäßig unterstützt wird, können Sie DIL so konfigurieren, dass diese Suchmaschine erkannt wird und die Suchbegriffe an Audience Manager zurückgegeben werden. Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Schlüsselwerte anderen Schlüsseln zuordnen {#map-key-values}

Verknüpfen Sie den Wert eines Schlüsselwertpaars mit einem anderen Schlüssel.

<!-- 

c_dil_map_keys.xml

 -->

**Beschreibung**

In einem Schlüssel-Wert-Paar identifiziert das `c_`-Präfix, das an den Schlüssel angehängt wird, das Signal als benutzerdefinierte Daten. Kundendefinierte Daten werden für das Targeting auf der jeweiligen Site verwendet, die Daten bei einem Ereignis-Aufruf weitergegeben hat. Manchmal möchten Sie jedoch, dass diese Informationen für alle Eigenschaften in Ihrem Audience Manager-Konto verfügbar sind. Zuordnen des Werts in einem Schlüssel-Wert-Paar `c_` zu einem Schlüssel auf Plattformebene. Dem Schlüssel auf Plattformebene wird `d_` vorangestellt und das Signal für das Targeting für alle Eigenschaften in Ihrem Konto zur Verfügung gestellt.

Sie erfassen z. B. ZIP-Code-Daten von einer bestimmten Site, möchten diese aber auf alle Audience Manager-Eigenschaften Zielgruppe haben. Um die Postleitzahl auf Plattformebene verfügbar zu machen, können Sie Ihren kundendefinierten ZIP-Code-Schlüssel (z.B. `c_zip`) auf eine Plattform definierten Schlüssel wie unten gezeigt.

**Code-Beispiel**

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

## Traffic-DIL im Google Tag-Manager (GTM) {#traffic-dil-gtm}

Richten Sie DIL mit einem GTM-Tag ein.

<!-- 

t_dil_google_tagmanager.xml

 -->

Bei diesem Verfahren wird davon ausgegangen, dass Sie über ein [!DNL Google Tag Manager]-Konto, einige Kenntnisse zu diesem Produkt und Ihre Audience Manager `dil.js`-Datei verfügen.

So senden Sie die Datei `dil.js` in GTM:

1. Erstellen Sie einen neuen Container oder öffnen Sie einen vorhandenen Container.
1. hinzufügen dem Container ein neues Tag.
1. Öffnen Sie das Tag, um es zu bearbeiten und:

   * Benennen Sie das Tag.
   * Wählen Sie **[!UICONTROL Custom HTML Tag]** aus der Dropdown-Liste **[!UICONTROL Tag Type]**.
   * Platzieren Sie im HTML-Feld den [!UICONTROL DIL]-Code (Bibliothek + den benutzerdefinierten Code) in den Skript-Tags `<script>DIL code</script>`.
   * Klicken **[!UICONTROL Save]**.

1. Veröffentlichen Sie den Container.
1. Erstellen Sie Container-Tag-Code und legen Sie ihn in Ihrem Bestand ab.

>[!MORELIKETHIS]
>
>* [Google Tag Manager-Hilfe](https://support.google.com/tagmanager#topic=3441530)
>* [Signale](../dil/dil-instance-methods.md#signals)
>* [Anforderungen an Präfixe für Schlüsselvariablen](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)


---
description: Codebeispiele und Beschreibungen für bestimmte DIL-Anwendungsfälle.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL-Anwendungsfälle und Code-Beispiele
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 2%

---

# DIL-Anwendungsfälle und Code-Beispiele{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>Ab Juli 2023 hat die Adobe die Entwicklung der [!DNL Data Integration Library (DIL)] und [!DNL DIL] -Erweiterung.
><br>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] Implementierung. Die Adobe wird sich jedoch nicht entwickeln [!DNL DIL] über diesen Punkt hinaus. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie.
><br>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) anstatt.

Codebeispiele und Beschreibungen für bestimmte DIL-Anwendungsfälle.

<!-- 

c_dil_use_case.xml

 -->

## Senden von Datenelementen an den Audience Manager mit DIL {#send-data-elements-dil}

Erstellen Sie eine Objektvariable, die Informationen zu Seitenelementen an Audience Manager sendet. Dies ist für die allgemeine Datenerfassung oder als Alternative zum Sammeln von Daten mit Analytics-Variablen nützlich.

<!-- 

c_dil_send_page_objects.xml

 -->

**Beschreibung**

Der folgende Code zeigt, wie Seitendaten erfasst und an den Audience Manager gesendet werden, mit dem [!UICONTROL DIL]. In diesen Beispielen wird eine Variable verwendet, um Datenelemente in einer flachen Liste oder in einem Array zu speichern. Denken Sie daran, Variablen als [Schlüssel-Wert-Paare](../reference/key-value-pairs-explained.md). Beachten Sie außerdem die `c_` -Präfix vor dem -Schlüssel im Schlüssel-Wert-Paar. Diese [erforderliches Präfix](../features/traits/trait-variable-prefixes.md) identifiziert Informationen als benutzerdefinierte Daten. Im ersten Beispiel müssen Sie manuell anhängen `c_` zum Schlüssel hinzu. Im zweiten Beispiel [!UICONTROL DIL] führt dies automatisch für Sie durch.

**Konsistente Werteigenschaften beibehalten**

Beachten Sie, dass die Werteigenschaften beim Übergeben von Daten gleich bleiben. Wenn Sie beispielsweise zwei identische Schlüssel mit unterschiedlichen Werten haben, hat der Wert des letzten Schlüssel-Wert-Paares Vorrang vor den vorhergehenden Wertobjekten. Beispiel: Übergeben von `color:blue` und `color:red` setzt den zurückgegebenen Wert auf Rot (überschreibt Blau).

**Beispiel 1: Senden von Daten als Schlüssel-Wert-Paare**

Dieses grundlegende Beispiel sendet Farb- und Preisdaten in Form von Schlüssel-Wert-Paaren an Audience Manager. Ihr Code könnte in etwa wie folgt aussehen:

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Beispiel 2: Senden von Daten in einem Objekt**

In diesem erweiterten Beispiel wird gezeigt, wie Daten in einem Objekt an Audience Manager gesendet werden. Wenn Sie mit dieser Methode arbeiten, [!UICONTROL DIL] ermöglicht die Übergabe eines Objekts als Funktionsparameter in die [!DNL signals()] -Methode. [!UICONTROL DIL] Ihr Code könnte in etwa wie folgt aussehen:

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

In diesem Fall wird die Variable `my_object` verwendet ein Array zum Speichern von Daten. Dieses Beispiel baut auf den Informationen auf, die von der oben empfohlenen Methode übergeben wurden, fügt jedoch eine zusätzliche Ebene hinzu, um einen Produkttyp und ein Modell aufzunehmen. Ihr Code könnte in etwa wie folgt aussehen:

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

Erfassen und Senden einer verweisenden URL an Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Diese Methode funktioniert nur, wenn Benutzer zwischen Seiten mit ähnlichen Protokollen (HTTP vs. HTTPS) wechseln. Beispielsweise behält der Browser eine verweisende URL bei, wenn Sie von einer sicheren Site zu einer anderen sicheren Site navigieren. Browser behalten die verweisende URL nicht bei, wenn Sie zwischen sicheren und unsicheren Sites wechseln. Dieses Verhalten ist eine normale Browserfunktionalität und kann nicht umgangen werden durch [!UICONTROL DIL].

**Code-Beispiel**

Ihr Code könnte in etwa wie folgt aussehen:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Suchmaschinentypen und Suchbegriffe erfassen {#capture-search-engine-types}

Senden Sie Informationen zum Suchmaschinentyp und zu Suchbegriffsuchen an Audience Manager.

>[!IMPORTANT]
>
>In diesem Abschnitt wird die alte Funktionalität beschrieben, die in den neuesten Versionen von DIL nicht unterstützt wird.

**Unterstützte Suchmaschinen**

Standardmäßig `DIL.getSearchReferrer` erkennt Suchvorgänge aus diesen Suchmaschinen (einschließlich internationaler Varianten):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Beschreibung**

Der folgende Code zeigt, wie Sie den Suchreferrer für eine der unterstützten Suchmaschinen erhalten. In diesem Fall nehmen wir an, dass ein Benutzer nach dem Begriff &quot;Wohnungen&quot;aus [!DNL Google] Kanada ( `www.google.ca`). Mit diesem Code können Sie diese Suchbegriffe erfassen und an den Audience Manager senden.

**Einfacher Code**

Grundlegender Code für den Abruf der verweisenden Stelle (aus `google.com`(z. B.) sieht wie folgt aus:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Beispiel für aufgelisteten Suchmaschinen-Code**

In diesem Fall nehmen wir an, dass ein Benutzer nach dem Begriff &quot;Wohnungen&quot;von gesucht hat [!DNL Google] Kanada ( `www.google.ca`). Beachten Sie, wie der Code die erforderlichen `c_` Parameter an Suchmaschine ( `c_se`) und Suchbegriff ( `c_st`). `c_` ist [erforderliches Präfix](../features/traits/trait-variable-prefixes.md) , der diese als kundendefinierte Variablen für den Audience Manager identifiziert.

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

**Beispiel für nicht aufgelisteten Suchmaschinen-Code**

In diesem Fall nehmen wir an, dass ein Benutzer nach dem Begriff &quot;Wohnungen&quot;von gesucht hat `dogpile.com`. weil [!DNL Dogpile] nicht standardmäßig unterstützt, können Sie DIL so konfigurieren, dass diese Suchmaschine erkannt wird und die Suchbegriffe an Audience Manager zurückgegeben werden. Ihr Code könnte in etwa wie folgt aussehen:

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

## Zuordnen von Schlüsselwerten zu anderen Schlüsseln {#map-key-values}

Verknüpfen Sie den Wert aus einem Schlüssel-Wert-Paar mit einem anderen Schlüssel.

<!-- 

c_dil_map_keys.xml

 -->

**Beschreibung**

In einem Schlüssel-Wert-Paar wird die `c_` an den Schlüssel angehängtes Präfix kennzeichnet das Signal als kundendefinierte Daten. Kundendefinierte Daten werden für das Targeting auf der spezifischen Site verwendet, die Daten bei einem Ereignisaufruf übergeben hat. Manchmal möchten Sie diese Informationen jedoch für alle Eigenschaften in Ihrem Audience Manager-Konto verfügbar machen. Zuordnen des Werts zu diesem Zweck `c_` Schlüssel-Wert-Paar zu einem Schlüssel auf Plattformebene. Ein Schlüssel auf Plattformebene ist mit dem Präfix `d_` und stellt das Signal für das Targeting in allen Eigenschaften in Ihrem Konto zur Verfügung.

Beispiel: Sie erfassen Postleitzahlendaten von einer bestimmten Site, möchten sie jedoch auf alle Eigenschaften Ihres Audience Managers ausrichten. Um die Postleitzahl auf Plattformebene verfügbar zu machen, können Sie Ihren kundendefinierten ZIP-Code-Schlüssel (z. B. `c_zip`) zu einem für die Plattform definierten Schlüssel hinzu, wie unten dargestellt.

**Code-Beispiel**

Ihr Code könnte in etwa wie folgt aussehen:

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

## Traffic-DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

Richten Sie DIL mit einem GTM-Tag ein und bedienen Sie es.

<!-- 

t_dil_google_tagmanager.xml

 -->

Diese Vorgehensweise setzt voraus, dass Sie über [!DNL Google Tag Manager] -Konto, einige Kenntnisse über dieses Produkt und Ihren Audience Manager `dil.js` -Datei.

Um den Traffic der `dil.js` -Datei in GTM:

1. Erstellen Sie einen neuen Container oder öffnen Sie einen vorhandenen Container.
1. Fügen Sie dem Container ein neues Tag hinzu.
1. Öffnen Sie das Tag, um es zu bearbeiten, und:

   * Benennen Sie das Tag.
   * Auswählen **[!UICONTROL Custom HTML Tag]** von **[!UICONTROL Tag Type]** Dropdown-Liste.
   * Platzieren Sie im Feld HTML die [!UICONTROL DIL] Code (Bibliothek und benutzerdefinierter Code) innerhalb von Skript-Tags `<script>DIL code</script>`.
   * Klicken **[!UICONTROL Save]**.

1. Veröffentlichen Sie den Container.
1. Generieren Sie Container-Tag-Code und platzieren Sie ihn in Ihrem Inventar.

>[!MORELIKETHIS]
>
>* [Google Tag Manager-Hilfezentrum](https://support.google.com/tagmanager#topic=3441530)
>* [Signale](../dil/dil-instance-methods.md#signals)
>* [Anforderungen an Präfixe für Schlüsselvariablen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

---
description: Code-Beispiele und Beschreibungen für bestimmte DIL-Anwendungsfälle.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL-Anwendungsfälle und Code-Beispiele
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# DIL-Anwendungsfälle und Code-Beispiele{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung des [!DNL Data Integration Library (DIL)] und der [!DNL DIL] eingestellt.
>
>Bestehende Kundinnen und Kunden können ihre [!DNL DIL] Implementierung weiterhin nutzen. Allerdings wird sich Adobe nicht über diesen Punkt hinaus [!DNL DIL] entwickeln. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) auf ihre langfristige Datenerfassungsstrategie hin zu überprüfen.
>
>Kunden, die nach Juli 2023 neue Datenerfassungsintegrationen implementieren möchten, sollten stattdessen [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) verwenden.

Code-Beispiele und Beschreibungen für bestimmte DIL-Anwendungsfälle.

<!-- 

c_dil_use_case.xml

 -->

## Senden von Datenelementen an Audience Manager mit DIL {#send-data-elements-dil}

Erstellen Sie eine Objektvariable, die Informationen zu Seitenelementen an den Audience Manager sendet. Dies ist für die allgemeine Datenerfassung oder als Alternative zur Datenerfassung mit Analytics-Variablen nützlich.

<!-- 

c_dil_send_page_objects.xml

 -->

**Beschreibung**

Der folgende Code veranschaulicht, wie Seitendaten erfasst und mit [!UICONTROL DIL] an den Audience Manager gesendet werden. In diesen Beispielen wird eine Variable verwendet, um Datenelemente in einer flachen Liste oder einem Array zu speichern. Denken Sie daran, Variablen als „Schlüssel[Wert-Paare“ ](../reference/key-value-pairs-explained.md). Beachten Sie außerdem das `c_` Präfix vor dem Schlüssel im Schlüssel-Wert-Paar. Dieses [erforderliche Präfix](../features/traits/trait-variable-prefixes.md) kennzeichnet Informationen als benutzerdefinierte Daten. Im ersten Beispiel müssen Sie `c_` manuell an den Schlüssel anhängen. Im zweiten Beispiel erledigt [!UICONTROL DIL] dies automatisch für Sie.

**Werteigenschaften konsistent halten**

Denken Sie daran, die Werteigenschaften beim Übergeben von Daten unverändert zu lassen. Wenn Sie beispielsweise zwei identische Schlüssel mit unterschiedlichen Werten haben, hat der Wert des letzten Schlüssel-Wert-Paares Vorrang vor den vorangehenden Wert-Objekten. Wenn Sie beispielsweise `color:blue` und `color:red` übergeben, wird der zurückgegebene Wert auf rot gesetzt (Blau wird überschrieben).

**Beispiel 1: Senden von Daten als Schlüssel-Wert-Paare**

Dieses Grundbeispiel sendet Farb- und Preisdaten in Form von Schlüssel-Wert-Paaren an den Audience Manager. Ihr Code könnte in etwa wie folgt aussehen:

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals(&lbrace; 
   c_color:"blue", 
   c_price:"900" 
&rbrace;); 
sample_dil.api.submit();
</code></pre>

**Beispiel 2: Senden von Daten in einem -Objekt**

Dieses erweiterte Beispiel zeigt, wie Daten in einem -Objekt an den -Audience Manager gesendet werden. Bei der Arbeit mit dieser Methode können Sie [!UICONTROL DIL] ein -Objekt als Funktionsparameter in die [!DNL signals()]-Methode übergeben. [!UICONTROL DIL] Ihr Code könnte in etwa wie folgt aussehen:

<pre class="java"><code>
var my_object = &lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Beispiel 3: Senden von Seitendaten in einem Array**

In diesem Fall verwendet die Variable `my_object` ein Array zum Speichern von Daten. Dieses Beispiel baut auf den Informationen auf, die von der oben empfohlenen Methode übergeben werden, fügt jedoch eine zusätzliche Ebene hinzu, um einen Produkttyp und ein Modell aufzunehmen. Ihr Code könnte in etwa wie folgt aussehen:

<pre class="java"><code>
var my_objects = &lbrack;&lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;, &lbrace; 
   type : "acura", 
   model : "tl" 
&rbrace;&rbrack;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
&lbrace; 
    sample_dil.api.signals(my_objects[i], "c_"); 
&rbrace; 
sample_dil.api.submit();
</code></pre>

## Verweisende URL erfassen {#capture-referring-url}

Erfassen Sie eine verweisende URL und senden Sie sie an den Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Diese Methode funktioniert nur, wenn Benutzende zwischen Seiten mit ähnlichen Protokollen (HTTP vs. HTTPS) wechseln. Beispielsweise behält der Browser eine verweisende URL bei, wenn Sie von einer sicheren Website zu einer anderen sicheren Website navigieren. Browser behalten die verweisende URL nicht bei, wenn Sie zwischen sicheren und unsicheren Websites wechseln. Dieses Verhalten ist eine normale Browser-Funktionalität und kann von [!UICONTROL DIL] nicht umgangen werden.

**Codebeispiel**

Ihr Code könnte in etwa wie folgt aussehen:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Erfassen von Suchmaschinentypen und Keyword-Suchbegriffen {#capture-search-engine-types}

Senden Sie Informationen über den Suchmaschinentyp und die Keyword-Suche an den Audience Manager.

>[!IMPORTANT]
>
>In diesem Abschnitt werden ältere Funktionen beschrieben, die von den neuesten DIL-Versionen nicht unterstützt werden.

**Unterstützte Suchmaschinen**

Standardmäßig erkennt `DIL.getSearchReferrer` die Suche über diese Suchmaschinen (einschließlich internationaler Varianten):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Beschreibung**

Der folgende Code zeigt, wie Sie den Such-Referrer für eine der unterstützten Suchmaschinen erhalten. Nehmen wir in diesem Fall an, ein Benutzer sucht nach dem Begriff „Wohnungen“ aus [!DNL Google] Canada ( `www.google.ca`). Dieser Code hilft Ihnen, diese Suchbegriffe zu erfassen und an den Audience Manager zu senden.

**Basis-Code**

Der Basis-Code zum Abrufen des Such-Referrers (z. B. aus `google.com`) sieht wie folgt aus:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Listed Search Engine Code Sample**

Nehmen wir in diesem Fall an, dass ein Benutzer nach dem Begriff „Wohnungen“ aus [!DNL Google] Canada (`www.google.ca`) gesucht hat. Beachten Sie, dass der Code den erforderlichen `c_`-Parameter Suchmaschine ( `c_se`) und Suchbegriff ( `c_st`) voranstellt. `c_` ist ein [erforderliches Präfix](../features/traits/trait-variable-prefixes.md) das diese als kundendefinierte Variablen für den Audience Manager identifiziert.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

**Code-Beispiel für nicht aufgeführte Suchmaschinen**

Nehmen wir in diesem Fall an, dass ein Benutzer in `dogpile.com` nach dem Begriff „Heime“ gesucht hat. Da [!DNL Dogpile] standardmäßig nicht unterstützt wird, können Sie DIL so konfigurieren, dass diese Suchmaschine erkannt wird und die Suchbegriffe an den Audience Manager zurückgegeben werden. Ihr Code könnte in etwa wie folgt aussehen:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, &lbrace;  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
&rbrace;); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

## Schlüsselwerte anderen Schlüsseln zuordnen {#map-key-values}

Verknüpfen Sie den Wert aus einem Schlüssel-Wert-Paar mit einem anderen Schlüssel.

<!-- 

c_dil_map_keys.xml

 -->

**Beschreibung**

In einem Schlüssel-Wert-Paar identifiziert das an den Schlüssel angehängte `c_`-Präfix das Signal als kundendefinierte Daten. Kundendefinierte Daten werden für die Zielgruppenbestimmung auf der spezifischen Site verwendet, die Daten bei einem Ereignisaufruf übergeben hat. Manchmal möchten Sie jedoch, dass diese Informationen für alle Eigenschaften in Ihrem Audience Manager-Konto verfügbar sind. Ordnen Sie dazu den Wert in einem Schlüssel-Wert-Paar auf `c_` einem Schlüssel auf Plattformebene zu. Ein Schlüssel auf Plattformebene hat das Präfix `d_` und stellt das Signal für das Targeting für alle Eigenschaften in Ihrem Konto zur Verfügung.

Beispielsweise erfassen Sie Postleitzahldaten von einer bestimmten Website, möchten sie jedoch auf alle Audience Manager-Eigenschaften ausrichten. Um die Postleitzahl auf Plattformebene verfügbar zu machen, können Sie Ihren kundendefinierten Postleitzahlschlüssel (z. B. `c_zip`) einem von Platform definierten Schlüssel zuordnen, wie unten dargestellt.

**Codebeispiel**

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

Einrichten und Bereitstellen von DIL mit einem GTM-Tag.

<!-- 

t_dil_google_tagmanager.xml

 -->

Bei diesem Verfahren wird davon ausgegangen, dass Sie über ein [!DNL Google Tag Manager]-Konto, einige Kenntnisse über dieses Produkt und Ihre Audience Manager-`dil.js` verfügen.

Traffic der `dil.js` in GTM:

1. Erstellen Sie einen neuen Container oder öffnen Sie einen vorhandenen Container.
1. Fügen Sie dem Container ein neues Tag hinzu.
1. Öffnen Sie das Tag, um es zu bearbeiten, und:

   * Benennen Sie das Tag.
   * Wählen Sie **[!UICONTROL Custom HTML Tag]** aus der Dropdown-Liste **[!UICONTROL Tag Type]** aus.
   * Platzieren Sie im Feld HTML den [!UICONTROL DIL]-Code (Bibliothek + benutzerdefinierter Code) in der `<script>DIL code</script>` Skript-Tags .
   * Klicken Sie auf **[!UICONTROL Save]**.

1. Publish - Der Container.
1. Erstellen Sie einen Container-Tag-Code und platzieren Sie ihn im Inventar.

>[!MORELIKETHIS]
>
>* [Hilfe-Center für den Google Tag-Manager](https://support.google.com/tagmanager#topic=3441530)
>* [Signale](../dil/dil-instance-methods.md#signals)
>* [Anforderungen an Präfixe für Schlüsselvariablen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html?lang=de#prefix-requirements-for-key-variables)

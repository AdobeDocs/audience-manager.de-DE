---
description: Codebeispiele und Beschreibungen für spezifische DIL-Verwendungen.
seo-description: Codebeispiele und Beschreibungen für spezifische DIL-Verwendungen.
seo-title: DIL-Anwendungsfälle und Codebeispiele
solution: Audience Manager
title: DIL-Anwendungsfälle und Codebeispiele
uuid: 27995 c 2 d -6572-438 e-af 99-b 5477 f 090 ae 9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# DIL-Anwendungsfälle und Codebeispiele{#dil-use-cases-and-code-samples}

Codebeispiele und Beschreibungen für spezifische DIL-Verwendungen.

<!-- 

c_dil_use_case.xml

 -->

## Datenelemente mit DIL an Audience Manager senden {#send-data-elements-dil}

Erstellen Sie eine Objektvariable, die Informationen zu Seitenelementen an Audience Manager sendet. Dies ist für allgemeine Datenerfassung oder als Alternative zur Datenerfassung mit Analytics-Variablen nützlich.

<!-- 

c_dil_send_page_objects.xml

 -->

**Beschreibung**

Der folgende Code zeigt, wie Seitendaten erfasst und an Audience Manager gesendet [!UICONTROL DIL]werden. Diese Beispiele verwenden eine Variable, um Datenelemente in einer einfachen Liste oder in einem Array festzuhalten. Variablen als [Schlüssel-Wert-Paare speichern](../reference/key-value-pairs-explained.md). Beachten Sie außerdem das `c_` Präfix vor dem Schlüssel im Schlüssel-Wert-Paar. Dieses [erforderliche Präfix](../features/traits/trait-variable-prefixes.md) identifiziert Informationen als benutzerdefinierte Daten. Im ersten Beispiel müssen Sie den Schlüssel manuell anhängen `c_` . Im zweiten Beispiel wird [!UICONTROL DIL] dies automatisch für Sie ausgeführt.

**Werteigenschaften konsistent beibehalten**

Denken Sie daran, die Werteigenschaften beim Übergeben von Daten unverändert beizubehalten. Wenn Sie beispielsweise zwei identische Schlüssel mit unterschiedlichen Werten haben, hat der Wert des letzten Schlüssel-Wert-Paars Vorrang vor den vorhergehenden Wertobjekten. Wenn Sie z. B. den zurückgegebenen `color:blue` Wert an Rot übergeben und den zurückgegebenen Wert auf rot `color:red` setzen (blau).

**Beispiel 1: Daten als Schlüssel-Wert-Paare senden**

Dieses Basisbeispiel sendet Farb- und Preisdaten in Form von Schlüssel/Wert-Paaren an Audience Manager. Ihr Code könnte wie folgt aussehen:

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
sample_ dil. api. signs ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**Beispiel 2: Daten in einem Objekt senden**

Dieses erweiterte Beispiel zeigt, wie Daten in einem Objekt an Audience Manager gesendet werden. Wenn Sie mit dieser Methode arbeiten, [!UICONTROL DIL] können Sie ein Objekt als Funktionsparameter in die [!DNL signals()] Methode übergeben. [!UICONTROL DIL] Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>var my_ object = { 
 color: " blue ", 
 Preis: " 900 "}; 
 
var sample_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
//Load Sie das Objekt und hängen Sie "c_" an alle Schlüssel in den Schlüssel/Wert-Paaren an und senden Sie Daten an audiencemanager. 
sample_ dil. api. signals (my_ object, "c_"). submit ();</code>
</pre>

**Beispiel 3: Senden von Seitendaten in einem Array**

In diesem Fall verwendet die Variable `my_object` ein Array, um Daten aufzunehmen. Dieses Beispiel baut auf den Informationen auf, die von der oben genannten Methode übergeben wurden, fügt jedoch eine zusätzliche Ebene hinzu, um einen Produkttyp und ein Modell aufzunehmen. Ihr Code könnte wie folgt aussehen:

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
 sample_ dil. api. signals (my_ objects [i], "c_"); 
} 
sample_ dil. api. submit ();</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [signalisiert](../dil/dil-instance-methods.md#signals)


## Verweisende URL erfassen {#capture-referring-url}

Erfassen und senden Sie eine verweisende URL an den Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Diese Methode funktioniert nur, wenn Benutzer zwischen Seiten mit ähnlichen Protokollen (HTTP vs. HTTPS) wechseln. Beispielsweise behält der Browser eine verweisende URL bei, wenn Sie von einer sicheren Site zu einer anderen sicheren Site navigieren. Browser behalten die verweisende URL nicht bei, wenn Sie zwischen sicheren und nicht sicheren Sites wechseln. Dies ist eine normale Browserfunktion und kann nicht umgangen [!UICONTROL DIL]werden.

**Codebeispiel**

Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
adobe_ dil. api. sign({d_ referer: document. referrer}). submit ();</code>
</pre>

## Suchmaschinentypen und Suchbegriffsuchbegriffe erfassen {#capture-search-engine-types}

Senden Sie Informationen über Suchmaschinentypen und Suchbegriffssuchen in Audience Manager.

>[!IMPORTANT]
>
>In diesem Abschnitt wird die Legacy-Funktionalität beschrieben, die in den aktuellen Versionen von DIL nicht unterstützt wird.

**Unterstützte Suchmaschinen**

`DIL.getSearchReferrer` Erkennt standardmäßig Suchvorgänge aus diesen Suchmaschinen (einschließlich internationale Variationen):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Beschreibung**

Der folgende Code zeigt, wie der Suchreferrer für alle unterstützten Suchmaschinen abgerufen wird. In diesem Fall gehen wir davon aus, dass ein Benutzer nach [!DNL Google] Kanada ( `www.google.ca`) nach dem Begriff "Hauszimmer" gesucht hat. Dieser Code hilft Ihnen dabei, diese Suchbegriffe zu erfassen und an Audience Manager zu senden.

**Einfacher Code**

Der Basiscode zum Abrufen des Suchverweises (z `google.com`. B. aus) sieht wie folgt aus:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Beispiel für eine Liste der Suchmaschinen-Codebeispiele**

In diesem Fall wird angenommen, dass ein Benutzer nach dem Begriff "Hauszimmer" aus [!DNL Google] Kanada ( `www.google.ca`) gesucht hat. Beachten Sie, wie der Code den erforderlichen `c_` Parameter für Suchmaschinen ( `c_se`) und Suchbegriff ( `c_st`) vorsetzt. `c_` ist ein [erforderliches Präfix](../features/traits/trait-variable-prefixes.md) , das diese als kundendefinierte Variablen in Audience Manager bezeichnet.

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

In diesem Fall wird angenommen, dass ein Benutzer nach dem Begriff "homes" gesucht `dogpile.com`hat. Da [!DNL Dogpile] Sie standardmäßig nicht unterstützt werden, können Sie DIL konfigurieren, um diese Suchmaschine zu erkennen und die Suchbegriffe in Audience Manager zurückzugeben. Ihr Code könnte wie folgt aussehen:

<pre class="java"><code>var adobe_ dil = DIL. create ({partner: "<i>partnername</i>"}); 
var search_ referrer = DIL. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
 Queryparam: " q "}); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signs ({ 
 c_ se: se. name, 
 c_ st: se. keywords 
 }). submit (); 
}</code>
</pre>

## Schlüsselwerte anderen Tasten zuordnen {#map-key-values}

Verknüpfen Sie den Wert von einem Schlüssel-Wert-Paar mit einem anderen Schlüssel.

<!-- 

c_dil_map_keys.xml

 -->

**Beschreibung**

In einem Schlüssel-Wert-Paar erkennt das `c_` an den Schlüssel angehängte Präfix das Signal als kundendefinierte Daten. Kundendefinierte Daten werden für das Targeting auf der spezifischen Site verwendet, die Daten an einen Ereignisaufruf übergeben hat. Manchmal möchten Sie diese Informationen jedoch auch für alle Eigenschaften in Ihrem Audience Manager-Konto verfügbar machen. Dazu ordnen Sie den Wert in einem `c_` Schlüssel-Wert-Paar einem Schlüssel auf Plattformebene zu. Ein Schlüssel auf Plattformebene ist `d_` mit dem Präfix versehen und stellt das Signal für das Targeting für alle Eigenschaften in Ihrem Konto zur Verfügung.

Beispiel: Sie erfassen ZIP-Codedaten aus einer bestimmten Site, möchten sie jedoch allen Ihren Audience Manager-Eigenschaften zuordnen. Um die Postleitzahl auf Plattformebene verfügbar zu machen, können Sie Ihren kundendefinierten ZIP-Codeschlüssel (z. B `c_zip`.) einer Plattform-definierten Plattform zuordnen, wie unten dargestellt.

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


## Traffic-DIL im Google Tag Manager (GTM) {#traffic-dil-gtm}

Richten Sie DIL mit einem GTM-Tag ein und stellen Sie es bereit.

<!-- 

t_dil_google_tagmanager.xml

 -->

Bei diesem Vorgang wird angenommen, dass Sie über ein [!DNL Google Tag Manager] Konto, ein Teil dieses Produkts und Ihre Audience Manager `dil.js` -Datei verfügen.

So erstellen Sie die `dil.js` Datei in GTM:

1. Erstellen Sie einen neuen Container oder öffnen Sie einen vorhandenen Container.
1. Fügen Sie dem Container ein neues Tag hinzu.
1. Öffnen Sie das Tag, um es zu bearbeiten und zu bearbeiten:

   * Geben Sie dem Tag einen Namen.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * Platzieren Sie im HTML-Feld den [!UICONTROL DIL] Code (Bibliothek + benutzerdefinierter Code) in Skript-Tags `<script>DIL code</script>`.
   * Klicken Sie auf **[!UICONTROL Save]**.

1. Veröffentlichen Sie den Behälter.
1. Erstellen Sie Container-Tag-Code und platzieren Sie ihn in Ihrem Bestand.

>[!MORE_ LIKE_ THIS]
>
>* [Hilfe Center für Google Tag Manager](https://support.google.com/tagmanager#topic=3441530)


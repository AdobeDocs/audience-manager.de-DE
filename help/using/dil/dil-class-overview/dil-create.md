---
description: Erstellt eine partnerspezifische DIL-Instanz.
seo-description: Erstellt eine partnerspezifische DIL-Instanz.
seo-title: DIL create
solution: Audience Manager
title: DIL create
uuid: 6 e 054600-703 c -4 a 97-af 2 a -8207 c 50013 db
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL-Methode{#dil-create}

## DIL create {#dil-create-new}

Erstellt eine partnerspezifische [!UICONTROL DIL] Instanz.

**Funktionssignatur:**`DIL.create: function (initConfig) {}`

**Initconfig Elemente**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>Die `visitorService` Eigenschaft ist *immer* erforderlich. Andere hier aufgeführte Eigenschaften sind optional, sofern nicht anders angegeben.

`initConfig` akzeptiert die folgenden Elemente:

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Durch diese Eigenschaft wird die Container-ID festgelegt, die von <span class="keyword">Audience Manager</span> für ID-Synchronisationen verwendet wird. Sie würden <code> containernsid </code> einstellen, wenn <span class="wintitle"> Sie über DIL </span> auf mehreren Sites bereitgestellt haben. Jede dieser Sites verfügt über eigene Container-ID und ID-Synchronisierungen. Wenn Sie nur 1 Site haben, ist die Container-ID standardmäßig 0, und Sie müssen dies nicht richtig festlegen. Wenden Sie sich an Ihren Berater, um eine Liste Ihrer Sites und Container-IDs abzurufen. </p> <p>Im <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID-Dienst </a>entspricht die Eigenschaft <code> idsynccontainerid </code><code> containernsid </code> in <span class="wintitle"> DIL </span>. Beachten Sie Folgendes, wenn <span class="wintitle"> Sie DIL </span><i>und</i> den ID-Dienst über mehrere Sites hinweg verwenden: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Legen Sie für jede Site dieselben Behälter-IDs auf <code> containernsid </code> und <code> idsynccontainerid </code>fest. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Sowohl <span class="wintitle"> DIL </span> als auch der ID-Dienst versuchen, ID an unseren Datenerfassungs-iframe zu senden. Der iframe stellt jedoch sicher, dass <span class="wintitle"> DIL </span> keine ID-Synchronisierung auslösen wird. Dies verhindert Duplizierung. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Nur <span class="wintitle"> DIL </span> sendet Daten an ein <a href="../../features/destinations/destinations.md"> URL-Ziel </a>. </li> 
     </ul> </p> <p>Siehe auch <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> idsynccontainerid </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Declaredid </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Sendet die <a href="../../features/declared-ids.md"> deklarierten ID-Variablen </a> bei jedem Ereignisaufruf an <span class="keyword"> Audience Manager </span>. </p> 
    </draft-comment> <p> <code> Delcaredid </code> wird verwendet, um Folgendes zu übermitteln: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: Ihnen von <span class="keyword"> Audience Manager </span>zugewiesene Datenpartner-ID. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Ihre eindeutige ID für einen Benutzer. </li> 
    </ul> <p> <p>Wichtig: Verwenden Sie nur nicht codierte Werte für Ihre IDs. Ein Codieren der führt zu doppelt codierten Identifikatoren. </p> </p> <p> <p>Hinweis: Wenn Sie den <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID-Dienst </a>verwenden, legen Sie Kunden-IDs mit der <code> Methode setcustomerids </code> statt <span class="wintitle"> DIL </span>fest. Siehe <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Kunden-IDs und Authentifizierungsstatus </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Delayalluntilwindowload </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Wenn "true" , werden alle Anforderungen (IFRAME, Ereignisaufrufe, ID-Synchronisierung und Destinationing) aus der Ausführung entfernt, bis das <code> Seitenladeereignis </code> ausgelöst wird. Der Standardwert ist <code> "false </code>«. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Disabledeclareducuidcookie </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> False ist standardmäßig falsch, d. h. <span class="keyword"> Audience Manager </span> setzt ein Cookie in der Domäne des Partners ein (setzt ein Erstanbieter-Cookie ein). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig: Dieses Element wurde mit <span class="wintitle"> DIL </span> -Version 8.0 veraltet (August 2018 veröffentlicht). Verwenden Sie stattdessen die Funktion <code> visitor. disableidsyncs </code><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"></a> im Experience Cloud ID-Dienst. </p> </p> <p> Wenn <code> "true </code>«, wird der destination publishing IFRAME nicht an die DOM- oder Auslösen-Ziele angehängt. Der Standardwert ist <code> "false </code>«. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig: Dieses Element wurde mit <span class="wintitle"> DIL </span> -Version 8.0 veraltet (August 2018 veröffentlicht). Verwenden Sie stattdessen die Funktion <code> visitor. disableidsyncs </code><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"></a> im Experience Cloud ID-Dienst. </p> </p> <p>Deaktiviert die ID-Synchronisierung. Sie müssen die ID-Synchronisierung deaktivieren, wenn Sie DIL v 6.2 + und den Besucher-ID-Dienst verwenden. Die <code> Funktion visitorservice </code> (siehe Beispielcode unten) übernimmt diesen Vorgang. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Enableerrorreporting </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Legen Sie <code> "true </code> «fest, um die Fehlerberichterstellung für alle <span class="wintitle"> DIL </span> -Instanzen auf der Seite zu aktivieren. Funktioniert nur mit Boolescher <code> True </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig: Dieses Element wurde mit <span class="wintitle"> DIL </span> -Version 8.0 veraltet (August 2018 veröffentlicht). Verwenden Sie stattdessen die Funktion <code> visitor. idsyncssluseakamai </code><a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"></a> im Experience Cloud ID-Dienst. </p> </p> <p> Legt fest, ob die Vorlage für die Zielveröffentlichung bei HTTPS-Verbindungen mit Akamai ausgeführt werden soll. Aktivierung pro Partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Zuordnungen </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Verbindet den Wert von einem Schlüssel-Wert-Paar zu einem anderen. Siehe <a href="../../dil/dil-use-cases.md#map-key-values"> Zuordnen von Schlüsselwerten zu anderen Schlüsseln </a>. Version 2.4 veröffentlicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Erforderlich. </p> <p>Das <code> Namespace </code> -Schlüssel-Wert-Paar enthält Ihre <span class="keyword"> Experience Cloud </span> -Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im <span class="wintitle"> Administrationsabschnitt </span> des <span class="keyword"> Experience Cloud </span> -Dashboards. Sie benötigen Administratorrechte, um dieses Dashboard anzuzeigen. Siehe Häufig gestellte Fragen <a href="../../faq/faq-features.md"></a> zu Produktfunktionen und <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> -funktionen - Benutzerverwaltung und FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Partner </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Erforderlich. </p> <p> Vom <span class="keyword"> Audience Manager </span>bereitgestellter Partnername. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Removefinishedscriptsandcallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Entfernt Skripten und Callbacks. Der Standardwert ist <code> "False </code>«. Gilt nur für die aktuelle <span class="wintitle"> DIL </span> -Instanz. Version 3.3 veröffentlicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Uuidcookie </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Setzt ein Cookie mit der eindeutigen Benutzer-ID, die von <span class="keyword"> Audience Manager zurückgegeben </span>wird. Siehe <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidcookie-Eigenschaften </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Visitorservice </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Erforderlich mit <span class="wintitle"> DIL </span> 6.2 oder höher. </p> <p> DIL nutzt die Funktion <code> setcustomerids </code> im <span class="wintitle"> Experience Cloud ID-Dienst </span> , um deklarierte IDs in <span class="keyword"> Audience Manager </span>zu übergeben. Weitere Informationen finden Sie unter <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external">Kunden-IDs und Authentifizierungszustände.</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispielcode**

Ein [!UICONTROL DIL] Beispielaufruf könnte wie folgt aussehen:

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

Eine erfolgreiche Antwort gibt die [!UICONTROL DIL] Instanz zurück. Ein nicht erfolgreicher Versuch gibt ein Fehlerobjekt zurück (nicht ausgelöst), wenn Ihr Code falsch konfiguriert ist oder wenn ein Fehler auftritt.

## Uuidcookie-Eigenschaften {#uuidcookie-props}

Definiert die von der `uuidCookie` Variablen verwendeten Eigenschaften. Diese Variable ist Teil der `DIL.create` Methode.

`uuidCookie` hat die folgenden Eigenschaften:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Name | Beschreibung |
|---|---|
| `name` | Der Name des Cookies ( `aam_did` standardeinstellung). |
| `days` | Cookie-Lebensdauer (standardmäßig 100 Tage). |
| `path` | Cookie-Pfad, z. B. `'/test'` ( `/` standardwert). |
| `domain` | Die Domäne, in der sich das Cookie befindet, z. B. `'adobe.com'` ( `'.'+document.domain` standardwert). |
| `secure` | Legt fest, dass nur Daten über eine HTTPS-Verbindung gesendet werden. |

## Visitorservice-Eigenschaften {#visitor-service-props}

Definiert die von der `visitorService` Variablen verwendeten Eigenschaften. Diese Variable ist Teil der `DIL.create` Methode.

`visitorService` hat die folgenden Eigenschaften:

| Name | Typ | Beschreibung |
|---|---|---|
| `namespace` | Zeichenfolge | Erforderlich. Stellt die Experience Cloud-Organisations-ID dar. Dies ist für Experience Cloud Core Service-Funktionen erforderlich. Derselbe Parameter, der zur Instanziierung der Besucher-ID-Funktion verwendet wird. |

**Codebeispiel:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```

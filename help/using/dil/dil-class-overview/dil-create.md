---
description: Erstellt eine partnerspezifische DIL-Instanz.
seo-description: Erstellt eine partnerspezifische DIL-Instanz.
seo-title: Erstellen einer DIL
solution: Audience Manager
title: Erstellen einer DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 12%

---


# DIL create-Methode{#dil-create}

## Erstellen einer DIL {#dil-create-new}

Erstellt eine partner-spezifische [!UICONTROL DIL] Instanz.

**Funktionssignatur:** `DIL.create: function (initConfig) {}`

**initConfig-Elemente**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>Die `visitorService` Eigenschaft ist *immer* erforderlich. Andere hier aufgelistete Eigenschaften sind optional, sofern nicht anders angegeben.

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
   <td colname="col3"> <p>Durch diese Eigenschaft wird die Container-ID festgelegt, die von <span class="keyword">Audience Manager</span> für ID-Synchronisationen verwendet wird. Sie würden festlegen, <code> containerNSID </code> wenn Sie über mehrere Sites hinweg <span class="wintitle"> DIL </span> bereitgestellt haben. Jede dieser Sites verfügt über eine eigene Container-ID und ID-Synchronisierung. Wenn Sie nur eine Site haben, ist die Container-ID standardmäßig 0, und Sie müssen dies nicht korrekt festlegen. Wenden Sie sich an Ihren Berater, um eine Liste Ihrer Sites und ihrer Container-IDs zu erhalten. </p> <p>Im <a href="https://docs.adobe.com/content/help/de-DE/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform-Identitätsdienst </a>entspricht die Eigenschaft <code> idSyncContainerID </code> dem Wert <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Beachten Sie Folgendes, wenn Sie <span class="wintitle"> DIL </span> und <i></i> den ID-Dienst über mehrere Sites hinweg verwenden: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Stellen Sie für jede Site dieselben Container-IDs ein <code> containerNSID </code> und <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Sowohl <span class="wintitle"> DIL </span> als auch der ID-Dienst versuchen, ID-Synchronisierungen an unseren Datenerfassungs-iFrame zu senden. Der iFrame stellt jedoch sicher, dass <span class="wintitle"> DIL </span> keine ID-Synchronisierung auslöst. Dadurch wird Doppelarbeit vermieden. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Nur <span class="wintitle"> DIL </span> sendet Daten an ein <a href="../../features/destinations/destinations.md"> URL-Ziel </a>. </li> 
     </ul> </p> <p>Siehe auch <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> wird verwendet, um </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: Ihnen vom <span class="keyword"> Audience Manager zugewiesene Datenpartner-ID </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Ihre eindeutige ID für einen Benutzer. </li> 
    </ul> <p> <p>Wichtig:  Verwenden Sie nur nicht kodierte Werte für Ihre IDs. Ein Codieren der führt zu doppelt codierten Identifikatoren. </p> </p> <p> <p>Hinweis:  Wenn Sie den <a href="https://docs.adobe.com/content/help/de-DE/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform-Identitätsdienst verwenden, </a>stellen Sie Kunden-IDs mit der <code> setCustomerIDs </code> Methode anstelle von <span class="wintitle"> DIL ein </span>. See <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Wenn "true", werden alle Anforderungen (IFRAME, Ereignis-Aufrufe, ID-Synchronisierung und Ziel) erst ausgeführt, wenn das <code> Page Load </code> Ereignis ausgelöst wird. Standardwert ist <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Standardmäßig ist "false"festgelegt, d. h. <span class="keyword"> Audience Manager </span> setzt ein Cookie in der Domäne des Partners (setzt ein Erstanbieter-Cookie). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig:  Dieses Element wurde mit <span class="wintitle"> DIL </span> Version 8.0 (veröffentlicht im August 2018) nicht mehr unterstützt. Verwenden Sie stattdessen die <code> visitor.disableIdSyncs </code> Funktion <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> im Adobe Experience Platform-Identitätsdienst. </p> </p> <p> Wenn <code> true </code>dies der Fall ist, wird das Ziel für die Veröffentlichung von IFRAME nicht an das DOM- oder Feuerlöschziel angehängt. Standardwert ist <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig:  Dieses Element wurde mit <span class="wintitle"> DIL </span> Version 8.0 (veröffentlicht im August 2018) nicht mehr unterstützt. Verwenden Sie stattdessen die <code> visitor.disableIdSyncs </code> Funktion <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> im Adobe Experience Platform-Identitätsdienst. </p> </p> <p>Deaktiviert die ID-Synchronisierung. Sie müssen die ID-Synchronisierung deaktivieren, wenn Sie DIL v6.2+ und den Besucher-ID-Dienst verwenden. Die <code> visitorService </code> Funktion (siehe Beispielcode unten) kümmert sich um diesen Vorgang. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Auf <code> true </code> die Option "Fehler-Berichte"für alle <span class="wintitle"> DIL- </span> Instanzen auf der Seite einstellen. Funktioniert <code> true </code> nur mit Booleschem Wert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig:  Dieses Element wurde mit <span class="wintitle"> DIL </span> Version 8.0 (veröffentlicht im August 2018) nicht mehr unterstützt. Verwenden Sie stattdessen die <code> visitor.idSyncSSLUseAkamai </code> Funktion <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> </a> im Adobe Experience Platform-Identitätsdienst. </p> </p> <p> Legt fest, ob die Vorlage für die Zielveröffentlichung bei HTTPS-Verbindungen mit Akamai ausgeführt werden soll. Aktivierung pro Partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Verbindet den Wert zwischen einem Schlüssel-Wert-Paar und einem anderen. Siehe <a href="../../dil/dil-use-cases.md#map-key-values"> Schlüsselwerte anderen Schlüsseln zuordnen </a>. Herausgegeben mit v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Erforderlich. </p> <p>Das <code> namespace </code> Schlüssel-Wert-Paar enthält Ihre <span class="keyword"> Experience Cloud- </span> Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im <span class="wintitle"> Administrationsbereich </span> des <span class="keyword"> Experience Cloud- </span> Dashboards. Sie benötigen Administratorrechte, um dieses Dashboard Ansicht. Weitere Informationen finden Sie in den häufig gestellten Fragen zu <a href="../../faq/faq-features.md"> Produktfunktionen </a> und <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administration - Benutzerverwaltung und häufig gestellte Fragen </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Erforderlich. </p> <p> Name des Partners, wie vom <span class="keyword"> Audience Manager angegeben </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Entfernt Skripten und Rückrufe. Standardwert ist <code> False </code>. Gilt nur für die aktuelle <span class="wintitle"> DIL </span> -Instanz. Herausgegeben mit Version 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Legt ein Cookie mit der eindeutigen Benutzer-ID fest, die von <span class="keyword"> Audience Manager zurückgegeben wird </span>. Siehe <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uidCookie-Eigenschaften </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Erforderlich mit <span class="wintitle"> DIL </span> 6.2 oder höher. </p> <p> DIL nutzt die <code> setCustomerIDs </code> Funktion des <span class="wintitle"> Adobe Experience Platform-Identitätsdienstes, </span> um deklarierte IDs an den <span class="keyword"> Audience Manager weiterzuleiten </span>. Weitere Informationen finden Sie unter <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">Kunden-IDs und Authentifizierungszustände.</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispielcode**

Ein Beispielaufruf [!UICONTROL DIL] könnte wie folgt aussehen:

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

Eine erfolgreiche Antwort gibt die [!UICONTROL DIL] Instanz zurück. Bei einem fehlgeschlagenen Versuch wird ein Fehlerobjekt zurückgegeben (nicht ausgegeben), wenn Ihr Code falsch konfiguriert ist oder wenn ein Fehler auftritt.

## uuidCookie-Eigenschaften {#uuidcookie-props}

Definiert die von der `uuidCookie` Variablen verwendeten Eigenschaften. Diese Variable ist Teil der `DIL.create` Methode.

`uuidCookie` hat die folgenden Eigenschaften:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Name | Beschreibung |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | Cookie-Lebensdauer (standardmäßig 100 Tage). |
| `path` | Cookie-Pfad, z. B. `'/test'` ( `/` ist Standard). |
| `domain` | Die Domäne, in der das Cookie gesetzt wird, z. B. `'adobe.com'` ( `'.'+document.domain` Standard). |
| `secure` | Legt ein Flag fest, um nur Daten über eine HTTPS-Verbindung zu senden. |

## visitorService-Eigenschaften {#visitor-service-props}

Definiert die von der `visitorService` Variablen verwendeten Eigenschaften. Diese Variable ist Teil der `DIL.create` Methode.

`visitorService` hat die folgenden Eigenschaften:

| Name | Typ | Beschreibung |
|---|---|---|
| `namespace` | Zeichenfolge | Erforderlich. Stellt die Experience Cloud-Organisations-ID dar. Dies ist für die Experience Cloud-Core-Service-Funktionalität erforderlich. Derselbe Parameter, mit dem die Besucher-ID-Funktion instanziiert wird. |

**Code-Beispiel:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```

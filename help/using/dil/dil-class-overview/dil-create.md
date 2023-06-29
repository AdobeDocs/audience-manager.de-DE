---
description: Erstellt eine Partner-spezifische DIL-Instanz.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: Erstellen einer DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 9%

---

# DIL-Erstellungsmethode{#dil-create}

>[!WARNING]
>
>Ab Juli 2023 hat die Adobe die Entwicklung der [!DNL Data Integration Library (DIL)] und [!DNL DIL] -Erweiterung.
><br>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] Implementierung. Die Adobe wird sich jedoch nicht entwickeln [!DNL DIL] über diesen Punkt hinaus. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie.
><br>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) anstatt.

## Erstellen einer DIL {#dil-create-new}

Erstellt eine partner-spezifische [!UICONTROL DIL] -Instanz.

**Funktionssignatur:** `DIL.create: function (initConfig) {}`

**initConfig-Elemente**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>Die `visitorService` Eigenschaft ist *always* erforderlich. Andere hier aufgelistete Eigenschaften sind optional, sofern nicht anders angegeben.

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
   <td colname="col3"> <p>Durch diese Eigenschaft wird die Container-ID festgelegt, die von <span class="keyword">Audience Manager</span> für ID-Synchronisationen verwendet wird. Sie würden <code> containerNSID </code> wenn Sie <span class="wintitle"> DIL </span> über mehrere Sites hinweg bereitgestellt werden. Jede dieser Sites verfügt über eine eigene Container-ID und ID-Synchronisierungen. Wenn Sie nur eine Site haben, ist die Container-ID standardmäßig 0 und Sie müssen dies nicht ordnungsgemäß festlegen. Wenden Sie sich an Ihren Berater, um eine Liste Ihrer Sites und deren Container-IDs zu erhalten. </p> <p>Im <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, die Eigenschaft <code> idSyncContainerID </code> entspricht <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Beachten Sie Folgendes, wenn Sie <span class="wintitle"> DIL </span> <i>und</i> den ID-Dienst über mehrere Sites hinweg: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Setzen Sie für jede Site dieselben Container-IDs auf <code> containerNSID </code> und <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Beide <span class="wintitle"> DIL </span> und der ID-Dienst versucht, ID-Synchronisationen an unseren Datenerfassungs-iFrame zu senden. Der iFrame stellt jedoch sicher, dass <span class="wintitle"> DIL </span> löst keine ID-Synchronisierung aus. Dies verhindert Duplizierung. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Nur <span class="wintitle"> DIL </span> sendet Daten an eine <a href="../../features/destinations/destinations.md"> URL-Ziel </a>. </li> 
     </ul> </p> <p>Siehe auch <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> wird verwendet, um Folgendes zu übergeben: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: Von Ihnen zugewiesene Datenpartner-ID <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Ihre eindeutige ID für einen Benutzer. </li> 
    </ul> <p> <p>Wichtig: Verwenden Sie nur nicht kodierte Werte für Ihre IDs. Ein Codieren der führt zu doppelt codierten Identifikatoren. </p> </p> <p> <p>Hinweis: Wenn Sie <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, legen Sie Kunden-IDs mit der <code> setCustomerIDs </code> -Methode anstelle von <span class="wintitle"> DIL </span>. Siehe <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Kunden-IDs und Authentifizierungsstatus </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Wenn "true", wird die Ausführung aller Anforderungen (IFRAME, Ereignisaufrufe, ID-Synchronisierung und Ziel) bis zum <code> Page Load </code> -Ereignis ausgelöst. Standardwert ist <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Standardmäßig "False", was bedeutet <span class="keyword"> Audience Manager </span> setzt ein Cookie in der Domäne des Partners (setzt ein Erstanbieter-Cookie). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig: Dieses Element ist veraltet mit <span class="wintitle"> DIL </span> Version 8.0 (veröffentlicht im August 2018). Verwenden Sie die <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> function </a> im Adobe Experience Platform Identity-Dienst. </p> </p> <p> Wenn <code> true </code>, hängt den Ziel-Publishing-IFRAME nicht an das DOM an oder löst Ziele aus. Standardwert ist <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig: Dieses Element ist veraltet mit <span class="wintitle"> DIL </span> Version 8.0 (veröffentlicht im August 2018). Verwenden Sie die <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> function </a> im Adobe Experience Platform Identity-Dienst. </p> </p> <p>Deaktiviert die ID-Synchronisierung. Sie müssen die ID-Synchronisierung bei der Verwendung von DIL v6.2+ und dem Besucher-ID-Dienst deaktivieren. Die <code> visitorService </code> -Funktion (siehe Beispielcode unten) übernimmt diesen Vorgang. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Legen Sie fest auf <code> true </code> zur Aktivierung der Fehlerberichterstellung für alle <span class="wintitle"> DIL </span> Instanzen auf der Seite. Funktioniert mit Boolesch <code> true </code> nur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig: Dieses Element ist veraltet mit <span class="wintitle"> DIL </span> Version 8.0 (veröffentlicht im August 2018). Verwenden Sie die <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> function </a> im Adobe Experience Platform Identity-Dienst. </p> </p> <p> Legt fest, ob die Vorlage für die Zielveröffentlichung bei HTTPS-Verbindungen mit Akamai ausgeführt werden soll. Aktivierung pro Partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Verbindet den Wert zwischen einem Schlüssel-Wert-Paar und einem anderen. Siehe <a href="../../dil/dil-use-cases.md#map-key-values"> Zuordnen von Schlüsselwerten zu anderen Schlüsseln </a>. Veröffentlicht mit v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Erforderlich. </p> <p>Die <code> namespace </code> Schlüssel-Wert-Paar enthält Ihr <span class="keyword"> Experience Cloud </span> Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im <span class="wintitle"> Administration </span> Abschnitt <span class="keyword"> Experience Cloud </span> Dashboard. Sie benötigen Administratorberechtigungen, um dieses Dashboard anzuzeigen. Siehe <a href="../../faq/faq-features.md"> Häufig gestellte Fragen zu Produktfunktionen </a> und <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administration - Benutzerverwaltung und häufig gestellte Fragen </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Erforderlich. </p> <p> Partnername gemäß <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Entfernt Skripte und Rückrufe. Standardwert ist <code> False </code>. Gilt für die aktuelle <span class="wintitle"> DIL </span> nur -Instanz. Veröffentlicht mit Version 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Legt ein Cookie mit der eindeutigen Benutzer-ID fest, die von zurückgegeben wird <span class="keyword"> Audience Manager </span>. Siehe <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie-Eigenschaften </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Erforderlich für <span class="wintitle"> DIL </span> 6.2 oder höher. </p> <p> DIL verlässt sich auf die <code> setCustomerIDs </code> -Funktion in der <span class="wintitle"> Adobe Experience Platform Identity Service </span> , um deklarierte IDs an zu übergeben. <span class="keyword"> Audience Manager </span>. Weitere Informationen finden Sie unter <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external">Kunden-IDs und Authentifizierungszustände.</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispielcode**

Beispiel [!UICONTROL DIL] -Aufruf könnte in etwa wie folgt aussehen:

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

Eine erfolgreiche Antwort gibt die [!UICONTROL DIL] -Instanz. Bei einem fehlgeschlagenen Versuch wird ein Fehlerobjekt (nicht ausgegeben) zurückgegeben, wenn der Code falsch konfiguriert ist oder wenn ein Fehler auftritt.

## uuidCookie-Eigenschaften {#uuidcookie-props}

Definiert die Eigenschaften, die von der `uuidCookie` -Variable. Diese Variable ist Teil der `DIL.create` -Methode.

`uuidCookie` weist die folgenden Eigenschaften auf:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Name | Beschreibung |
|---|---|
| `name` | Der Cookie-Name ( `aam_did` ist Standard). |
| `days` | Cookie-Lebensdauer (standardmäßig 100 Tage). |
| `path` | Cookie-Pfad, z. B. `'/test'` ( `/` ist Standard). |
| `domain` | Die Domäne, in der das Cookie gesetzt ist, z. B. `'adobe.com'` ( `'.'+document.domain` ist Standard). |
| `secure` | Legt eine Markierung fest, um nur Daten über eine HTTPS-Verbindung zu senden. |

## visitorService-Eigenschaften {#visitor-service-props}

Definiert die Eigenschaften, die von der `visitorService` -Variable. Diese Variable ist Teil der `DIL.create` -Methode.

`visitorService` weist die folgenden Eigenschaften auf:

| Name | Typ | Beschreibung |
|---|---|---|
| `namespace` | Zeichenfolge | Erforderlich. Stellt die Experience Cloud-Organisations-ID dar. Dies ist für die Experience Cloud Core Service-Funktionalität erforderlich. Derselbe Parameter, der zur Instanziierung der Besucher-ID-Funktion verwendet wird. |

**Code-Beispiel:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```

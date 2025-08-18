---
description: Erstellt eine partnerspezifische DIL-Instanz.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL erstellen
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 4%

---

# DIL-Erstellungsmethode{#dil-create}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung des [!DNL Data Integration Library (DIL)] und der [!DNL DIL] eingestellt.
>
>Bestehende Kundinnen und Kunden können ihre [!DNL DIL] Implementierung weiterhin nutzen. Adobe wird jedoch keine [!DNL DIL] über diesen Punkt hinaus entwickeln. Kundinnen und Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) auf ihre langfristige Datenerfassungsstrategie hin zu überprüfen.
>
>Kunden, die nach Juli 2023 neue Datenerfassungsintegrationen implementieren möchten, sollten stattdessen [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

## DIL erstellen {#dil-create-new}

Erstellt eine partnerspezifische [!UICONTROL DIL].

**Funktionssignatur:** `DIL.create: function (initConfig) {}`

**initConfig-Elemente**

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
   <td colname="col3"> <p>Diese Eigenschaft legt die Container-ID fest, die von <span class="keyword"> Audience Manager-</span> für ID-Synchronisierungen verwendet wird. Sie würden <code> containerNSID </code> festlegen, wenn Sie <span class="wintitle"> DIL-</span> auf mehreren Sites bereitgestellt haben. Jede dieser Sites verfügt über eine eigene Container-ID und ID-Synchronisierung. Wenn Sie nur über eine Site verfügen, ist die Container-ID standardmäßig 0 und Sie müssen diese nicht ordnungsgemäß festlegen. Wenden Sie sich an Ihren Berater, um eine Liste Ihrer Sites und ihrer Container-IDs zu erhalten. </p> <p>In der <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service-</a> entspricht die Eigenschaft <code> idSyncContainerID </code> der <code> containerNSID </code> in <span class="wintitle"> DIL-</span>. Beachten Sie Folgendes, wenn Sie <span class="wintitle"> DIL </span> (<i>) </i> ID-Service auf mehreren Sites verwenden: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Legen Sie für jede Site dieselben Container-IDs für <code> containerNSID </code> und <code> idSyncContainerID </code> fest. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Sowohl <span class="wintitle"> DIL </span> als auch der ID-Service versuchen, ID-Synchronisierungen an unseren Datenerfassungs-iFrame zu senden. Der iFrame stellt jedoch sicher, dass <span class="wintitle"> DIL-</span> keine ID-Synchronisierung auslöst. Dies verhindert Duplizierungen. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Nur <span class="wintitle"> DIL-</span> sendet Daten an eine <a href="../../features/destinations/destinations.md"> URL-Ziel-</a>. </li> 
     </ul> </p> <p>Siehe auch <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID-</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> wird verwendet, um eine der folgenden Eigenschaften zu übergeben: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: Datenpartner-ID, die Ihnen von <span class="keyword"> Audience Manager-</span> zugewiesen wurde. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Ihre eindeutige ID für einen Benutzer. </li> 
    </ul> <p> <p>Wichtig: Verwenden Sie für Ihre IDs nur nicht kodierte Werte. Durch die Kodierung werden doppelt kodierte Kennungen erstellt. </p> </p> <p> <p>Hinweis: Wenn Sie die <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service-</a> verwenden, legen Sie Kunden-IDs mit der <code> setCustomerIDs </code>-Methode anstelle <span class="wintitle"> DIL-</span> fest. Siehe <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> von Kunden-IDs und Authentifizierungsstatus </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Wenn „true“, wird die Ausführung aller Anfragen (IFRAME, Ereignisaufrufe, ID-Synchronisierung und Ziel) zurückgestellt, bis das <code> Page Load </code>-Ereignis ausgelöst wird. Der Standardwert ist <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Standardmäßig „False“, was bedeutet, <span class="keyword"> Audience Manager </span> ein Cookie in der Domain des Partners setzt (ein Erstanbieter-Cookie setzt). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig: Dieses Element ist seit <span class="wintitle"> DIL-</span> Version 8.0 (veröffentlicht im August 2018) veraltet. Verwenden Sie stattdessen die Funktion <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> im Adobe Experience Platform Identity Service </a>. </p> </p> <p> Falls <code> true </code>, wird der Ziel-Publishing-IFRAME nicht an das DOM angehängt oder Ziele werden ausgelöst. Der Standardwert ist <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig: Dieses Element ist seit <span class="wintitle"> DIL-</span> Version 8.0 (veröffentlicht im August 2018) veraltet. Verwenden Sie stattdessen die Funktion <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> im Adobe Experience Platform Identity Service </a>. </p> </p> <p>Deaktiviert die ID-Synchronisierung. Sie müssen die ID-Synchronisierung deaktivieren, wenn Sie DIL v6.2+ und den Besucher-ID-Dienst verwenden. Die <code> visitorService </code> (siehe Beispielcode unten) übernimmt diesen Vorgang. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Legen Sie die Einstellung auf <code> true </code> fest, um die Fehlerberichterstattung für alle <span class="wintitle"> DIL </span>-Instanzen auf der Seite zu aktivieren. Funktioniert nur mit booleschen <code> true </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> <p>Wichtig: Dieses Element ist seit <span class="wintitle"> DIL-</span> Version 8.0 (veröffentlicht im August 2018) veraltet. Verwenden Sie stattdessen die Funktion <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> im Adobe Experience Platform Identity Service </a>. </p> </p> <p> Gibt an, ob die Zielveröffentlichungsvorlage Akamai für HTTPS-Verbindungen verwenden soll. Aktivierung pro Partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Verknüpft den Wert von einem Schlüssel-Wert-Paar zu einem anderen. Siehe <a href="../../dil/dil-use-cases.md#map-key-values"> Zuordnen von Schlüsselwerten zu anderen </a>. Version 2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Erforderlich. </p> <p>Das <code> namespace </code> Schlüssel-Wert-Paar enthält Ihre <span class="keyword"> Experience Cloud </span>-Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im Abschnitt <span class="wintitle">-Administration </span> des <span class="keyword">-Dashboards von </span> Experience Cloud. Sie benötigen Administratorberechtigungen, um dieses Dashboard anzeigen zu können. Häufig gestellte Fragen zu den <a href="../../faq/faq-features.md"> Produktfunktionen </a> und <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administration - Benutzerverwaltung und häufig gestellte </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Erforderlich. </p> <p> Partnername, wie von <span class="keyword"> Audience Manager </span> angegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolesch </p> </td> 
   <td colname="col3"> <p> Entfernt Skripte und Callbacks. Der Standardwert ist <code> False </code>. Gilt nur für die aktuelle <span class="wintitle"> DIL </span>. Version 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Setzt ein Cookie mit der eindeutigen Benutzer-ID, die von <span class="keyword"> Audience Manager-</span> zurückgegeben wird. Siehe <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie-Eigenschaften </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objekt </p> </td> 
   <td colname="col3"> <p>Erforderlich bei <span class="wintitle"> DIL </span> 6.2 oder höher. </p> <p> DIL übergibt deklarierte IDs mithilfe der <code> setCustomerIDs </code> im <span class="wintitle"> Adobe Experience Platform Identity Service-</span> an <span class="keyword"> Audience Manager-</span>. Weitere Informationen finden Sie unter <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html" format="https" scope="external"> von Kunden-IDs und Authentifizierungsstatus </a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispielcode**

Ein Beispielaufruf für [!UICONTROL DIL] könnte in etwa wie folgt aussehen:

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

Eine erfolgreiche Antwort gibt die [!UICONTROL DIL]-Instanz zurück. Ein erfolgloser Versuch gibt ein Fehlerobjekt zurück (nicht ausgelöst), wenn der Code falsch konfiguriert ist oder ein Fehler auftritt.

## uuidCookie-Eigenschaften {#uuidcookie-props}

Definiert die von der `uuidCookie` verwendeten Eigenschaften. Diese Variable ist Teil der `DIL.create`.

`uuidCookie` weist die folgenden Eigenschaften auf:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Name | Beschreibung |
|---|---|
| `name` | Der Cookie-Name (`aam_did` ist Standard). |
| `days` | Cookie-Lebensdauer (standardmäßig 100 Tage). |
| `path` | Cookie-Pfad, z. B. `'/test'` ( `/` ist Standard). |
| `domain` | Die Domain, in der das Cookie gesetzt wird, z. B. `'adobe.com'` ( `'.'+document.domain` ist Standard). |
| `secure` | Legt eine Markierung fest, um Daten nur über eine HTTPS-Verbindung zu senden. |

## VisitorService-Eigenschaften {#visitor-service-props}

Definiert die von der `visitorService` verwendeten Eigenschaften. Diese Variable ist Teil der `DIL.create`.

`visitorService` weist die folgenden Eigenschaften auf:

| Name | Typ | Beschreibung |
|---|---|---|
| `namespace` | Zeichenfolge | Erforderlich. Stellt die Experience Cloud-Organisations-ID dar. Dies ist für die Experience Cloud Core Service-Funktionalität erforderlich. Derselbe Parameter wird zum Instanziieren der Besucher-ID-Funktion verwendet. |

**Codebeispiel:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```

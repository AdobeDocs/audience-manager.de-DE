---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: Durchführen von Server-zu-Server-DCS-API-Aufrufen
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: Aufrufsyntax, Beispiel, und Parameter bei Server-zu-Server-DCS-API-Aufrufen
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Durchführen von Server-zu-Server-DCS-API-Aufrufen {#making-server-to-server-dcs-api-calls}

Für Aufrufe sind der Hostname des regionalen DCS-Servers und die Benutzer-ID erforderlich. Wenn Sie nicht über die erforderlichen Benutzer- und Regions-IDs verfügen, finden Sie weitere Informationen unter [Abrufen von Benutzer-IDs und Regionen aus einer DCS-Antwort](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) und/oder [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Sobald Sie Benutzer- und Regions-IDs haben, können Sie Server-zu-Server-Aufrufe an den DCS ausführen. Syntax und Beispiele finden Sie in diesem Abschnitt .

>[!NOTE]
>
>Im Code und in den Beispielen *kursiv* ein variabler Platzhalter. Ersetzen Sie den Platzhalter durch einen echten Wert, wenn Sie Server-zu-Server-Aufrufe an die [!DNL DCS] durchführen.

## Aufrufsyntax und Beispiel {#call-syntax-example}

Eine einfache Server-zu-Server-Anfrage, die Daten an den [!DNL DCS] sendet, verwendet die unten dargestellte Syntax.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Ein Beispielaufruf sieht dem folgenden Beispiel ähnlich.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Aufrufparameter {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Dieser Teil des Aufrufs enthält: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Ihr Domain-Alias, der von <span class="keyword"> Audience Manager zugewiesen </span> (z. B. <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Die Ziel-Domain, die immer <i><code> demdex.net</code></i> ist. Siehe <a href="../../../reference/demdex-calls.md"> Aufrufe an die Domain „demdex.net“</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Der Host-Parameter des HTTP-Headers, der den Namen des regionalen <span class="wintitle"> DCS</span>-Servers anzeigt. Der Host-Name ist an eine Regions-ID gebunden. Daher benötigen Sie diese, bevor Sie diese Art von Aufrufen durchführen. Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> von DCS-Regions-IDs, Standorten und Hostnamen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Dieser Teil des Aufrufs: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifiziert den Aufruf als einen Ereignisaufruf. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definiert den Beginn der URL-Zeichenfolge, die die Daten enthält, die Sie an den DCS senden möchten. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dies ist der eindeutige Benutzer-ID-Schlüssel, der den Wert der <span class="keyword"> Audience Manager</span>-Benutzer-ID in einem Schlüssel-Wert-Paar enthält. </p> <p>Verwenden Sie <code><i>d_uuid</i></code>, wenn Sie die <span class="keyword"> Audience Manager</span>-Benutzer-ID übergeben. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dies ist der eindeutige Benutzer-ID-Schlüssel, der den Wert der <span class="keyword"> Experience Cloud</span>-Benutzer-ID in einem Schlüssel-Wert-Paar enthält. Siehe auch <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Abrufen der Benutzer-ID aus dem ID-Dienst-Cookie</a>. </p> <p>Verwenden Sie <i><code> d_mid</code></i>, wenn Sie eine <span class="keyword"> Experience Cloud</span> ID übergeben, die vom <span class="keyword"> Experience Cloud</span> ID-Service erfasst wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionale Antwortparameter. </p> <p> Keine dieser Informationen ist erforderlich, um Daten an den <span class="wintitle"> DCS zu senden</span>. Wenn der <span class="wintitle"> DCS</span> jedoch eine Antwort zurückgeben soll, müssen Sie <i><code> d_rtbd=json</code></i> in Ihre Anfrage aufnehmen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielantwort {#sample-response}

Siehe [Empfangen von Daten vom DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

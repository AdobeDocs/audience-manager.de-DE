---
description: ID-Service-Kunden sollten in diesem Abschnitt Informationen darüber finden, wie das Besucher-Cookie für die IDs gelesen wird, die für DCS-API-Aufrufe erforderlich sind.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Abrufen von Benutzer-IDs und Regionen über den Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 2%

---

# Abrufen von Benutzer-IDs und Regionen über den Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID-Service-Kunden sollten in diesem Abschnitt Informationen darüber finden, wie das Besucher-Cookie für die IDs gelesen wird, die für [!DNL DCS] API-Aufrufe erforderlich sind.

## Abrufen der Benutzer-ID aus dem ID-Dienst-Cookie {#get-user-ids-from-service-cookie}

Der [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) weist Benutzern, die Ihre Website besuchen, Besucher- und Regions-IDs zu. Diese IDs identifizieren Benutzende für alle Lösungen im [!DNL Experience Cloud] und sind erforderlich, wenn Sie [!DNL DCS] Aufrufe durchführen möchten.

* Die [!UICONTROL user ID] ist erforderlich, um Daten zu identifizieren und mit einem bestimmten Besucher zu verknüpfen.
* Der [!UICONTROL region ID] ist erforderlich, da er an einen regionalen Servernamen gebunden ist, den Sie zum Senden von Daten an die [!DNL DCS] benötigen. Die [!DNL DCS] speichert Informationen in Rechenzentren, die geografisch den Besuchern der Website am nächsten liegen. Siehe [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

ID-Service-Kunden können diese Informationen aus dem ID-Service-Cookie oder durch Aufruf einer -Funktion extrahieren. In der folgenden Tabelle werden die Aufgaben oder Schritte beschrieben, die Sie für die ersten Schritte ausführen müssen.

Code in *Kursiv* stellt einen Variablenplatzhalter dar.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Aufgabe </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Überprüfen Sie den Status Ihres <span class="keyword"> Experience Cloud</span>s</b> </p> </td> 
   <td colname="col2"> <p>Sie benötigen ein <span class="keyword"> Experience Cloud</span>-Konto, um den ID-Dienst verwenden zu können. Wenn Sie über ein <span class="keyword"> Experience Cloud</span>-Konto verfügen, großartig! </p> <p> Wenn Sie nicht Teil des <span class="keyword"> Experience Cloud</span> sind, melden Sie sich an. Wir würden uns freuen, Sie zu haben, und es ist immer Platz für mehr. Anweisungen zum Einrichten eines Kontos finden Sie unter <a href="https://experienceleague.adobe.com/en/docs/core-services/interface/services/getting-started" format="https" scope="external"> Aktivieren Ihrer Lösungen für zentrale Services</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Richten Sie den <span class="keyword">-ID-Dienst ein</span></b> </p> </td> 
   <td colname="col2"> <p>Der <span class="keyword"> ID-</span> besteht aus JavaScript-Code, der auf jeder Seite abgelegt wird, die Sie für die Datenerfassung verwenden möchten. Weitere Informationen finden Sie in den Implementierungshandbüchern </a> ID-Service <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lesen Sie den <span class="keyword"> ID-Service</span>-Cookie</b> </p> </td> 
   <td colname="col2"> <p>Der <span class="keyword">-ID</span>Dienst speichert die Benutzer- und Regions-ID im AMCV-Cookie. Der vollständige Cookie-Name ist <code>AMCV_<i>###</i>@AdobeOrg</code>. Die <code><i>###</i></code> Elemente sind Platzhalter für Ihre Organisations-ID. Weitere Informationen finden Sie unter <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> von Cookies und der Experience Cloud</a>ID. </p> <p>Analysieren Sie das AMCV-Cookie nach diesen Schlüssel-Wert-Paaren: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Dieses Schlüssel-Wert-Paar enthält die <span class="keyword"> Experience Cloud</span>-Benutzer-ID. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Dieses Schlüssel-Wert-Paar enthält die Regions-ID (manchmal auch als <span class="term">-Standorthinweis bezeichnet</span>, die mit einem regionalen Server-Namen verknüpft ist. </li> 
     </ul> </p> <p>Sie können den <span class="wintitle">-DCS aufrufen</span> sobald Sie über die Benutzer- und Regions-IDs verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Abrufen der <span class="keyword"> Experience Cloud ID</span> mit getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Optional)</i> Diese Funktion gibt die <span class="keyword"> Experience Cloud</span>-Besucher-ID zurück. Es wurde für benutzerdefinierte Lösungen und spezifische Anwendungsfälle entwickelt. Siehe <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Arbeiten mit getMarketingCloudVisitorID </a> unten und die <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> Dokumentation zum ID-Service</a>. </p> <p>Sie müssen dies nicht verwenden, wenn Sie die Benutzer- und Standort-IDs aus dem ID-Service-Cookie erhalten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Arbeiten mit `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Eine andere Möglichkeit, die Besucher-ID abzurufen, ist mit der `getMarketingCloudVisitorID`. Wenn diese Funktion aufgerufen wird, wird der [!DNL ID service] abgefragt und eine ID zurückgegeben. `getMarketingCloudVisitorID` akzeptiert das optionale `callback`-Argument wie folgt:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Nutzung und Zweck des Callbacks {#callback-usage}

`callback` ist optional. Diese Funktion funktioniert ohne sie, gibt jedoch nur dann eine ID zurück, wenn ein Besucher ein [!DNL Experience Cloud] Cookie in seinem Browser hat. Wenn das Besucher-Cookie fehlt oder ein Besucher keine ID hat, gibt die Funktion ein leeres `()`-Objekt zurück. Dies kann auch passieren, nachdem die Seite geladen wurde und der Besucher eine neue ID erhält. Um dies zu vermeiden, erzwingt `callback` diese Funktion, nach dem Laden der Seite nach einer Besucher-ID zu suchen. Ohne `callback` gibt die Besucher-ID-Funktion keine ID zurück, selbst wenn sie später in den Browser des Besuchers geschrieben wird.

## Nächste Schritte {#next-steps}

Sobald Sie über die Benutzer- und Regions-ID verfügen, können Sie mit dem Senden und Empfangen [!DNL DCS] Daten beginnen. Siehe [Erstellen von DCS-API-Aufrufen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).

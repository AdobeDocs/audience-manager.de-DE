---
description: Informationen zum Lesen des Besucher-Cookies für die IDs, die zum Aufrufen der DCS API erforderlich sind, finden Sie in diesem Abschnitt.
seo-description: Informationen zum Lesen des Besucher-Cookies für die IDs, die zum Aufrufen der DCS API erforderlich sind, finden Sie in diesem Abschnitt.
seo-title: Abrufen von Benutzer-IDs und Regionen über Adobe Experience Platform Identity Service
solution: Audience Manager
title: Abrufen von Benutzer-IDs und Regionen über Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 9%

---


# Abrufen von Benutzer-IDs und Regionen über Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Informationen zum Lesen des Besucher-Cookies für die IDs, die zum Durchführen von [!DNL DCS] API-Aufrufen erforderlich sind, finden Sie in diesem Abschnitt.

## Abrufen der Benutzer-ID aus dem ID-Dienst-Cookie {#get-user-ids-from-service-cookie}

Der Identitätsdienst für [Adobe Experience Platformen](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html) weist Benutzern, die Ihre Website besuchen, Besucher- und Regions-IDs zu. Diese IDs identifizieren Benutzer in allen Lösungen in der [!DNL Experience Cloud] und sind erforderlich, wenn Sie [!DNL DCS] Aufrufe tätigen möchten.

* Der [!UICONTROL user ID] ist erforderlich, um Daten zu identifizieren und mit einem bestimmten Besucher zu verbinden.
* Die [!UICONTROL region ID] ist erforderlich, da sie an einen regionalen Servernamen gebunden ist, den Sie an die [!DNL DCS]Gruppe senden müssen. Die [!DNL DCS] Daten werden in Rechenzentren gespeichert, die den Site-Besuchern am nächsten liegen. Siehe [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

ID-Dienstkunden können diese Informationen aus dem ID-Dienst-Cookie oder durch Aufruf einer Funktion extrahieren. Die folgende Tabelle beschreibt die Aufgaben oder Schritte, die Sie zum Einstieg ausführen müssen.

Code *kursiv* stellt einen variablen Platzhalter dar.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Aufgabe </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Überprüfen Sie den Status Ihres <span class="keyword"> Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Sie benötigen ein <span class="keyword"> Experience Cloud</span> -Konto, um den ID-Dienst verwenden zu können. Wenn Sie ein <span class="keyword"> Experience Cloud</span> Account haben, super! </p> <p> Wenn Sie nicht Teil des <span class="keyword"> Experience Cloud</span>sind, dann melden Sie sich an. Wir würden dich gerne haben und es gibt immer Platz für mehr. Anweisungen zum Einrichten eines Kontos finden Sie unter <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Aktivieren Ihrer Lösungen für Hauptdienste</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>Der <span class="keyword"> ID-Dienst</span> besteht aus JavaScript-Code, der auf jeder Seite platziert wird, die Sie für die Datenerfassung verwenden möchten. Weitere Informationen finden Sie in den <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> Implementierungshandbüchern</a> für den ID-Dienst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Cookie des <span class="keyword"> ID-Diensts</span> lesen</b> </p> </td> 
   <td colname="col2"> <p>Der <span class="keyword"> ID-Dienst</span> speichert die Benutzer- und Regions-ID im AMCV-Cookie. Der vollständige Cookie-Name lautet <code>AMCV_<i>###</i>@AdobeOrg</code>. Die <code><i>###</i></code> Elemente sind Platzhalter für Ihre Organisations-ID. See <a href="https://docs.adobe.com/content/help/de-DE/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>Parsen Sie das AMCV-Cookie für diese Schlüssel/Wert-Paare: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Dieses Schlüssel-Wert-Paar enthält die <span class="keyword"> Experience Cloud</span> -Benutzer-ID. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Dieses Schlüssel-Wert-Paar enthält die Regions-ID (manchmal auch als <span class="term"> Standorthinweis</span>bezeichnet), die mit einem regionalen Servernamen verknüpft ist. </li> 
     </ul> </p> <p>Sie können das <span class="wintitle"> DCS</span> aufrufen, sobald Sie über die Benutzer- und Regions-IDs verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Abrufen der <span class="keyword"> Experience Cloud-ID</span> mit getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Optional)</i> Diese Funktion gibt die <span class="keyword"> Experience Cloud</span> -Besucher-ID zurück. Es wurde für benutzerdefinierte Lösungen und spezielle Anwendungsfälle entwickelt. Siehe <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Arbeiten mit getMarketingCloudVisitorID</a> unten und die zugehörige Dokumentation <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> zum</a>ID-Dienst. </p> <p>Sie müssen dies nicht verwenden, wenn Sie die Benutzer- und Standort-IDs aus dem ID-Dienst-Cookie abrufen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Arbeiten mit `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Eine andere Möglichkeit, die Besucher-ID abzurufen, ist die `getMarketingCloudVisitorID` Funktion. Wenn diese Funktion aufgerufen wird, wird die Abfrage [!DNL ID service] und eine ID zurückgegeben. `getMarketingCloudVisitorID` akzeptiert das optionale `callback` Argument wie folgt:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Nutzung und Zweck des Rückrufs {#callback-usage}

`callback` ist optional. Diese Funktion funktioniert ohne sie, gibt jedoch nur dann eine ID zurück, wenn ein Besucher über ein [!DNL Experience Cloud] Cookie in seinem Browser verfügt. Wenn das Besucher-Cookie fehlt oder ein Besucher keine ID hat, gibt die Funktion ein leeres `()` Objekt zurück. Dies kann auch nach dem Laden der Seite und dem Empfang einer neuen ID durch den Besucher passieren. Um dies zu vermeiden, `callback` zwingt diese Funktion, nach dem Laden der Seite nach einer Besucher-ID zu suchen. Andernfalls gibt die Besucher-ID-Funktion keine ID zurück, auch wenn sie später in den Browser des Besuchers geschrieben wurde. `callback`

## Nächste Schritte {#next-steps}

Sobald Sie über die Benutzer- und Regions-ID verfügen, können Sie Beginn zum Senden und Empfangen von [!DNL DCS] Daten haben. Siehe [Durchführen von DCS-API-Aufrufen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
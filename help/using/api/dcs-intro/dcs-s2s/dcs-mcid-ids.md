---
description: Kunden von ID-Diensten sollten in diesem Abschnitt Informationen zum Lesen des Besucher-Cookies für die IDs finden, die zum Ausführen von DCS-API-Aufrufen erforderlich sind.
seo-description: Kunden von ID-Diensten sollten in diesem Abschnitt Informationen zum Lesen des Besucher-Cookies für die IDs finden, die zum Ausführen von DCS-API-Aufrufen erforderlich sind.
seo-title: Abrufen von Benutzer-IDs und Regionen über Adobe Experience Platform Identity Service
solution: Audience Manager
title: Abrufen von Benutzer-IDs und Regionen über Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 9%

---

# Abrufen von Benutzer-IDs und Regionen über Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Kunden von ID-Diensten sollten in diesem Abschnitt Informationen zum Lesen des Besucher-Cookies für die IDs finden, die zum Ausführen von API-Aufrufen mit der Bezeichnung [!DNL DCS] erforderlich sind.

## Abrufen der Benutzer-ID vom ID-Dienst-Cookie {#get-user-ids-from-service-cookie}

Der [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html) weist Besucherkennung und Regions-IDs Benutzern zu, die zu Ihrer Website gelangen. Diese IDs identifizieren Benutzer über alle Lösungen im [!DNL Experience Cloud] und sind erforderlich, wenn Sie [!DNL DCS]-Aufrufe durchführen möchten.

* [!UICONTROL user ID] ist erforderlich, um Daten zu einem bestimmten Besucher zu identifizieren und zuzuordnen.
* Der [!UICONTROL region ID] ist erforderlich, da er an einen regionalen Servernamen gebunden ist, den Sie an [!DNL DCS] senden müssen. Der [!DNL DCS] speichert Informationen in Rechenzentren, die den Site-Besuchern am nächsten sind. Siehe [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

ID-Dienstkunden können diese Informationen aus dem ID-Dienst-Cookie oder durch Aufruf einer Funktion extrahieren. In der folgenden Tabelle werden die Aufgaben und Schritte beschrieben, die Sie zum Einstieg ausführen müssen.

Code in *kursiv* stellt einen Variablenplatzhalter dar.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Aufgabe </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Überprüfen Sie den Status Ihres <span class="keyword">-Experience Cloud</span></b> . </p> </td> 
   <td colname="col2"> <p>Sie benötigen ein <span class="keyword">-Experience Cloud</span>-Konto, um den ID-Dienst verwenden zu können. Wenn Sie ein <span class="keyword"> Experience Cloud</span> Konto haben, großartig! </p> <p> Wenn Sie nicht Teil des <span class="keyword">-Experience Cloud</span> sind, melden Sie sich an. Wir würden dich sehr gerne haben und es gibt immer Platz für mehr. Anweisungen zum Einrichten eines Kontos finden Sie unter <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Aktivieren Ihrer Lösungen für Hauptdienste</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Einrichten des ID-Diensts <span class="keyword"></span></b> </p> </td> 
   <td colname="col2"> <p>Der ID-Dienst <span class="keyword"></span> besteht aus JavaScript-Code, der auf jeder Seite eingefügt wird, die Sie für die Datenerfassung verwenden möchten. Weitere Informationen finden Sie in den Implementierungshandbüchern für den ID-Dienst <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"></a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lesen Sie den <span class="keyword"> ID-Dienst</span> Cookie</b> </p> </td> 
   <td colname="col2"> <p>Der ID-Dienst <span class="keyword"></span> speichert die Benutzer- und Regions-ID im AMCV-Cookie. Der vollständige Cookie-Name ist <code>AMCV_<i>###</i>@AdobeOrg</code>. Die <code><i>###</i></code> -Elemente sind Platzhalter für Ihre Organisations-ID. Weitere Informationen finden Sie unter <a href="https://docs.adobe.com/content/help/de-DE/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies und die Experience Cloud-ID</a> . </p> <p>Analysieren Sie das AMCV-Cookie für diese Schlüssel-Wert-Paare: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Dieses Schlüssel-Wert-Paar enthält die  <span class="keyword"> Experience </span> Cloud-Benutzer-ID. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Dieses Schlüssel-Wert-Paar enthält die Regions-ID (manchmal auch als  <span class="term"> Standorthinweis</span> bezeichnet), die mit einem regionalen Servernamen verknüpft ist. </li> 
     </ul> </p> <p>Sie können die <span class="wintitle"> DCS</span> aufrufen, sobald Sie über die Benutzer- und Regions-IDs verfügen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Rufen Sie die <span class="keyword"> Experience Cloud-ID</span> mit getMarketingCloudVisitorID</b> ab. </p> </td> 
   <td colname="col2"> <p><i>(Optional)</i> Diese Funktion gibt die  <span class="keyword"> Experience </span> Cloud-Besucher-ID zurück. Sie wurde für benutzerdefinierte Lösungen und spezifische Anwendungsfälle entwickelt. Siehe <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Arbeiten mit getMarketingCloudVisitorID</a> unten und die <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> zugehörige Dokumentation zum ID-Dienst</a>. </p> <p>Sie müssen dies nicht verwenden, wenn Sie die Benutzer- und Standort-IDs aus dem ID-Dienst-Cookie abrufen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Arbeiten mit `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Eine weitere Möglichkeit, die Besucher-ID abzurufen, ist die Funktion `getMarketingCloudVisitorID` . Wenn diese Funktion aufgerufen wird, fragt sie [!DNL ID service] ab und gibt eine ID zurück. `getMarketingCloudVisitorID` akzeptiert das optionale  `callback` Argument wie folgt:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Nutzung und Zweck des Rückrufs {#callback-usage}

`callback` ist optional. Diese Funktion funktioniert ohne sie, gibt jedoch nur dann eine ID zurück, wenn ein Besucher in seinem Browser über ein [!DNL Experience Cloud] -Cookie verfügt. Wenn das Besucher-Cookie fehlt oder ein Besucher keine ID hat, gibt die Funktion ein leeres `()` -Objekt zurück. Dies kann auch geschehen, nachdem die Seite geladen wurde und der Besucher eine neue ID erhält. Um dies zu vermeiden, erzwingt `callback`, dass diese Funktion nach dem Laden der Seite nach einer Besucher-ID sucht. Ohne `callback` gibt die Besucher-ID-Funktion keine ID zurück, selbst wenn sie später in den Browser des Besuchers geschrieben wird.

## Nächste Schritte {#next-steps}

Sobald Sie über die Benutzer- und Regions-ID verfügen, können Sie mit dem Senden und Empfangen von [!DNL DCS]-Daten beginnen. Siehe [Ausführen von DCS-API-Aufrufen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).

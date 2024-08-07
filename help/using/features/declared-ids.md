---
description: Funktionsweise deklarierter IDs, Einrichten von Verfahren, Codebeispielen und Variablen.
keywords: id sync
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: Declared IDs
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 8%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Funktionsweise von [!UICONTROL declared IDs], Einrichten von Verfahren, Codebeispielen und Variablen.

## [!UICONTROL Declared ID] Zielsetzung {#declared-id-targeting}

Austausch und Synchronisieren von Benutzer-IDs mit [!DNL Audience Manager] von Geräten oder Browsern, die keine persistenten Speichermechanismen verwenden oder akzeptieren, z. B. von Drittanbietern [!DNL cookies].

## Zweck von [!UICONTROL Declared ID] Targeting {#declared-id-targeting-purpose}

Einige Browser und die meisten Mobilgeräte akzeptieren nicht den Drittanbieter [!DNL cookies]. Dadurch wird es schwierig, Informationen über Site-Besucher beizubehalten oder beständige IDs zuzuweisen. Um dieses Problem zu beheben, verwendet [!DNL Audience Manager] [!UICONTROL DIL], damit Sie [!UICONTROL declared IDs] bei einem Ereignisaufruf übergeben können. Außerdem kann ein [!UICONTROL declared ID] als universelle ID fungieren, die für denselben Benutzer für alle Lösungen in der [!DNL Experience Cloud] gilt. In der folgenden Tabelle wird der ID-Targeting-/Matching-Prozess beschrieben:

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Verarbeitung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Ereignisaufruf</b> </td> 
   <td colname="col2"> <p>Um zu funktionieren, benötigen Sie <span class="wintitle"> DIL </span> und den Code für den <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a> auf der Seite. <span class="wintitle"> DIL </span> erhält <span class="wintitle"> deklarierte IDs </span> aus der <code> setVisitorID </code> -Funktion, die vom <span class="keyword"> Adobe Experience Platform Identity Service </span> bereitgestellt wird, und übergibt diese an <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Übereinstimmung mit ID</b> </td> 
   <td colname="col2"> <p>Audience Manager versucht, die Client- und Besucher-ID mit einer entsprechenden ID in unserem System abzugleichen. Wenn keine übereinstimmende ID vorhanden ist, erstellt Audience Manager eine neue ID und ordnet sie der Client- und Besucher-ID zu. </p> <p> <p>Hinweis: Die neueste Zuordnung wird verwendet, wenn Ihre ID mehr als einer Audience Manager-ID zugeordnet ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Rückgabe-ID</b> </td> 
   <td colname="col2"> <p>Audience Manager schreibt seine synchronisierte ID in ein Erstanbieter-Cookie (oder einen anderen adressierbaren Speicher) in der Client-Domäne oder Anwendung. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Nachfolgende Ereignisaufrufe</b> </td>
   <td colname="col2"> <p>Zusätzliche Ereignisaufrufe lesen die Audience Manager-ID aus der Domäne des Kunden und senden sie an den Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Um zu beginnen, müssen Sie den [!DNL Experience Cloud] ID-Dienst und [!UICONTROL DIL] für die Seiten Ihrer Site konfigurieren, die Sie für die Datenerfassung verwenden möchten. Siehe [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) und [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out-Aufrufe {#opt-out-calls}

Der Prozess [!UICONTROL declared ID] berücksichtigt die Site-Besucherpräferenzen, um das Targeting von [!DNL Audience Manager] durch Ihre Website abzuwählen. Wenn [!DNL Audience Manager] eine Opt-out-Anfrage erhält, enthält der von [!DNL DCS] zurückgegebene [!DNL JSON] den Fehlercode 171 mit der Meldung `Encountered opt out tag` anstelle der [!DNL Audience Manager] Benutzer-ID.

* [!DNL Audience Manager] kann ein [!UICONTROL declared ID] Opt-out neben einem [!DNL Audience Manager] [!UICONTROL UUID] in der [!DNL URL] übergeben.
* Das Opt-out [!UICONTROL declared ID] wird pro Partner in den [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) gespeichert. Es gibt kein Opt-out auf Plattformebene mit [!UICONTROL declared IDs]. Außerdem wählt [!DNL Audience Manager] den Benutzer aus diesem bestimmten Bereich am Rand aus (der Opt-out erstreckt sich nicht über [!DNL DCS] Bereiche).

Weitere Informationen zum Abmelden von der Datenerfassung finden Sie unter [Datenschutz](../overview/data-security-and-privacy/data-privacy.md) .

## [!UICONTROL Declared ID] Opt-out-Beispiele {#opt-out-examples}

Sie können mit den Schlüssel-Wert-Paaren `d_cid` und `d_cid_ic` Opt-out-Anfragen für [!UICONTROL declared ID] stellen. Die veralten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../reference/cid.md). In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

### Opt-outs mit [!UICONTROL CID] und [!UICONTROL CID_IC]

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-out über </th> 
   <th colname="col2" class="entry"> Code-Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eine Datenanbieter-ID und eine Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Einen Integrations-Code und eine Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mehrere Schlüssel-Wert-Paare <code> d_cid </code> und <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-outs mit [!UICONTROL DPID], [!UICONTROL DPUUID] und [!UICONTROL UUID] (veraltet)

Diese Methoden funktionieren weiterhin, werden jedoch als veraltet betrachtet. Diese Informationen werden für veraltete Zwecke und als Referenz bereitgestellt. Zu den alten Opt-outs gehören:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-out (veraltet) </th> 
   <th colname="col2" class="entry"> Code-Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Nur <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opt-out auf Partnerebene </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Ein Opt-out auf Partnerebene wird für die neueste Zuordnung dieses <code> dpid </code> + <code> dpuuid </code> -Paares zu einer AAM UUID gespeichert. Wenn noch keine vorhandene Zuordnung vorhanden ist, prüft der Audience Manager, ob die Anforderung eine AAM UUID im Cookie enthält, und verwendet diese, falls sie dies tut, zum Speichern der Opt-out-Funktion. Andernfalls generiert Audience Manager eine neue AAM-UUID und speichert die Opt-out-Option darunter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> und explizit <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> hat immer Vorrang. Wenn die Kombination <code> dpid </code> + <code> dpuuid </code> einer anderen AAM UUID zugeordnet ist, wird die Opt-out-Funktion unter der in der Anfrage übergebenen AAM UUID ( <code> d_uuid </code>) gespeichert. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variablen und Syntax für [!UICONTROL Declared IDs] {#variables-and-syntax}

In der folgenden Tabelle sind die Schlüssel-Wert-Paare aufgeführt, die Ihre [!DNL Audience Manager] Datenanbieter-IDs und Benutzer-IDs oder Integrationscodes übergeben, falls verwendet. Hinweis: *kursiv* gibt einen Variablenplatzhalter an. Es wurden Leerzeichen hinzugefügt, die das Lesen erleichtern.

In jedem Schlüssel-Wert-Paar:

* Das Symbol `=` trennt den Schlüssel von den zugehörigen Werten.
* Das nicht druckbare [!DNL ASCII] Zeichen `%01` trennt die Werte.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Enthält eine Datenanbieter-ID und eine zugehörige eindeutige Benutzer-ID in einem einzelnen Schlüssel-Wert-Paar. <code> d_cid </code> ersetzt <code> d_dpid </code> und <code> d_dpuuid </code>, die als veraltet gelten, aber weiterhin unterstützt werden. Siehe <a href="../reference/cid.md"> CID ersetzt DPID und DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Enthält einen Integrationscode und eine zugehörige eindeutige Benutzer-ID in einem einzelnen Schlüssel-Wert-Paar. <code> d_cid_ic </code> ersetzt <code> d_dpid </code> und <code> d_dpuuid </code>, die veraltet sind, aber weiterhin unterstützt werden. Siehe <a href="../reference/cid.md"> CID ersetzt DPID und DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielereignisaufrufe {#sample-event-calls}

Angesichts dieser Schlüssel-Wert-Paare und ihrer erforderlichen Syntax würden Sie Ereignisaufrufe durchführen, wie unten dargestellt.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> enthält Ereignisaufrufe </th> 
   <th colname="col2" class="entry"> Code-Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eine Datenanbieter-ID und eine Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Einen Integrations-Code und eine Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mehrere Schlüssel-Wert-Paare <code> d_cid </code> und <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variablen {#declared-id-variables}

Beschreibt die Konfigurationsvariablen, die verwendet werden, um [!UICONTROL declared IDs] bis [!UICONTROL DIL] an [!DNL Audience Manager.] zu übergeben

## [!UICONTROL DIL] verwendet den [!DNL Adobe Experience Platform Identity Service], um [!UICONTROL Declared IDs] zu übergeben {#dil-id-service-pass-declared-ids}

Bei Verwendung mit dem [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) müssen Sie [!UICONTROL declared IDs] nicht mehr mit den veralteten `dpid` - und `dpuuid` -Variablen übergeben. Stattdessen verlassen sich die aktuellen Versionen von [!UICONTROL DIL] darauf, dass die Funktion `visitorService` die Funktion [!UICONTROL declared IDs] von der Funktion `setCustomerIDs` in der [!UICONTROL Adobe Experience Platform Identity Service] abruft. Weitere Informationen finden Sie unter [Kunden-IDs und Authentifizierungsstatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). Sie würden `visitorService` in `DIL.create` aufrufen, wie unten dargestellt.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Im Schlüssel-Wert-Paar `namespace` ist `MCORG` Ihre [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im Abschnitt &quot;[!UICONTROL Administration]&quot;des Dashboards &quot;[!DNL Experience Cloud]&quot;. Sie benötigen Administratorberechtigungen, um dieses Dashboard anzuzeigen. Siehe [Administration: Core Services](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## Veraltete Funktionen {#deprecated-functions}

Mit den neuesten Versionen von [!UICONTROL DIL] (6.2+) müssen Sie diese Schlüssel-Wert-Paare nicht verwenden, um [!UICONTROL declared IDs] zu übergeben. Dies liegt daran, dass [!UICONTROL DIL] jetzt auf der im obigen Codebeispiel gezeigten Funktion `visitorService` beruht. Diese Funktion erhält [!UICONTROL declared IDs] von der [!UICONTROL Adobe Experience Platform Identity Service]. Wir verweisen jedoch hier auf diese Variablen aus historischen und veralteten Gründen. Im folgenden Code finden Sie ein Beispiel dafür, wie Sie `DIL.create` so konfigurieren, dass ein [!UICONTROL declared ID] von der [!UICONTROL Visitor ID Service] abgerufen wird.
In der folgenden Tabelle werden die Legacy-Variablen beschrieben, die vom `declaredId` -Objekt verwendet werden:

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>Vom Audience Manager zugewiesene Datenpartner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>Die eindeutige Datenanbieter-ID für den Benutzer. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] und [!UICONTROL DPUUID]

[!DNL Audience Manager] vergleicht und stimmt die kombinierten `DPID` und `DPUUID` mit einer entsprechenden Benutzer-ID in unserem System überein. Wenn keine ID vorhanden ist, erstellt [!DNL Audience Manager] eine neue Benutzer-ID und synchronisiert sie mit der Kombination `DPID/DPUUID` . Sobald [!DNL Audience Manager] eine Benutzer-ID (die `UUID`) erfüllt oder erstellt, wird diese ID in der Antwort [!DNL JSON] an die [!DNL cookie] in der Domäne des Kunden (Erstanbieter-ID [!DNL cookie]) oder in einem anderen lokalen Speicher zurückgegeben.

Rufen Sie diese Funktion auf, wenn Sie [!UICONTROL DIL] v6.1 oder früher verwenden. Diese Funktion wird jedoch nicht mehr für die neue Version unterstützt, die [!UICONTROL declared IDs] von der [!DNL Adobe Experience Platform Identity Service] erhält.

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>Sie müssen programmatisch den Code entwickeln, der die ID-Werte für die Schlüssel `d_dpuuid` und `d_dpid` bereitstellt.

### Übergeben von IDs nach [!UICONTROL DIL] Instanziierungen

>[!NOTE]
>
>Wenn Sie einen [!DNL API] -Aufruf mit einer anderen `declaredID` -Kombination vornehmen, wird die neue Kombination nur für diesen Aufruf verwendet. Weitere reguläre Ereignisaufrufe verwenden die ursprüngliche Kombination `DIL.create` `declaredID` .

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Beispiele für Anfragen/Antworten {#request-response-examples}

Die Anfrage sendet einen Datenanbieter und eine Benutzer-ID an [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

Die Antwort gibt die Audience Manager-ID (z. B. `UUID`) zurück, die in ein Erstanbieter-Cookie in der Seitendomäne geschrieben wird.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Keine Target- und Opt-out-Aufrufe {#do-not-target}

Der Prozess [!UICONTROL declared ID] berücksichtigt die Site-Besucherpräferenzen, um das Targeting von [!DNL Audience Manager] durch Ihre Website abzuwählen. Wenn [!DNL Audience Manager] eine Opt-out-Anfrage erhält, gibt der [!DNL DCS] ein leeres [!DNL JSON] -Objekt anstelle der [!DNL Audience Manager] Benutzer-ID zurück.

>[!MORELIKETHIS]
>
>* [CID ersetzt DPID und DPUUID](../reference/cid.md)

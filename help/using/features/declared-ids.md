---
description: Funktionsweise von deklarierten IDs, Einrichten von Prozeduren, Code-Beispielen und Variablen.
keywords: ID-Synchronisierung
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

Funktionsweise[!UICONTROL declared IDs] Einrichtung von Prozeduren, Code-Beispielen und Variablen.

## [!UICONTROL Declared ID] Zielsetzung {#declared-id-targeting}

Austausch und Synchronisierung von Benutzer-IDs mit [!DNL Audience Manager] von Geräten oder Browsern, die keine persistenten Speichermechanismen wie [!DNL cookies] von Drittanbietern verwenden oder akzeptieren.

## Zweck des [!UICONTROL Declared ID] Targeting {#declared-id-targeting-purpose}

Einige Browser und die meisten Mobilgeräte akzeptieren keine [!DNL cookies] von Drittanbietern. Dies erschwert die Speicherung von Informationen über Site-Besucher oder die Zuweisung persistenter IDs. Um dieses Problem zu beheben, verwendet [!DNL Audience Manager] [!UICONTROL DIL], damit Sie bei einem Ereignisaufruf [!UICONTROL declared IDs] übergeben können. Außerdem kann ein [!UICONTROL declared ID] als universelle ID agieren, die für denselben Benutzer für alle Lösungen in der [!DNL Experience Cloud] gilt. Die folgende Tabelle beschreibt den Prozess zum Targeting von IDs/Abgleich:

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
   <td colname="col2"> <p>Dazu benötigen Sie <span class="wintitle"> DIL-</span> und den <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service-</a>-Code auf der Seite. <span class="wintitle"> DIL </span> erhält <span class="wintitle"> deklarierten IDs, die von der <code> setVisitorID </code> Funktion </span> werden, die von der <span class="keyword"> Adobe Experience Platform Identity Service-</span> bereitgestellt wird, und übergibt diese an <span class="keyword"> Audience Manager-</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Match-ID</b> </td> 
   <td colname="col2"> <p>Der Audience Manager versucht, die Client- und Besucher-ID mit einer entsprechenden ID in unserem System abzugleichen. Wenn keine übereinstimmende ID vorhanden ist, erstellt der Audience Manager eine neue ID und verknüpft sie mit der Client- und Besucher-ID. </p> <p> <p>Hinweis: Die neueste Zuordnung wird verwendet, wenn Ihre ID mehr als einer Audience Manager-ID zugeordnet ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Rückgabe-ID</b> </td> 
   <td colname="col2"> <p>Der Audience Manager schreibt seine synchronisierte ID in ein Erstanbieter-Cookie (oder einen anderen adressierbaren Speicherplatz) in der Client-Domain oder im Programm. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Nachfolgende Ereignisaufrufe</b> </td>
   <td colname="col2"> <p>Zusätzliche Ereignisaufrufe lesen die Audience Manager-ID aus der Domain des Clients und senden diese an den Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Zu Beginn müssen Sie den [!DNL Experience Cloud]-ID-Service konfigurieren und die Seiten auf Ihrer Site [!UICONTROL DIL], die Sie für die Datenerfassung verwenden möchten. Siehe [DIL erstellen](../dil/dil-class-overview/dil-create.md#dil-create) und [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out-Aufrufe {#opt-out-calls}

Der [!UICONTROL declared ID] berücksichtigt die Präferenzen der Site-Besucher, die sich vom Targeting [!DNL Audience Manager] Ihrer Website abmelden möchten. Wenn [!DNL Audience Manager] eine Opt-out-Anfrage erhält, enthält die vom [!DNL DCS] zurückgegebene [!DNL JSON] den Fehlercode 171 mit der `Encountered opt out tag` Nachricht anstelle der [!DNL Audience Manager] Benutzer-ID.

* [!DNL Audience Manager] können eine [!UICONTROL declared ID]-Abmeldung zusammen mit einer [!DNL Audience Manager]-[!UICONTROL UUID] im [!DNL URL] übergeben.
* Die [!UICONTROL declared ID] Opt-out-Option wird in der [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) pro Partner gespeichert. Es gibt kein Opt-out auf Plattformebene mit [!UICONTROL declared IDs]. Darüber hinaus verhindert [!DNL Audience Manager], dass Benutzende aus diesem bestimmten Bereich am Edge abgemeldet werden (die Abmeldung betrifft nicht [!DNL DCS] Bereiche).

Weitere [ zum Opt-out von der Datenerfassung finden ](../overview/data-security-and-privacy/data-privacy.md) unter „Datenschutz“.

## Beispiele für [!UICONTROL Declared ID] Opt-out {#opt-out-examples}

Mit den Schlüssel-Wert-Paaren `d_cid` und `d_cid_ic` können Sie [!UICONTROL declared ID] Anfragen zum Opt-out stellen. Die veralten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../reference/cid.md). In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

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
   <td colname="col1"> <p>Mehrere <code> d_cid </code> und <code> d_cid_ic </code> Schlüssel-Wert-Paare. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-outs mit [!UICONTROL DPID], [!UICONTROL DPUUID] und [!UICONTROL UUID] (veraltet)

Diese Methoden funktionieren weiterhin, gelten aber als veraltet. Diese Informationen werden zu Legacy-Zwecken und als Referenz bereitgestellt. Zu den Legacy-Opt-outs gehören:

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Ein Opt-out auf Partnerebene wird für die neueste Zuordnung dieses <code> dpid </code> + <code> dpuuid </code> Paares zu einer AAM-UUID gespeichert. Wenn keine zuvor bestehende Zuordnung vorhanden ist, prüft Audience Manager, ob die Anfrage eine AAM-UUID im Cookie enthält. Ist dies der Fall, verwendet Adobe diese zum Speichern des Opt-outs. Andernfalls generiert Audience Manager eine neue AAM-UUID und speichert die Abmeldung darunter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> und explizite <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> hat immer Vorrang. Wenn die Kombination <code> dpid </code> + <code> dpuuid </code> einer anderen AAM-UUID zugeordnet ist, wird das Opt-out unter der in der Anfrage übergebenen AAM-UUID gespeichert ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variablen und Syntax für [!UICONTROL Declared IDs] {#variables-and-syntax}

In der folgenden Tabelle sind die Schlüssel-Wert-Paare aufgeführt, die bei Verwendung Ihre [!DNL Audience Manager]-Datenanbieter-ID sowie Benutzer-IDs oder Integrations-Codes übergeben. Hinweis: *Kursiv* gibt einen Variablenplatzhalter an. Es wurden Leerzeichen hinzugefügt, um die Lesbarkeit zu verbessern.

In jedem Schlüssel-Wert-Paar:

* Das `=` trennt den Schlüssel von den zugehörigen Werten.
* Die nicht druckbare [!DNL ASCII] trennt die Werte `%01`.

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
   <td colname="col2"> <p>Enthält einen Integrations-Code und eine zugehörige eindeutige Benutzer-ID in einem einzelnen Schlüssel-Wert-Paar. <code> d_cid_ic </code> ersetzt <code> d_dpid </code> und <code> d_dpuuid </code>, die veraltet sind, aber weiterhin unterstützt werden. Siehe <a href="../reference/cid.md"> CID ersetzt DPID und DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiele für Ereignisaufrufe {#sample-event-calls}

Angesichts dieser Schlüssel-Wert-Paare und ihrer erforderlichen Syntax würden Sie wie unten dargestellt Ereignisaufrufe durchführen.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Der Ereignisaufruf umfasst </th> 
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
   <td colname="col1"> <p>Mehrere <code> d_cid </code> und <code> d_cid_ic </code> Schlüssel-Wert-Paare. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variablen {#declared-id-variables}

Beschreibt die Konfigurationsvariablen, mit denen [!UICONTROL declared IDs] über [!UICONTROL DIL] an [!DNL Audience Manager.] weitergeleitet werden

## [!UICONTROL DIL] verwendet die [!DNL Adobe Experience Platform Identity Service], um [!UICONTROL Declared IDs] zu übergeben {#dil-id-service-pass-declared-ids}

Bei Verwendung mit dem [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) müssen Sie keine [!UICONTROL declared IDs] mit den veralteten `dpid`- und `dpuuid`-Variablen mehr übergeben. Stattdessen verwenden die aktuellen Versionen von [!UICONTROL DIL] die Funktion `visitorService` , um die [!UICONTROL declared IDs] aus der Funktion `setCustomerIDs` in der [!UICONTROL Adobe Experience Platform Identity Service] abzurufen. Weitere Informationen finden Sie unter [Kunden-IDs und Authentifizierungsstatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). Sie würden `visitorService` wie unten dargestellt in `DIL.create` aufrufen.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Im `namespace` Schlüssel-Wert-Paar ist `MCORG` Ihre [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im Abschnitt [!UICONTROL Administration] des [!DNL Experience Cloud]-Dashboards. Sie benötigen Administratorberechtigungen, um dieses Dashboard anzeigen zu können. Siehe [Administration: Zentrale Dienste](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## Veraltete Funktionen {#deprecated-functions}

Bei den neuesten Versionen von [!UICONTROL DIL] (6.2+) müssen Sie diese Schlüssel-Wert-Paare nicht verwenden, um [!UICONTROL declared IDs] zu übergeben. Dies liegt daran, dass [!UICONTROL DIL] jetzt auf die im obigen Codebeispiel dargestellte `visitorService` angewiesen ist. Diese Funktion wird aus der [!UICONTROL Adobe Experience Platform Identity Service] [!UICONTROL declared IDs]. Wir verweisen hier jedoch aus historischen und Legacy-Gründen auf diese Variablen. Im folgenden Code finden Sie ein Beispiel dafür, wie Sie `DIL.create` konfigurieren, um eine [!UICONTROL declared ID] aus dem [!UICONTROL Visitor ID Service] abzurufen.
In der folgenden Tabelle werden die Legacy-Variablen beschrieben, die vom `declaredId`-Objekt verwendet werden:

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
   <td colname="col3"> <p>Datenpartner-ID, die vom Audience Manager zugewiesen wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>Die eindeutige Datenanbieter-ID für den Benutzer. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] und [!UICONTROL DPUUID]

[!DNL Audience Manager] vergleicht und gleicht die kombinierten `DPID` und `DPUUID` mit einer entsprechenden Benutzer-ID in unserem System ab. Wenn keine ID vorhanden ist, erstellt [!DNL Audience Manager] eine neue Benutzer-ID und synchronisiert sie mit der `DPID/DPUUID`. Sobald [!DNL Audience Manager] mit einer Benutzer-ID (der `UUID`) übereinstimmt oder eine solche erstellt, wird diese ID in der [!DNL JSON] Antwort auf die [!DNL cookie] in der Domain des Clients (Erstanbieter-[!DNL cookie]) oder einem anderen lokalen Speicher zurückgegeben.

Rufen Sie diese Funktion auf, wenn Sie [!UICONTROL DIL] v6.1 oder früher verwenden. Diese Funktion wird jedoch zugunsten der neuen Version, die aus der [!DNL Adobe Experience Platform Identity Service] [!UICONTROL declared IDs] wird, nicht mehr unterstützt.

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
>Sie müssen programmgesteuert den Code entwickeln, der die ID-Werte für die `d_dpuuid`- und `d_dpid` bereitstellt.

### Übergeben von IDs nach [!UICONTROL DIL] Instanziierung

>[!NOTE]
>
>Wenn Sie einen [!DNL API] Aufruf mit einer anderen `declaredID` ausführen, wird die neue Kombination nur für diesen Aufruf verwendet. Weitere regelmäßige Ereignisaufrufe verwenden die ursprüngliche `DIL.create` `declaredID`.

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

Die Antwort gibt die Audience Manager-ID zurück (z. B. `UUID`), die in ein Erstanbieter-Cookie in der Seiten-Domain geschrieben wird.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## KEIN Targeting von und Opt-out-Aufrufen {#do-not-target}

Der [!UICONTROL declared ID] berücksichtigt die Präferenzen der Site-Besucher, die sich vom Targeting [!DNL Audience Manager] Ihrer Website abmelden möchten. Wenn [!DNL Audience Manager] eine Opt-out-Anfrage erhält, gibt die [!DNL DCS] ein leeres [!DNL JSON]-Objekt anstelle der [!DNL Audience Manager] Benutzer-ID zurück.

>[!MORELIKETHIS]
>
>* [CID ersetzt DPID und DPUUID](../reference/cid.md)

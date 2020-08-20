---
description: Funktionsweise deklarierter IDs, Einrichtung von Verfahren, Codebeispielen und Variablen.
keywords: id sync
seo-description: Funktionsweise deklarierter IDs, Einrichtung von Verfahren, Codebeispielen und Variablen.
seo-title: Deklarierte IDs
solution: Audience Manager
title: Deklarierte IDs
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
translation-type: tm+mt
source-git-commit: 29708d5fc528ac9da08f4c5a7f2bcaa11b240d8b
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 10%

---


# [!UICONTROL Declared IDs] {#declared-ids}

Funktionsweise, [!UICONTROL declared IDs] Einrichten von Prozeduren, Codebeispielen und Variablen.

## [!UICONTROL Declared ID] Zielsetzung {#declared-id-targeting}

Tauschen Sie Benutzer-IDs mit [!DNL Audience Manager] Geräten oder Browsern aus, die keine persistenten Datenspeicherung verwenden oder akzeptieren, wie z. B. Drittanbieter, und synchronisieren Sie diese [!DNL cookies].

## Zweck des [!UICONTROL Declared ID] Targeting {#declared-id-targeting-purpose}

Einige Browser und die meisten Mobilgeräte akzeptieren kein Drittanbieter [!DNL cookies]. Dadurch wird es schwierig, Informationen über Site-Besucher beizubehalten oder beständige IDs zuzuweisen. Um dieses Problem zu beheben, [!DNL Audience Manager] können Sie [!UICONTROL DIL] es verwenden, um einen Ereignis-Aufruf [!UICONTROL declared IDs] zu übermitteln. Darüber hinaus [!UICONTROL declared ID] kann ein Benutzer als universelle ID fungieren, die für denselben Benutzer in allen Lösungen in der [!DNL Experience Cloud]Benutzeroberfläche gilt. Die folgende Tabelle beschreibt den ID-Targeting-/Abgleichungsprozess:

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Verarbeitung </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Ereignis-Aufruf</b> </td> 
   <td colname="col2"> <p>Zur Arbeit benötigen Sie <span class="wintitle"> DIL </span> und den <a href="https://docs.adobe.com/content/help/de-DE/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service- </a> Code auf der Seite. <span class="wintitle"> DIL </span> erhält <span class="wintitle"> deklarierte IDs </span> aus der <code> setVisitorID </code> Funktion, die vom <span class="keyword"> Adobe Experience Platform Identity Service bereitgestellt wird, </span> und übergibt diese an den <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Übereinstimmung-ID</b> </td> 
   <td colname="col2"> <p>Audience Manager versucht, die Client- und Besucher-ID mit einer entsprechenden ID in unserem System abzugleichen. Wenn keine übereinstimmende ID vorhanden ist, erstellt Audience Manager eine neue ID und verknüpft diese mit der Client- und Besucher-ID. </p> <p> <p>Hinweis:  Die neueste Zuordnung wird verwendet, wenn Ihre ID mehr als einer Audience Manager-ID zugeordnet ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Rückgabe-ID</b> </td> 
   <td colname="col2"> <p>Audience Manager schreibt seine synchronisierte ID in ein Erstanbieter-Cookie (oder einen anderen adressierbaren Datenspeicherung-Bereich) in der Clientdomäne oder Anwendung. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Nachfolgende Ereignis-Aufrufe</b> </td>
   <td colname="col2"> <p>Zusätzliche Ereignis-Aufrufe lesen die Audience Manager-ID aus der Clientdomäne und senden diese an den Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Um zu beginnen, müssen Sie den [!DNL Experience Cloud] ID-Dienst und [!UICONTROL DIL] über die Seiten Ihrer Site, die Sie für die Datenerfassung verwenden möchten, konfigurieren. Siehe [DIL Erstellen](../dil/dil-class-overview/dil-create.md#dil-create) und [Deklarieren von ID-Variablen](../features/declared-ids.md#declared-id-variables).

## Ausschluss-Anrufe {#opt-out-calls}

Der [!UICONTROL declared ID] [!DNL Audience Manager] Vorgang berücksichtigt die Voreinstellungen des Site-Besuchers, um das Targeting auf Ihrer Website abzuwählen. When [!DNL Audience Manager] receives an opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the error code 171, with the message `Encountered opt out tag`, instead of the [!DNL Audience Manager] user ID.

* [!DNL Audience Manager] kann ein [!UICONTROL declared ID] Opt-out zusammen mit einem [!DNL Audience Manager] in der [!UICONTROL UUID] [!DNL URL].
* Das [!UICONTROL declared ID] Opt-out wird in der Datei [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) pro Partner gespeichert. Es gibt keinen Ausschluss auf Plattformebene [!UICONTROL declared IDs]. Darüber hinaus [!DNL Audience Manager] wird der Benutzer an der Kante aus dieser bestimmten Region ausgeschlossen (das Opt-out erfolgt nicht über [!DNL DCS] Regionen hinweg).

Weitere Informationen zum Ausschluss von der Datenerfassung finden Sie unter [Datenschutz](../overview/data-security-and-privacy/data-privacy.md) .

## [!UICONTROL Declared ID] Ausschluss-Beispiele {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. Die veralten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../reference/cid.md). In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

### Opt-Outs mit [!UICONTROL CID] und [!UICONTROL CID_IC]

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
   <td colname="col1"> <p>Mehrere <code> d_cid </code> und <code> d_cid_ic </code> Schlüssel/Wert-Paare. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-Outs mit [!UICONTROL DPID], [!UICONTROL DPUUID]und [!UICONTROL UUID] (nicht mehr unterstützt)

Diese Methoden funktionieren weiterhin, werden jedoch als veraltet betrachtet. Diese Informationen werden zu veralteten Zwecken und als Referenz bereitgestellt. Ältere Opt-outs umfassen:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ausschluss (überholt) </th> 
   <th colname="col2" class="entry"> Code-Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> erst dann </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausschluss auf Partnerebene </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Ein Ausschluss auf Partnerebene wird für die neueste Zuordnung dieses <code> dpid </code> +- <code> dpuuid </code> Paars zu einer AAM UUID gespeichert. Wenn es keine bereits vorhandene Zuordnung gibt, prüft Audience Manager, ob die Anforderung eine AAM UUUID im Cookie enthält. Ist dies der Fall, verwendet diese zum Speichern der Ausschluss-ID. Andernfalls generiert Audience Manager eine neue AAM UUID und speichert die Ausschluss-ID darin. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> und explizit <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> immer Vorrang hat. Wenn die <code> dpid </code> +- <code> dpuuid </code> Kombination einer anderen AAM UUUID zugeordnet wird, wird die Ausschluss-ID unter der AAM UUID gespeichert, die in der Anforderung weitergegeben wird ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variablen und Syntax für [!UICONTROL Declared IDs] {#variables-and-syntax}

In der folgenden Tabelle werden die Schlüssel-Wert-Paare Liste, die bei Verwendung Ihre [!DNL Audience Manager] Datenanbieter-ID und Benutzer-IDs oder Integrationscodes weitergeben. Note, *italics* indicates a variable placeholder. Es wurden Leerzeichen hinzugefügt, um das Lesen zu vereinfachen.

In jedem Schlüssel-Wert-Paar:

* Das `=` Symbol trennt den Schlüssel von den zugehörigen Werten.
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
   <td colname="col2"> <p>Enthält eine Datenanbieter-ID und eine zugehörige eindeutige Benutzer-ID in einem Schlüssel/Wert-Paar. <code> d_cid </code> ersetzt <code> d_dpid </code> und <code> d_dpuuid </code>, die als nicht mehr unterstützt, aber dennoch unterstützt werden. Siehe <a href="../reference/cid.md">CID ersetzt DPID und DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Enthält einen Integrationscode und eine zugehörige eindeutige Benutzer-ID in einem einzelnen Schlüssel/Wert-Paar. <code> d_cid_ic </code> ersetzt <code> d_dpid </code> und <code> d_dpuuid </code>, die nicht mehr unterstützt, aber trotzdem unterstützt werden. Siehe <a href="../reference/cid.md">CID ersetzt DPID und DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ereignis-Beispielaufrufe {#sample-event-calls}

Angesichts dieser Schlüssel-Wert-Paare und ihrer erforderlichen Syntax würden Sie wie unten gezeigt Ereignis-Aufrufe durchführen.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ereignis-Aufruf beinhaltet </th> 
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
   <td colname="col1"> <p>Mehrere <code> d_cid </code> und <code> d_cid_ic </code> Schlüssel/Wert-Paare. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variablen {#declared-id-variables}

Beschreibt die Konfigurationsvariablen, die verwendet werden, um [!UICONTROL declared IDs] [!UICONTROL DIL] an [!DNL Audience Manager.]

## [!UICONTROL DIL] verwendet [!DNL Adobe Experience Platform Identity Service] die [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Bei Verwendung mit dem [Adobe Experience Platform-Identitätsdienst](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html)müssen Sie nicht mehr [!UICONTROL declared IDs] mit den veralteten `dpid` und `dpuuid` Variablen weitergeben. Stattdessen [!UICONTROL DIL] verlassen sich die aktuellen Versionen auf die `visitorService` Funktion, um die [!UICONTROL declared IDs] aus der `setCustomerIDs` Funktion in der [!UICONTROL Adobe Experience Platform Identity Service]zu erhalten. For more information, see [Customer IDs and Authentication States](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Sie rufen `visitorService` wie unten gezeigt `DIL.create` an.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Im `namespace` Schlüssel-Wert-Paar `MCORG` ist Ihre [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im [!UICONTROL Administration] Abschnitt des [!DNL Experience Cloud] Dashboards. Sie benötigen Administratorrechte, um dieses Dashboard Ansicht. See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Veraltete Funktionen {#deprecated-functions}

Bei den neuesten Versionen von [!UICONTROL DIL] (6.2+) müssen Sie diese Schlüssel-Wert-Paare nicht verwenden, um sie weiterzugeben [!UICONTROL declared IDs]. Das liegt daran, dass [!UICONTROL DIL] jetzt die im obigen Codebeispiel dargestellte `visitorService` Funktion verwendet wird. Diese Funktion wird [!UICONTROL declared IDs] von der [!UICONTROL Adobe Experience Platform Identity Service]. Wir verweisen hier jedoch auf diese Variablen aus historischen und alten Gründen. Im folgenden Code finden Sie ein Beispiel für die Konfiguration `DIL.create` zum Abrufen eines [!UICONTROL declared ID] Formulars aus dem [!UICONTROL Visitor ID Service].
In der folgenden Tabelle werden die vom `declaredId` Objekt verwendeten Variablen beschrieben:

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
   <td colname="col3"> <p>Von Audience Manager zugewiesene Datenpartner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Zeichenfolge </td> 
   <td colname="col3"> <p>Die eindeutige Datenanbieter-ID für den Benutzer. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] und [!UICONTROL DPUUID]

[!DNL Audience Manager] vergleicht und stimmt mit der kombinierten `DPID` und `DPUUID` einer entsprechenden Benutzer-ID in unserem System überein. Wenn keine ID vorhanden ist, [!DNL Audience Manager] wird eine neue Benutzer-ID erstellt und mit der `DPID/DPUUID` Kombination synchronisiert. Sobald eine Benutzer-ID (die [!DNL Audience Manager] ) `UUID`übereinstimmt oder erstellt wird, gibt sie diese ID in der [!DNL JSON] Antwort auf die [!DNL cookie] [!DNL cookie]Domäne des Kunden (Erstanbieter-ID) oder eine andere lokale Datenspeicherung zurück.

Rufen Sie diese Funktion auf, wenn Sie [!UICONTROL DIL] v6.1 oder früher verwenden. Diese Funktion wurde jedoch zugunsten der neuen Version aufgegeben, die [!UICONTROL declared IDs] von der [!DNL Adobe Experience Platform Identity Service].

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
>Sie müssen programmgesteuert den Code entwickeln, der die ID-Werte für die Schlüssel `d_dpuuid` und `d_dpid` -Schlüssel bereitstellt.

### Weitergeben von IDs nach [!UICONTROL DIL] Instanziierung

>[!NOTE]
>
>Wenn Sie einen [!DNL API] Aufruf mit einer anderen `declaredID` Kombination durchführen, wird die neue Kombination nur für diesen Aufruf verwendet. Bei weiteren regulären Ereignis-Aufrufen wird die ursprüngliche `DIL.create` Kombination verwendet `declaredID` .

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Anforderungs-/Antwortbeispiele {#request-response-examples}

Die Anforderung sendet einen Datenanbieter und eine Benutzer-ID an [!DNL Audience Manager]:

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

## Keine Zielgruppe- und Ausschluss-Aufrufe {#do-not-target}

Der [!UICONTROL declared ID] [!DNL Audience Manager] Vorgang berücksichtigt die Voreinstellungen des Site-Besuchers, um das Targeting auf Ihrer Website abzuwählen. Wenn [!DNL Audience Manager] eine Abmeldeanforderung eingeht, gibt die [!DNL DCS] ein leeres [!DNL JSON] Objekt anstelle der [!DNL Audience Manager] Benutzer-ID zurück.

>[!MORELIKETHIS]
>
>* [CID ersetzt DPID und DPUUID](../reference/cid.md)


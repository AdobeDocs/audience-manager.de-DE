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

Funktionsweise von [!UICONTROL declared IDs], Einrichten von Prozeduren, Codebeispielen und Variablen.

## [!UICONTROL Declared ID] Zielsetzung {#declared-id-targeting}

Tauschen Sie Benutzer-IDs mit [!DNL Audience Manager] von Geräten oder Browsern aus, die keine persistenten Datenspeicherung verwenden oder akzeptieren, wie z. B. [!DNL cookies] von Drittanbietern.

## Zweck von [!UICONTROL Declared ID] Targeting {#declared-id-targeting-purpose}

Einige Browser und die meisten Mobilgeräte akzeptieren kein Drittanbieter [!DNL cookies]. Dadurch wird es schwierig, Informationen über Site-Besucher beizubehalten oder beständige IDs zuzuweisen. Um dieses Problem zu beheben, verwendet [!DNL Audience Manager] [!UICONTROL DIL], damit Sie [!UICONTROL declared IDs] bei einem Ereignis-Aufruf übermitteln können. Außerdem kann ein [!UICONTROL declared ID] als universelle ID fungieren, die für denselben Benutzer in allen Lösungen von [!DNL Experience Cloud] gilt. Die folgende Tabelle beschreibt den ID-Targeting-/Abgleichungsprozess:

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
   <td colname="col2"> <p>Für die Arbeit benötigen Sie <span class="wintitle"> DIL </span> und den <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external">-Adobe Experience Platform-Identitätsdienst </a>-Code auf der Seite. <span class="wintitle"> DIL  </span> erhält  <span class="wintitle"> deklarierte IDs  </span> aus der  <code> setVisitorID </code> Funktion des  <span class="keyword"> Adobe Experience Platform-Identitätsdienstes  </span> und übergibt diese an den  <span class="keyword"> Audience Manager  </span>. </p> </td> 
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

Um zu beginnen, müssen Sie den [!DNL Experience Cloud]-ID-Dienst und [!UICONTROL DIL] für die Seiten Ihrer Site konfigurieren, die Sie für die Datenerfassung verwenden möchten. Siehe [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) und [Deklarierte ID-Variablen](../features/declared-ids.md#declared-id-variables).

## Ausschluss-Aufrufe {#opt-out-calls}

Der [!UICONTROL declared ID]-Prozess berücksichtigt Site-Besucher-Voreinstellungen, um [!DNL Audience Manager]-Targeting von Ihrer Website abzuwählen. Wenn [!DNL Audience Manager] eine Abmeldeanforderung empfängt, enthält das von [!DNL DCS] zurückgegebene [!DNL JSON] den Fehlercode 171 mit der Meldung `Encountered opt out tag` anstelle der [!DNL Audience Manager] Benutzer-ID.

* [!DNL Audience Manager] kann ein  [!UICONTROL declared ID] Opt-out neben einem  [!DNL Audience Manager] [!UICONTROL UUID] in der übergeben  [!DNL URL].
* Die [!UICONTROL declared ID]-Abmeldung wird pro Partner im [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) gespeichert. Mit [!UICONTROL declared IDs] gibt es kein Ausschluss auf Plattformebene. Außerdem wird der Benutzer durch [!DNL Audience Manager] aus dieser bestimmten Region am Rand ausgeschlossen (die Ausschluss-Option überschreitet nicht die Bereiche [!DNL DCS]).

Weitere Informationen zum Ausschluss von der Datenerfassung finden Sie unter [Datenschutz](../overview/data-security-and-privacy/data-privacy.md).

## [!UICONTROL Declared ID] Ausschluss-Beispiele  {#opt-out-examples}

Sie können mit den Schlüssel-Wert-Paaren `d_cid` und `d_cid_ic` Abmeldeanfragen stellen. [!UICONTROL declared ID] Die veralten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../reference/cid.md). In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

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
   <td colname="col1"> <p>Mehrere Schlüssel-Wert-Paare <code> d_cid </code> und <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-Outs mit [!UICONTROL DPID], [!UICONTROL DPUUID] und [!UICONTROL UUID] (nicht mehr unterstützt)

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Ein Ausschluss auf Partnerebene wird für die letzte Zuordnung dieses <code> dpid </code> + <code> dpuuid </code>-Paars zu einer AAM UUID gespeichert. Wenn es keine bereits vorhandene Zuordnung gibt, prüft Audience Manager, ob die Anforderung eine AAM UUUID im Cookie enthält. Ist dies der Fall, verwendet diese zum Speichern der Ausschluss-ID. Andernfalls generiert Audience Manager eine neue AAM UUID und speichert die Ausschluss-ID darin. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> +  <code> d_dpid </code> und explizit  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> immer Vorrang hat. Wenn die Kombination <code> dpid </code> + <code> dpuuid </code> einer anderen AAM UUUID zugeordnet wird, wird die Ausschluss-ID unter der AAM UUID gespeichert, die in der Anforderung ( <code> d_uuid </code>) übergeben wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variablen und Syntax für [!UICONTROL Declared IDs] {#variables-and-syntax}

In der folgenden Tabelle werden die Schlüssel-Wert-Paare Liste, die bei Verwendung Ihre [!DNL Audience Manager] Datenanbieter-ID und Benutzer-IDs oder Integrationscodes übermitteln. Hinweis: *kursiv* gibt einen Variablenplatzhalter an. Es wurden Leerzeichen hinzugefügt, um das Lesen zu vereinfachen.

In jedem Schlüssel-Wert-Paar:

* Das `=`-Symbol trennt den Schlüssel von den zugehörigen Werten.
* Das nicht druckbare [!DNL ASCII]-Zeichen `%01` trennt die Werte.

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
   <td colname="col2"> <p>Enthält eine Datenanbieter-ID und eine zugehörige eindeutige Benutzer-ID in einem Schlüssel/Wert-Paar. <code> d_cid </code> ersetzt  <code> d_dpid </code> und  <code> d_dpuuid </code>, die als nicht mehr unterstützt, aber dennoch unterstützt werden. Siehe <a href="../reference/cid.md">CID ersetzt DPID und DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Enthält einen Integrationscode und eine zugehörige eindeutige Benutzer-ID in einem einzelnen Schlüssel/Wert-Paar. <code> d_cid_ic </code> ersetzt  <code> d_dpid </code> und  <code> d_dpuuid </code>, die nicht mehr unterstützt, aber dennoch unterstützt werden. Siehe <a href="../reference/cid.md">CID ersetzt DPID und DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispiel-Ereignis-Aufrufe {#sample-event-calls}

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
   <td colname="col1"> <p>Mehrere Schlüssel-Wert-Paare <code> d_cid </code> und <code> d_cid_ic </code>. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variablen {#declared-id-variables}

Beschreibt die Konfigurationsvariablen, mit denen [!UICONTROL declared IDs] durch [!UICONTROL DIL] an [!DNL Audience Manager.] übergeben wird

## [!UICONTROL DIL] verwendet  [!DNL Adobe Experience Platform Identity Service] die  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Bei Verwendung mit dem [Adobe Experience Platform-Identitätsdienst](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html) müssen Sie [!UICONTROL declared IDs] nicht mehr mit den nicht mehr unterstützten Variablen `dpid` und `dpuuid` übergeben. Stattdessen verlassen sich die aktuellen Versionen von [!UICONTROL DIL] auf die Funktion `visitorService`, um [!UICONTROL declared IDs] von der Funktion `setCustomerIDs` in [!UICONTROL Adobe Experience Platform Identity Service] abzurufen. Weitere Informationen finden Sie unter [Kunden-IDs und Authentifizierungsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Sie würden `visitorService` in `DIL.create` aufrufen, wie unten dargestellt.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Im Schlüssel-Wert-Paar `namespace` ist `MCORG` Ihre [!DNL Experience Cloud]-Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im Abschnitt [!UICONTROL Administration] des [!DNL Experience Cloud]-Dashboards. Sie benötigen Administratorrechte, um dieses Dashboard Ansicht. Siehe [Administration: Hauptdienste](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Veraltete Funktionen {#deprecated-functions}

Bei den neuesten Versionen von [!UICONTROL DIL] (6.2+) müssen Sie diese Schlüssel-Wert-Paare nicht verwenden, um [!UICONTROL declared IDs] weiterzugeben. Das liegt daran, dass [!UICONTROL DIL] jetzt auf der Funktion `visitorService` basiert, die im obigen Codebeispiel gezeigt wird. Diese Funktion ruft [!UICONTROL declared IDs] von [!UICONTROL Adobe Experience Platform Identity Service] ab. Wir verweisen hier jedoch auf diese Variablen aus historischen und alten Gründen. Im folgenden Code finden Sie ein Beispiel dafür, wie `DIL.create` so konfiguriert wird, dass ein [!UICONTROL declared ID] von [!UICONTROL Visitor ID Service] abgerufen wird.
Die folgende Tabelle beschreibt die vom `declaredId`-Objekt verwendeten alten Variablen:

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

[!DNL Audience Manager] vergleicht und stimmt mit der kombinierten  `DPID` und  `DPUUID` mit einer entsprechenden Benutzer-ID in unserem System überein. Wenn keine ID vorhanden ist, erstellt [!DNL Audience Manager] eine neue Benutzer-ID und synchronisiert sie mit der Kombination `DPID/DPUUID`. Wenn [!DNL Audience Manager] eine Benutzer-ID (die `UUID`) erfüllt oder erstellt, gibt sie diese ID in der [!DNL JSON]-Antwort auf das [!DNL cookie] in der Clientdomäne (Erstanbieter [!DNL cookie]) oder in einer anderen lokalen Datenspeicherung zurück.

Rufen Sie diese Funktion auf, wenn Sie [!UICONTROL DIL] v6.1 oder früher verwenden. Diese Funktion wurde jedoch zugunsten der neuen Version aufgegeben, die [!UICONTROL declared IDs] von [!DNL Adobe Experience Platform Identity Service] erhält.

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

### Übergeben von IDs nach [!UICONTROL DIL]-Instanziierungen

>[!NOTE]
>
>Wenn Sie einen [!DNL API]-Aufruf mit einer anderen `declaredID`-Kombination durchführen, wird die neue Kombination nur für diesen Aufruf verwendet. Bei weiteren regulären Ereignis-Aufrufen wird die ursprüngliche `DIL.create` `declaredID`-Kombination verwendet.

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

Der [!UICONTROL declared ID]-Prozess berücksichtigt Site-Besucher-Voreinstellungen, um [!DNL Audience Manager]-Targeting von Ihrer Website abzuwählen. Wenn [!DNL Audience Manager] eine Abmeldeanforderung empfängt, gibt [!DNL DCS] ein leeres [!DNL JSON]-Objekt anstelle der [!DNL Audience Manager]-Benutzer-ID zurück.

>[!MORELIKETHIS]
>
>* [CID ersetzt DPID und DPUUID](../reference/cid.md)


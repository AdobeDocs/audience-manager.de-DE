---
description: Wie deklarierte IDs funktionieren, richten Sie Prozeduren, Codebeispiele und Variablen ein.
keywords: ID-Synchronisierung
seo-description: Wie deklarierte IDs funktionieren, richten Sie Prozeduren, Codebeispiele und Variablen ein.
seo-title: Deklarierte IDs
solution: Audience Manager
title: Deklarierte IDs
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 36 d 2 a 3
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Deklarierte IDs {#declared-ids}

Wie deklarierte IDs funktionieren, richten Sie Prozeduren, Codebeispiele und Variablen ein.

## Deklariertes ID-Targeting {#declared-id-targeting}

Tauschen Sie Benutzer-IDs mit Audience Manager von Geräten oder Browsern aus, die keine persistenten Speichermechanismen verwenden oder akzeptieren, z. B. Drittanbieter-Cookies.

<!-- declared_id_about.xml -->

## Zweck des deklarierten ID-Ziels {#declared-id-targeting-purpose}

Einige Browser und die meisten Mobilgeräte akzeptieren keine Drittanbieter-Cookies. Dadurch ist es schwierig, Informationen zu Site-Besuchern beizubehalten oder persistente IDs zuzuweisen. Um dieses Problem zu beheben, verwendet Audience Manager, [!UICONTROL DIL] damit Sie [!UICONTROL declared IDs] bei einem Ereignisaufruf weitergeben können. Außerdem [!UICONTROL declared ID] kann eine universelle ID als universelle ID gelten, die für denselben Benutzer in allen Lösungen des Benutzers [!DNL Experience Cloud]gilt. In der folgenden Tabelle wird der ID-Targeting-/Übereinstimmungsprozess beschrieben:

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
   <td colname="col2"> <p>Um zu funktionieren, benötigen <span class="wintitle"> Sie DIL </span> und den <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID-Dienst </a> -Code auf der Seite. <span class="wintitle"> DIL </span> ruft <span class="wintitle"> IDs </span> aus der Funktion <code> setvisitorid </code> ab, die vom <span class="keyword"> Experience Cloud ID-Dienst </span> bereitgestellt wird, und übergibt diese an <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Übereinstimmung ID</b> </td> 
   <td colname="col2"> <p>Audience Manager versucht, die Client- und Besucher-ID mit einer entsprechenden ID in unserem System zu vergleichen. Wenn keine übereinstimmende ID vorhanden ist, erstellt Audience Manager eine neue ID und verknüpft sie mit dem Client und der Besucher-ID. </p> <p> <p>Hinweis: Die aktuellste Zuordnung wird verwendet, wenn Ihre ID mehreren Audience Manager-Ids zugeordnet ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Rückgabe-ID</b> </td> 
   <td colname="col2"> <p>Audience Manager schreibt seine synchronisierte ID in der Client-Domäne oder Anwendung in ein Erstanbieter-Cookie (oder einen anderen adressierbaren Speicherplatz). </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Nachfolgende Ereignisaufrufe</b> </td>
   <td colname="col2"> <p>Zusätzliche Ereignisaufrufe lesen die Audience Manager-ID aus der Domäne des Kunden und senden diese an Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Um zu beginnen, müssen Sie den [!DNL Experience Cloud] ID-Dienst und [!UICONTROL DIL] die Seiten auf Ihrer Site konfigurieren, die Sie für die Datenerfassung verwenden möchten. Siehe [DIL-erstellen](../dil/dil-class-overview/dil-create.md#dil-create) und [deklarierte ID-Variablen](../features/declared-ids.md#declared-id-variables).

## Abmeldeaufrufe {#opt-out-calls}

Der [!UICONTROL declared ID] Prozess berücksichtigt die Voreinstellungen der Site-Besucher, um das Targeting von Audience Manager durch Ihre Website auszuschließen. Wenn Audience Manager eine Abmeldeanfrage empfängt, wird die [!DNL JSON] von dem Fehler [!UICONTROL DCS] "Enthält" zurückgegebene Version 171 mit der Meldung" Encountered opt out tag" anstatt der Audience Manager-Benutzer-ID zurückgegeben.

* Audience Manager kann eine [!UICONTROL declared ID] Abmeldung neben Audience Manager [!UICONTROL UUID] im Abschnitt[!DNL URL]
* Die [!UICONTROL declared ID] Abmeldung wird im [! UICONTROL Profile Cache Server ([!UICONTROL PCS]) pro Partner. Es gibt keine [!UICONTROL declared IDs]Abmeldeoption auf Plattformebene. Darüber hinaus wird der Benutzer von Audience Manager aus diesem bestimmten Bereich auf der Kante abgelegt (der Ausschluss ist nicht über [!UICONTROL DCS] die Regionen hinweg möglich).

Weitere [Informationen](../overview/data-security-and-privacy/data-privacy.md) zur Deaktivierung der Datenerfassung finden Sie unter Datenschutz.

## Deklarierte ID-Ausschluss-Beispiele {#opt-out-examples}

Sie können [!UICONTROL declared ID] Abmeldeanforderungen mit den `d_cid` Schlüsselwertpaaren `d_cid_ic` erstellen. Die alten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden aber als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Ausschlussmöglichkeiten mit CID und CID_ IC

Eine Beschreibung und eine Syntax finden Sie unter [URL-Variablen und Syntax für deklarierte IDs](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ausschluss mit </th> 
   <th colname="col2" class="entry"> Codebeispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eine Datenanbieter-ID und Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/demoptout.jpg? d_ cid = 123% 19887… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrationscode und Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/demoptout? d_ cid_ ic = 456% 1321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mehrere d <code> _ cid </code> - und <code> d_ cid_ ic </code> -Schlüssel-Wert-Paare. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/demoptout? d_ cid = 123% 19887 &amp; d_ cid_ ic = 456% 1321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Ausschlussmöglichkeiten mit DPID, DPUUID und UUID (nicht mehr unterstützt)

Diese Methoden funktionieren weiterhin, werden aber als veraltet betrachtet. Diese Informationen werden für ältere Zwecke und Verweise bereitgestellt. Zu den alten Ausschlussmöglichkeiten gehören:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ausschluss (nicht mehr unterstützt) </th> 
   <th colname="col2" class="entry"> Codebeispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code></code> nur d_ uuid </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=AAM <i></i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausschluss auf Partnerebene </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= Benutzer ID &amp; d_ dpid = Datenanbieter-ID </code> </p> <p>Eine Abmeldung auf Partnerebene wird für die neueste Zuordnung dieses <code> dpid </code> + <code> dpuuid </code> -Paars zu einer AAM UUID gespeichert. Wenn keine bereits vorhandene Zuordnung vorhanden ist, prüft Audience Manager, ob die Anforderung eine AAM UUID im Cookie enthält, und verwendet, wenn dies der Fall ist, zum Speichern des Abmeldens verwendet. Andernfalls generiert Audience Manager eine neue AAM UUID und speichert die Abmeldeoption darunter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> und explizite <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>Benutzer ID &amp; d_ dpuuid = Data Provider's Benutzer ID &amp;<i>d_ dpid = data provider ID</i></code> </p> <p> <code> d_ uuid </code> hat immer Vorrang. Wenn die <code> dpid </code> + <code> dpuuid </code> -Kombination einer anderen AAM UUID zugeordnet wird, wird das Opt-out unter der AAM UUID gespeichert, die in der Anforderung übergeben wird ( <code> d_ uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variablen und Syntax für deklarierte IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

Die folgende Tabelle listet die Schlüssel/Wert-Paare auf, die Ihre [!DNL Audience Manager] Datenanbieter-ID sowie Benutzer-IDs oder Integrationscodes übergeben, sofern verwendet. Note, *italics* indicates a variable placeholder. Es wurden Leerzeichen hinzugefügt, um die Lesbarkeit zu erleichtern.

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
   <td colname="col1"> <p> <code> d_ cid =<i>Datenanbieter ID</i> % 01<i>Benutzer-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Enthält eine Datenanbieter-ID und eine zugehörige Benutzer-ID in einem einzelnen Schlüssel-Wert-Paar. <code> d_ cid </code> ersetzt <code> d_ dpid </code> und <code> d_ dpuuid </code>, die als veraltet gelten, aber weiterhin unterstützt werden. Siehe <a href="../reference/cid.md">CID ersetzt DPID und DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid_ ic =<i>Integrationscode</i> % 01<i>Benutzer-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Enthält einen Integrationscode und eine zugehörige eindeutige Benutzer-ID in einem einzelnen Schlüssel-Wert-Paar. <code> d_ cid_ ic </code> ersetzt <code> d_ dpid </code> und <code> d_ dpuuid </code>, die nicht mehr unterstützt werden, aber weiterhin unterstützt werden. Siehe <a href="../reference/cid.md">CID ersetzt DPID und DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Beispielereignisaufrufe {#sample-event-calls}

Anhand dieser Schlüssel-Wert-Paare und der erforderlichen Syntax würden Sie Ereignisaufrufe wie unten dargestellt durchführen.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ereignisaufruf beinhaltet </th> 
   <th colname="col2" class="entry"> Codebeispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eine Datenanbieter-ID und Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/event? d_ cid = 123% 19887… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrationscode und Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/event? d_ cid_ ic = 456% 1321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mehrere d <code> _ cid </code> - und <code> d_ cid_ ic </code> -Schlüssel-Wert-Paare. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/event? d_ cid = 123% 19887 &amp; d_ cid_ ic = 456% 1321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID ersetzt DPID und DPUUID](../reference/cid.md)


## Deklarierte ID-Variablen {#declared-id-variables}

Beschreibt die Konfigurationsvariablen, mit denen [!UICONTROL DIL] deklarierte IDs weitergegeben werden. [!DNL Audience Manager.]

## DIL Verwendet den Experience Cloud ID-Dienst, um deklarierte IDs zu übermitteln {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Bei Verwendung mit dem [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/)müssen Sie nicht mehr [!UICONTROL declared IDs] mit den veralteten `dpid` und `dpuuid` Variablen übergeben werden. Stattdessen werden die aktuellen Versionen von [!UICONTROL DIL] der `visitorService` Funktion verwendet, um von [!UICONTROL declared IDs] der `setCustomerIDs` Funktion in zu [!UICONTROL Experience Cloud ID Service]erhalten. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). Sie würden wie `visitorService` unten dargestellt `DIL.create` aufgerufen werden.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Ist im `namespace` Schlüssel-Wert-Paar `MCORG` Ihre [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, können Sie sie im [!UICONTROL Administration][!DNL Experience Cloud] Dashboard finden. Sie benötigen Administratorrechte, um dieses Dashboard anzuzeigen. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Veraltete Funktionen {#deprecated-functions}

Mit den neuesten Versionen von [!UICONTROL DIL] (6.2 +) müssen Sie diese Schlüssel/Wert-Paare nicht verwenden [!UICONTROL declared IDs]. Dies beruht darauf, dass [!UICONTROL DIL] nun die `visitorService` im obigen Codebeispiel angezeigte Funktion verwendet wird. Diese Funktion erhält [!UICONTROL declared IDs] von der [!UICONTROL Experience Cloud ID Service]. Wir verweisen jedoch auf diese Variablen zu historischen und alten Zwecken. Im folgenden Code finden Sie ein Beispiel dafür, wie Sie konfigurieren können `DIL.create` , wie Sie eine [!UICONTROL declared ID] von [!UICONTROL Visitor ID Service]denen erhalten.
Die folgende Tabelle beschreibt die alten Variablen, die vom `declaredId` Objekt verwendet werden:

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

### `DPID` und `DPUUID`

Audience Manager vergleicht die Kombination `DPID` und entspricht der `DPUUID` zugehörigen Benutzer-ID in unserem System. Wenn keine ID vorhanden ist, erstellt Audience Manager eine neue Benutzer-ID und synchronisiert sie mit der `DPID/DPUUID` Kombination. Sobald Audience Manager eine Benutzer-ID (die) `UUID`übereinstimmt oder erstellt, wird diese ID in der [!DNL JSON] Antwort auf das Cookie in der Domäne des Clients (Erstanbieter-Cookie) oder einem anderen lokalen Speicher zurückgegeben.

Rufen Sie diese Funktion auf, wenn [!UICONTROL DIL] Sie v 6.1 oder früher verwenden. Diese Funktion wurde jedoch zugunsten der neuen Version veraltet, die von [!UICONTROL declared IDs][!UICONTROL Experience Cloud ID Service]der folgenden stammt.

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
>Hinweis: Sie müssen programmgesteuert den Code entwickeln, der die ID-Werte für die `d_dpuuid` und `d_dpid` die Schlüssel bereitstellt.

### Ids nach DIL Instanziiert

>[!NOTE]
>
>Wenn Sie [!DNL API] einen Aufruf mit einer anderen `declaredID` Kombination vornehmen, wird die neue Kombination nur für diesen Aufruf verwendet. Weitere normale Ereignisaufrufe verwenden die ursprüngliche `DIL.create``declaredID` Kombination.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Anforderungs-/Antwortbeispiele {#request-response-examples}

Die Anforderung sendet einen Datenanbieter und eine Benutzer-ID an den Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

Die Antwort gibt die Audience Manager-ID (z. `UUID`B.) zurück, die in ein Erstanbieter-Cookie in der Seitendomäne geschrieben wird.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Keine Target- und Ausschluss-Aufrufe {#do-not-target}

Der [!UICONTROL declared ID] Prozess berücksichtigt die Voreinstellungen der Site-Besucher, um das Targeting von Audience Manager durch Ihre Website auszuschließen. Wenn Audience Manager eine Abmeldeanforderung erhält, wird ein [!UICONTROL DCS] leeres [!DNL JSON] Objekt anstelle der Audience Manager-Benutzer-ID zurückgegeben.

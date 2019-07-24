---
description: Wie deklarierte IDs funktionieren, richten Sie Prozeduren, Codebeispiele und Variablen ein.
keywords: ID-Synchronisierung
seo-description: Wie deklarierte IDs funktionieren, richten Sie Prozeduren, Codebeispiele und Variablen ein.
seo-title: Deklarierte IDs
solution: Audience Manager
title: Deklarierte IDs
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 36 d 2 a 3
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Declared IDs {#declared-ids}

Wie deklarierte IDs funktionieren, richten Sie Prozeduren, Codebeispiele und Variablen ein.

## Deklariertes ID-Targeting {#declared-id-targeting}

Tauschen Sie Benutzer-IDs mit Audience Manager von Geräten oder Browsern aus, die keine persistenten Speichermechanismen verwenden oder akzeptieren, z. B. Drittanbieter-Cookies.

<!-- declared_id_about.xml -->

## Purpose of Declared ID Targeting {#declared-id-targeting-purpose}

Einige Browser und die meisten Mobilgeräte akzeptieren keine Drittanbieter-Cookies. Dadurch ist es schwierig, Informationen zu Site-Besuchern beizubehalten oder persistente IDs zuzuweisen. To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. In der folgenden Tabelle wird der ID-Targeting-/Übereinstimmungsprozess beschrieben:

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
   <td colname="col2"> <p>To work, you need <span class="wintitle"> DIL </span> and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a> code on the page. <span class="wintitle"> DIL </span> ruft <span class="wintitle"> IDs </span> aus der Funktion <code> setvisitorid </code> ab, die vom <span class="keyword"> Experience Cloud ID-Dienst </span> bereitgestellt wird, und übergibt diese an <span class="keyword"> Audience Manager </span>. </p> </td> 
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

To get started, you need to configure the [!DNL Experience Cloud] ID service and [!UICONTROL DIL] across the pages on your site that you want to use for data collection. See [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out Calls {#opt-out-calls}

The [!UICONTROL declared ID] process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message "Encountered opt out tag", instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* The [!UICONTROL declared ID] opt-out is stored in the [!UICONTROL Profile Cache Serveîr ([!UICONTROL PCS]) on a per-partner basis. There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## Declared ID Opt-Out Examples {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. Siehe [CID ersetzt DPID und DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Ausschlussmöglichkeiten mit CID und CID_ IC

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

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
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= Benutzer ID &amp; d_ dpid = Datenanbieter-ID </code> </p> <p>A partner level opt-out gets stored for the latest mapping of this <code> dpid </code> + <code> dpuuid </code> pair to an AAM UUID. Wenn keine bereits vorhandene Zuordnung vorhanden ist, prüft Audience Manager, ob die Anforderung eine AAM UUID im Cookie enthält, und verwendet, wenn dies der Fall ist, zum Speichern des Abmeldens verwendet. Andernfalls generiert Audience Manager eine neue AAM UUID und speichert die Abmeldeoption darunter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> und explizite <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>Benutzer ID &amp; d_ dpuuid = Data Provider's Benutzer ID &amp;<i>d_ dpid = data provider ID</i></code> </p> <p> <code> d_ uuid </code> hat immer Vorrang. If the <code> dpid </code> + <code> dpuuid </code> combination maps to another AAM UUID, the opt-out is stored under the AAM UUID passed in the request ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables and Syntax for Declared IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

The following table lists the key-value pairs that pass in your [!DNL Audience Manager] data provider ID and user IDs or integration codes, if used. Note, *italics* indicates a variable placeholder. Es wurden Leerzeichen hinzugefügt, um die Lesbarkeit zu erleichtern.

In jedem Schlüssel-Wert-Paar:

* The `=` symbol separates the key from its related values.
* The non-printing [!DNL ASCII] character `%01` separates the values.

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

## Sample Event Calls {#sample-event-calls}

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
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>name</i>/event? d_ cid = 123% 19887 &amp; d_ cid_ ic = 456% 1321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID ersetzt DPID und DPUUID](../reference/cid.md)


## Declared ID Variables {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL Uses the Experience Cloud ID Service to Pass Declared IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

When used with the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), you no longer need to pass in [!UICONTROL declared IDs] with the deprecated `dpid` and `dpuuid` variables. Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call `visitorService` in `DIL.create` as shown below.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In the `namespace` key-value pair, `MCORG` is your [!DNL Experience Cloud] Organization ID. If you don't have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. Sie benötigen Administratorrechte, um dieses Dashboard anzuzeigen. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Deprecated Functions {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don't need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That's because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. Wir verweisen jedoch auf diese Variablen zu historischen und alten Zwecken. See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
The following table describes the legacy variables used by the `declaredId` object:

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

Audience Manager compares and matches the combined `DPID` and `DPUUID` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once Audience Manager matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the cookie in the client's domain (first-party cookie) or other local storage.

Call this function when you're using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

<pre class="js"><code>DIL. create ({ 
 Partner: " Name des Partners ", 
 Declaredid: { 
 dpuuid: <i>dpuuid</i>, 
 DPID: <i>dpid</i> 
 } 
 });</code>
</pre>

>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### Ids nach DIL Instanziiert

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original `DIL.create`  `declaredID` combination.

<pre class="js"><code>DIL. getdil (' partnername '). api. sign({…}). declaredid ({ 
 dpuuid:<i>dpuuid</i> 
 dpid:<i>dpid</i> }). 
submit ();</code>
</pre>

## Request/Response Examples {#request-response-examples}

Die Anforderung sendet einen Datenanbieter und eine Benutzer-ID an den Audience Manager:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Do Not Target and Opt-Out Calls {#do-not-target}

The [!UICONTROL declared ID] process honors site visitor preferences to opt-out of Audience Manager targeting by your website. When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.
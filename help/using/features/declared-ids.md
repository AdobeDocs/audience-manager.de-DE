---
description: Funktionsweise deklarierter IDs, Einrichtung von Verfahren, Codebeispielen und Variablen.
keywords: id sync
seo-description: Funktionsweise deklarierter IDs, Einrichtung von Verfahren, Codebeispielen und Variablen.
seo-title: Deklarierte IDs
solution: Audience Manager
title: Deklarierte IDs
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Deklarierte IDs {#declared-ids}

Funktionsweise deklarierter IDs, Einrichtung von Verfahren, Codebeispielen und Variablen.

## Deklariertes ID-Targeting {#declared-id-targeting}

Austausch und Synchronisierung von Benutzer-IDs mit Audience Manager von Geräten oder Browsern, die keine persistenten Speichermechanismen wie Drittanbieter-Cookies verwenden oder akzeptieren.

<!-- declared_id_about.xml -->

## Zweck des deklarierten ID-Targeting {#declared-id-targeting-purpose}

Einige Browser und die meisten Mobilgeräte akzeptieren keine Drittanbieter-Cookies. Dadurch wird es schwierig, Informationen über Site-Besucher beizubehalten oder beständige IDs zuzuweisen. Um dieses Problem zu beheben, können Sie mit Audience Manager [!UICONTROL DIL] einen Ereignisaufruf [!UICONTROL declared IDs] weiterleiten. Darüber hinaus [!UICONTROL declared ID] kann eine universelle ID verwendet werden, die für denselben Benutzer in allen Lösungen in der [!DNL Experience Cloud]Benutzeroberfläche gilt. Die folgende Tabelle beschreibt den ID-Targeting-/Abgleichungsprozess:

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
   <td colname="col2"> <p>Zur Arbeit benötigen Sie <span class="wintitle"> DIL </span> und den <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID-Dienst- </a> Code auf der Seite. <span class="wintitle"> DIL </span> ruft <span class="wintitle"> deklarierte IDs </span> aus der <code> setVisitorID </code> Funktion ab, die vom Experience Cloud ID-Dienst bereitgestellt wird, <span class="keyword"> und leitet diese an </span> Audience Manager weiter <span class="keyword"></span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Übereinstimmung-ID</b> </td> 
   <td colname="col2"> <p>Audience Manager versucht, der Kunden- und Besucher-ID eine entsprechende ID in unserem System zuzuordnen. Wenn keine übereinstimmende ID vorhanden ist, erstellt Audience Manager eine neue ID und verknüpft sie mit der Kunden- und Besucher-ID. </p> <p> <p>Hinweis:  Die neueste Zuordnung wird verwendet, wenn Ihre ID mehr als einer Audience Manager-ID zugeordnet ist. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Rückgabe-ID</b> </td> 
   <td colname="col2"> <p>Audience Manager schreibt seine synchronisierte ID in ein Erstanbieter-Cookie (oder einen anderen adressierbaren Speicherplatz) in der Clientdomäne oder Anwendung. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Nachfolgende Ereignisaufrufe</b> </td>
   <td colname="col2"> <p>Zusätzliche Ereignisaufrufe lesen die Audience Manager-ID aus der Domäne des Clients und senden sie an Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Um zu beginnen, müssen Sie den [!DNL Experience Cloud] ID-Dienst und [!UICONTROL DIL] die Seiten Ihrer Site konfigurieren, die Sie für die Datenerfassung verwenden möchten. Siehe [DIL-Variablen erstellen](../dil/dil-class-overview/dil-create.md#dil-create) und [deklarieren](../features/declared-ids.md#declared-id-variables).

## Ausschluss-Anrufe {#opt-out-calls}

Der [!UICONTROL declared ID] Prozess berücksichtigt die Voreinstellungen der Site-Besucher, um das Zielgruppen-Manager-Targeting auf Ihrer Website abzuwählen. Wenn Audience Manager eine Abmeldeanforderung erhält, enthält die [!DNL JSON] [!UICONTROL DCS] zurückgegebene Datei den Fehlercode 171 mit der Meldung "Abmelde-Tag gefunden"anstelle der Benutzer-ID von Audience Manager.

* Audience Manager kann eine [!UICONTROL declared ID] Abmeldung zusammen mit einem Audience Manager [!UICONTROL UUID] in der [!DNL URL]einreichen.
* Der [!UICONTROL declared ID] Ausschluss wird im [!UICONTROL Profile Cache Server ([!UICONTROL PCS]) pro Partner gespeichert. Es gibt keinen Ausschluss auf Plattformebene [!UICONTROL declared IDs]. Darüber hinaus wählt Audience Manager den Benutzer aus dieser bestimmten Region am Rand aus (die Abmeldung erfolgt nicht über [!UICONTROL DCS] Regionen hinweg).

Weitere Informationen zum Ausschluss von der Datenerfassung finden Sie unter [Datenschutz](../overview/data-security-and-privacy/data-privacy.md) .

## Deklarierte ID-Ausschluss-Beispiele {#opt-out-examples}

Sie können eine [!UICONTROL declared ID] Abmeldeanforderung mit den Paaren `d_cid` und `d_cid_ic` Schlüssel-Wert durchführen. Die alten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Ausschluss mit CID und CID_IC

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../features/declared-ids.md#variables-and-syntax).

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
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ein Integrationscode und eine Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mehrere <code> d_cid </code> und <code> d_cid_ic </code> Schlüssel/Wert-Paare. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-Outs mit DPID, DPUUID und UUID (nicht mehr unterstützt)

Diese Methoden funktionieren weiterhin, werden jedoch als veraltet betrachtet. Diese Informationen werden zu Legacy- und Referenzzwecken bereitgestellt. Ältere Opt-outs umfassen:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ausschluss (überholt) </th> 
   <th colname="col2" class="entry"> Codebeispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> erst dann </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausschluss auf Partnerebene </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Ein Ausschluss auf Partnerebene wird für die neueste Zuordnung dieses <code> dpid </code> +- <code> dpuuid </code> Paars zu einer AAM-UUID gespeichert. Wenn es keine bereits vorhandene Zuordnung gibt, prüft Audience Manager, ob die Anforderung eine AAM-UUID im Cookie enthält, und verwendet sie, falls dies der Fall ist, zum Speichern der Ausschluss-ID. Andernfalls generiert Audience Manager eine neue AAM-UUID und speichert die Ausschluss-Option darunter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> und explizit <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> immer Vorrang hat. Wenn die <code> dpid </code> +- <code> dpuuid </code> Kombination einer anderen AAM-UUID zugeordnet wird, wird die Abmeldung unter der AAM-UUUID gespeichert, die in der Anforderung weitergegeben wird ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variablen und Syntax für deklarierte IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

In der folgenden Tabelle sind die Schlüssel-Wert-Paare aufgeführt, die bei Verwendung Ihre [!DNL Audience Manager] Datenanbieter-ID und Benutzer-IDs oder Integrationscodes übermitteln. Note, *italics* indicates a variable placeholder. Es wurden Leerzeichen hinzugefügt, um das Lesen zu vereinfachen.

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

## Beispielereignisaufrufe {#sample-event-calls}

Angesichts dieser Schlüssel-Wert-Paare und ihrer erforderlichen Syntax würden Sie Ereignisaufrufe wie unten gezeigt durchführen.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ereignisaufruf umfasst </th> 
   <th colname="col2" class="entry"> Codebeispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eine Datenanbieter-ID und Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ein Integrationscode und eine Benutzer-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mehrere <code> d_cid </code> und <code> d_cid_ic </code> Schlüssel/Wert-Paare. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Deklarierte ID-Variablen {#declared-id-variables}

Beschreibt die Konfigurationsvariablen, mit denen deklarierte IDs [!UICONTROL DIL] an [!DNL Audience Manager.]

## DIL verwendet den Experience Cloud ID-Dienst zum Übergeben deklarierter IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Bei Verwendung mit dem [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/)müssen Sie nicht mehr [!UICONTROL declared IDs] mit den veralteten `dpid` und `dpuuid` Variablen weitergeben. Stattdessen [!UICONTROL DIL] verlassen sich die aktuellen Versionen auf die `visitorService` Funktion, um die [!UICONTROL declared IDs] aus der `setCustomerIDs` Funktion in der [!UICONTROL Experience Cloud ID Service]zu erhalten. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). Sie rufen `visitorService` wie unten gezeigt `DIL.create` an.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Im `namespace` Schlüssel-Wert-Paar `MCORG` ist Ihre [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im [!UICONTROL Administration] Abschnitt des [!DNL Experience Cloud] Dashboards. Sie benötigen Administratorrechte, um dieses Dashboard anzuzeigen. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Veraltete Funktionen {#deprecated-functions}

Bei den neuesten Versionen von [!UICONTROL DIL] (6.2+) müssen Sie diese Schlüssel-Wert-Paare nicht verwenden, um sie weiterzugeben [!UICONTROL declared IDs]. Das liegt daran, dass [!UICONTROL DIL] jetzt die im obigen Codebeispiel dargestellte `visitorService` Funktion verwendet wird. Diese Funktion wird [!UICONTROL declared IDs] von der [!UICONTROL Experience Cloud ID Service]. Wir verweisen hier jedoch auf diese Variablen aus historischen und alten Gründen. Im folgenden Code finden Sie ein Beispiel für die Konfiguration `DIL.create` zum Abrufen eines [!UICONTROL declared ID] Formulars aus dem [!UICONTROL Visitor ID Service].
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

### `DPID` und `DPUUID`

Audience Manager vergleicht und stimmt mit der kombinierten `DPID` und `DPUUID` einer entsprechenden Benutzer-ID in unserem System überein. Wenn keine ID vorhanden ist, erstellt Audience Manager eine neue Benutzer-ID und synchronisiert sie mit der `DPID/DPUUID` Kombination. Sobald Audience Manager eine Benutzer-ID (die `UUID`[!DNL JSON] ) gefunden oder erstellt hat, gibt sie diese ID in der Antwort auf das Cookie in der Domäne des Kunden (Erstanbieter-Cookie) oder in einem anderen lokalen Speicher zurück.

Rufen Sie diese Funktion auf, wenn Sie [!UICONTROL DIL] v6.1 oder früher verwenden. Diese Funktion wurde jedoch zugunsten der neuen Version aufgegeben, die [!UICONTROL declared IDs] von der [!UICONTROL Experience Cloud ID Service].

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
>Beachten Sie, dass Sie den Code programmgesteuert entwickeln müssen, der die ID-Werte für die Schlüssel `d_dpuuid` und `d_dpid` -Schlüssel bereitstellt.

### Weitergeben von IDs nach DIL-Instanziierungen

>[!NOTE]
>
>Wenn Sie einen [!DNL API] Aufruf mit einer anderen `declaredID` Kombination durchführen, wird die neue Kombination nur für diesen Aufruf verwendet. Weitere reguläre Ereignisaufrufe verwenden die ursprüngliche `DIL.create` `declaredID` Kombination.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Anforderungs-/Antwortbeispiele {#request-response-examples}

Die Anforderung sendet einen Datenanbieter und eine Benutzer-ID an Audience Manager:

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

## Keine Target- und Ausschluss-Aufrufe {#do-not-target}

Der [!UICONTROL declared ID] Prozess berücksichtigt die Voreinstellungen der Site-Besucher, um das Zielgruppen-Manager-Targeting auf Ihrer Website abzuwählen. Wenn Audience Manager eine Abmeldeanforderung erhält, gibt das [!UICONTROL DCS] Objekt ein leeres [!DNL JSON] Objekt anstelle der Audience Manager-Benutzer-ID zurück.

>[!MORELIKETHIS]
>
>* [CID ersetzt DPID und DPUUID](../reference/cid.md)


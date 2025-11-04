---
description: Listet die Syntax und die unterstützten Attribute (oder Schlüssel-Wert-Paare) auf, die Sie an die Datenerfassungs-Server (DCS) übergeben können, und beschreibt sie. Diese Informationen können Ihnen dabei helfen, Ihre DCS-Anfragen zu formatieren und die von diesem System zurückgegebenen Parameter zu verstehen.
seo-description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-title: Supported Attributes for DCS API Calls
solution: Audience Manager
title: Unterstützte Attribute für DCS-API-Aufrufe
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 2%

---

# Unterstützte Attribute für [!DNL DCS] [!DNL API] {#supported-attributes-for-dcs-api-calls}

Listet die Syntax und die unterstützten Attribute (oder Schlüssel-Wert-Paare) auf, die Sie an die [!UICONTROL Data Collection Servers] übergeben können, und beschreibt sie ([!DNL DCS]). Diese Informationen können Ihnen bei der Formatierung Ihrer [!DNL DCS]-Anfragen und beim Verständnis der von diesem System zurückgegebenen Parameter helfen.

## Präfixe für Attribute {#attribute-prefixes}

Der [!DNL DCS] beruht auf bestimmten Präfixen, die den Schlüsseln in Schlüssel-Wert-Paaren hinzugefügt werden, um den Typ der Daten zu klassifizieren, die Sie übergeben.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüsselpräfix </th> 
   <th colname="col2" class="entry"> Reserviert für </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>Kundendefinierte Attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>-Attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP-Header-Daten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Private, kundendefinierte Attribute. </p> <p> Der DCS akzeptiert Ihre eigenen privaten Daten, wenn der Schlüssel ein <code> p_</code> Präfix hat. Private Daten werden für die Auswertung von Eigenschaften verwendet, aber sie werden nicht in unserem System protokolliert oder gespeichert. Angenommen, Sie haben eine Eigenschaft als <code> customers = p_age&lt;25</code> definiert und übergeben <code> p_age=23</code> in einem Ereignisaufruf. Unter diesen Bedingungen qualifiziert sich der Benutzer, der die altersbasierten Qualifizierungskriterien erfüllt, für das Merkmal, aber das Schlüssel-Wert-Paar wird entfernt, nachdem <span class="keyword"> Audience Manager </span> Anfrage empfangen hat und nicht protokolliert wird. </p> </td>
  </tr> 
 </tbody> 
</table>

## Attribute [!DNL d_] {#d-attributes}

Alle diese Angaben sind optional, es sei denn, Sie wünschen eine Antwort von der [!DNL DCS]. Wenn der [!DNL DCS] eine Antwort zurückgeben soll, ist `d_rtbd=json` erforderlich.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribut </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p>Wird verwendet, um den Aufrufer zu identifizieren, der den Aufruf an die <span class="wintitle"> DCS</span>-API durchführt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Gibt eine JavaScript-Funktion an, die Sie mit der <span class="wintitle"> DCS</span>-Antwort als Funktionsparameter der Rückruffunktion ausführen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Enthält ein oder mehrere Paare von Datenanbieter-IDs (<code> DPID</code>) und Datenanbieter-Benutzer-IDs (<code> DPUUID</code>), die von <span class="keyword"> Audience Manager zugewiesen werden</span>. Wenn Sie mehrere Paare von <code> DPID</code>s und <code> DPUUID</code>s verwenden, trennen Sie jedes Paar mit dem nicht druckbaren <code> %01</code>. Beispiel: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> ersetzt <code> d_dpid</code> und <code> d_dpuuid</code>, die veraltet sind, aber weiterhin unterstützt werden. Siehe <a href="../../../reference/cid.md"> CID ersetzt DPID und DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Enthält einen Integrations-Code und eine zugehörige eindeutige Benutzer-ID in einem einzelnen Schlüssel-Wert-Paar. </p> <p><code> d_cid_ic</code> ersetzt <code> d_dpid</code> und <code> d_dpuuid</code>, die veraltet sind, aber weiterhin unterstützt werden. Siehe <a href="../../../reference/cid.md"> CID ersetzt DPID und DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Deaktivieren Sie die Verwendung von Drittanbieter-Cookies, um die Vorschriften zum Schutz untergeordneter Elemente einzuhalten. Dieser Parameter wird vom Adobe Adobe Experience Platform Identity Service dynamisch festgelegt und hängt von der <code> idSyncDisable3rdPartySyncing</code> ab. Siehe <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/coppa.html" format="https" scope="external"> COPPA-Unterstützung im Adobe Experience Platform Identity Service</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Optional. Auf Kundenanfrage aktiviert. Wenden Sie sich an Ihren Adobe Audience Manager-Berater oder an die Kundenunterstützung. </p> <p>Gibt an, dass Eigenschaften und Segmente innerhalb der <code> JSON</code> Antwort zurückgegeben werden sollen. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> gibt <a href="../../../reference/ids-in-aam.md"> Legacy-Segment</a>IDs für die Segmente zurück. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> gibt Segment-IDs für die Segmente zurück. </p> </li>
     </ul> </p> <p>Eine Beispielantwort könnte wie die folgende aussehen: </p> <p>
     <code class="syntax javascript">
      &lbrace;
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      &rbrace;
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. Siehe <code> d_cid</code> und <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. Siehe <code> d_cid</code> und <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>Gibt URL-Zieldaten in der <code> JSON</code> Antwort zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> ist ein reserviertes Attribut, das bei der Integration zwischen Adobe Analytics und Audience Manager verwendet wird. </p> <p>Wir raten davon ab, Eigenschaften zu erstellen, die reservierte Attribute verwenden. Adobe kann reservierte Attribute jederzeit ändern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Gibt die in der Antwort zu verwendende <code> JSON</code> an. Normalerweise sollten Sie dies auf <code> d_jsonv=1</code> setzen. Durch Festlegen von <code> d_jsonv=0</code> wird die ID-Synchronisierung deaktiviert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Gibt die Experience Cloud-ID an, die vom <span class="keyword"> Experience Cloud</span> ID-Service festgelegt und verwendet wird. Weitere Informationen zur ECID finden Sie unter <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> von Cookies und Experience Cloud Identity Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>Namensraum-ID. Gibt an, welcher JavaScript-Container verwendet wird. Wird von <span class="wintitle"> DIL</span> zu für die ID-Synchronisierung verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Ermöglicht es Audience Manager, zwischen mobilen Anforderungen und Desktop-Anforderungen zu unterscheiden. Folgende Werte werden unterstützt: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. <code> d_rs</code> ist ein reserviertes Attribut, das bei der Legacy-Integration zwischen <span class="keyword"> Adobe Analytics </span> <span class="keyword"> Audience Manager verwendet </span>. </p> <p>Wir raten davon ab, Eigenschaften zu erstellen, die reservierte Attribute verwenden. Adobe kann reservierte Attribute jederzeit ändern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Erforderlich, wenn eine <code> JSON</code> Antwort vom <span class="wintitle"> DCS gewünscht </span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Wenn Sie dies auslassen, gibt <span class="wintitle"> DCS</span> ein Pixel in der Kopfzeile zurück. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Wenn Sie dies einbeziehen, gibt <span class="wintitle"> DCS</span> ein <code> JSON</code> -Objekt im Hauptteil der Antwort zurück. Siehe folgendes Beispiel. Ihre Antwort könnte komplexer sein. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      &lbrace;
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      &rbrace;
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> steht für <span class="term"> Score-ID</span>. Dies ist eine eindeutige ID für eine Eigenschaft oder ein Segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Übergibt eine Datenquelle für die Eigenschaftsbewertung. Es werden nur Eigenschaften aus dieser Datenquelle ausgewertet. </p> <p>Angenommen, Sie haben: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Eigenschaft T1</b> mit: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Trait-Regel: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Data Source (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID-Integrationscode: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Eigenschaft T2</b> mit: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Trait-Regel: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Data Source (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID-Integrationscode: ic2 </li> 
     </ul> </p> <p>In einem Beispielaufruf wird <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code> nur die Eigenschaft T1 zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>Der Zweck ist identisch mit dem oben beschriebenen <code> d_tdpid</code>. In diesem Fall wird die Datenquelle jedoch mithilfe des Integrations-Codes übergeben. </p> <p>Betrachten Sie den Beispielaufruf, wobei die oben beschriebenen Eigenschaften beibehalten werden: </p> <p><code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code> wird nur die Eigenschaft T2 zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>Unique User ID. Identifiziert einen Besucher, wenn dieser Wert nicht in einem Cookie verfügbar ist. </p> </td> 
  </tr>
 </tbody>
</table>

## h_attributes

Diese Kopfzeilen enthalten Informationen wie Anfragen für Daten und Antworten in einem HTTP-Aufruf.

| Attribut | Beschreibung |
| --- | --- |
| `h_host` | Dieser wird auf den spezifischen Datenerfassungs-Host-Namen des Clients festgelegt. Es erscheint als `host name .demdex.net`. Siehe [Grundlegendes zu Aufrufen an die Domäne „demdex.net“](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=en). |
| `h_user-agent` | Auf den Wert der `User-Agent`-Kopfzeile festlegen. |
| `h_accept-language` | Auf den Wert der `Accept-Language`-Kopfzeile festlegen. |
| `h_referer` | Auf den Wert der `Referer`-Kopfzeile festlegen. |
| `h_referrer` | Auf den Wert der `Referrer`-Kopfzeile festlegen. |
| `h_date` | Auf den Wert der `Date`-Kopfzeile festlegen. |

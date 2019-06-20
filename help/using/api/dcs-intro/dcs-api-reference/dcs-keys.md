---
description: Listet die Syntax und unterstützte Attribute (oder Schlüssel/Wert-Paare) auf und beschreibt sie, die Sie an die Datenerfassungsserver (DCS) übergeben können. Diese Informationen können Ihnen dabei helfen, Ihre DCS-Anforderungen zu formatieren und die von diesem System zurückgegebenen Parameter zu verstehen.
seo-description: Listet die Syntax und unterstützte Attribute (oder Schlüssel/Wert-Paare) auf und beschreibt sie, die Sie an die Datenerfassungsserver (DCS) übergeben können. Diese Informationen können Ihnen dabei helfen, Ihre DCS-Anforderungen zu formatieren und die von diesem System zurückgegebenen Parameter zu verstehen.
seo-title: Unterstützte Attribute für DCS-API-Aufrufe
solution: Audience Manager
title: Unterstützte Attribute für DCS-API-Aufrufe
uuid: 0 b 98 ed 11-314 b -4500-afde -45 a 041112150
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Unterstützte Attribute für DCS-API-Aufrufe {#supported-attributes-for-dcs-api-calls}

Listet die Syntax und unterstützte Attribute (oder Schlüssel/Wert-Paare) auf und beschreibt diese, die Sie an die [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]) übergeben können. Diese Informationen können Ihnen dabei helfen, [!UICONTROL DCS] Ihre Anforderungen zu formatieren und die von diesem System zurückgegebenen Parameter zu verstehen.

## Attributpräfixe {#attribute-prefixes}

Der [!UICONTROL DCS] Parameter beruht auf bestimmten Präfixe, die den Schlüssel in Schlüssel/Wert-Paaren hinzugefügt wurden, um die Art der übermittelten Daten zu klassifizieren.

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> -Attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP-Header-Daten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Private, kundendefinierte Attribute. </p> <p> Das DCS akzeptiert Ihre eigenen privaten Daten, wenn der Schlüssel über ein <code> p_</code> präfix verfügt. Private Daten werden für die Eigenschaftenauswertung verwendet, werden aber nicht in unserem System protokolliert oder gespeichert. Angenommen, Sie haben eine Eigenschaft, die als <code> Kunden = p_ age &lt; 25</code> definiert ist, und Sie geben <code> p_ age = 23</code> in einen Ereignisaufruf ein. Anhand dieser Bedingungen qualifiziert sich der Benutzer, der die altersbasierten Qualifizierungskriterien erfüllt, für die Eigenschaft, jedoch wird das Schlüssel-Wert-Paar abgelegt, nachdem <span class="keyword"> Audience Manager</span> die Anforderung erhält und nicht protokolliert wurde. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_ Attribute {#d-attributes}

Alle diese sind optional, es sei denn, eine Antwort von [!UICONTROL DCS]. Wenn Sie [!UICONTROL DCS] eine Antwort zurückgeben `d_rtbd=json` möchten, müssen Sie dies tun.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribut </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_ invoer</code> </p> </td> 
   <td colname="col2"> <p>Dient zur Identifizierung des Aufrufers, der den Aufruf an die <span class="wintitle"> DCS</span> -API durchführt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Gibt eine javascript-Funktion an, die Sie mithilfe der <span class="wintitle"> DCS</span> -Antwort als Funktionsparameter der Callback-Funktion ausführen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Enthält mindestens eine Paare von Datenanbieter-IDs (<code> DPID</code>) und Datenanbieter-Benutzer-IDs (<code> DPUUID</code>), die von <span class="keyword"> Audience Manager zugewiesen</span>werden. Wenn Sie mehrere Paare von <code> dpids</code>und <code> dpuuids</code>verwenden, trennen Sie die einzelnen Paare durch das nicht druckbare Zeichen <code> % 01</code>. Beispiel: <code><i>DPID</i>% 01<i>DPUUUID</i></code>. </p> <p><code> d_ cid</code> ersetzt <code> d_ dpid</code> und <code> d_ dpuuid</code>, die nicht mehr unterstützt werden, aber dennoch unterstützt werden. Siehe <a href="../../../reference/cid.md">CID ersetzt DPID und DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cid_ ic</code> </p> </td> 
   <td colname="col2"> <p>Enthält einen Integrationscode und eine zugehörige eindeutige Benutzer-ID in einem einzelnen Schlüssel-Wert-Paar. </p> <p><code> d_ cid_ ic</code> ersetzt <code> d_ dpid</code> und <code> d_ dpuuid</code>, die nicht mehr unterstützt werden, aber dennoch unterstützt werden. Siehe <a href="../../../reference/cid.md">CID ersetzt DPID und DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ coppa</code> </p> </td> 
   <td colname="col2"> <p>Deaktivieren Sie die Nutzung von Drittanbieter-Cookies, um Kindergeld einzuhalten. Dieser Parameter wird dynamisch vom Adobe Experience Cloud ID-Dienst festgelegt und hängt von der <code> idsyncdisable 3 rdpartysyncing-Konfiguration</code> ab. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_coppa.html" format="https" scope="external"> COPPA Support in the Experience Cloud ID Service</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_ cts = 1</code> </p> <p><code> d_ cts = 2</code> </p> </td> 
   <td colname="col2"> <p>Optional. Aktiviert bei Kundenanfragen. Wenden Sie sich an Ihren Adobe Audience Manager-Berater oder an den Kundendienst. </p> <p>Gibt an, dass Eigenschaften und Segmente innerhalb der <code> JSON</code> -Antwort zurückgegeben werden sollen. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_ cts = 1</code> gibt <a href="../../../reference/ids-in-aam.md"> Legacy-Segment-IDs</a> für die Segmente zurück. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_ cts = 2</code> gibt Segment-IDs für die Segmente zurück. </p> </li>
     </ul> </p> <p>Eine Beispielantwort könnte wie folgt aussehen: </p> <p>
     <code class="syntax javascript">{"stuff": [], "uuid": " 07955261652886032950143702505894272138 "," dcs_ region ": 7, "Eigenschaften": [420020, 5421506], "segments": [984263, 985264], "tid": " ss 3 otqpiqp 0 = "} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpid</code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. Siehe <code> d_ cid</code> und <code> d_ cid_ ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. Siehe <code> d_ cid</code> und <code> d_ cid_ ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ dst = 1</code> </p> </td> 
   <td colname="col2"> <p>Gibt in der <code> JSON</code> -Antwort URL-Zieldaten zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_ dst_ filter</code> ist ein reserviertes Attribut, das in der Integration zwischen Adobe Analytics und Audience Manager verwendet wird. </p> <p>Wir empfehlen, Eigenschaften zu erstellen, die reservierte Attribute verwenden. Adobe kann reservierte Attribute jederzeit ändern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ jsonv = 1|0</code> </p> </td> 
   <td colname="col2"> <p>Gibt die <code> JSON</code> -Version an, die in der Antwort verwendet werden soll. Normalerweise sollten Sie dies <code> auf d_ jsonv = 1</code>einstellen. Durch das Festlegen <code> von d_ jsonv = 0</code> wird die ID-Synchronisierung deaktiviert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Gibt die Experience Cloud ID-Einstellung an und verwendet diese vom <span class="keyword"> Experience Cloud</span> ID-Dienst. For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ nsid</code> </p> </td> 
   <td colname="col2"> <p>Name-Leerzeichen-ID. Gibt an, welcher javascript-Container verwendet wird. Wird von <span class="wintitle"> DIL</span> zur ID-Synchronisierung verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ ptfm </code> </p> </td> 
   <td colname="col2"> <p>Ermöglicht es Audience Manager, Mobilanforderungen von Desktopanforderungen zu unterscheiden. Folgende Werte werden unterstützt: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> Browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. <code> d_ rs</code> ist ein reserviertes Attribut, das in der alten Integration zwischen <span class="keyword"> Adobe Analytics</span> und <span class="keyword"> Audience Manager verwendet</span>wird. </p> <p>Wir empfehlen, Eigenschaften zu erstellen, die reservierte Attribute verwenden. Adobe kann reservierte Attribute jederzeit ändern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ rtbd = json</code> </p> </td> 
   <td colname="col2"> <p>Erforderlich, wenn eine <code> JSON</code> -Antwort vom <span class="wintitle"> DCS</span>gewünscht wird. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Wenn Sie dies weglassen, gibt das <span class="wintitle"> DCS</span> ein Pixel in der Kopfzeile zurück. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Wenn Sie dies einbeziehen, gibt das <span class="wintitle"> DCS</span> ein <code> JSON</code> -Objekt im Textkörper der Antwort zurück. Siehe Beispiel unten. Ihre Antwort könnte komplexer sein. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">{"stuff": [], "uuid": " 22920112968019678612904394744954398990 "," dcs_ region ": 7, "tid": " ss 3 otqpiqp 0 = "} </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> steht für <span class="term"> Score-ID</span>. Dies ist eine eindeutige ID für eine Eigenschaft oder ein Segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ tdpid</code> </p> </td> 
   <td colname="col2"> <p>Übergibt eine Datenquelle für die Eigenschaftenauswertung. Nur Eigenschaften aus dieser Datenquelle werden ausgewertet. </p> <p>Beispiel: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Merkmal T 1</b> mit: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Eigenschaftsregel: "<code> key 1 = = val 1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Datenquelle (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID-Integrationscode: ic 1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Merkmal T 2</b> mit: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Eigenschaftsregel: "<code> key 2 = = val 2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Datenquelle (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID-Integrationscode: ic 2 </li> 
     </ul> </p> <p>In einem Beispielaufruf <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>wird nur die Eigenschaft T 1 zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ tdpid_ ic</code> </p> </td> 
   <td colname="col2"> <p>Der Zweck ist mit dem oben beschriebenen <code> Parameter d_ tdpid</code> identisch. In diesem Fall wird die Datenquelle jedoch mit dem Integrationscode übergeben. </p> <p>Beachten Sie den Beispielaufruf, wenn Sie die oben beschriebenen Eigenschaften beibehalten: </p> <p>Für <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>wird nur Eigenschaft T 2 zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ uuid</code> </p> </td> 
   <td colname="col2"> <p>Unique User ID. Identifiziert einen Besucher, wenn dieser Wert nicht aus einem Cookie zur Verfügung steht. </p> </td> 
  </tr>
 </tbody>
</table>
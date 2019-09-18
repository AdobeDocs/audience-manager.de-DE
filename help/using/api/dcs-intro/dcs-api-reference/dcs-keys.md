---
description: Listet die Syntax und die unterstützten Attribute (oder Schlüssel-Wert-Paare) auf und beschreibt sie, die Sie an die Datenerfassungsserver (DCS) weitergeben können. Anhand dieser Informationen können Sie Ihre DCS-Anforderungen formatieren und die von diesem System zurückgegebenen Parameter verstehen.
seo-description: Listet die Syntax und die unterstützten Attribute (oder Schlüssel-Wert-Paare) auf und beschreibt sie, die Sie an die Datenerfassungsserver (DCS) weitergeben können. Anhand dieser Informationen können Sie Ihre DCS-Anforderungen formatieren und die von diesem System zurückgegebenen Parameter verstehen.
seo-title: Unterstützte Attribute für DCS-API-Aufrufe
solution: Audience Manager
title: Unterstützte Attribute für DCS-API-Aufrufe
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
translation-type: tm+mt
source-git-commit: 6e2cb69cd2f65851b82ed9a28f4a108562ce6ab8

---


# Unterstützte Attribute für DCS-API-Aufrufe {#supported-attributes-for-dcs-api-calls}

Listet die Syntax und die unterstützten Attribute (oder Schlüssel-Wert-Paare) auf und beschreibt sie, die Sie an das [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]) weitergeben können. Diese Informationen helfen Ihnen dabei, Ihre [!UICONTROL DCS] Anforderungen zu formatieren und die von diesem System zurückgegebenen Parameter zu verstehen.

## Attributpräfixe {#attribute-prefixes}

Die [!UICONTROL DCS] Daten werden anhand bestimmter Präfixe klassifiziert, die den Schlüsseln in Schlüssel/Wert-Paaren hinzugefügt werden.

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
   <td colname="col2"> <p>Private, benutzerdefinierte Attribute. </p> <p> Der DCS akzeptiert Ihre eigenen privaten Daten, wenn der Schlüssel ein <code> p_</code> -Präfix hat. Private Daten werden zur Eigenschaftsbewertung verwendet, werden jedoch nicht in unserem System gespeichert. Nehmen wir beispielsweise an, Sie haben eine Eigenschaft definiert als <code> Customers = p_age&lt;25</code> und Sie geben <code> p_age=23</code> in einem Ereignisaufruf ein. Unter diesen Bedingungen qualifiziert sich der Benutzer, der die altersbasierten Qualifikationskriterien erfüllt, für die Eigenschaft. Das Schlüssel-Wert-Paar wird jedoch gelöscht, nachdem <span class="keyword"> Audience Manager</span> die Anforderung erhält und nicht protokolliert wird. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_ Attribute {#d-attributes}

Alle diese Optionen sind optional, es sei denn, Sie möchten eine Antwort von der [!UICONTROL DCS]. Wenn die Antwort [!UICONTROL DCS] zurückgegeben werden soll, ist dies `d_rtbd=json` erforderlich.

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
   <td colname="col2"> <p>Dient zur Identifizierung des Aufrufers, der den Aufruf der <span class="wintitle"> DCS</span> -API durchführt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Gibt eine JavaScript-Funktion an, die Sie mit der <span class="wintitle"> DCS</span> -Antwort als Funktionsparameter der Rückruffunktion ausführen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Enthält ein oder mehrere Paare von Datenanbieter-IDs (<code> DPID</code>) und Datenanbieter-Benutzer-IDs (<code> DPUUID</code>), die von <span class="keyword"> Audience Manager</span>zugewiesen wurden. Wenn Sie mehrere Paare von <code> DPIDs und </code> DPUUIDs verwenden, trennen Sie jedes Paar mit dem nicht druckbaren Zeichen <code> %01</code><code></code>. Beispiel: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> ersetzt <code> d_dpid</code> und <code> d_dpuuid</code>, die nicht mehr unterstützt werden, die jedoch weiterhin unterstützt werden. Siehe <a href="../../../reference/cid.md">CID ersetzt DPID und DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Enthält einen Integrationscode und eine zugehörige eindeutige Benutzer-ID in einem einzelnen Schlüssel/Wert-Paar. </p> <p><code> d_cid_ic</code> ersetzt <code> d_dpid</code> und <code> d_dpuuid</code>, die nicht mehr unterstützt werden, aber weiterhin unterstützt werden. Siehe <a href="../../../reference/cid.md">CID ersetzt DPID und DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Deaktivieren Sie die Verwendung von Drittanbieter-Cookies, um die Kinderschutzbestimmungen einzuhalten. Dieser Parameter wird vom Adobe Experience Cloud ID-Dienst dynamisch festgelegt und hängt von der <code> idSyncDisable3rdPartySyncing-Konfiguration</code> ab. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_coppa.html" format="https" scope="external"> COPPA Support in the Experience Cloud ID Service</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Optional. Bei Kundenanforderung aktiviert. Wenden Sie sich an Ihren Adobe Audience Manager-Berater oder an den Kundendienst. </p> <p>Gibt an, dass Eigenschaften und Segmente innerhalb der <code> JSON</code> -Antwort zurückgegeben werden sollen. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> gibt <a href="../../../reference/ids-in-aam.md"> Legacy-Segment-IDs</a> für die Segmente zurück. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> gibt Segment-IDs für die Segmente zurück. </p> </li>
     </ul> </p> <p>Eine Beispielantwort könnte wie folgt aussehen: </p> <p>
     <code class="syntax javascript">
      { "stuff": [], "uuid": "07955261652886032950143702505894272138", "dcs_region":, "Eigenschaften": [420020, 5421506], "Segmente": [984263, 985264], "tid": "ss3OTqPiQp0=" } </code> </p> </td> 
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
   <td colname="col2"> <p>Gibt URL-Zieldaten in der <code> JSON</code> -Antwort zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> ist ein reserviertes Attribut, das bei der Integration zwischen Adobe Analytics und Audience Manager verwendet wird. </p> <p>Wir empfehlen, keine Eigenschaften zu erstellen, die reservierte Attribute verwenden. Adobe kann reservierte Attribute jederzeit ändern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Gibt die <code> JSON</code> -Version an, die in der Antwort verwendet werden soll. Normalerweise sollten Sie dies auf <code> d_jsonv=1</code>einstellen. Durch Festlegen von <code> d_jsonv=0</code> werden ID-Synchronisierungen deaktiviert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Gibt die Experience Cloud-ID an, die vom <span class="keyword"> Experience Cloud</span> ID-Dienst festgelegt und verwendet wird. For more information about the ECID, see <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>Namespace-ID benennen. Gibt an, welcher JavaScript-Container verwendet wird. Wird von <span class="wintitle"> DIL</span> zur ID-Synchronisierung verwendet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Ermöglicht Audience Manager, mobile Anforderungen von Desktop-Anforderungen zu unterscheiden. Folgende Werte werden unterstützt: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> Browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. <code> d_rs</code> ist ein reserviertes Attribut, das in der Integration von <span class="keyword"> Adobe Analytics</span> und <span class="keyword"> Audience Manager</span>verwendet wird. </p> <p>Wir empfehlen, keine Eigenschaften zu erstellen, die reservierte Attribute verwenden. Adobe kann reservierte Attribute jederzeit ändern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Erforderlich, wenn Sie eine <code> JSON</code> -Antwort vom <span class="wintitle"> DCS</span>erhalten möchten. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Wenn Sie dies weglassen, gibt der <span class="wintitle"> DCS</span> ein Pixel in der Kopfzeile zurück. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Wenn Sie dies einbeziehen, gibt der <span class="wintitle"> DCS</span> ein <code> JSON</code> -Objekt im Hauptteil der Antwort zurück. Siehe Beispiel unten. Ihre Antwort könnte komplexer sein. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      { "stuff": [], "uuid": "2292011296801967861290439474954398990", "dcs_region":, "tid": "ss3OTqPiQp0=" } </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> steht für <span class="term"> Score-ID</span>. Dies ist eine eindeutige ID für eine Eigenschaft oder ein Segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Übergibt eine Datenquelle zur Eigenschaftsbewertung. Nur Eigenschaften aus dieser Datenquelle werden ausgewertet. </p> <p>Angenommen, Sie haben Folgendes: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Eigenschaft T1</b> mit: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Eigenschaftsregel: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Datenquelle (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">DPID-Integrationscode: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Eigenschaft T2</b> mit: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Eigenschaftsregel: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Datenquelle (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">DPID-Integrationscode: ic2 </li> 
     </ul> </p> <p>Bei einem Beispielaufruf <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>wird nur die Eigenschaft T1 zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>Der Zweck ist identisch mit dem oben beschriebenen Parameter <code> d_tdpid</code> . In diesem Fall wird die Datenquelle jedoch mithilfe des Integrationscodes weitergeleitet. </p> <p>Berücksichtigen Sie bei den oben beschriebenen Eigenschaften den Beispielaufruf: </p> <p>Für <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>wird nur die Eigenschaft T2 zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>Eindeutige Benutzer-ID. Identifiziert einen Besucher, wenn dieser Wert in einem Cookie nicht verfügbar ist. </p> </td> 
  </tr>
 </tbody>
</table>
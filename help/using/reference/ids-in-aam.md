---
description: In diesem Dokument finden Sie die vollständige Liste der Adobe Audience Manager-IDs.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid
seo-description: In diesem Dokument finden Sie die vollständige Liste der Adobe Audience Manager-IDs.
seo-title: Index von IDs in Audience Manager
solution: Audience Manager
title: Index von IDs in Audience Manager
uuid: 292185 ec -7 c 6 a -414 b-ab 17-800 c 21 cb 1 f 01
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Index von IDs in Audience Manager{#index-of-ids-in-audience-manager}

In diesem Dokument finden Sie die vollständige Liste der Adobe Audience Manager-IDs.

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Name und Beschreibung </th> 
   <th colname="col3" class="entry"> Beispiel  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>Eigenschafts-ID</b> </p> <p>Die Eigenschafts-ID identifiziert Eigenschaften eindeutig in der <span class="keyword"> Audience Manager</span> -Umgebung. Jeder Eigenschaft wird in der Benutzeroberfläche eine Eigenschafts-ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>Segment-ID </b> </p> <p>Die Segment-ID identifiziert Segmente eindeutig in der <span class="keyword"> Audience Manager</span> -Umgebung. Jedem Segment in der Benutzeroberfläche wird eine Segment-ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Csegid </p> </td> 
   <td colname="col2"> <p> <b>Legacy-Segment-ID </b> </p> <p>Diese ID identifiziert Segmente in der <span class="keyword"> Audience Manager</span> -Umgebung eindeutig. Jedem Segment in der Benutzeroberfläche wird eine Legacy-Segment-ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destid </p> </td> 
   <td colname="col2"> <p> <b>Ziel-ID </b> </p> <p>Die Ziel-ID identifiziert Ziele in der <span class="keyword"> Audience Manager</span> -Umgebung eindeutig. Jedem Ziel in der Benutzeroberfläche wird eine ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>Datenquellen-ID (auch als Datenanbieter-ID bezeichnet)</b> </p> <p>Die Datenquellen-ID ist ein Namespace für IDs oder Eigenschaften. Jeder Datenquelle (Datenprovider) in der Benutzeroberfläche wird eine ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>Eindeutige Benutzer-ID des Datenanbieters </b><b>(auch als CRM-ID bezeichnet)</b> </p> <p>Eine Drittanbieter-ID. Dies ist die ID, mit der Sie Endbenutzer in Ihrem eigenen CRM-System identifizieren. Sie können dpuuids mit <span class="keyword"> Audience Manager</span> -uuids synchronisieren und dpuuids aus Ihren verschiedenen <span class="wintitle"> Data Sources</span> (dpids) im <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> ID-Synchronisierungsprozess</a>synchronisieren. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -4432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-ID </p> </td> 
   <td colname="col2"> <p>Siehe DPUUID oben. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -4432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_ IC </p> </td>
   <td colname="col2"> <p> <b>Kunden-ID, Kunden-ID-Integrationscode</b> </p> <p> <b>Die Schlüssel CID und CID_ IC <a href="../reference/cid.md"> ersetzen DPID und DPUUID</a>.</b> Sie bieten dieselben Funktionen wie DPID und DPUUID, sind jedoch effizienter, da sie die Datenanbieter-ID und Benutzer-ID (oder Integrationscode) in ein einzelnes Schlüssel-Wert-Paar aufnehmen. </p> </td> 
   <td colname="col3"> <p><code> 81841% 013 ad 2948 b 1570 a 7 e 408 a 7 cfb 7 ff 4879 e 4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> Audience Manager</span> Unique User ID </b> </p> <p> Eine numerische 38-stellige Geräte-ID, die <span class="keyword"> Audience Manager</span> jedem Gerät zuordnet, mit dem es interagiert. <span class="keyword"> Audience Manager</span> versucht, diese ID als Cookie in der Domäne "demdex. net" zu speichern. </p> <p>Die UUID des Audience Manager wird in Ereignisaufrufen als d_ uuid gesendet. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imsorgid </p> </td> 
   <td colname="col2"> <p> <b>Organisations-ID</b> </p> <p>Dies ist die ID, mit der ein Unternehmen bei der Anmeldung für die Experience Cloud bereitgestellt wird. Um zu erfahren, wie Sie die Organisations-ID Ihres Unternehmens finden, lesen Sie <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Unternehmen und Kontoverknüpfung</a> und blättern Sie nach unten, um Ihre Organisations-ID zu finden.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>Partner-ID</b> </p> <p> Die PID ist in <span class="keyword"> Audience Manager die ID eines Unternehmens</span>. <span class="keyword"> Audience Manager</span> verknüpft eine imsorgid zu einer PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>Die Experience Cloud ID (ECID, Legacy-Abkürzungen MID oder MCID) wird mathematisch aus Ihrer Organisations-ID und der eindeutigen Benutzer-ID <span class="keyword"> von Audience Manager</span> abgeleitet. Solange diese IDs konstant bleiben, ist das Generieren der richtigen ECID für einen bestimmten Benutzer einfach ein mathematischer Fehler. Bei derselben Organisations-ID und denselben UUID für Audience Manager erhalten Sie immer denselben ECID-Wert. Weitere Informationen über die ECID finden Sie im Dokument <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies und Experience Cloud ID</a> . </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>RIDA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>Gerätewerbung-ID</b> </p> <p>Eine ID, die für jedes Hardwaregerät eindeutig ist und für Werbezwecke verwendet wird. Wird normalerweise vom Hersteller des Betriebssystems oder des Geräts bereitgestellt. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Geräte-Advertising-ID - IDFA - ios-Geräte</b> </p> <p> <b>IDFA</b> -IDs sind vom Gerätehersteller bereitgestellte Mobilgeräte-ids. Diese IDs stellen Geräte dar, die das ios-Betriebssystem ausführen. </p> </td> 
   <td colname="col3"> <p> Das Format besteht aus 32 <i>Großbuchstaben</i> aus Hexadezimalziffern, die in fünf Gruppen angezeigt und durch Bindestriche getrennt werden, im Formular 8-4-4-4-12, insgesamt 36 Zeichen. </p> <p><code> AEBE 52 E 7-03 EE -455 A-B 3 C 4-E 77283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Geräte-Advertising-ID - GAID - Android-Geräte</b> </p> <p><b>GAID</b> -IDs sind vom Gerätehersteller bereitgestellte Mobilgeräte-ids. Diese IDs stellen Geräte dar, die das Android-Betriebssystem ausführen. </p> </td> 
   <td colname="col3"> <p>Das Format besteht ausschließlich aus 32 <i>Kleinbuchstaben</i> hexadezimalen Ziffern, die in fünf Gruppen angezeigt und durch Bindestriche getrennt werden, im Formular 8-4-4-4-12, insgesamt 36 Zeichen. </p> <p> <code> e 4 fe 9 bde-caa 0-47 b 6-908 d-ffba 3 fa 184 f 2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Roku-Streaming-Geräte</b> </p> <p><b>GAID</b> RIDA-IDs sind Streaming-Gerätebezeichner, die vom Hersteller von Roku-Geräten bereitgestellt werden.</p> </td>
   <td colname="col3"> <p>Das Format besteht ausschließlich aus 32 <i>Kleinbuchstaben</i> hexadezimalen Ziffern, die in fünf Gruppen angezeigt und durch Bindestriche getrennt werden, im Formular 8-4-4-4-12, insgesamt 36 Zeichen. </p> <p> <code> fcb 2 a 29 c -315 a -5 e 6 b-bcfd-d 889 ba 19 aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID - MAID - Windows 10-Geräte</b> </p> <p><b>MAID</b> -IDs sind Gerätebezeichner, die von Windows 10 auf einem pro-Gerät pro Gerät generiert werden.</p> </td>
   <td colname="col3"> <p>Maids werden als alphanumerische Zeichenfolgen formatiert.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Samsung-Geräte</b> </p> Samsung duids sind Gerätekennungen, die von Samsung tvs bereitgestellt werden.</p> </td>
   <td colname="col3"> <p>Samsung duids werden als alphanumerische Zeichenfolgen formatiert.</p></td>
  </tr>
 </tbody> 
</table>
---
description: Die vollständige Liste der Adobe Audience Manager-IDs finden Sie in diesem Dokument.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuuid, uuuid, uuid, uuuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuuid, uuid
seo-description: Die vollständige Liste der Adobe Audience Manager-IDs finden Sie in diesem Dokument.
seo-title: Index der IDs in Audience Manager
solution: Audience Manager
title: Index der IDs in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Index der IDs in Audience Manager{#index-of-ids-in-audience-manager}

Die vollständige Liste der Adobe Audience Manager-IDs finden Sie in diesem Dokument.

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
   <td colname="col1"> <p>AAM UUUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> Audience Manager</span> Unique User ID </b> </p> <p> Eine numerische, 38-stellige Geräte-ID, die <span class="keyword"> Audience Manager</span> jedem Gerät zuordnet, mit dem sie interagiert. Denken Sie an diese ID, wenn Sie in der Benutzeroberfläche von Audience Manager eine Erwähnung individueller Benutzer sehen.<p><span class="keyword"> Audience Manager</span> versucht, diese ID als Cookie in der Drittanbieterdomäne "demdex.net"zu speichern.</p> </p> <p>Die Audience Manager-UUID wird bei Ereignisaufrufen als d_uuid-Signal gesendet. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ImsOrgId </p> </td> 
   <td colname="col2"> <p> <b>Organisations-ID</b> </p> <p>Diese ID wird einem Unternehmen bei der Anmeldung bei der Experience Cloud bereitgestellt. Um zu erfahren, wie Sie die Organisations-ID Ihres Unternehmens finden, lesen Sie <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organisationen und Kontoverknüpfung</a> und blättern Sie nach unten, um Ihre Organisations-ID zu finden.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>Partner-ID</b> </p> <p> Die PID ist die ID eines Unternehmens in <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> verknüpft eine imsOrgId mit einer PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>Die Experience Cloud ID (ECID, ältere Abkürzungen MID oder MCID) wird mathematisch aus Ihrer Organisations-ID und der <span class="keyword"> Audience Manager</span> Unique User ID abgeleitet. Solange diese IDs konstant bleiben, stellt die Generierung der richtigen ECID für einen bestimmten Benutzer einfach ein mathematisches Problem dar. Mit derselben Organisations-ID und der Audience Manager-UUID erhalten Sie immer denselben ECID-Wert. Weitere Informationen zur ECID finden Sie im Dokument " <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies"und "Experience Cloud ID</a> ". </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SID </p> </td> 
   <td colname="col2"> <p> <b>Eigenschaften-ID</b> </p> <p>Die Eigenschaften-ID identifiziert Eigenschaften eindeutig in der <span class="keyword"> Audience Manager</span> -Umgebung. Jeder Eigenschaft in der Benutzeroberfläche wird eine Eigenschaften-ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SID </p> </td> 
   <td colname="col2"> <p> <b>Segment-ID </b> </p> <p>Die Segment-ID identifiziert Segmente eindeutig in der <span class="keyword"> Audience Manager</span> -Umgebung. Jedem Segment in der Benutzeroberfläche wird eine Segment-ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>Legacy-Segment-ID </b> </p> <p>Diese ID identifiziert Segmente eindeutig in der <span class="keyword"> Audience Manager</span> -Umgebung. Jedem Segment in der Benutzeroberfläche wird eine Legacy-Segment-ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destID </p> </td> 
   <td colname="col2"> <p> <b>Ziel-ID </b> </p> <p>Die Ziel-ID identifiziert Ziele eindeutig in der <span class="keyword"> Audience Manager</span> -Umgebung. Jedem Ziel in der Benutzeroberfläche wird eine ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>Datenquellen-ID (auch als Datenanbieter-ID bezeichnet)</b> </p> <p>Die Datenquellen-ID ist ein Namespace für IDs oder Eigenschaften. Jeder Datenquelle (Datenanbieter) in der Benutzeroberfläche wird eine ID zugewiesen. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>Eindeutige Datenanbieter-Benutzer-ID </b> <b>(auch als CRM-ID bezeichnet)</b> </p> <p>Eine Drittanbieter-ID. Mit dieser ID können Sie Endbenutzer in Ihrem eigenen CRM-System identifizieren. Sie können DPUUIDs mit <span class="keyword"> Audience Manager</span> -UUIDs synchronisieren und DPUUIDs aus verschiedenen <span class="wintitle"> Data Sources</span> (DPIDs) im <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> ID-Synchronisierungsprozess</a>synchronisieren. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-ID </p> </td> 
   <td colname="col2"> <p>Siehe DPUUID oben. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_IC </p> </td>
   <td colname="col2"> <p> <b>Kunden-ID, Kunden-ID-Integrationscode</b> </p> <p> <b>Die Schlüssel-Wert-Paare CID und CID_IC <a href="../reference/cid.md"> ersetzen DPID und DPUUID</a>.</b> Sie bieten dieselben Funktionen wie DPID und DPUUID, sind jedoch effizienter, da sie die Datenanbieter-ID und die Benutzer-ID (oder den Integrationscode) in einem Schlüssel-Wert-Paar enthalten. </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7cfb7ff4879e4 </code> </p> </td> 
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
   <td colname="col2"> <p> <b>Geräte-Advertising-ID</b> </p> <p>Eine ID, die für jedes Hardwaregerät eindeutig ist und für Werbezwecke verwendet wird. In der Regel vom Hersteller des Geräts oder Betriebssystems bereitgestellt. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku-ID, Playstation-ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Geräte-Advertising-ID - IDFA - iOS-Geräte</b> </p> <p> <b>IDFA</b> -IDs sind vom Gerätehersteller bereitgestellte Identifikatoren für Mobilgeräte. Diese IDs stellen Geräte dar, auf denen das iOS-Betriebssystem ausgeführt wird. </p> </td> 
   <td colname="col3"> <p> Das Format besteht ausschließlich aus 32 <i>Hexadezimalziffern</i> in Großbuchstaben, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, in der Form 8-4-4-4-12, mit einer Gesamtlänge von 36 Zeichen. </p> <p><code> AEBE52E7-03EE-455A-B3C4-E57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Geräte-Anzeigen-ID - GAID - Android-Geräte</b> </p> <p><b>GAID</b> -IDs sind vom Gerätehersteller bereitgestellte Mobilgerätekennungen. Diese IDs stellen Geräte dar, auf denen das Android-Betriebssystem ausgeführt wird. </p> </td> 
   <td colname="col3"> <p>Das Format besteht ausschließlich aus 32 <i>kleinen</i> hexadezimalen Ziffern, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, in der Form 8-4-4-4-12, mit einer Gesamtlänge von 36 Zeichen. </p> <p> <code> e4fe9bde-caa0-47b6-908d-ffba3fa184f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Roku-Streaming-Geräte</b> </p> <p><b>GAID</b> -RIDA-IDs sind Streaming-Geräte-IDs, die vom Hersteller der Roku-Geräte bereitgestellt werden.</p> </td>
   <td colname="col3"> <p>Das Format besteht ausschließlich aus 32 <i>kleinen</i> hexadezimalen Ziffern, die in fünf Gruppen angezeigt werden und durch Bindestriche getrennt sind, in der Form 8-4-4-4-12, mit einer Gesamtlänge von 36 Zeichen. </p> <p> <code> fcb2a29c-315a-5e6b-bcfd-d889ba19aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID - MAID - Windows 10-Geräte</b> </p> <p><b>MAID</b> -IDs sind Geräte-IDs, die von Windows 10 pro Gerät und Benutzer generiert werden.</p> </td>
   <td colname="col3"> <p>MAIDs werden als alphanumerische Zeichenfolgen formatiert.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Samsung-Geräte</b> </p> Samsung DUIDs sind Gerätekennungen, die von Samsung TVs bereitgestellt werden.</p> </td>
   <td colname="col3"> <p>Samsung DUIDs werden als alphanumerische Zeichenfolgen formatiert.</p></td>
  </tr>
 </tbody> 
</table>
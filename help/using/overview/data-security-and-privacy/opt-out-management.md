---
description: Adobe erfüllt alle branchenweit geltenden Standards für die Abmeldeverwaltung. Lesen Sie für vollständige Informationen zu den von Audience Manager unterstützten Abmeldearten.
seo-description: Adobe erfüllt alle branchenweit geltenden Standards für die Abmeldeverwaltung. Lesen Sie für vollständige Informationen zu den von Audience Manager unterstützten Abmeldearten.
seo-title: Abmeldeverwaltung
solution: Audience Manager
title: Abmeldeverwaltung
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Abmeldeverwaltung{#opt-out-management}

Adobe erfüllt alle branchenweit geltenden Standards für die Abmeldeverwaltung. Lesen Sie für vollständige Informationen zu den von Audience Manager unterstützten Abmeldearten.

## Globale Abmeldung {#global-opt-out}

Das globale Ausschluss stellt eine Abmeldung für alle Marken in Audience Manager und anderen Adobe Experience Cloud-Lösungen dar. In der folgenden Tabelle sind die Methoden aufgeführt, die für das globale Ausschluss verwendet werden:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Abmeldung für </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>Auf der Seite <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> "Datenschutzoptionen" </a> stehen Funktionen mit einem Klick zur Verfügung, mit denen Endbenutzer die Datenerfassung durch die Adobe Experience Cloud-Anzeigenlösungen (einschließlich Audience Manager) steuern und abwählen können. Weitere Informationen finden Sie im Abschnitt zum <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Geschäftskunden </a> auf der Seite "Datenschutzoptionen". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direkte API-Aufrufe an Audience Manager </p> </td> 
   <td colname="col2"> <p>Sie können die Datenerfassung durch alle Audience Manager-Marken deaktivieren, indem Sie unten die DCS API aufrufen und die <a href="../../reference/ids-in-aam.md"> Audience Manager-Benutzer-ID einschließen </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Als Ergebnis setzen wir <code>demdex=NOTARGET</code> - und <code>dextp=NOTARGET</code> -Cookies für die gesendete Audience Manager-Benutzer-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgeräte </p> </td> 
   <td colname="col2"> <p>Siehe Ausschluss- und Datenschutzeinstellungen für: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android-Geräte </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS-Geräte </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Ihre Endbenutzer können sich auch von der globalen Datenerfassung abmelden, indem sie die Websites unserer Partner für Branchenstandards besuchen.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Befolgen Sie die oben beschriebenen Abmeldeanfragen:

* Audience Manager beendet in Zukunft die Datenerfassung, Segmentierung oder Aktivierung.
* Historische Daten werden nach 120 Tagen aus dem Benutzerprofil entfernt.

## Ausschluss auf Partnerebene {#partner-opt-out}

Die Abmeldung auf Partnerebene ermöglicht die Abwahl der Datenerfassung durch bestimmte Audience Manager-Partner. Die Abmeldung auf Partnerebene funktioniert mit [deklarierten ID](../../features/declared-ids.md) -Aufrufen und Geräte-ID-Aufrufen, wie in den folgenden Abschnitten beschrieben.

### Abmeldung auf Partnerebene mit deklarierten ID-Aufrufen

Nach einer Abmeldung auf Partnerebene mit einem deklarierten ID-Aufruf:

* Die letzte Geräte-ID (Unique User ID[für](../../reference/ids-in-aam.md)Audience Manager), die mit der [CRM-ID](../../reference/ids-in-aam.md) verknüpft ist, wird aus der Datenerfassung ausgeschlossen.
* Audience Manager beendet die Datenerfassung, Segmentierung oder Aktivierung für die letzte Geräte-ID, die mit der CRM-ID verknüpft ist.
* Es werden keine Verlaufsdaten gelöscht.

<br/>

**Ausschluss-Anrufe**

Wenn Audience Manager eine Abmeldeanforderung auf Partnerebene erhält, enthält die vom DCS zurückgegebene JSON den [Fehlercode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)mit der Meldung [!UICONTROL "Encountered opt out tag"], nicht die Audience Manager-Benutzer-ID.

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**Beispiele**

Sie können eine deklarierte ID-Abmeldeanforderung mit den Paaren `d_cid` und dem Schlüssel- `d_cid_ic` Wert erstellen. Die alten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

**Ausschluss mit CID und CID_IC**

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../../features/declared-ids.md#variables-and-syntax).

| Ausschluss mit | Codebeispiel |
|--- |--- |
| Eine Datenanbieter-ID und Benutzer-ID. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| Ein Integrationscode und eine Benutzer-ID. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| Mehrere Schlüssel-Wert-Paare d_cid und d_cid_ic. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### Ausschluss auf Partnerebene mit Geräte-ID-Aufrufen

Sie können die Datenerfassung für eine bestimmte Geräte-ID für eine Marke deaktivieren, indem Sie die folgenden Aufrufe an die [DCS-API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)richten:

| Ausschluss mit | Codebeispiel |
|--- |--- |
| Eine eindeutige Benutzer-ID für Audience Manager (`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Eine Experience Cloud ID (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Mehr über `uuid`und `mid` im `imsOrgId`ID-Index in Audience Manager[](/help/using/reference/ids-in-aam.md) .

Nach einer Abmeldung auf Partnerebene mit einem Geräte-ID-Aufruf:

* Die Geräte-ID wird aus der Datenerfassung ausgeschlossen.
* Audience Manager beendet die Datenerfassung, Segmentierung oder Aktivierung für den Partner und fährt mit der Geräte-ID fort.
* Es werden keine Verlaufsdaten gelöscht.

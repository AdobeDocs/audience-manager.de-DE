---
description: Adobe erfüllt alle branchenweiten Standards hinsichtlich der Abmeldeverwaltung. Lesen Sie die Informationen zu den vom Audience Manager unterstützten Abmeldetypen.
seo-description: Adobe erfüllt alle branchenweiten Standards hinsichtlich der Abmeldeverwaltung. Lesen Sie die Informationen zu den vom Audience Manager unterstützten Abmeldetypen.
seo-title: Ausschluss-Management
solution: Audience Manager
title: Ausschluss-Management
uuid: 61 b 43 e 0 e-bfe 3-497 e-ade 2-6 a 942 a 98407 e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Ausschluss-Management{#opt-out-management}

Adobe erfüllt alle branchenweiten Standards hinsichtlich der Abmeldeverwaltung. Lesen Sie die Informationen zu den vom Audience Manager unterstützten Abmeldetypen.

## Globale Abmeldung {#global-opt-out}

Das globale Opt-out stellt eine Abmeldung aus Audience Manager und anderen Adobe Experience Cloud-Lösungen für alle Marken dar. In der folgenden Tabelle sind die Methoden aufgeführt, die für die globale Abmeldefunktion verwendet werden:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ausschluss für </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>Auf der <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Seite </a> "Ihre Datenschutzeinstellungen" finden Sie 1 Klick-Funktionen, mit denen Ihre Endbenutzer die Datenerfassung durch die Adobe Experience Cloud-Werbelösungen (einschließlich Audience Manager) steuern und ausschließen können. Informationen dazu finden Sie im <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Abschnitt Geschäftskunden </a> auf der Seite Datenschutzeinstellungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direct API-Aufrufe an Audience Manager </p> </td> 
   <td colname="col2"> <p>Sie können die Datenerfassung von allen Audience Manager-Marken abmelden, indem Sie unten einen Aufruf an die DCS-API durchführen und die <a href="../../reference/ids-in-aam.md"> Audience Manager-Benutzer-ID </a>einbinden: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex = 12345678901234567890123456789012345678; dextp = 12; DST = 12 " </code> </p> <p>Daher setzen wir die Cookies <code>demdex = NOTARGET</code> und <code>dextp = NOTARGET</code> für die gesendete Audience Manager-Benutzer-ID ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgeräte </p> </td> 
   <td colname="col2"> <p>Siehe Opt-out- und Datenschutzeinstellungen für: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android-Geräte </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS-Geräte </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Ihre Endbenutzer können sich auch aus der globalen Datenerfassung ausschließen, indem Sie die Websites unserer Branchenstandards besuchen.

* [Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI](https://optout.networkadvertising.org/?c=1#!/)).

Befolgen Sie die oben beschriebenen Abmeldeanforderungen:

* Der Audience Manager stoppt alle Datensammlungen, Segmentierung oder Aktivierung.
* Historische Daten werden nach 120 Tagen aus dem Benutzerprofil entfernt.

## Ausschluss auf Partnerebene {#partner-opt-out}

Das Opt-out auf Partnerebene ermöglicht die Abmeldung von der Datenerfassung durch bestimmte Audience Manager-Partner. Die Abmeldung auf Partnerebene funktioniert mit [deklarierten ID](../../features/declared-ids.md) -Aufrufen und Geräte-ID-Aufrufen, wie in den folgenden Abschnitten beschrieben.

### Ausschluss auf Partnerebene mit deklarierten ID-Aufrufen

Auf Partnerebene mit einem deklarierten ID-Aufruf folgen:

* Die mit der CRM-ID verknüpfte letzte Geräte-ID ([Unique User ID](../../reference/ids-in-aam.md)für Audience [Manager)](../../reference/ids-in-aam.md) wird aus der Datenerfassung abgemeldet.
* Audience Manager stoppt alle Datensammlungen, Segmentierungen oder Aktivierungen, die für die letzte Geräte-ID, die mit der CRM-ID verknüpft ist, vorwärtsgesetzt werden.
* Es werden keine historischen Daten gelöscht.

<br/>

**Abmeldeaufrufe**

Wenn Audience Manager eine Abmeldeanfrage auf Partner-Ebene empfängt, enthält der vom DCS zurückgegebene JSON den [Fehlercode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), mit der Meldung [!UICONTROL "Encountered opt out tag"]anstelle der Benutzer-ID des Audience Manager.

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

Sie können eine deklarierte ID-Ausschluss-Anforderung mit den `d_cid` Schlüsselwertpaaren erstellen `d_cid_ic` . Die alten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden aber als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../../reference/cid.md). In den Beispielen gibt *kursiv einen* Variablenplatzhalter an.

**Ausschlussmöglichkeiten mit CID und CID_ IC**

Eine Beschreibung und eine Syntax finden Sie unter [URL-Variablen und Syntax für deklarierte IDs](../../features/declared-ids.md#variables-and-syntax).

| Ausschluss mit | Codebeispiel |
|--- |--- |
| Eine Datenanbieter-ID und Benutzer-ID. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| Integrationscode und Benutzer-ID. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| Mehrere d_ cid- und d_ cid_ ic-Schlüssel-Wert-Paare. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### Ausschluss auf Partnerebene mit Geräte-ID-Aufrufen

Sie können die Datenerfassung für eine bestimmte Geräte-ID für eine Marke abwählen, indem Sie die folgenden Aufrufe an die [DCS-API durchführen](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Ausschluss mit | Codebeispiel |
|--- |--- |
| Eine eindeutige Benutzer-ID für Audience Manager (`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Eine Experience Cloud ID (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Lesen Sie mehr darüber `uuid`und `mid``imsOrgId` im [Index von IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Befolgen einer Abmeldeoption auf Partnerebene mit einem Geräte-ID-Aufruf:

* Die Geräte-ID wird aus der Datenerfassung abgemeldet.
* Audience Manager stoppt alle Datenerfassung, Segmentierung oder Aktivierung für den Partner, und zwar künftig für die Geräte-ID.
* Es werden keine historischen Daten gelöscht.

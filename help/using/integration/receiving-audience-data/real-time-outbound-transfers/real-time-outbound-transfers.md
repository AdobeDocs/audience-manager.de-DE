---
description: Der ausgehende Echtzeit-Datenübertragungsprozess gibt Benutzerdaten als eine Reihe von JSON-Objekten zurück, die mit einer POST-Methode weitergegeben werden.
seo-description: Der ausgehende Echtzeit-Datenübertragungsprozess gibt Benutzerdaten als eine Reihe von JSON-Objekten zurück, die mit einer POST-Methode weitergegeben werden.
seo-title: Echtzeit-Datenübertragungen in Echtzeit
solution: Audience Manager
title: Echtzeit-Datenübertragungen in Echtzeit
uuid: 1895 e 818-7 ab 8-4569-a 920-4 b 0 a 4 c 8 b 83 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Outbound Data Transfers {#real-time-outbound-data-transfers}

The outbound real-time data transfer process returns user data as a series of [!DNL JSON] objects passed in with a `POST` method.

<!-- c_outbound_json.xml -->

## Empfehlungen

Um diese Methode verwenden zu können, empfehlen wir Ihren Datenpartner:

* Accepts data in [!DNL JSON] format.
* Provides a URL that can be used by the `POST` call to return data.
* Accepts secure `HTTPS` data transfers. [!DNL Audience Manager] diese Datei nicht mit dem unsicheren `HTTP` Protokoll versenden.

## Häufigkeit

Diese Datenübertragungsmethode kann Daten in Echtzeit senden, wenn Benutzer sich für Segmente qualifizieren. Darüber hinaus kann diese Methode Stapel von Offline- oder Onlinedaten so oft wie alle 24 Stunden senden.

## Erforderliche Antworten

By default, the recipient server must return the `200 OK` code to indicate successful receipt. Andere Codes werden als Fehler interpretiert. Diese Antwort wird innerhalb von 3000 Millisekunden erwartet. In response to a failure, [!DNL Audience Manager] will make 1 retry attempt only.

## Parameter

The following table defines the elements in the returned [!DNL JSON] data file.

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Datentyp </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>Processtime</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>Zeitpunkt der Ausführung der Anforderung. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ DPID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Eine ID, die angibt, ob die Datei Android- oder ios-IDs enthält. Verwendet die folgenden ID-Werte: </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android IDs (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS IDs (IDFA): <code> 20915</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ ID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Client-ID, an die das System, an das Sie Daten senden, verwendet wird. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Destination_ ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Die ID, die Ihr Zielpartner Ihnen zugewiesen hat. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ count</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Total number of users in the <code> POST</code> request. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Benutzer</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Benutzerobjekten. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datapartner_ UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Datenpartner-UUID. Lassen Sie leer, wenn Ihr Datenpartner keine UUID hat. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Regionen</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> The <span class="keyword"> Audience Manager</span> region ID where we've seen this device. For instance, if the device had some activity in Paris (Europe), the region ID would be <code> 6</code>. Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmente</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segmentobjekten. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Die Ziel-ID-Zielzuordnung. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Status</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Definiert den Status eines Benutzers im Segment. Akzeptiert Folgendes: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Aktiv (Standard) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inaktiv, abgemeldet oder nicht segmentiert. </li> 
    </ul> <p>Benutzer werden nicht segmentiert, wenn sie: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Aus einem Segment, das auf der Segmentregel basiert, entfernt. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Removed from a segment based on the segment's <a href="../../../features/traits/segment-ttl-explained.md"> time-to-live interval</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">In einen inaktiven Status verschoben, wenn er in den letzten 120 Tagen nicht gesehen wurde. </li> 
    </ul> <p>All partner IDs that are synced to an <span class="keyword"> Audience Manager</span> ID will receive the <code> "Status":"0"</code> flag when a user is unsegmented. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datetime</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>Die Zeit, die ein Site-Besucher für die Eigenschaft qualifiziert hat. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicherheit

You can secure your real-time outbound data transfer process by [signing HTTP requests](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) using private keys or by having [!DNL Audience Manager] authenticate through the [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) protocol.

## Codebeispiel

Eine Echtzeit-Datenantwort kann wie folgt aussehen:

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```

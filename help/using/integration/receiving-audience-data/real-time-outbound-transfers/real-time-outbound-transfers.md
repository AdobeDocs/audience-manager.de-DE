---
description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: Real-Time Outbound Data Transfers
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 4e84682dea46f5b6c76464c66199f7a468bec334

---


# Real-Time Outbound Data Transfers {#real-time-outbound-data-transfers}

Der ausgehende Echtzeit-Datenübertragungsprozess liefert Benutzerdaten als eine Reihe [!DNL JSON] formatierter Nachrichten an eine Zielplattform.

<!-- c_outbound_json.xml -->

## Empfehlungen

Um diese Methode zu verwenden, muss die Zielplattform die folgenden Anforderungen erfüllen:

* Es muss einen Endpunkt bereitstellen, [!DNL URL] der skaliert werden kann, um ein hohes Volumen an Nachrichten von Audience Manager zu erhalten.
* Sie muss Daten im [!DNL JSON] Format (`Content-type: application/json`) annehmen.
* Es muss sichere `HTTPS` Datenübertragungen akzeptieren. [!DNL Audience Manager] will not send messages through the unsecure  protocol.`HTTP`

## Häufigkeit

This data transfer method can send data in near real-time as users qualify for segments. Real-time messages are only delivered while the user is online and actively visible to the Audience Manager Edge network. Optionally, this method can also send batches of offline or onboarded data as frequently as every 24-hours.

## Batch Transfers

Both real-time and batch transfers are sent to the same endpoint and use the same message format. When batch transfers are enabled, the destination platform will see a spike in message volume while the batch messages are delivered. Viele der Segmentqualifikationen, die durch Echtzeitmeldungen gesendet werden, werden in den Batch-Nachrichten wiederholt. Bei der Stapelübertragung werden nur die Segmentqualifikationen (oder Unqualifikationen) berücksichtigt, die sich seit der letzten Charge geändert haben.

## Ratenbeschränkungen

Für den Durchsatz bereitgestellter Nachrichten gibt es keine Ratenbeschränkungen. Das Festlegen von Ratenbeschränkungen könnte zu Datenverlusten führen.

## Erforderliche Antworten

Standardmäßig muss der Empfängerserver den `200 OK` Code zurückgeben, um eine erfolgreiche Quittung anzuzeigen. Andere Codes werden als Fehler interpretiert. Diese Antwort wird innerhalb von 3000 Millisekunden erwartet. Bei einem Fehler [!DNL Audience Manager] wird nur ein Wiederholungsversuch durchgeführt.

## Parameter

Die folgende Tabelle definiert die Elemente in der [!DNL JSON] Datendatei, die Sie an das Ziel senden.

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
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Time when the request was executed. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>user_DPID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Eine ID, die den Typ der Geräte-IDs angibt, die in der Meldung in der Eigenschaft User.DataPartner_UUID enthalten sind. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android-IDs (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS-IDs (IDFA): <code> 20915</code> </li>
     <li>Web-/Cookie-IDs: variiert nach Zielplattform</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Stellt das Zielkonto in der Zielplattform dar. Diese ID stammt von der Zielplattform.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Die ID des Zielobjekts von Audience Manager. Diese ID stammt aus Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Gesamtzahl der Benutzer in der <code> POST</code> -Anforderung. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Benutzer</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Benutzerobjekten. Standardmäßig enthält jede Nachricht 1 bis 10 Benutzer, damit die Nachrichtengröße optimal bleibt. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>user.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die UUID für <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>UUID der Zielplattform oder der globalen Geräte-ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>user.AAM_Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> Die <span class="keyword"> Audience Manager</span> -Regions-ID, in der wir dieses Gerät gesehen haben. Wenn das Gerät z. B. in Paris (Europa) aktiv wäre, wäre die Regions-ID <code> 6</code>. Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmente</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segmentobjekten. Bei Echtzeitmeldungen enthält das Array alle Segmente, denen der Benutzer angehört. For batch messages, the array contains only segment changes since the last batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>The identifier for the segment. In den meisten Fällen ist dies die vom Audience Manager generierte Segment-ID (eine Ganzzahl). In some cases, if the destination platform allows, customers can define the segment identifier in the Audience Manager UI (open text field), which would then reflect in this property. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Defines the status of a user in the segment. Accepts the following values: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1: Active (default)</code> </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inaktiv, ausgeschaltet oder nicht segmentiert. </li> 
    </ul> <p>Benutzer sind nicht segmentiert, wenn sie: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Removed from a segment based on the segment rule. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Aus einem Segment entfernt, basierend auf dem <a href="../../../features/traits/segment-ttl-explained.md"> Time-to-Live-Intervall</a>des Segments. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">In einen inaktiven Status verschoben, wenn sie in den letzten 120 Tagen nicht gesehen wurden. </li>
     <li>Entfernt aufgrund einer Datenschutzänderungsanfrage (d.h. [!DNL GDPR])</li>
    </ul> <p>Alle Partner-IDs, die mit einer <span class="keyword"> Audience Manager</span> -ID synchronisiert werden, erhalten das Flag <code> "Status":"0"</code> , wenn ein Benutzer nicht segmentiert ist. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Der Zeitpunkt, zu dem die Qualifizierung des Benutzersegments zuletzt überprüft wurde.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicherheit

Sie können Ihren ausgehenden Datenübertragungsprozess in Echtzeit durch [Signieren von HTTP-Anfragen](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) mit privaten Schlüsseln oder durch [!DNL Audience Manager] Authentifizierung über das [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) -Protokoll sichern.

## Anfrage

Eine Echtzeitanforderung kann wie folgt aussehen:

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
   "AAM_Regions": ["9"],
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
   "AAM_Regions": ["9"],
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

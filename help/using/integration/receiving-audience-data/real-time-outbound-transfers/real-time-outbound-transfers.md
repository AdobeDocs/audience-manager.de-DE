---
description: Der ausgehende Echtzeit-Datenübertragungsprozess gibt Benutzerdaten als eine Reihe von JSON-Objekten zurück, die mit einer POST-Methode übergeben werden.
seo-description: Der ausgehende Echtzeit-Datenübertragungsprozess gibt Benutzerdaten als eine Reihe von JSON-Objekten zurück, die mit einer POST-Methode übergeben werden.
seo-title: Ausgehende Datenübertragungen in Echtzeit
solution: Audience Manager
title: Ausgehende Datenübertragungen in Echtzeit
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


#  Ausgehende Datenübertragungen in Echtzeit {#real-time-outbound-data-transfers}

Der ausgehende Echtzeit-Datenübertragungsprozess gibt Benutzerdaten als eine Reihe von [!DNL JSON] Objekten zurück, die mit einer `POST` Methode übergeben werden.

<!-- c_outbound_json.xml -->

## Empfehlungen

Zur Verwendung dieser Methode empfehlen wir Ihrem Datenpartner,

* Akzeptiert Daten im [!DNL JSON] Format.
* Stellt eine URL bereit, die vom `POST` Aufruf zum Zurückgeben von Daten verwendet werden kann.
* Akzeptiert sichere `HTTPS` Datenübertragungen. [!DNL Audience Manager] wird diese Datei nicht mit dem unsicheren `HTTP` Protokoll senden.

## Häufigkeit

Mit dieser Datenübertragungsmethode können Daten in Echtzeit gesendet werden, wenn Benutzer sich für Segmente qualifizieren. Darüber hinaus kann diese Methode Stapel von Offline- oder Onboarded-Daten genauso oft wie alle 24 Stunden senden.

## Erforderliche Antworten

Standardmäßig muss der Empfängerserver den `200 OK` Code zurückgeben, um eine erfolgreiche Quittung anzuzeigen. Andere Codes werden als Fehler interpretiert. Diese Antwort wird innerhalb von 3000 Millisekunden erwartet. Bei einem Fehler [!DNL Audience Manager] wird nur ein Wiederholungsversuch durchgeführt.

## Parameter

Die folgende Tabelle definiert die Elemente in der zurückgegebenen [!DNL JSON] Datendatei.

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
   <td colname="col3"> <p>Zeitpunkt der Ausführung der Anforderung. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>user_DPID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Eine ID, die angibt, ob die Datei Android- oder iOS-IDs enthält. Verwendet die folgenden ID-Werte: </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android-IDs (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS-IDs (IDFA): <code> 20915</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>client_ID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Client-ID, die von dem System verwendet wird, an das Sie Daten senden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Die ID, die Ihnen von Ihrem Zielpartner zugewiesen wurde. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Gesamtzahl der Benutzer in der <code> POST</code> -Anforderung. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Benutzer</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Benutzerobjekten. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die UUID für <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>UUID des Datenpartners. Lassen Sie das Feld leer, wenn Ihr Datenpartner keine UUID hat. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> Die <span class="keyword"> Audience Manager</span> -Regions-ID, in der wir dieses Gerät gesehen haben. Wenn das Gerät z. B. in Paris (Europa) aktiv wäre, wäre die Regions-ID <code> 6</code>. Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmente</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segmentobjekten. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Die Segment-ID-Zielzuordnung. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Status</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Definiert den Status eines Benutzers im Segment. akzeptiert Folgendes: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Aktiv (Standard) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inaktiv, ausgeschaltet oder nicht segmentiert. </li> 
    </ul> <p>Benutzer sind nicht segmentiert, wenn sie: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Aus einem Segment entfernt, das auf der Segmentregel basiert. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Aus einem Segment entfernt, basierend auf dem <a href="../../../features/traits/segment-ttl-explained.md"> Time-to-Live-Intervall</a>des Segments. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">In einen inaktiven Status verschoben, wenn sie in den letzten 120 Tagen nicht gesehen wurden. </li> 
    </ul> <p>Alle Partner-IDs, die mit einer <span class="keyword"> Audience Manager</span> -ID synchronisiert werden, erhalten das Flag <code> "Status":"0"</code> , wenn ein Benutzer nicht segmentiert ist. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Der Zeitpunkt der letzten Segmentqualifizierung.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicherheit

Sie können Ihren ausgehenden Datenübertragungsprozess in Echtzeit durch [Signieren von HTTP-Anfragen](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) mit privaten Schlüsseln oder durch [!DNL Audience Manager] Authentifizierung über das [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) -Protokoll sichern.

## Codebeispiel

Eine Echtzeitdatenantwort kann wie folgt aussehen:

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

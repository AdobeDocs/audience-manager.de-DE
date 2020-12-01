---
description: Der ausgehende Echtzeit-Datenübertragungsprozess gibt Benutzerdaten als eine Reihe von JSON-Objekten zurück, die mit einer POST-Methode übergeben werden.
seo-description: Der ausgehende Echtzeit-Datenübertragungsprozess gibt Benutzerdaten als eine Reihe von JSON-Objekten zurück, die mit einer POST-Methode übergeben werden.
seo-title: Ausgehende Datenübertragungen in Echtzeit
solution: Audience Manager
title: Ausgehende Datenübertragungen in Echtzeit
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 5%

---


# Ausgehende Datenübertragungen in Echtzeit {#real-time-outbound-data-transfers}

Der ausgehende Echtzeit-Datenübertragungsprozess liefert Benutzerdaten als Folge von [!DNL JSON] formatierten Nachrichten an eine Zielplattform.

<!-- c_outbound_json.xml -->

## Empfehlungen

Um diese Methode zu verwenden, muss die Zielplattform die folgenden Anforderungen erfüllen:

* Es muss einen Endpunkt [!DNL URL] bereitstellen, der skaliert werden kann, um ein hohes Volumen an Nachrichten von Audience Manager zu empfangen.
* Es muss Daten im Format [!DNL JSON] (`Content-type: application/json`) akzeptieren.
* Es muss sichere `HTTPS` Datenübertragungen akzeptieren. [!DNL Audience Manager] sendet keine Nachrichten über das unsichere  `HTTP` Protokoll.

## Häufigkeit

Mit dieser Datenübertragungsmethode können Daten in Echtzeit gesendet werden, wenn Benutzer sich für Segmente qualifizieren. Echtzeit-Nachrichten werden nur gesendet, wenn der Benutzer online ist und aktiv für das Edge-Netzwerk des Audience Managers sichtbar ist. Optional kann diese Methode auch Stapel von Offline- oder Onboarded-Daten so oft wie alle 24 Stunden senden.

## Stapelübertragungen

Sowohl Echtzeit- als auch Batch-Übertragungen werden an denselben Endpunkt gesendet und verwenden dasselbe Nachrichtenformat. Wenn Batch-Transfers aktiviert sind, wird der Zielplattform eine Spitze des Nachrichtenvolumens angezeigt, während die Batch-Nachrichten gesendet werden. Viele der Segmentqualifikationen, die durch Echtzeitmeldungen gesendet werden, werden in den Batch-Nachrichten wiederholt. Bei der Stapelübertragung werden nur die Segmentqualifikationen (oder Unqualifikationen) berücksichtigt, die sich seit der letzten Charge geändert haben.

## Ratenbeschränkungen

Für den Durchsatz bereitgestellter Nachrichten gibt es keine Ratenbeschränkungen. Das Festlegen von Ratenbeschränkungen könnte zu Datenverlusten führen.

## Erforderliche Antworten

Standardmäßig muss der Empfänger-Server den `200 OK`-Code zurückgeben, um eine erfolgreiche Quittung anzuzeigen. Andere Codes werden als Fehler interpretiert. Diese Antwort wird innerhalb von 3000 Millisekunden erwartet. Bei einem Fehler unternimmt [!DNL Audience Manager] nur einen Wiederholungsversuch.

## Parameter

Die folgende Tabelle definiert die Elemente in der Datendatei [!DNL JSON], die Sie an das Ziel senden.

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
   <td colname="col3"> <p>Zeitpunkt, zu dem die Anforderung ausgeführt wurde. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
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
   <td colname="col3"> <p>Stellt das Zielgruppen-Konto in der Zielplattform dar. Diese ID stammt von der Zielplattform.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Die ID des Audience Manager-"target"-Objekts. Diese ID stammt von Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Gesamtzahl der Benutzer in der <code> POST</code>-Anforderung. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Benutzerobjekten. Standardmäßig enthält jede Nachricht 1 bis 10 Benutzer, damit die Nachrichtengröße optimal bleibt. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die UUID des Audience Managers <span class="keyword">.</span> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>UUID der Zielplattform oder der globalen Geräte-ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> Die Regions-ID <span class="keyword"> des Audience Managers</span>, auf dem dieses Gerät angezeigt wurde. Wenn das Gerät beispielsweise eine Aktivität in Paris (Europa) hätte, wäre die Regions-ID <code> 6</code>. Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segmentobjekten. Bei Echtzeitmeldungen enthält das Array alle Segmente, denen der Benutzer angehört. Bei Stapelmeldungen enthält das Array nur Segmentänderungen seit dem letzten Stapel.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmnent.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Der Bezeichner für das Segment. In den meisten Fällen ist dies die vom Audience Manager generierte Segment-ID (eine Ganzzahl). In einigen Fällen können Kunden, sofern die Zielplattform dies zulässt, die Segmentkennung in der Benutzeroberfläche des Audience Managers definieren (Open Text Field), die dann in dieser Eigenschaft übernommen wird. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Definiert den Status eines Benutzers im Segment. Akzeptiert die folgenden Werte: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Aktiv (Standard) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inaktiv, ausgeschaltet oder nicht segmentiert. </li> 
    </ul> <p>Benutzer sind nicht segmentiert, wenn sie: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Aus einem Segment entfernt, das auf der Segmentregel basiert. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Aus einem Segment entfernt, das auf dem <a href="../../../features/traits/segment-ttl-explained.md"> Time-to-Live Intervall</a> des Segments basiert. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">In einen inaktiven Status verschoben, wenn sie in den letzten 120 Tagen nicht gesehen wurden. </li>
     <li>Entfernt aufgrund einer Datenschutzänderungsanfrage (d.h. <span class="keyword"> GDPR</span>)</li>
    </ul> <p>Alle Partner-IDs, die mit einer <span class="keyword">-Audience Manager</span>-ID synchronisiert werden, erhalten das <code> "Status":"0"</code>-Flag, wenn ein Benutzer nicht segmentiert ist. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Der Zeitpunkt, zu dem die Qualifizierung des Benutzersegments zuletzt überprüft wurde.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicherheit

Sie können Ihren ausgehenden Datenübermittlungsprozess in Echtzeit durch [Unterschreiben von HTTP-Anfragen](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) mit privaten Schlüsseln oder durch [!DNL Audience Manager] Authentifizierung über das Protokoll [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) sichern.

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

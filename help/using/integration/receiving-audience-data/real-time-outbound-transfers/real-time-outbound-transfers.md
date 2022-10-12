---
description: Der ausgehende Echtzeit-Datenübertragungsprozess gibt Benutzerdaten als eine Reihe von JSON-Objekten zurück, die mit einer POST-Methode übergeben werden.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: Ausgehende Datenübertragungen in Echtzeit
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 5%

---

# Ausgehende Datenübertragungen in Echtzeit {#real-time-outbound-data-transfers}

Der ausgehende Echtzeit-Datenübertragungsprozess stellt Benutzerdaten als eine Reihe von [!DNL JSON] formatierte Nachrichten an eine Zielplattform.

<!-- c_outbound_json.xml -->

## Empfehlungen

Um diese Methode verwenden zu können, muss die Zielplattform die folgenden Anforderungen erfüllen:

* Sie muss einen Endpunkt bereitstellen [!DNL URL] die skaliert werden können, um eine große Anzahl von Nachrichten von Audience Manager zu erhalten;
* Sie muss Daten in [!DNL JSON] format (`Content-type: application/json`);
* Sie muss sicher sein `HTTPS` Datenübertragungen. [!DNL Audience Manager] sendet keine Nachrichten über die unsichere `HTTP` Protokoll.

## Häufigkeit

Diese Datenübertragungsmethode kann Daten nahezu in Echtzeit senden, da sich Benutzer für Segmente qualifizieren. Echtzeit-Nachrichten werden nur gesendet, wenn der Benutzer online ist und für das Audience Manager-Edge-Netzwerk aktiv sichtbar ist. Optional kann diese Methode auch Batches von Offline- oder integrierten Daten so oft wie alle 24 Stunden senden.

## Batch-Übertragungen

Sowohl Echtzeit- als auch Batch-Übertragungen werden an denselben Endpunkt gesendet und verwenden dasselbe Nachrichtenformat. Wenn Batch-Übertragungen aktiviert sind, wird auf der Zielplattform beim Versand der Batch-Nachrichten ein Anstieg des Nachrichtenvolumens festgestellt. Viele der Segmentqualifikationen, die über Echtzeit-Nachrichten gesendet werden, werden in den Batch-Nachrichten wiederholt. Batch-Übertragungen umfassen nur die Segmentqualifikationen (oder Nicht-Qualifikationen), die sich seit der letzten Batch-Bereitstellung geändert haben.

## Ratenbeschränkungen

Für den Durchsatz gesendeter Nachrichten gelten keine Ratenbeschränkungen. Das Festlegen von Ratenbeschränkungen könnte zu Datenverlust führen.

## Erforderliche Antworten

Standardmäßig muss der Empfängerserver die `200 OK` Code, um den erfolgreichen Empfang anzuzeigen. Andere Codes werden als Fehler interpretiert. Diese Antwort wird innerhalb von 3000 Millisekunden erwartet. Als Reaktion auf einen Fehler [!DNL Audience Manager] wird nur einen Wiederholungsversuch unternehmen.

## Parameter

Die folgende Tabelle definiert die Elemente in der [!DNL JSON] -Datendatei, die Sie an das Ziel senden.

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
   <td colname="col3"> <p>Zeitpunkt der Ausführung der Anfrage. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Eine ID, die den Typ der Geräte-IDs angibt, die in der Nachricht in der Eigenschaft User.DataPartner_UUID enthalten sind. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android IDs (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS IDs (IDFA): <code> 20915</code> </li>
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
   <td colname="col3"> <p>Die ID des Audience Manager-Objekts "Ziel". Diese ID stammt aus Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Gesamtzahl der Benutzer in der <code> POST</code> -Anfrage. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Benutzerobjekten. Standardmäßig enthält jede Nachricht zwischen 1 und 10 Benutzer, um die Nachrichtengröße optimal zu halten. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Die <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Ziel-Plattform-UUID oder die globale Geräte-ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> Die <span class="keyword"> Audience Manager</span> Regions-ID, wo wir dieses Gerät gesehen haben. Wenn das Gerät beispielsweise eine Aktivität in Paris (Europa) hätte, wäre die Regions-ID <code> 6</code>. Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS Region IDs, Locations, and Host Names</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segmentobjekten. Bei Echtzeit-Nachrichten enthält das Array alle Segmente, zu denen der Benutzer gehört. Bei Batch-Nachrichten enthält das Array nur Segmentänderungen seit dem letzten Batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Die Kennung für das Segment. In den meisten Fällen ist dies die vom Audience Manager generierte Segment-ID (eine Ganzzahl). In einigen Fällen können Kunden, wenn die Zielplattform dies zulässt, die Segmentkennung in der Audience Manager-Benutzeroberfläche definieren (geöffnetes Textfeld), was dann in dieser Eigenschaft widergespiegelt wird. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Definiert den Status eines Benutzers im Segment. Akzeptiert die folgenden Werte: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Aktiv (Standard) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inaktiv, abgemeldet oder nicht segmentiert. </li> 
    </ul> <p>Benutzer werden nicht segmentiert, wenn sie: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Aus einem Segment basierend auf der Segmentregel entfernt. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Aus einem Segment entfernt, das auf der <a href="../../../features/traits/segment-ttl-explained.md"> Time-to-Live-Intervall</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">In einen inaktiven Status verschoben, wenn sie in den letzten 120 Tagen nicht gesehen wurden. </li>
     <li>Entfernt aufgrund einer Datenschutzänderungsanfrage (d. h. <span class="keyword"> DSGVO</span>)</li>
    </ul> <p>Alle Partner-IDs, die mit einer <span class="keyword"> Audience Manager</span> Die ID erhält die <code> "Status":"0"</code> kennzeichnen, wenn ein Benutzer nicht segmentiert ist. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Der Zeitpunkt, zu dem die Qualifizierung des Benutzersegments zuletzt überprüft wurde.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicherheit

Sie können Ihren ausgehenden Datenübertragungsprozess in Echtzeit durch [Signieren von HTTP-Anforderungen](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) Verwendung privater Schlüssel oder [!DNL Audience Manager] über die [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) Protokoll.

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

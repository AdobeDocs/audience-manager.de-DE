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
source-wordcount: '677'
ht-degree: 2%

---

# Ausgehende Datenübertragungen in Echtzeit {#real-time-outbound-data-transfers}

Der ausgehende Echtzeit-Datenübertragungsprozess stellt Benutzerdaten als eine Reihe [!DNL JSON] formatierten Nachrichten an eine Zielplattform bereit.

<!-- c_outbound_json.xml -->

## Empfehlungen

Um diese Methode verwenden zu können, muss die Zielplattform die folgenden Anforderungen erfüllen:

* Sie muss eine Endpunkt-[!DNL URL] bereitstellen, die für den Empfang einer großen Anzahl von Nachrichten von Audience Manager skalierbar ist.
* Sie muss Daten im [!DNL JSON] Format (`Content-type: application/json`) akzeptieren.
* Sie muss sichere `HTTPS` Datenübertragungen akzeptieren. [!DNL Audience Manager] senden keine Nachrichten über das Protokoll „Unsicheres `HTTP`&quot;.

## Häufigkeit

Diese Datenübertragungsmethode kann Daten nahezu in Echtzeit senden, da Benutzende für Segmente qualifiziert sind. Echtzeitnachrichten werden nur dann bereitgestellt, wenn der/die Benutzende online ist und im Audience Manager Edge-Netzwerk aktiv angezeigt wird. Optional kann diese Methode auch Batches von Offline- oder Onboarding-Daten so häufig wie alle 24 Stunden senden.

## Batch-Übertragungen

Sowohl Echtzeit- als auch Batch-Übertragungen werden an denselben Endpunkt gesendet und verwenden dasselbe Nachrichtenformat. Wenn Batch-Übertragungen aktiviert sind, weist die Zielplattform beim Versand der Batch-Nachrichten eine Spitze beim Nachrichtenvolumen auf. Viele der Segmentqualifikationen, die über Echtzeitnachrichten gesendet werden, werden in den Batch-Nachrichten wiederholt. Stapelübertragungen umfassen nur die Segmentqualifikationen (oder Aufhebungen von Qualifikationen), die sich seit der letzten Batch-Lieferung geändert haben.

## Ratenbeschränkungen

Für den Durchsatz der zugestellten Nachrichten wurden keine Ratenbeschränkungen festgelegt. Das Festlegen von Ratenbeschränkungen kann zu Datenverlust führen.

## Erforderliche Antworten

Standardmäßig muss der Empfänger-Server den `200 OK`-Code zurückgeben, um einen erfolgreichen Empfang anzuzeigen. Andere Codes werden als Fehler interpretiert. Diese Antwort wird innerhalb von 3000 Millisekunden erwartet. Als Reaktion auf einen Fehler unternimmt [!DNL Audience Manager] nur einen Wiederholungsversuch.

## Parameter

In der folgenden Tabelle werden die Elemente in der [!DNL JSON]-Datendatei definiert, die Sie an das Ziel senden.

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
   <td colname="col3"> <p>Zeitpunkt, zu dem die Anfrage ausgeführt wurde. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Eine ID, die den Typ der in der Nachricht enthaltenen Geräte-IDs in der Eigenschaft User.DataPartner_UUID angibt. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android-IDs (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS-IDs (IDFA): <code> 20915</code> </li>
     <li>Web-/Cookie-IDs: variiert je nach Zielplattform</li>
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
   <td colname="col3"> <p>Die ID des Audience Manager-„Ziel“-Objekts. Diese ID stammt aus Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Gesamtzahl der Benutzer in der <code> POST</code>. </p> </td> 
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
   <td colname="col3"> <p>Zielplattform-UUID oder die globale Geräte-ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> Die <span class="keyword"> Audience Manager</span>-Regions-ID, in der wir dieses Gerät gesehen haben. Wenn das Gerät beispielsweise in Paris (Europa) aktiv war, würde die Regions-ID <code> 6</code>. Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> von DCS-Regions-IDs, Standorten und Hostnamen</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Ein Array von Segmentobjekten. Bei Echtzeitnachrichten enthält das Array alle Segmente, zu denen der Benutzer gehört. Bei Batch-Nachrichten enthält das -Array nur Segmentänderungen seit dem letzten Batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Die Kennung für das Segment. In den meisten Fällen ist dies die von Audience Manager generierte Segment-ID (eine Ganzzahl). Wenn es die Zielplattform zulässt, können Kundinnen und Kunden in einigen Fällen die Segmentkennung in der Audience Manager-Benutzeroberfläche definieren (offenes Textfeld), die dann in dieser Eigenschaft widergespiegelt wird. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Ganzzahl </p> </td> 
   <td colname="col3"> <p>Definiert den Status eines Benutzers im Segment. Akzeptiert die folgenden Werte: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Aktiv (Standard) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inaktiv, Abgewählt oder nicht segmentiert. </li> 
    </ul> <p>Benutzende werden nicht segmentiert, wenn sie: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Aus einem Segment entfernt, basierend auf der Segmentregel. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Aus einem Segment entfernt, basierend auf dem <a href="../../../features/traits/segment-ttl-explained.md"> Time-to-Live-Intervall </a> Segments. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">In einen inaktiven Status verschoben, wenn sie in den letzten 120 Tagen nicht gesehen wurden. </li>
     <li>Wegen einer Datenschutzänderungsanfrage (d. h. <span class="keyword"> DSGVO) </span></li>
    </ul> <p>Alle Partner-IDs, die mit einer <span class="keyword"> Audience Manager</span> ID synchronisiert werden, erhalten die <code> "Status":"0"</code>-Markierung, wenn eine Benutzerin oder ein Benutzer nicht segmentiert ist. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Der Zeitpunkt, zu dem die Benutzersegmentqualifikation zuletzt überprüft wurde.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sicherheit

Sie können Ihren in Echtzeit ausgehenden Datenübertragungsprozess schützen, indem Sie [HTTP-Anfragen signieren](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) private Schlüssel verwenden oder sich über das [!DNL Audience Manager]OAuth 2.0[-Protokoll authentifizieren &#x200B;](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md).

## Anfrage

Eine Echtzeitanfrage kann in etwa wie folgt aussehen:

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

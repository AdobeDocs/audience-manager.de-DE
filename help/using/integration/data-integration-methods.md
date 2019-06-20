---
description: Eine allgemeine Übersicht darüber, wie Audience Manager Informationen mit anderen Datenanbietern und Systemen austauscht.
seo-description: Eine allgemeine Übersicht darüber, wie Audience Manager Informationen mit anderen Datenanbietern und Systemen austauscht.
seo-title: Datenintegrationsmethoden
solution: Audience Manager
title: Datenintegrationsmethoden
uuid: 17 a 4179 a-e 99 b -49 eb -8 f 45-f 2946 afbd 27 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Datenintegrationsmethoden {#data-integration-methods}

Eine allgemeine Übersicht darüber, wie Audience Manager Informationen mit anderen Datenanbietern und Systemen austauscht.

## Unterstützte Datenintegrationsmethoden: Echtzeit- und Server-to-Server {#supported-methods}

Die Auswahl der richtigen Integrationsmethode hängt von einer Kombination aus Geschäftsanforderungen und den technischen Funktionen Ihres Datenpartners ab. Audience Manager tauscht die Besucherinformationen mit anderen Datenanbietern durch eine der folgenden Methoden aus:

* **Echtzeit:** Überträgt Daten sofort, wenn ein Benutzer Ihre Site besucht. Diese Methode wird auch als *`synchronous`* Integration bezeichnet.
* **Batch (Server-to-Server):** Überträgt Daten zwischen Servern in einem festgelegten Zeitplan, nachdem ein Besucher die Seite verlassen hat. Diese Methode wird auch als *`out-of-band`* oder *`asynchronous`* Integration bezeichnet.

## Voraussetzungen: Eigenschaften-Taxonomie erstellen {#prereqs}

Bevor der Integrationsprozess beginnt, denken Sie daran, [Eigenschaften](../features/traits/create-onboarded-rule-based-traits.md) und eine [Ordnerstruktur](../features/traits/trait-storage.md#create-trait-storage-folder) in der [!DNL Audience Manager] Benutzeroberfläche zu erstellen. Die Taxonomie enthält alle in einer logischen Hierarchie organisierten Eigenschaften.

## Anwendungsfälle für die Integration {#integration-use-cases}

Eine Anwendungsfall-Zusammenfassung der Audience Manager-Datenintegrationsmethoden mit den Vor- und Nachteile von jedem.

### Server-zu-Server-Integrationen real

<!-- c_int_types_use_cases.xml -->

Durch eine Echtzeit-Serverintegration werden Benutzerdaten zwischen Audience Manager-Servern und einem anderen Targeting-System schnell synchronisiert. In den meisten Fällen erfolgt der Datenaustausch innerhalb von Sekunden oder Minuten, abhängig von der Aktualisierungsrate des Targeting-Systems. Beachten Sie jedoch, dass das Zielsystem dieses Aktualisierungsintervall und nicht den Audience Manager bestimmt. Außerdem kann die Aktualisierungsrate zwischen verschiedenen Systemen variieren. Eine Echtzeit-Integration von Server zu Server ist der bevorzugte Integrationstyp für den Datenaustausch. Audience Manager verwendet diese Methode, wenn Targeting-Partner diese unterstützen können.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Damit können Sie Benutzer für Segmente qualifizieren, ohne sie erneut auf der Seite, in einem Video-Player usw. anzuzeigen. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduziert die Anzahl der HTTP-Aufrufe von der Seite. Weniger Aufrufe unterstützen die Benutzererfahrung. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Hilft bei der zeitsensitiven Targeting, damit Sie schnell auf einem qualifizierten Benutzer handeln können. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Nützlich beim Wechsel zu einer DSP für Offsite-Targeting. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nachteile:</td>
  <td class="stentry"> Weniger nützlich für Onsite-Targeting, wenn Sie den Benutzer auf derselben Seite oder auf der nächsten Seite als Ziel auswählen müssen, basierend auf einem Benutzer für dieses Segment.</td>
 </tr>
</table>

### Server-zu-Server-Batch-Integrationen

Eine Server-zu-Server-Batch-Integration-Bundles-Daten und senden sie in anderen Systemen in festgelegten Intervallen anstatt in Echtzeit. Datenübertragungsintervalle werden ab 24 Stunden gestartet. Einige Datenanbieter unterstützen diesen Integrationstyp nur. Wir haben jedoch einen allgemeinen Trend von Batch-Integrationen in Echtzeit-Integrationsmethoden gesehen.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Damit können Sie Benutzer für Segmente qualifizieren, ohne sie erneut auf der Seite, in einem Video-Player usw. anzuzeigen. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Nützlich für Targeting, der nicht zeitempfindlich ist. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nachteile:</td>
  <td class="stentry"> Das Synchronisierungsintervall kann das Targeting gegenüber den aktuellen Daten verzögern.</td>
 </tr>
</table>

### Echtzeitanrufe

Echtzeit-Aufrufe tauschen Daten mit Audience Manager sofort aus, da ein Benutzer Ihre Site besucht oder Aktionen auf der Seite durchführt. Mit dieser Methode erhalten Targeting-Systeme die aktuellsten Segmentqualifizierungsdaten und können diese Informationen während eines Inhalts oder einer Anzeigenbereitstellungsentscheidung berücksichtigen. Dieser Prozess arbeitet auch mit den Publisher-Anzeigen von Publisher zusammen, wobei wir qualifizierte Segmente auf ein Erstanbieter-Cookie aktualisieren, das als Schlüssel-Wert-Paare in einen Anzeigenaufruf gelesen wird. Derzeit verwendet Audience Manager Echtzeitanrufe für die Integration mit [!DNL Target] und anderen Content Management-Systemen.

<table> 
 <tr>
  <td> <p>Vorteile: </p></td>
  <td> <p> Ermöglicht das Targeting der nächsten Seite, des Inhaltsbereichs oder der Anzeigenimpression basierend auf der letzten Segmentqualifizierung. </p></td> 
 </tr> 
 <tr>
  <td> <p>Nachteile: </p></td>
  <td> <p>Fügt einen Aufruf an Audience Manager auf der Seite hinzu.</p></td>
 </tr> 
</table>


### Pixel synchronisiert mit Targeting-Systemen

Die Pixelsynchronisierung ordnet Segmente Pixel auf der Seite zu. Das Pixel löst Daten aus und sendet Daten, wenn sich ein Benutzer für ein bestimmtes Segment qualifiziert. Die Pixelsynchronisierung ist ein rudimentärer und unzuverlässiger Datenübertragungsmechanismus. Datenanbieter und -systeme der obersten Ebene verwenden diese selten.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> <p> Echtzeit-Datenübertragungen. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Nachteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Kann viele clientseitige Aufrufe von der Seite hinzufügen. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Unzuverlässig für die Datenübertragung. Der Wert von 5% bis 20% ist normal. </li>
   </ul></td>
 </tr> 
</table>

## Auswählen einer Datenauslieferungsmethode {#data-delivery-choices}

Beschreibt technische und geschäftliche Gründe für das Senden von Daten über synchrone (Echtzeit) oder asynchrone (Server-to-Server) Methoden.

<!-- c_int_delivery_choices.xml -->

### Auswählen eines Datenauslieferungstyps

* **Technische Aspekte:** Die Datenbereitstellung hängt von den technischen Funktionen des Datenpartners ab. Audience Manager kann Daten aus dem Browser oder per Batch-Updates über Offline- und Server-zu-Server-Kommunikationsprozesse senden/empfangen.
* **Geschäftliche Aspekte:** Die geschäftlichen Gründe für die Auswahl einer Auslieferungsmethode oder eines anderen hängen von den technischen Fähigkeiten Ihres Zielpartners ab und davon, wie Sie diese Daten verwenden möchten. synchrone Datenübertragungen sind normalerweise sinnvoll, wenn Sie sofort Maßnahmen für Benutzerdaten ergreifen müssen. Asynchrone Datenübertragungen können nützlich sein, wenn keine sofortige Aktion erforderlich ist und wenn Sie Zeit haben, tiefere Benutzerprofile zur späteren Verwendung zu erstellen.

## Echtzeit-Datenübertragungsprozess {#real-time-data-transfer-process}

Eine allgemeine Übersicht darüber, wie Audience Manager einen synchronen Datenaustausch mit einem Drittanbieter durchführt.

### Echtzeit-Datenübertragung

<!-- c_int_overview_sync.xml -->

Datenübertragungen in Echtzeit senden und empfangen Segment-IDs als Benutzerbesuche oder werden auf Ihrer Site ausgeführt. synchrone Datenübertragungen sind normalerweise sinnvoll, wenn Sie Benutzer direkt qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

### Echtzeit-Datenintegrationsschritte

Der Echtzeit-Datenintegrationsprozess funktioniert wie folgt:

1. Ein Benutzer besucht die Site eines Kunden, die den Audience Manager-Code enthält.
1. Audience Manager lädt einen Iframe und ruft einen [!UICONTROL Data Collection Server] Aufruf an ([!UICONTROL DCS]).
1. Der [!UICONTROL DCS] Server ruft den Drittanbieterserver (in Echtzeit) auf, um zu überprüfen, ob der Anbieter über Segmentinformationen zum Benutzer verfügt.
1. Der Dritte gibt Segmentinformationen zu diesem Benutzer an den Audience Manager zurück.
1. Audience Manager ingests segmentinformationen und stellt diese für Targeting zur Verfügung.

![](assets/rt_reduce70.png)

## Batch-Datenübertragungsprozess {#batch-data-transfer-process}

Eine allgemeine Übersicht darüber, wie Audience Manager Daten synchron (in Echtzeit) mit einem Drittanbieter austauscht.

### Batch-Datenintegration

<!-- c_int_overview_async.xml -->

Der Batch-Datenintegrationsprozess (Server-to-Server) folgt den meisten Schritten, die im Echtzeit-Datenübertragungsprozess beschrieben werden. Anstatt Segment-IDs sofort zurückzugeben, werden Benutzerinformationen auf unseren Servern gespeichert und in regelmäßigen Abständen mit einem Drittanbieter-Datenprovider synchronisiert. Der asynchrone Datenübertragungsprozess ist nützlich, wenn:

* Sofortige Datenübertragungen sind nicht erforderlich.
* Erfassen von Daten, um einen großen Pool segmentierter Benutzer zu erstellen.
* Sie möchten Datendiskrepanzen und `HTTP` Aufrufe vom Browser verringern.

### Stapeldatenintegrationsschritte

1. Ein Benutzer besucht eine Kunden-Site.
1. Audience Manager und der Drittanbieter-Datenanbieter weisen dem Besucher eine eindeutige ID zu (normalerweise mit einem Cookie).
1. Audience Manager ruft den Drittanbieter-Datenprovider auf, um Besucher-IDs abzugleichen.
1. Eine geplante Anforderung (üblicherweise in einem täglichen Intervall) umgeht Besuchersegmentdaten zwischen Audience Manager und Ihrem Drittanbieter-Datenanbieter.

![](assets/s2s_70.png)

Informationen zur Beschreibung der Zeitrahmen, wenn Audience Manager eingehende und ausgehende Server-to-Server ([!UICONTROL S2S])-Dateiübertragungen verarbeitet, finden Sie unter [Berichte zu Berichterstellung und Dateiübertragung](../reference/reporting-file-transfer-timeframe.md).

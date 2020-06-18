---
description: Ein Überblick über den Informationsaustausch zwischen Audience Manager und anderen Datenanbietern und Systemen.
seo-description: Ein Überblick über den Informationsaustausch zwischen Audience Manager und anderen Datenanbietern und Systemen.
seo-title: Datenintegrationsmethoden
solution: Audience Manager
title: Datenintegrationsmethoden
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 1%

---


# Datenintegrationsmethoden {#data-integration-methods}

Ein Überblick über den Informationsaustausch zwischen Audience Manager und anderen Datenanbietern und Systemen.

## Unterstützte Datenintegrationsmethoden: Echtzeit und Server-zu-Server {#supported-methods}

Die Wahl der richtigen Integrationsmethode hängt von einer Kombination aus Geschäftsanforderungen und den technischen Fähigkeiten Ihres Datenpartners ab. Audience Manager tauscht Besucher-Informationen mit anderen Datenanbietern auf eine der folgenden Methoden aus:

* **Echtzeit:** Sendet Daten sofort, wenn ein Benutzer Ihre Site besucht. Diese Methode wird auch als *`synchronous`* Integration bezeichnet.
* **Stapel (Server-to-Server):** Sendet Daten nach einem festgelegten Zeitplan zwischen Servern, nachdem ein Besucher die Seite verlassen hat. Diese Methode wird auch als *`out-of-band`* oder *`asynchronous`* Integration bezeichnet.

## Voraussetzungen: Eigenschaften-Taxonomie erstellen {#prereqs}

Bevor der Integrationsprozess beginnt, müssen Sie Eigenschaften [und eine](../features/traits/create-onboarded-rule-based-traits.md) Ordnerstruktur [in der](../features/traits/trait-storage.md#create-trait-storage-folder) Benutzeroberfläche [!DNL Audience Manager] erstellen. Die Taxonomie enthält alle Eigenschaften, die in einer logischen Hierarchie organisiert sind.

## Anwendungsfälle der Integration {#integration-use-cases}

Eine Anwendungsfallzusammenfassung mit den Audience Manager-Datenintegrationsmethoden sowie deren Vor- und Nachteile.

### Server-zu-Server-Integrationen in Echtzeit

<!-- c_int_types_use_cases.xml -->

Bei einer Echtzeit-Server-zu-Server-Datenintegration werden Benutzerdaten schnell zwischen Audience Manager-Servern und einem anderen Targeting-System synchronisiert. In den meisten Fällen findet der Datenaustausch in Sekunden oder Minuten statt, je nach der Aktualisierungsrate des Targeting-Systems. Beachten Sie jedoch, dass das Targeting-System dieses Aktualisierungsintervall und nicht den Audience Manager bestimmt. Darüber hinaus kann die Aktualisierungsrate je nach System variieren. Eine Server-zu-Server-Integration in Echtzeit ist der bevorzugte Integrationstyp für den Datenaustausch. Audience Manager verwendet diese Methode, wenn Targeting-Partner sie unterstützen können.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Damit können Sie Benutzer für Segmente qualifizieren, ohne sie erneut auf der Seite, in einem Videoplayer usw. anzuzeigen. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduziert die Anzahl der HTTP-Aufrufe von der Seite. Weniger Aufrufe tragen dazu bei, die Benutzererfahrung zu erhalten. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Hilft beim zeitabhängigen Targeting, damit Sie schnell handeln können. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Nützlich beim Wechsel zu einem DSP für Offsite-Targeting. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nachteile:</td>
  <td class="stentry"> Weniger nützlich für Onsite-Targeting, wenn Sie den Benutzer auf derselben Seite oder auf der nächsten Zielgruppe entsprechend der Benutzerqualifikation für dieses Segment erstellen müssen.</td>
 </tr>
</table>

### Batch-Integrationen von Server zu Server

Bei einer Batch-Integration zwischen Server und Server werden Daten gebündelt und in festgelegten Intervallen und nicht in Echtzeit an andere Systeme gesendet. Beginn der Datenübertragungsintervalle ab 24 Stunden. Einige Datenanbieter unterstützen nur diesen Integrationstyp. Wir haben jedoch einen allgemeinen Trend gesehen, weg von Batch-Integrationen hin zu Echtzeit-Integrationsmethoden.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Damit können Sie Benutzer für Segmente qualifizieren, ohne sie erneut auf der Seite, in einem Videoplayer usw. anzuzeigen. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Nützlich für Targeting, das nicht zeitempfindlich ist. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nachteile:</td>
  <td class="stentry"> Das Synchronisierungsintervall kann das Targeting der aktuellsten Daten verzögern.</td>
 </tr>
</table>

### Echtzeitaufrufe

Echtzeitaufrufe tauschen Daten sofort mit dem Audience Manager aus, wenn ein Benutzer Ihre Site besucht oder auf der Seite aktiv wird. Mit dieser Methode erhalten Targeting-Systeme die aktuellsten Segmentqualifizierungsdaten und können diese Informationen bei der Inhaltsentscheidung oder bei der Versand-Entscheidung berücksichtigen. Dieser Prozess funktioniert auch mit Herausgeber-Anzeigenservern, bei denen qualifizierte Segmente auf ein Erstanbieter-Cookie aktualisiert werden, das als Schlüssel-Wert-Paare in einen Anzeigenaufruf gelesen wird. Derzeit verwendet Audience Manager Echtzeitaufrufe zur Integration mit [!DNL Target] und anderen Content-Managements.

<table> 
 <tr>
  <td> <p>Vorteile: </p></td>
  <td> <p> Ermöglicht die Zielgruppe der nächsten Seite, des Inhaltsbereichs oder der Anzeigenimpression auf Grundlage der neuesten Segmentqualifikation. </p></td> 
 </tr> 
 <tr>
  <td> <p>Nachteile: </p></td>
  <td> <p>Fügt einen Aufruf an Audience Manager von der Seite hinzu.</p></td>
 </tr> 
</table>


### Pixel synchronisiert mit Targeting-Systemen

Die Pixelsynchronisierung ordnet Segmente Pixeln auf der Seite zu. Das Pixel wird ausgelöst und sendet Daten, wenn ein Benutzer sich für ein bestimmtes Segment qualifiziert. Die Pixelsynchronisierung ist ein rudimentärer und unzuverlässiger Datenübertragungsmechanismus. Datenanbieter und Systeme der obersten Ebene verwenden sie selten.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> <p> Datenübertragung in Echtzeit </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Nachteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Kann viele clientseitige Aufrufe von der Seite hinzufügen. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Unzuverlässig für die Datenübertragung. 5 % bis 20 % Verlust ist normal. </li>
   </ul></td>
 </tr> 
</table>

## Auswählen einer Data Versand-Methode {#data-delivery-choices}

Beschreibt technische und geschäftliche Gründe für das Senden von Daten über synchrone (Echtzeit-) oder asynchrone (Server-zu-Server-) Methoden.

<!-- c_int_delivery_choices.xml -->

### Auswählen eines Data Versand-Typs

* **Technische Überlegungen:** Der Versand von Daten hängt von den technischen Möglichkeiten des Datenpartners ab. Audience Manager können Daten in Echtzeit vom Browser oder durch Batch-Aktualisierungen über Offline-, Server-zu-Server-Kommunikationsprozesse senden/empfangen.
* **Geschäftsaspekte:** Die geschäftlichen Gründe für die Auswahl der einen oder anderen Versand-Methode hängen von den technischen Möglichkeiten Ihres Zielpartners und davon ab, wie Sie diese Daten verwenden möchten. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie sofort auf Benutzerdaten reagieren müssen. Asynchrone Datenübertragungen können nützlich sein, wenn sofortiges Handeln nicht erforderlich ist und Sie Zeit haben, tiefere Profil für die spätere Verwendung zu erstellen.

## Datenübertragungsprozess in Echtzeit {#real-time-data-transfer-process}

Eine allgemeine Übersicht darüber, wie Audience Manager einen synchronen Datenaustausch mit einem Drittanbieter durchführt.

### Datenübertragung in Echtzeit

<!-- c_int_overview_sync.xml -->

Echtzeit-Datenübertragungen senden und empfangen Segment-IDs als Benutzerbesuche oder ergreifen Aktionen auf Ihrer Site. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie Benutzer sofort qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

### Schritte zur Datenintegration in Echtzeit

Der Datenintegrationsprozess in Echtzeit funktioniert wie folgt:

1. Ein Benutzer besucht die Site eines Kunden, die Audience Manager-Code enthält.
1. Audience Manager lädt einen Iframe und ruft die [!UICONTROL Data Collection Server] ([!DNL DCS]) auf.
1. Der Drittanbieterserver [!DNL DCS] ruft (in Echtzeit) auf, um zu prüfen, ob der Anbieter Segmentinformationen über den Benutzer hat.
1. Der Drittanbieter gibt Segmentinformationen über diesen Benutzer an den Audience Manager zurück.
1. Audience Manager erfasst Segmentinformationen und stellt sie für das Targeting bereit.

![](assets/rt_reduce70.png)

## Batch-Datenübermittlungsprozess {#batch-data-transfer-process}

Eine allgemeine Übersicht darüber, wie Audience Manager Daten synchron (in Echtzeit) mit einem Drittanbieter austauschen.

### Batch-Datenintegration

<!-- c_int_overview_async.xml -->

Der Prozess der Datenintegration (Server-zu-Server) von Batch folgt den meisten Schritten, die im Datenübertragungsprozess in Echtzeit beschrieben werden. Statt jedoch Segment-IDs sofort zurückzugeben, werden Benutzerinformationen in regelmäßigen Abständen auf unseren Servern gespeichert und mit einem Drittanbieter synchronisiert. Der Prozess der asynchronen Datenübertragung ist nützlich, wenn:

* Eine sofortige Datenübertragung ist nicht erforderlich.
* Datenerfassung zum Aufbau eines großen Pools segmentierter Benutzer.
* Sie möchten Datendiskrepanzen und `HTTP` Aufrufe vom Browser reduzieren.

### Batch-Datenintegrationsschritte

1. Ein Benutzer besucht eine Kunden-Site.
1. Audience Manager und der Drittanbieter für Daten weisen dem Besucher eine eindeutige ID zu (üblicherweise mit einem Cookie).
1. Audience Manager ruft den Drittanbieter-Datenanbieter auf, um Besucher-IDs zuzuordnen.
1. Bei einer geplanten Anforderung, die in der Regel täglich erfolgt, werden die Segmentdaten des Besuchers zwischen Audience Manager und Ihrem Drittanbieter ausgetauscht.

![](assets/s2s_70.png)

Informationen zu den Zeiträumen, in denen Audience Manager eingehende und ausgehende Server-zu-Server-Dateiübertragungen ([!UICONTROL S2S]) verarbeitet, finden Sie unter Richtlinien für die [Berichte- und Dateiübertragung](../reference/reporting-file-transfer-timeframe.md).

---
description: Ein Überblick darüber, wie Audience Manager Informationen mit anderen Datenanbietern und -systemen austauschen.
seo-description: Ein Überblick darüber, wie Audience Manager Informationen mit anderen Datenanbietern und -systemen austauschen.
seo-title: Datenintegrationsmethoden
solution: Audience Manager
title: Datenintegrationsmethoden
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Drittanbieterintegration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 1%

---

# Datenintegrationsmethoden {#data-integration-methods}

Ein Überblick darüber, wie Audience Manager Informationen mit anderen Datenanbietern und -systemen austauschen.

## Unterstützte Datenintegrationsmethoden: Echtzeit und [!DNL Server-to-Server] {#supported-methods}

Die Wahl der richtigen Integrationsmethode hängt von einer Kombination aus geschäftlichen Anforderungen und den technischen Fähigkeiten Ihres Datenpartners ab. Audience Manager tauschen Besucherinformationen mit anderen Datenanbietern auf eine der folgenden Arten aus:

* **Echtzeit:** Überträgt Daten sofort, wenn ein Benutzer Ihre Site besucht. Diese Methode wird auch als *`synchronous`* -Integration bezeichnet.
* **Batch ([!DNL Server-to-Server]):**  Übergibt Daten nach dem Verlassen der Seite durch einen Besucher auf einen festgelegten Zeitplan zwischen Servern. Diese Methode wird auch als *`out-of-band`*- oder *`asynchronous`*-Integration bezeichnet.

## Voraussetzungen: Erstellen einer Eigenschaftstaxonomie {#prereqs}

Bevor der Integrationsprozess beginnt, denken Sie an [Eigenschaften erstellen](../features/traits/create-onboarded-rule-based-traits.md) und an eine [Ordnerstruktur](../features/traits/trait-storage.md#create-trait-storage-folder) in der [!DNL Audience Manager] -Benutzeroberfläche. Die Taxonomie enthält alle [!UICONTROL traits], die in einer logischen Hierarchie organisiert sind.

## Anwendungsfälle für die Integration {#integration-use-cases}

Eine Anwendungsfallzusammenfassung der Audience Manager-Datenintegrationsmethoden sowie der Vor- und Nachteile jeder einzelnen Methode.

### Echtzeit [!DNL Server-to-Server] Integrationen

<!-- c_int_types_use_cases.xml -->

Bei einer Echtzeit-Datenintegration [!DNL server-to-server] werden Benutzerdaten schnell zwischen den Audience Manager-Servern und einem anderen Targeting-System synchronisiert. In den meisten Fällen erfolgt der Datenaustausch innerhalb von Sekunden oder Minuten, je nach Aktualisierungsrate des Targeting-Systems. Beachten Sie jedoch, dass das Targeting-System dieses Aktualisierungsintervall und nicht den Audience Manager bestimmt. Darüber hinaus kann die Aktualisierungsrate zwischen verschiedenen Systemen variieren. Die Integration von [!UICONTROL server-to-server] in Echtzeit ist der bevorzugte Integrationstyp für den Datenaustausch. Audience Manager verwendet diese Methode immer dann, wenn Targeting-Partner sie unterstützen können.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Damit können Sie Benutzer für Segmente qualifizieren, ohne sie erneut auf der Seite, in einem Videoplayer usw. anzuzeigen. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Reduziert die Anzahl der HTTP-Aufrufe von der Seite. Weniger Aufrufe tragen dazu bei, das Benutzererlebnis zu erhalten. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Hilft mit zeitkritischem Targeting, sodass Sie schnell Aktionen für einen qualifizierten Benutzer durchführen können. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Nützlich beim Wechsel zu einer DSP für Offsite-Targeting. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nachteile:</td>
  <td class="stentry"> Weniger nützlich für Onsite-Targeting, wenn Sie den Benutzer auf derselben Seite oder auf der nächsten Seite ansprechen müssen, je nachdem, ob Sie einen Benutzer für dieses Segment qualifizieren.</td>
 </tr>
</table>

### [!DNL Server-to-Server] Batch-Integrationen

Bei einer Batch-Integration von [!DNL server-to-server] werden Daten gebündelt und in festgelegten Intervallen und nicht nahezu in Echtzeit an andere Systeme gesendet. Die Datenübertragungsintervalle beginnen mit 24 Stunden. Einige Datenanbieter unterstützen nur diesen Integrationstyp. Wir haben jedoch einen allgemeinen Trend von Batch-Integrationen zu Echtzeit-Integrationsmethoden gesehen.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Damit können Sie Benutzer für Segmente qualifizieren, ohne sie erneut auf der Seite, in einem Videoplayer usw. anzuzeigen. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Nützlich für Targeting, das nicht zeitkritisch ist. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nachteile:</td>
  <td class="stentry"> Das Synchronisierungsintervall kann die Zielgruppenbestimmung für die aktuellsten Daten verzögern.</td>
 </tr>
</table>

### Echtzeitaufrufe

Echtzeit-Aufrufe tauschen Daten sofort mit Audience Manager aus, wenn ein Benutzer Ihre Site besucht oder auf der Seite Maßnahmen ergreift. Mit dieser Methode erhalten Targeting-Systeme die aktuellsten Daten zur Segmentqualifizierung und können diese Informationen bei der Entscheidung über einen Inhalt oder einen Anzeigenversand berücksichtigen. Dieser Prozess funktioniert auch mit Publisher-Adservern, bei denen wir qualifizierte Segmente in ein Erstanbieter-Cookie aktualisieren, das als Schlüssel-Wert-Paare in einen Anzeigenaufruf gelesen wird. Derzeit verwendet Audience Manager Echtzeit-Aufrufe zur Integration in [!DNL Adobe Target] und andere Content-Management-Systeme.

<table> 
 <tr>
  <td> <p>Vorteile: </p></td>
  <td> <p> Ermöglicht das Targeting der nächsten Seite, des Inhaltsbereichs oder der Anzeigenimpressionen anhand der neuesten Segmentqualifizierung. </p></td> 
 </tr> 
 <tr>
  <td> <p>Nachteile: </p></td>
  <td> <p>Fügt einen Aufruf an Audience Manager von der Seite hinzu.</p></td>
 </tr> 
</table>


### Pixel-Synchronisation mit Targeting-Systemen

Bei der Pixelsynchronisierung werden Segmente Pixel auf der Seite zugeordnet. Das Pixel löst Daten aus und sendet sie, wenn ein Benutzer sich für ein bestimmtes Segment qualifiziert. Die Pixelsynchronisierung ist ein rudimentärer und unzuverlässiger Datenübertragungsmechanismus. Datenanbieter und -systeme der obersten Ebene verwenden sie selten.

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
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Unzuverlässig für die Datenübertragung. Ein Verlust von 5 % bis 20 % ist normal. </li>
   </ul></td>
 </tr> 
</table>

## Auswählen einer Datenbereitstellungsmethode {#data-delivery-choices}

Beschreibt technische und geschäftliche Gründe für das Senden von Daten über synchrone (Echtzeit) oder asynchrone (Server-zu-Server) Methoden.

<!-- c_int_delivery_choices.xml -->

### Auswahl eines Datenbereitstellungstyps

* **Technische Aspekte:** Die Datenbereitstellung hängt von den technischen Funktionen des Datenpartners ab. Audience Manager können Daten in Echtzeit vom Browser oder durch Batch-Aktualisierungen über Offline-, Server-zu-Server-Kommunikationsprozesse senden/empfangen.
* **Geschäftliche Aspekte:** Die geschäftlichen Gründe für die Auswahl einer Versandmethode oder einer anderen hängen von den technischen Möglichkeiten Ihres Zielpartners und davon ab, wie Sie diese Daten verwenden möchten. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie sofort Maßnahmen in Bezug auf Benutzerdaten ergreifen müssen. Asynchrone Datenübertragungen können nützlich sein, wenn keine sofortigen Maßnahmen erforderlich sind und Sie Zeit haben, tiefere Benutzerprofile für die spätere Verwendung zu erstellen.

## Echtzeit-Datenübertragungsprozess {#real-time-data-transfer-process}

Ein allgemeiner Überblick darüber, wie Audience Manager einen synchronen Datenaustausch mit einem Drittanbieter durchführt.

### Echtzeit-Datenübertragung

<!-- c_int_overview_sync.xml -->

Bei Echtzeit-Datenübertragungen werden Segment-IDs gesendet und empfangen, wenn ein Benutzer Ihre Site besucht oder Maßnahmen ergreift. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie Benutzer sofort qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

### Schritte zur Datenintegration in Echtzeit

Der Echtzeit-Datenintegrationsprozess funktioniert wie folgt:

1. Ein Benutzer besucht die Site eines Kunden, die Audience Manager-Code enthält.
1. Audience Manager lädt einen Iframe und führt einen Aufruf an [!UICONTROL Data Collection Server] ([!DNL DCS]) durch.
1. Der [!DNL DCS] ruft den Drittanbieter-Server (in Echtzeit) auf, um zu überprüfen, ob der Anbieter über Segmentinformationen zum Benutzer verfügt.
1. Der Drittanbieter gibt Segmentinformationen über diesen Benutzer an den Audience Manager zurück.
1. Audience Manager erfasst Segmentinformationen und stellt sie für das Targeting bereit.

![](assets/rt_reduce70.png)

## Batch-Datenübertragungsprozess {#batch-data-transfer-process}

Ein allgemeiner Überblick darüber, wie Audience Manager Daten synchron (in Echtzeit) mit einem Drittanbieter austauschen.

### Batch-Datenintegration

<!-- c_int_overview_async.xml -->

Der Integrationsprozess für Batch-Daten ([!DNL server-to-server]) folgt den meisten im Echtzeit-Datenübertragungsprozess beschriebenen Schritten. Anstatt jedoch sofort Segment-IDs zurückzugeben, werden Benutzerinformationen auf unseren Servern gespeichert und in regelmäßigen Abständen mit einem Drittanbieter-Datenanbieter synchronisiert. Der Prozess der asynchronen Datenübertragung ist nützlich, wenn:

* Eine sofortige Datenübertragung ist nicht erforderlich.
* Erfassen von Daten zum Erstellen eines großen Pools segmentierter Benutzer.
* Sie möchten Datendiskrepanzen und `HTTP` -Aufrufe aus dem Browser reduzieren.

### Schritte zur Batch-Datenintegration

1. Ein Benutzer besucht eine Kunden-Site.
1. Audience Manager und der Drittanbieter für Daten weisen dem Besucher eine eindeutige ID zu (normalerweise mit einem Cookie).
1. Audience Manager ruft den Drittanbieter von Daten auf, um Besucher-IDs zuzuordnen.
1. Bei einer geplanten Anforderung, die normalerweise in einem täglichen Intervall erfolgt, werden Besuchersegmentdaten zwischen Audience Manager und Ihrem Drittanbieter ausgetauscht.

![](assets/s2s_70.png)

Informationen zu den Zeitrahmen für eingehende und ausgehende [!DNL Server-to-Server] ([!UICONTROL S2S]) Dateiübertragungen durch Audience Manager finden Sie unter [Zeitrahmen für die Berichterstellung und Dateiübertragung](../reference/reporting-file-transfer-timeframe.md).

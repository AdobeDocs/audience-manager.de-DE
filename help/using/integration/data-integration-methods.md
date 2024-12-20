---
description: Ein allgemeiner Überblick darüber, wie Audience Manager Informationen mit anderen Datenanbietern und Systemen austauschen.
seo-description: A high-level overview of how Audience Manager exchanges information with other data providers and systems.
seo-title: Data Integration Methods
solution: Audience Manager
title: Datenintegrationsmethoden
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third-party Integration
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# Datenintegrationsmethoden {#data-integration-methods}

Ein allgemeiner Überblick darüber, wie Audience Manager Informationen mit anderen Datenanbietern und Systemen austauschen.

## Unterstützte Datenintegrationsmethoden: Echtzeit und [!DNL Server-to-Server] {#supported-methods}

Die Wahl der richtigen Integrationsmethode hängt von einer Kombination aus geschäftlichen Anforderungen und den technischen Fähigkeiten Ihres Datenpartners ab. Der Audience Manager tauscht Besucherinformationen mit anderen Datenanbietern auf eine der folgenden Arten aus:

* **Echtzeit:** Überträgt Daten sofort, wenn ein Benutzer Ihre Site besucht. Diese Methode wird auch als *`synchronous`*-Integration bezeichnet.
* **Batch ([!DNL Server-to-Server]):** Überträgt Daten zwischen Servern nach einem festgelegten Zeitplan, nachdem ein Besucher die Seite verlassen hat. Diese Methode wird auch als *`out-of-band`*- oder *`asynchronous`*-Integration bezeichnet.

## Voraussetzungen: Erstellen einer Eigenschaftstaxonomie {#prereqs}

Bevor der Integrationsprozess beginnt, denken Sie daran[ in der [!DNL Audience Manager]-Benutzeroberfläche Eigenschaften ](../features/traits/create-onboarded-rule-based-traits.md) eine [Ordnerstruktur](../features/traits/trait-storage.md#create-trait-storage-folder) zu erstellen. Die Taxonomie enthält alle [!UICONTROL traits], die in einer logischen Hierarchie organisiert sind.

## Anwendungsfälle für die Integration {#integration-use-cases}

Eine Zusammenfassung der Anwendungsfälle von Audience Manager-Datenintegrationsmethoden zusammen mit den Vor- und Nachteilen der jeweiligen Methode.

### Integrationen von [!DNL Server-to-Server] in Echtzeit

<!-- c_int_types_use_cases.xml -->

Eine Echtzeit-[!DNL server-to-server] synchronisiert Benutzerdaten schnell zwischen Audience Manager-Servern und einem anderen Targeting-System. In den meisten Fällen erfolgt der Datenaustausch je nach Aktualisierungsrate des Targeting-Systems innerhalb von Sekunden oder Minuten. Beachten Sie jedoch, dass das Zielsystem dieses Aktualisierungsintervall bestimmt und nicht den Audience Manager. Außerdem kann die Aktualisierungsrate zwischen verschiedenen Systemen variieren. Eine Echtzeit-[!UICONTROL server-to-server] ist der bevorzugte Integrationstyp für den Datenaustausch. Diese Methode wird von Audience Manager immer dann verwendet, wenn Zielgruppenbestimmungspartner sie unterstützen können.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Ermöglicht es Ihnen, Benutzer für Segmente zu qualifizieren, ohne sie erneut auf der Seite, in einem Video-Player usw. zu sehen. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Verringert die Anzahl der HTTP-Aufrufe von der Seite. Weniger Aufrufe helfen, das Benutzererlebnis zu erhalten. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Hilft beim zeitabhängigen Targeting, damit Sie schnell Aktionen für einen qualifizierten Benutzer durchführen können. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Nützlich beim Wechsel zu einer DSP für Offsite-Targeting. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nachteile:</td>
  <td class="stentry"> Weniger nützlich für das Targeting auf einer Site, wenn Benutzende auf derselben Seite oder auf der nächsten Seite angesprochen werden müssen, je nachdem, ob eine Benutzerin oder ein Benutzer für dieses Segment qualifiziert wird.</td>
 </tr>
</table>

### [!DNL Server-to-Server] Batch-Integrationen

Bei einer [!DNL server-to-server] Batch-Integration werden Daten gebündelt und in bestimmten Intervallen und nicht nahezu in Echtzeit an andere Systeme gesendet. Die Intervalle für die Datenübertragung beginnen nach 24 Stunden. Einige Datenanbieter unterstützen nur diesen Integrationstyp. Es gab jedoch einen allgemeinen Trend von Batch-Integrationen hin zu Echtzeit-Integrationsmethoden.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Ermöglicht es Ihnen, Benutzer für Segmente zu qualifizieren, ohne sie erneut auf der Seite, in einem Video-Player usw. zu sehen. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Nützlich für die Zielgruppenbestimmung, die nicht zeitkritisch ist. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nachteile:</td>
  <td class="stentry"> Das Synchronisierungsintervall kann die Zielgruppenbestimmung für die aktuellen Daten verzögern.</td>
 </tr>
</table>

### Echtzeit-Aufrufe

Bei Echtzeit-Aufrufen werden Daten sofort mit dem Audience Manager ausgetauscht, wenn ein Benutzer Ihre Site besucht oder eine Aktion auf der Seite durchführt. Mit dieser Methode erhalten Targeting-Systeme die aktuellsten Segmentqualifikationsdaten und können diese Informationen bei einer Entscheidung über die Bereitstellung von Inhalten oder Anzeigen berücksichtigen. Außerdem funktioniert dieser Prozess mit Publisher-Ad-Servern, auf denen wir qualifizierte Segmente zu einem Erstanbieter-Cookie aktualisieren, das als Schlüssel-Wert-Paare in einen Ad-Aufruf gelesen wird. Derzeit nutzt Audience Manager Echtzeit-Aufrufe zur Integration mit [!DNL Adobe Target] und anderen Content-Management-Systemen.

<table> 
 <tr>
  <td> <p>Vorteile: </p></td>
  <td> <p> Ermöglicht das Targeting der nächsten Seite, des nächsten Inhaltsbereichs oder der nächsten Anzeigenimpression anhand der letzten Segmentqualifikation. </p></td> 
 </tr> 
 <tr>
  <td> <p>Nachteile: </p></td>
  <td> <p>Fügt dem Audience Manager einen Seitenaufruf hinzu.</p></td>
 </tr> 
</table>


### Pixel werden mit Zielsystemen synchronisiert

Bei der Pixelsynchronisierung werden Segmente den Pixeln auf der Seite zugeordnet. Das Pixel löst Daten aus und überträgt sie, wenn sich ein Benutzer für ein bestimmtes Segment qualifiziert. Die Pixelsynchronisation ist ein rudimentärer und unzuverlässiger Datenübertragungsmechanismus. Datenanbieter und Systeme der obersten Ebene verwenden sie nur selten.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Vorteile: </p></td>
  <td class="stentry"> <p> Echtzeit-Datenübertragungen. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Nachteile: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Es können viele Client-seitige Aufrufe von der Seite hinzugefügt werden. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Unzuverlässig für die Datenübertragung. 5% bis 20% Verlust ist normal. </li>
   </ul></td>
 </tr> 
</table>

## Auswählen einer Datenbereitstellungsmethode {#data-delivery-choices}

Beschreibt technische und geschäftliche Gründe für das Senden von Daten über synchrone (Echtzeit) oder asynchrone (Server-zu-Server) Methoden.

<!-- c_int_delivery_choices.xml -->

### Datenbereitstellungstyp auswählen

* **Technische Überlegungen:** Die Datenbereitstellung hängt von den technischen Fähigkeiten des Datenpartners ab. Der Audience Manager kann Daten in Echtzeit über den Browser senden/empfangen oder durch Batch-Aktualisierungen über Offline-Server-zu-Server-Kommunikationsprozesse aktualisieren.
* **Geschäftliche Überlegungen** Die geschäftlichen Gründe für die Auswahl der einen oder anderen Versandmethode hängen von den technischen Fähigkeiten Ihres Zielpartners und davon ab, wie Sie diese Daten verwenden möchten. Synchrone Datenübertragungen sind in der Regel dann nützlich, wenn Sie unmittelbar auf Benutzerdaten reagieren müssen. Asynchrone Datenübertragungen können nützlich sein, wenn kein sofortiges Handeln erforderlich ist und wenn Sie Zeit haben, tiefere Benutzerprofile für die spätere Verwendung zu erstellen.

## Echtzeit-Datenübertragungsprozess {#real-time-data-transfer-process}

Ein allgemeiner Überblick darüber, wie Audience Manager einen synchronen Datenaustausch mit einem Drittanbieter durchführt.

### Echtzeit-Datenübertragung

<!-- c_int_overview_sync.xml -->

Bei Echtzeit-Datenübertragungen werden Segment-IDs gesendet und empfangen, wenn ein Benutzer Ihre Site besucht oder eine Aktion auf Ihrer Site ausführt. In der Regel sind synchrone Datenübertragungen nützlich, wenn Sie Benutzende qualifizieren oder segmentieren müssen, während sie durch Ihren Bestand navigieren.

### Schritte zur Echtzeit-Datenintegration

Der Echtzeit-Datenintegrationsprozess funktioniert wie folgt:

1. Ein Besucher besucht die Website eines Kunden, die Audience Manager-Code enthält.
1. Audience Manager lädt einen Iframe und ruft die [!UICONTROL Data Collection Server] ([!DNL DCS]) auf.
1. Der [!DNL DCS] ruft den Drittanbieterserver (in Echtzeit) auf, um zu überprüfen, ob der Anbieter über Segmentinformationen zum Benutzer verfügt.
1. Der Drittanbieter gibt Segmentinformationen zu diesem Benutzer an den Audience Manager zurück.
1. Audience Manager nimmt Segmentinformationen auf und stellt sie für die Zielgruppenbestimmung zur Verfügung.

![](assets/rt_reduce70.png)

## Batch-Datenübertragungsprozess {#batch-data-transfer-process}

Ein allgemeiner Überblick darüber, wie der Audience Manager Daten synchron (in Echtzeit) mit einem Drittanbieter austauscht.

### Batch-Datenintegration

<!-- c_int_overview_async.xml -->

Der Batch-([!DNL server-to-server])-Datenintegrationsprozess folgt den meisten Schritten, die im Echtzeit-Datenübertragungsprozess beschrieben werden. Anstatt jedoch Segment-IDs sofort zurückzugeben, werden Benutzerinformationen auf unseren Servern gespeichert und in regelmäßigen Abständen mit einem Drittanbieter synchronisiert. Der asynchrone Datenübertragungsprozess ist nützlich, wenn:

* Sofortige Datenübertragungen sind nicht erforderlich.
* Erfassen von Daten, um einen großen Pool segmentierter Benutzender zu erstellen.
* Sie möchten Datendiskrepanzen reduzieren und Aufrufe aus dem Browser `HTTP`.

### Schritte zur Batch-Datenintegration

1. Ein Benutzer besucht eine Kunden-Site.
1. Audience Manager und Drittanbieter weisen dem Besucher eine eindeutige ID zu (in der Regel mit einem Cookie).
1. Audience Manager ruft den Drittanbieter-Datenanbieter auf, um Besucher-IDs abzugleichen.
1. Bei einer geplanten Anfrage werden in der Regel in einem täglichen Intervall Besuchersegmentdaten zwischen dem Audience Manager und dem Drittanbieter ausgetauscht.

![](assets/s2s_70.png)

Informationen zu den Zeitrahmen, in denen der Audience Manager eingehende und ausgehende [!DNL Server-to-Server] ([!UICONTROL S2S])-Dateiübertragungen verarbeitet, finden Sie [Richtlinien für Berichte und Dateiübertragungen](../reference/reporting-file-transfer-timeframe.md).

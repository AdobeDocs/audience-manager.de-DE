---
description: Zu den Datenerfassungskomponenten gehören die Datenerfassungsserver, die DIL-API, eingehende Server-zu-Server-Datenübertragungen und Protokolldateien.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: Datenerfassungskomponenten
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 3%

---

# Datenerfassungskomponenten{#data-collection-components}

Zu den Datenerfassungskomponenten gehören die Datenerfassungsserver, die DIL-API, eingehende Server-zu-Server-Datenübertragungen und Protokolldateien.

<!-- 

c_compcollect.xml

 -->

Audience Manager enthält die folgenden Datenerfassungskomponenten:

* [Datenerfassungs-Server (DCS) und Profil-Cache-Server (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Data Integration Library (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Eingehende Server-zu-Server](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Protokolldateien](../../reference/system-components/components-data-collection.md#log-files)

## Datenerfassungsserver (DCS) und Profil-Cache-Server (PCS) {#dcs-pcs}

DCS und PCS arbeiten zusammen und bieten separate Services für die Realisierung von Eigenschaften, Zielgruppensegmentierung und Datenspeicherung.

**[!UICONTROL Data Collection Servers (DCS)]Funktion**

In der [!DNL Audience Manager]:

* Empfängt Eigenschaftsdaten aus einem Ereignisaufruf und wertet sie aus. Dazu gehören Informationen, die für die Echtzeit-Segmentierung verwendet werden, und Daten, die in terminierten Intervallen von Server-zu-Server-Übertragungen übergeben werden.
* Segmentiert Benutzende anhand ihrer realisierten Eigenschaften und der mit [Segment Builder) erstellten ](../../features/segments/segment-builder.md).
* Erstellt und verwaltet Geräte- und authentifizierte Profil-IDs. Dazu gehören Kennungen wie Datenanbieter-IDs, Benutzer-IDs, deklarierte IDs, Integrations-Codes usw.
* Prüft den PC auf zusätzliche Eigenschaften, die ein Benutzer bereits vor einem Echtzeit-Ereignisaufruf erkannt hat. Auf diese Weise kann der DCS Benutzer auf der Grundlage von Echtzeitdaten und historischen Daten qualifizieren.
* Schreibt Protokolldateien und sendet diese zur Speicherung und Verarbeitung an Analysesysteme.

**[!DNL DCS]managt die Nachfrage durch[!UICONTROL Global Server Load Balancing (GSLB)]**

Die [!DNL DCS] ist ein geografisch verteiltes und in Lastenverteilung ausbalanciertes System. Dies bedeutet, [!DNL Audience Manager] je nach geografischem Standort eines Site-Besuchers Anfragen an ein regionales Rechenzentrum senden und von dort weiterleiten können. Diese Strategie trägt dazu bei, die Antwortzeiten zu verbessern, da eine [!DNL DCS] Antwort direkt an ein Rechenzentrum gesendet wird, das Informationen über diesen Besucher enthält. [!UICONTROL GSLB] macht unser System effizient, da relevante Daten auf Servern gespeichert werden, die dem Benutzer am nächsten sind.

>[!IMPORTANT]
>
>Die [!DNL DCS] erkennt nur Web-Traffic, der von Geräten stammt, die IPv4 verwenden.

Bei einem Ereignisaufruf wird der geografische Standort in einem Schlüssel-Wert-Paar erfasst, das in einem größeren JSON-Dateninhalt zurückgegeben wird. Dieses Schlüssel-Wert-Paar ist der `"dcs_region": region ID`.

![](assets/dcs-map.png)

Als Kunde interagieren Sie über unseren Datenerfassungscode indirekt mit dem [!DNL DCS]. Sie können über eine Reihe von APIs auch direkt mit dem [!DNL DCS] arbeiten. Siehe [Methoden und Code der DCS-API (Data Collection Server)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

Das [!UICONTROL PCS] ist eine große Datenbank (im Grunde ein riesiges Server-seitiges Cookie). Sie speichert Daten, die für aktive Benutzer von Server-zu-Server-Übertragungen und den [!DNL DCS] empfangen wurden. [!UICONTROL PCS] Daten bestehen aus Geräte-IDs, authentifizierten Profil-IDs und den zugehörigen Eigenschaften. Wenn der [!DNL DCS] einen Echtzeitaufruf erhält, prüft er die [!UICONTROL PCS] auf andere Eigenschaften, zu denen ein Benutzer gehören oder für die er qualifiziert ist. Wenn eine Eigenschaft zu einem späteren Zeitpunkt zu einem Segment hinzugefügt wird, werden diese Eigenschaften-IDs dem [!UICONTROL PCS] hinzugefügt, und Benutzende können sich automatisch ohne Besuch einer bestimmten Site oder App für dieses Segment qualifizieren. Die [!UICONTROL PCS] hilft, das Verständnis Ihrer Benutzer durch [!DNL Audience Manager] zu vertiefen, da sie Benutzer in Echtzeit oder hinter den Kulissen mit neuen und historischen Eigenschaftsdaten abgleichen und segmentieren kann. Durch dieses Verhalten erhalten Sie ein vollständigeres und genaueres Bild Ihrer Benutzer als durch Echtzeitqualifikationen.

Es gibt keine UI-Steuerelemente, mit denen unsere Kunden direkt mit dem [!UICONTROL PCS] arbeiten können. Der Kundenzugriff auf den [!UICONTROL PCS] erfolgt indirekt über seine Rolle als Datenspeicher und Datenübertragungen. Die [!UICONTROL PCS] läuft auf Apache Cassandra.

**Löschen inaktiver IDs aus der[!UICONTROL PCS]**

Wie bereits erwähnt, speichert die [!UICONTROL PCS] Eigenschaften-IDs für aktive Benutzer. Ein aktiver Benutzer ist jeder Benutzer, der von den [Edge-Daten-Servern](../../reference/system-components/components-edge.md) in den letzten 14 Tagen von einer beliebigen Domain aus gesehen wurde. Diese Aufrufe der [!UICONTROL PCS] halten eine Benutzerin oder einen Benutzer in einem aktiven Status:

* [!DNL /event] Aufrufe
* [!DNL /ibs] Aufrufe (ID-Synchronisierung)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Der [!UICONTROL PCS] leert Eigenschaften, wenn sie 17 Tage lang inaktiv sind. Diese Eigenschaften gehen jedoch nicht verloren. Sie werden in Hadoop aufbewahrt. Wenn der/die Benutzende zu einem anderen Zeitpunkt erneut angezeigt wird, überträgt Hadoop alle seine/ihre Eigenschaften zurück an die [!UICONTROL PCS], in der Regel innerhalb eines Zeitraums von 24 Stunden.

**Andere [!UICONTROL DCS/PCS]: Datenschutz-Opt-out**

Diese Server-Systeme behandeln Datenschutz- und Benutzer-Opt-out-Anfragen. Benutzer-Cookie-Informationen werden nicht in der Protokolldatei erfasst, wenn ein Benutzer die Datenerfassung abgelehnt hat. Weitere Informationen zu unseren Datenschutzrichtlinien finden Sie im [Adobe Privacy Center](https://www.adobe.com/de/privacy/advertising-services.html).

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] ist der Code, den Sie zur Datenerfassung auf der Seite platzieren. Weitere Informationen zu verfügbaren Services und [ finden Sie in der ](../../dil/dil-overview.md)DIL-API.

## Eingehender Server-zu-Server {#inbound-outbound-server}

Hierbei handelt es sich um Systeme, die Daten empfangen, die von verschiedenen Server-zu-Server-Integrationen mit unseren Kunden gesendet werden. Weitere Informationen finden Sie in [ Dokumentation unter ](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) von Zielgruppendaten .

## Protokolldateien {#log-files}

Der [!UICONTROL PCS] erstellt Daten und schreibt sie in die Protokolldateien. Diese werden zur Verarbeitung, Berichterstellung und Speicherung an andere Datenbanksysteme gesendet.

>[!MORELIKETHIS]
>
>* [Adobe Datenschutzcenter](https://www.adobe.com/de/privacy.html)

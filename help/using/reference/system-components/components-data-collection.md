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
* [ Eingehender Server-zu-Server](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Protokolldateien](../../reference/system-components/components-data-collection.md#log-files)

## Datenerfassungs-Server (DCS) und Profil-Cache-Server (PCS) {#dcs-pcs}

DCS und PCS arbeiten zusammen und bieten getrennt Dienste im Zusammenhang mit der Realisierung von Eigenschaften, der Zielgruppensegmentierung und der Datenspeicherung an.

**[!UICONTROL Data Collection Servers (DCS)]Funktion**

In &quot;[!DNL Audience Manager]&quot;: Der DES:

* Erhält und wertet Eigenschaftsdaten aus einem Ereignisaufruf. Dazu gehören Informationen, die für die Echtzeit-Segmentierung verwendet werden, sowie Daten, die in terminierten Intervallen durch Server-zu-Server-Übertragungen übergeben werden.
* Segmentiert Benutzer anhand ihrer realisierten Eigenschaften und der mit [Segment Builder](../../features/segments/segment-builder.md) erstellten Qualifizierungsregeln.
* Erstellt und verwaltet Geräte-IDs und authentifizierte Profil-IDs. Dazu gehören Kennungen wie Datenanbieter-IDs, Benutzer-IDs, deklarierte IDs, Integrationscodes usw.
* Prüft das PCS auf zusätzliche Eigenschaften, die ein Benutzer bereits vor einem Echtzeit-Ereignisaufruf realisiert hat. Dadurch kann der DES Benutzer anhand von Echtzeitdaten und historischen Daten qualifizieren.
* Schreibt Protokolldateien und sendet diese zur Speicherung und Verarbeitung an Analysesysteme.

**[!DNL DCS]Verwaltung der Nachfrage durch[!UICONTROL Global Server Load Balancing (GSLB)]**

Die [!DNL DCS] ist ein geografisch verteiltes und lastausgeglichenes System. Das bedeutet, dass [!DNL Audience Manager] Anfragen an und von einem regionalen Rechenzentrum basierend auf dem geografischen Standort eines Site-Besuchers weiterleiten kann. Diese Strategie trägt dazu bei, die Reaktionszeiten zu verbessern, da eine [!DNL DCS] -Antwort direkt an ein Rechenzentrum gesendet wird, das Informationen zu diesem Besucher enthält. [!UICONTROL GSLB] macht unser System effizient, da relevante Daten in Servern zwischengespeichert werden, die dem Benutzer am nächsten sind.

>[!IMPORTANT]
>
>Der [!DNL DCS] erkennt nur Web-Traffic von Geräten, die IPv4 verwenden.

Bei einem Ereignisaufruf wird der geografische Standort in einem Schlüssel-Wert-Paar erfasst, das in einem größeren Textkörper von JSON-Daten zurückgegeben wird. Dieses Schlüssel-Wert-Paar ist der Parameter `"dcs_region": region ID` .

![](assets/dcs-map.png)

Als Kunde interagieren Sie indirekt über unseren Datenerfassungscode mit dem [!DNL DCS]. Sie können auch direkt mit dem [!DNL DCS] über eine Reihe von APIs arbeiten. Siehe [API-Methoden und Code für den Datenerfassungsserver (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

Die [!UICONTROL PCS] ist eine große Datenbank (im Grunde ein riesiges serverseitiges Cookie). Sie speichert Daten, die für aktive Benutzer von Server-zu-Server-Übertragungen und den [!DNL DCS] empfangen wurden. [!UICONTROL PCS] -Daten bestehen aus Geräte-IDs, authentifizierten Profil-IDs und den zugehörigen Eigenschaften. Wenn der [!DNL DCS] einen Echtzeitaufruf erhält, wird der [!UICONTROL PCS] auf andere Eigenschaften überprüft, zu denen ein Benutzer gehören kann oder für die er sich qualifiziert. Wenn einem Segment zu einem späteren Zeitpunkt eine Eigenschaft hinzugefügt wird, werden diese Eigenschafts-IDs dem [!UICONTROL PCS] hinzugefügt und Benutzer können sich automatisch für dieses Segment qualifizieren, ohne eine bestimmte Site oder App zu besuchen. Die [!UICONTROL PCS] hilft [!DNL Audience Manager] dabei, das Verständnis Ihrer Benutzer zu vertiefen, da sie Benutzer in Echtzeit oder hinter den Kulissen mit neuen und historischen Eigenschaftsdaten abgleichen und segmentieren kann. Durch dieses Verhalten erhalten Sie ein vollständiges und genaueres Bild Ihrer Benutzer als durch Echtzeitqualifikationen allein.

Es gibt keine Steuerelemente der Benutzeroberfläche, die unseren Kunden die direkte Arbeit mit dem [!UICONTROL PCS] ermöglichen. Der Kundenzugriff auf die [!UICONTROL PCS] ist indirekt über ihre Rolle als Datenspeicher und Datenübertragungen. Der [!UICONTROL PCS] wird auf Apache Cassandra ausgeführt.

**Löschen inaktiver IDs aus dem[!UICONTROL PCS]**

Wie bereits erwähnt, speichert [!UICONTROL PCS] Eigenschaften-IDs für aktive Benutzer. Ein aktiver Benutzer ist ein Benutzer, der von den [Edge-Datenservern](../../reference/system-components/components-edge.md) aus einer beliebigen Domäne in den letzten 14 Tagen gesehen wurde. Diese Aufrufe an die [!UICONTROL PCS] halten einen Benutzer in einem aktiven Status:

* [!DNL /event] Aufrufe
* [!DNL /ibs] -Aufrufe (ID-Synchronisierungen)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Die [!UICONTROL PCS] leert Eigenschaften, wenn sie 17 Tage lang inaktiv sind. Diese Eigenschaften gehen jedoch nicht verloren. Sie sind im Hadoop gespeichert. Wenn der Benutzer zu einem anderen Zeitpunkt erneut angezeigt wird, sendet Hadoop alle seine Eigenschaften zurück auf den [!UICONTROL PCS], normalerweise innerhalb eines Zeitraums von 24 Stunden.

**Andere [!UICONTROL DCS/PCS] Prozesse: Datenschutz-Opt-out**

Diese Serversysteme handhaben Datenschutz- und Benutzerabmeldeanfragen. Benutzer-Cookie-Informationen werden nicht in der Protokolldatei erfasst, wenn ein Benutzer sich gegen die Datenerfassung entschieden hat. Weitere Informationen zu unseren Datenschutzrichtlinien finden Sie im [Adobe Privacy Center](https://www.adobe.com/de/privacy/advertising-services.html).

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] ist Code, den Sie zur Datenerfassung auf der Seite platzieren. Weitere Informationen zu den verfügbaren Diensten und Methoden finden Sie in der [DIL-API](../../dil/dil-overview.md) .

## Eingehender Server-zu-Server {#inbound-outbound-server}

Dies sind Systeme, die Daten empfangen, die von verschiedenen Server-zu-Server-Integrationen mit unseren Kunden gesendet werden. Weitere Informationen finden Sie in der Dokumentation zu [Senden von Zielgruppendaten](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) .

## Protokolldateien {#log-files}

Der [!UICONTROL PCS] erstellt und schreibt Daten in die Protokolldateien. Diese werden zur Verarbeitung, Berichterstellung und Speicherung an andere Datenbanksysteme gesendet.

>[!MORELIKETHIS]
>
>* [Adobe Datenschutzcenter](https://www.adobe.com/de/privacy.html)

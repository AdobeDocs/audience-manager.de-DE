---
description: Zu den Datenerfassungskomponenten gehören die Datenerfassungsserver, die DIL-API, eingehende Server-zu-Server-Datenübertragungen und Protokolldateien.
seo-description: Zu den Datenerfassungskomponenten gehören die Datenerfassungsserver, die DIL-API, eingehende Server-zu-Server-Datenübertragungen und Protokolldateien.
seo-title: Datenerfassungskomponenten
solution: Audience Manager
title: Datenerfassungskomponenten
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 1%

---


# Datenerfassungskomponenten{#data-collection-components}

Zu den Datenerfassungskomponenten gehören die Datenerfassungsserver, die DIL-API, eingehende Server-zu-Server-Datenübertragungen und Protokolldateien.

<!-- 

c_compcollect.xml

 -->

Audience Manager enthält die folgenden Datenerfassungskomponenten:

* [Datenerfassungsserver (DCS) und Profil-Cache-Server (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Data Integration Library (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Inbound Server-to-Server](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Protokolldateien](../../reference/system-components/components-data-collection.md#log-files)

## Datenerfassungsserver (DCS) und Profil-Cache-Server (PCS) {#dcs-pcs}

DCS und PCS arbeiten zusammen und bieten separate Dienste zur Realisierung von Eigenschaften, zur Segmentierung von Audiencen und zur Datenspeicherung von Daten.

**[!UICONTROL Data Collection Servers (DCS)]Funktion **

In [!DNL Audience Manager]dem DCS:

* Erhält und wertet Eigenschaftendaten aus einem Ereignis-Aufruf. Dies umfasst Informationen, die für die Echtzeit-Segmentierung verwendet werden, sowie Daten, die in regelmäßigen Abständen von Server zu Server-Transfers übergeben werden.
* Segmentiert Benutzer anhand ihrer realisierten Eigenschaften und der von Ihnen mit dem [Segmentaufbau](../../features/segments/segment-builder.md)erstellten Qualifizierungsregeln.
* Erstellt und verwaltet Geräte-IDs und authentifizierte Profil-IDs. Dazu gehören Bezeichner wie Datenanbieter-IDs, Benutzer-IDs, deklarierte IDs, Integrationscodes usw.
* Prüft das PCS auf zusätzliche Eigenschaften, die ein Anwender bereits vor einem Echtzeit-Ereignis-Aufruf realisiert hat. Dadurch kann der DCS Benutzer anhand von Echtzeitdaten und Verlaufsdaten qualifizieren.
* Schreibt Protokolldateien und sendet diese zur Datenspeicherung und Verarbeitung an Analysesysteme.

**[!DNL DCS]Verwaltung der Nachfrage durch[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!DNL DCS] is a geographically distributed and load-balanced system. Dies bedeutet, dass Anfragen von und zu einem regionalen Rechenzentrum geleitet werden [!DNL Audience Manager] können, basierend auf dem geografischen Standort eines Site-Besuchers. Diese Strategie hilft, die Reaktionszeiten zu verbessern, da eine [!DNL DCS] Antwort direkt an ein Rechenzentrum mit Informationen zu diesem Besucher weitergeleitet wird. [!UICONTROL GSLB] macht unser System effizient, weil relevante Daten in Servern zwischengespeichert werden, die dem Benutzer am nächsten kommen.

>[!IMPORTANT]
>
>Der Webverkehr wird [!DNL DCS] nur von Geräten erkannt, die IPv4 verwenden.

Bei einem Ereignis-Aufruf wird der geografische Standort in einem Schlüssel-Wert-Paar erfasst, das in einem größeren Textkörper von JSON-Daten zurückgegeben wird. Dieses Schlüssel-Wert-Paar ist der `"dcs_region": region ID` Parameter.

![](assets/dcs-map.png)

Als Kunde wenden Sie sich über unseren Datenerfassungscode [!DNL DCS] indirekt an den Kunden. Sie können auch direkt mit der [!DNL DCS] über eine Reihe von APIs arbeiten. Siehe API-Methoden und Code für [Datenerfassungsserver (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

Das [!UICONTROL PCS] ist eine große Datenbank (im Grunde ein riesiges serverseitiges Cookie). Es speichert Daten, die von Server-zu-Server-Transfers und der [!DNL DCS]Variablen für aktive Benutzer empfangen wurden. [!UICONTROL PCS] Daten bestehen aus Geräte-IDs, authentifizierten Profil-IDs und den zugehörigen Eigenschaften. Wenn der Benutzer einen Echtzeitaufruf [!DNL DCS] [!UICONTROL PCS] erhält, prüft er, ob andere Eigenschaften vorliegen, denen ein Benutzer angehören kann oder für die er sich qualifiziert. Wenn zu einem Segment zu einem späteren Zeitpunkt eine Eigenschaft hinzugefügt wird, werden diese Eigenschaften-IDs dem Segment hinzugefügt [!UICONTROL PCS] und Benutzer können sich automatisch für dieses Segment qualifizieren, ohne eine bestimmte Site oder App zu besuchen. Das [!UICONTROL PCS] [!DNL Audience Manager]hilft, das Verständnis Ihrer Benutzer zu vertiefen, da es Benutzer in Echtzeit oder hinter den Kulissen mit neuen und historischen Eigenschaftsdaten abgleichen und segmentieren kann. Mit diesem Verhalten erhalten Sie ein vollständiges und genaueres Bild Ihrer Benutzer als mit der Qualifikation in Echtzeit.

Es gibt keine Steuerelemente für die Benutzeroberfläche, mit denen unsere Kunden direkt mit dem [!UICONTROL PCS]System arbeiten können. Der Zugriff des Kunden auf die [!UICONTROL PCS] Website erfolgt indirekt über seine Rolle als Datenspeicher und Datenübertragung. Der [!UICONTROL PCS] läuft auf dem Apache Cassandra.

**Entfernen inaktiver IDs aus der[!UICONTROL PCS]**

Wie bereits erwähnt, speichert die [!UICONTROL PCS] Eigenschaften-IDs für aktive Benutzer. Ein aktiver Benutzer ist jeder Benutzer, der in den letzten 14 Tagen von den [Edge-Datenservern](../../reference/system-components/components-edge.md) aus einer beliebigen Domäne gesehen wurde. Diese Aufrufe zur [!UICONTROL PCS] aktiven Verwendung eines Benutzers:

* [!DNL /event] aufrufen
* [!DNL /ibs] Aufrufe (ID-Syncs)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Die [!UICONTROL PCS] Flusheigenschaften werden angezeigt, wenn sie 17 Tage lang inaktiv sind. Diese Eigenschaften gehen jedoch nicht verloren. Sie werden in Hadoop gespeichert. Wenn der Benutzer zu einem anderen Zeitpunkt erneut angezeigt wird, schiebt Hadoop alle Eigenschaften zurück in die [!UICONTROL PCS]Regel innerhalb von 24 Stunden.

**Andere[!UICONTROL DCS/PCS]Prozesse: Datenschutzabmeldung**

Diese Serversysteme bearbeiten Datenschutzanforderungen und Abmeldeanforderungen für Benutzer. Benutzercookie-Informationen werden nicht in der Protokolldatei erfasst, wenn ein Benutzer sich aus der Datenerfassung ausgeschlossen hat. Weitere Informationen zu unseren Datenschutzrichtlinien finden Sie im [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## Data Integration Library (DIL){#dil} 

[!UICONTROL DIL] ist Code, den Sie für die Datenerfassung auf der Seite platzieren. Weitere Informationen zu verfügbaren Diensten und Methoden finden Sie in der [DIL-API](../../dil/dil-overview.md) .

## Inbound Server-to-Server {#inbound-outbound-server}

Dies sind Systeme, die Daten empfangen, die von verschiedenen Server-zu-Server-Integrationen mit unseren Clients gesendet werden. Weitere Informationen finden Sie in der Dokumentation zum [Senden von Audiencen](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) .

## Log Files {#log-files}

Das [!UICONTROL PCS] erstellt Daten und schreibt sie in die Protokolldateien. Diese werden zur Verarbeitung, zum Berichte und zur Datenspeicherung an andere Datenbanksysteme gesendet.

>[!MORELIKETHIS]
>
>* [Adobe Datenschutzcenter](https://www.adobe.com/privacy.html)


---
description: Zu den Datenerfassungskomponenten gehören die Datenerfassungsserver, die DIL-API, eingehende Server-zu-Server-Datenübertragungen und Protokolldateien.
seo-description: Zu den Datenerfassungskomponenten gehören die Datenerfassungsserver, die DIL-API, eingehende Server-zu-Server-Datenübertragungen und Protokolldateien.
seo-title: Datenerfassungskomponenten
solution: Audience Manager
title: Datenerfassungskomponenten
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 6%

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

**[!UICONTROL Data Collection Servers (DCS)]Funktion**

In [!DNL Audience Manager] wird der DES:

* Erhält und wertet Eigenschaftendaten aus einem Ereignis-Aufruf. Dies umfasst Informationen, die für die Echtzeit-Segmentierung verwendet werden, sowie Daten, die in regelmäßigen Abständen von Server zu Server-Transfers übergeben werden.
* Segmentiert Benutzer basierend auf ihren realisierten Eigenschaften und den Qualifizierungsregeln, die Sie mit [Segmentaufbau](../../features/segments/segment-builder.md) erstellen.
* Erstellt und verwaltet Geräte-IDs und authentifizierte Profil-IDs. Dazu gehören Bezeichner wie Datenanbieter-IDs, Benutzer-IDs, deklarierte IDs, Integrationscodes usw.
* Prüft das PCS auf zusätzliche Eigenschaften, die ein Anwender bereits vor einem Echtzeit-Ereignis-Aufruf realisiert hat. Dadurch kann der DCS Benutzer anhand von Echtzeitdaten und Verlaufsdaten qualifizieren.
* Schreibt Protokolldateien und sendet diese zur Datenspeicherung und Verarbeitung an Analysesysteme.

**[!DNL DCS]Verwaltung der Nachfrage durch[!UICONTROL Global Server Load Balancing (GSLB)]**

Das [!DNL DCS] ist ein geografisch verteiltes und lastausbalanciertes System. Das bedeutet, dass [!DNL Audience Manager] Anfragen von und zu einem regionalen Rechenzentrum leiten kann, basierend auf dem geografischen Standort eines Site-Besuchers. Diese Strategie hilft, die Reaktionszeiten zu verbessern, da eine [!DNL DCS]-Antwort direkt an ein Rechenzentrum mit Informationen zu diesem Besucher weitergeleitet wird. [!UICONTROL GSLB] macht unser System effizient, weil relevante Daten in Servern zwischengespeichert werden, die dem Benutzer am nächsten kommen.

>[!IMPORTANT]
>
>[!DNL DCS] erkennt nur Web-Traffic, der von Geräten stammt, die IPv4 verwenden.

Bei einem Ereignis-Aufruf wird der geografische Standort in einem Schlüssel-Wert-Paar erfasst, das in einem größeren Textkörper von JSON-Daten zurückgegeben wird. Dieses Schlüssel-Wert-Paar ist der Parameter `"dcs_region": region ID`.

![](assets/dcs-map.png)

Als Kunde wenden Sie sich indirekt über unseren Datenerfassungscode mit dem [!DNL DCS] an. Sie können auch direkt mit dem [!DNL DCS] über eine Reihe von APIs arbeiten. Siehe API-Methoden und Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md) für Datenerfassungsserver (DCS).[

**[!UICONTROL Profile Cache Servers (PCS)]**

Das [!UICONTROL PCS] ist eine große Datenbank (im Grunde ein riesiges serverseitiges Cookie). Sie speichert Daten, die für aktive Benutzer von Server-zu-Server-Übertragungen und den [!DNL DCS] empfangen wurden. [!UICONTROL PCS]-Daten bestehen aus Geräte-IDs, authentifizierten Profil-IDs und den zugehörigen Eigenschaften. Wenn das [!DNL DCS] einen Echtzeitaufruf erhält, prüft es das [!UICONTROL PCS] auf andere Eigenschaften, zu denen ein Benutzer gehören kann oder für die er sich qualifiziert. Wenn zu einem Segment zu einem späteren Zeitpunkt eine Eigenschaft hinzugefügt wird, werden diese Eigenschaften-IDs dem [!UICONTROL PCS] hinzugefügt und Benutzer können sich automatisch für dieses Segment qualifizieren, ohne eine bestimmte Site oder App zu besuchen. Das [!UICONTROL PCS] hilft Ihnen, das Verständnis Ihrer Benutzer zu vertiefen, da es Benutzer in Echtzeit oder hinter den Kulissen mit neuen und historischen Eigenschaftsdaten abgleichen und segmentieren kann. [!DNL Audience Manager] Mit diesem Verhalten erhalten Sie ein vollständiges und genaueres Bild Ihrer Benutzer als mit der Qualifikation in Echtzeit.

Es gibt keine Steuerelemente der Benutzeroberfläche, mit denen unsere Kunden direkt mit dem [!UICONTROL PCS] arbeiten können. Der Zugriff des Kunden auf das [!UICONTROL PCS] ist indirekt, durch seine Rolle als Datenspeicher und Datenübertragung. Das [!UICONTROL PCS] läuft auf Apache Cassandra.

**Entfernen inaktiver IDs aus der[!UICONTROL PCS]**

Wie oben angegeben speichert das [!UICONTROL PCS] Eigenschaften-IDs für aktive Benutzer. Ein aktiver Benutzer ist jeder Benutzer, der in den letzten 14 Tagen von den [Edge-Datenservern](../../reference/system-components/components-edge.md) aus einer beliebigen Domäne gesehen wurde. Diese Aufrufe an das [!UICONTROL PCS] halten einen Benutzer in einem aktiven Status:

* [!DNL /event] aufrufen
* [!DNL /ibs] Aufrufe (ID-Syncs)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Die Eigenschaften von [!UICONTROL PCS] werden entfernt, wenn sie 17 Tage lang inaktiv sind. Diese Eigenschaften gehen jedoch nicht verloren. Sie sind im Hadoop gelagert. Wenn der Benutzer zu einem anderen Zeitpunkt erneut angezeigt wird, verschiebt Hadoop alle Eigenschaften zurück auf das [!UICONTROL PCS], normalerweise innerhalb von 24 Stunden.

**Andere  [!UICONTROL DCS/PCS] Prozesse: Datenschutzabmeldung**

Diese Serversysteme bearbeiten Datenschutzanforderungen und Abmeldeanforderungen für Benutzer. Benutzercookie-Informationen werden nicht in der Protokolldatei erfasst, wenn ein Benutzer sich aus der Datenerfassung ausgeschlossen hat. Weitere Informationen zu unseren Datenschutzrichtlinien finden Sie im [Datenschutzzentrum für Adoben](https://www.adobe.com/de/privacy/advertising-services.html).

## Data Integration Library (DIL)- {#dil}

[!UICONTROL DIL] ist Code, den Sie für die Datenerfassung auf der Seite platzieren. Weitere Informationen zu verfügbaren Diensten und Methoden finden Sie unter [DIL API](../../dil/dil-overview.md).

## Inbound Server-to-Server {#inbound-outbound-server}

Dies sind Systeme, die Daten empfangen, die von verschiedenen Server-zu-Server-Integrationen mit unseren Clients gesendet werden. Weitere Informationen finden Sie in der Dokumentation zu [Senden von Audiencen](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md).

## Protokolldateien {#log-files}

Das [!UICONTROL PCS] erstellt und schreibt Daten in die Protokolldateien. Diese werden zur Verarbeitung, zum Berichte und zur Datenspeicherung an andere Datenbanksysteme gesendet.

>[!MORELIKETHIS]
>
>* [Datenschutzzentrum von Adobe](https://www.adobe.com/de/privacy.html)


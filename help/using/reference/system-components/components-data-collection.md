---
description: Zu den Datenerfassungskomponenten gehören die Datenerfassungsserver, die DIL-API, eingehende Server-zu-Server-Datenübertragungen und Protokolldateien.
seo-description: Zu den Datenerfassungskomponenten gehören die Datenerfassungsserver, die DIL-API, eingehende Server-zu-Server-Datenübertragungen und Protokolldateien.
seo-title: Datenerfassungskomponenten
solution: Audience Manager
title: Datenerfassungskomponenten
uuid: 51 bb 1719-5 ff 2-4 bc 7-8 eb 1-98795 e 05 d 08 f
translation-type: tm+mt
source-git-commit: 0b9da38fd8b999637bdf6c3fe6af8aa2426eb6ae

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

Das DCS und die PCS arbeiten zusammen und bieten separat services in Bezug auf Merkmalisierung, Zielgruppensegmentierung und Datenspeicherung.

**[!UICONTROL Data Collection Servers (DCS)]Funktion**

In [!DNL Audience Manager], das DCS:

* Empfängt und wertet Eigenschaftsdaten aus einem Ereignisaufruf aus. Dazu gehören Informationen zur Echtzeitsegmentierung und Daten, die in geplanten Intervallen von Server-zu-Server-Übertragungen übermittelt werden.
* Segmentiert Benutzer auf Grundlage ihrer neu gestalteten Eigenschaften und der Qualifizierungsregeln, die Sie mit [dem Segmentaufbau erstellen](../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74).
* Erstellt und verwaltet Geräte-IDs und authentifizierte Profil-IDs. Dazu gehören ids wie Datenanbieter-IDs, Benutzer-IDs, deklarierte IDs, Integrationscodes usw.
* Überprüft die PCS auf zusätzliche Eigenschaften, die ein Benutzer bereits vor einem Echtzeit-Ereignisaufruf implementiert hat. Dadurch können die Benutzer Benutzer anhand von Echtzeitdaten und historischen Daten qualifizieren.
* Schreibt Protokolldateien und sendet diese an Analytics-Systeme zum Speichern und Verarbeiten.

**[!UICONTROL DCS]Verwaltet Nachfrage durch[!UICONTROL Global Server Load Balancing (GSLB)]**

Das ist [!UICONTROL DCS] ein geografisch verteilte und ausgeglichenes System. Dies bedeutet [!DNL Audience Manager] , dass direkte Anforderungen an und von einem regionalen Rechenzentrum abhängig vom geografischen Standort eines Site-Besuchers gesendet werden können. Diese Strategie hilft bei der Verbesserung der Antwortzeiten, da eine [!UICONTROL DCS] Antwort direkt an ein Rechenzentrum gesendet wird, das Informationen über diesen Besucher enthält. [!UICONTROL GSLB] macht unser System effizient, da relevante Daten auf Servern zwischengespeichert werden, die dem Benutzer am nächsten gelegen sind.

>[!IMPORTANT]
>
>Der Webverkehr wird [!UICONTROL DCS] nur von Geräten erkannt, die ipv 4 verwenden.

Bei einem Ereignisaufruf wird der geografische Standort in einem Schlüssel-Wert-Paar erfasst, das in einer größeren JSON-Datei zurückgegeben wird. Dieses Schlüssel-Wert-Paar ist der `"dcs_region": region ID` Parameter.

![](assets/dcs-map.png)

Als Kunde treten Sie indirekt [!UICONTROL DCS] über unseren Datenerfassungscode auf. Sie können auch direkt mit einer [!UICONTROL DCS] Reihe von apis arbeiten. Siehe [Datenerfassungsserver-API-Methoden und -code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

Die ist [!UICONTROL PCS] eine große Datenbank (im Allgemeinen ein riesiges serverseitiges Cookie). Speichert Daten, die für aktive Benutzer von Server-zu-Server-Übertragungen und vom Server [!UICONTROL DCS]empfangen wurden. [!UICONTROL PCS] Daten bestehen aus Geräte-IDs, authentifizierten Profil-IDs und den zugehörigen Eigenschaften. Wenn ein [!UICONTROL DCS] Echtzeitanruf erfolgt, prüft er, [!UICONTROL PCS] ob der Benutzer zu anderen Eigenschaften gehört oder damit berechtigt ist. Wenn einem Segment zu einem späteren Zeitpunkt eine Eigenschaft hinzugefügt wird, werden diese IDs dem Benutzer [!UICONTROL PCS] hinzugefügt und die Benutzer können sich automatisch für dieses Segment qualifizieren, ohne dass eine bestimmte Site oder App aufgerufen wird. Mit der Hilfe [!UICONTROL PCS] können Sie [!DNL Audience Manager]das Verständnis Ihrer Benutzer vertiefen, da sie Benutzer in Echtzeit oder hinter den Szenen mit neuen und historischen Eigenschaftendaten vergleichen und segmentieren können. Durch dieses Verhalten erhalten Sie ein vollständigeres und genaueres Bild Ihrer Benutzer als nur aus Echtzeitnachweisen.

Es gibt keine Steuerelemente für die Benutzeroberfläche, mit denen unsere Kunden direkt mit denen [!UICONTROL PCS]arbeiten können. Der Kundenzugriff auf die Variable [!UICONTROL PCS] ist indirekt, über seine Rolle als Datenspeicher und Datenübertragungen. Die [!UICONTROL PCS] Ausführung auf Apache Cassandra.

**Löschen inaktiver IDs aus der[!UICONTROL PCS]**

Wie bereits erwähnt, speichert die Eigenschaft [!UICONTROL PCS] &quot;Eigenschaften&quot; IDs für aktive Benutzer. Ein aktiver Benutzer ist ein Benutzer, der in den letzten 14 Tagen von den [Edge-Datenservern](../../reference/system-components/components-edge.md) aus einer beliebigen Domäne gesehen wurde. Diese Aufrufe ermöglichen [!UICONTROL PCS] den Benutzer in einem aktiven Zustand:

* [!DNL /event] Aufrufe
* [!DNL /ibs] Aufrufe (ID-Synchronisierungen)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Die [!UICONTROL PCS] Leeren Eigenschaften, wenn sie 17 Tage inaktiv sind. Diese Eigenschaften gehen jedoch nicht verloren. Sie werden in Hadoop gespeichert. Wenn der Benutzer zu einem anderen Zeitpunkt erneut angezeigt wird, führt Hadoop alle Eigenschaften zurück, [!UICONTROL PCS]die normalerweise innerhalb eines Zeitraums von 24 Stunden liegen.

**Andere[!UICONTROL DCS/PCS]Prozesse: Datenschutzausschluss**

Diese Serversysteme behandeln die Anforderungen für Datenschutz und Benutzer. Benutzercookie-Informationen werden nicht in der Protokolldatei erfasst, wenn ein Benutzer die Datenerfassung abschließt. Weitere Informationen zu unseren Datenschutzrichtlinien finden Sie im [Datenschutzzentrum von Adobe](https://www.adobe.com/privacy/advertising-services.html).

## Data Integration Library (DIL){#dil} 

[!UICONTROL DIL] ist Code, den Sie zur Datenerfassung auf der Seite platzieren. Weitere Informationen zu den verfügbaren Diensten und Methoden finden Sie in der [DIL-API](../../dil/dil-overview.md) .

## Inbound Server-to-Server {#inbound-outbound-server}

Dies sind Systeme, die Daten empfangen, die von verschiedenen Server-zu-Server-Integrationen an unsere Kunden gesendet werden. Weitere Informationen finden Sie in der Dokumentation zum [Senden von Zielgruppendaten](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) .

## Protokolldateien {#log-files}

Erstellt [!UICONTROL PCS] und schreibt Daten in die Protokolldateien. Diese werden an andere Datenbanksysteme zur Verarbeitung, Berichterstellung und Speicherung gesendet.

>[!MORE_ LIKE_ THIS]
>
>* [Adobe Datenschutzcenter](https://www.adobe.com/privacy.html)


---
description: Zu den Datenaktionskomponenten gehören Kundendaten-Feeds, der Datenerfassungsserver, SFTP/S3/HTTP-Publisher, IRIS und der Profil-Cache-Server.
seo-description: Data action components include Customer Data Feeds, the Data Collection Server, SFTP/S3/HTTP publishers, IRIS, and the Profile Cache Server.
seo-title: Data Action Components
solution: Audience Manager
title: Datenaktionskomponenten
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: System Components
exl-id: 8065c19f-1930-4164-a952-1686aa5cb622
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# Datenaktionskomponenten{#data-action-components}

Zu den Datenaktionskomponenten gehören Kundendaten-Feeds, der Datenerfassungsserver, SFTP/S3/HTTP-Publisher, IRIS und der Profil-Cache-Server.

<!-- 

c_compact.xml

 -->

Aktionskomponenten sind Systeme und Prozesse, mit denen Sie Daten in und aus [!DNL Audience Manager] verschieben und (aus Mangel an einer besseren Wortgruppe) Dinge damit ausführen können. Zu diesen [!DNL Audience Manager] -Komponenten gehören:

## Kundendaten-Feeds (CDF) {#cdf}

[!UICONTROL CDF] sind Dateien, die stündlich an Kunden gesendet werden. Diese enthalten Benutzer-IDs zusammen mit zugehörigen Segment-IDs, Eigenschafts-IDs und anderen Daten. Weitere Informationen finden Sie unter [Übersicht über den Kundendaten-Feed](../../features/cdf-files.md).

## Datenerfassungs-Server (DCS) {#dcs}

Siehe [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Die [!UICONTROL SFTP/S3] -Herausgeber erhalten synchronisierte ID-Daten von der [!UICONTROL Outbound Feed Converter]. Wenn diese Dateien bereit sind, sendet der [!UICONTROL SFTP/S3 publishers] diese Daten an ein vom Client angegebenes Ziel. Diese Dateien enthalten synchronisierte ID-Daten mit einer 1:n-Zuordnung von [!DNL Audience Manager] Benutzer-IDs (UUID) zu:

* Geräte-ID/Datenanbieter-IDs (DPUUID)
* Qualifizierte Segment-IDs
* Eigenschaften-IDs

[!DNL Audience Manager] -Kunden haben keinen Zugriff auf Funktionen, die die [!UICONTROL SFPT/S3 publishers] direkt steuern. Kunden verwenden diesen Dienst indirekt, wenn sie Daten erstellen und an Ziele senden. Das System [!UICONTROL SFTP/S3] ist im Wesentlichen ein automatisierter Auftragsprozess, der in geplanten Abständen ausgeführt wird.

## IRIS {#iris}

In der griechischen Mythologie ist [!UICONTROL Iris] eine Figur, die schnell reist und Nachrichten übermittelt. Das System [!UICONTROL IRIS] ist ein Namensvetter, der die Eigenschaften dieser Figur aus der alten Welt widerspiegelt. In moderner Form ist [!UICONTROL IRIS] ein Dienst zur Datensynchronisierung und -übertragung mit geringer Latenz, mit hoher Häufigkeit.

[!UICONTROL IRIS] arbeitet mit demselben Datentyp wie das [!UICONTROL SFTP/S3]-System. [!UICONTROL IRIS] ist jedoch anders, da es Daten in Echtzeit an Ziele sendet und nicht in festgelegten Intervallen. Dies ist ein separates System, da die [!UICONTROL SFTP/S3]-Herausgeber keine Daten an ein HTTP-Ziel senden können und nicht für Echtzeit-Datenübertragungen konzipiert sind.

Es gibt keine Steuerelemente der Benutzeroberfläche, mit denen Kunden direkt mit [!UICONTROL IRIS] arbeiten können. Kunden arbeiten indirekt mit [!UICONTROL IRIS], wenn sie Daten erstellen und an Ziele und für andere Prozesse senden, für die eine schnelle Datenübertragung erforderlich ist.

Beispiele für [!UICONTROL IRIS] -Dienste und -Funktionen sind:

* Schnelle Synchronisation von Cookies und Segmenten (innerhalb von 30 Sekunden). Es kann das [!DNL Audience Manager] -Cookie, Partnercookies oder beides synchronisieren.
* Echtzeit-Datenübertragungen. [!UICONTROL IRIS] ist für das Senden von Segmentqualifikationsereignissen in Echtzeit an einen Partner oder ein anderes Ziel verantwortlich. Diese Daten sind im JSON-Format formatiert und werden über eine HTTP `POST` -Anfrage gesendet.

* Massenübertragung von Server-zu-Server-Daten: Wenn Sie große Datenmengen mit [!DNL Audience Manager] austauschen, ist [!UICONTROL IRIS] das System, mit dem Ihre Server interagieren, um Daten zu übertragen.

* Zuverlässiges, skalierbares und fehlertolerantes Infrastruktursystem. Zu den Systemen mit der Leistung [!UICONTROL IRIS] gehören Amazon SQS, Amazon EC2 und Cassandra.

**Segmentzuordnungsregeln**

Um den Traffic zwischen [!UICONTROL IRIS] und Segmentzielen zu optimieren, sendet [!UICONTROL IRIS] Segmente basierend auf einem Regelsatz an Ziele.

1. **Neue Segmentqualifizierung**: Wenn sich ein Gerät für ein neues Segment qualifiziert, sendet [!UICONTROL IRIS] alle mit diesem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind.

1. **Neue Segmentdisqualifizierung**: Wenn sich ein Gerät nicht mehr für ein Segment qualifiziert, sendet [!UICONTROL IRIS] alle mit diesem Gerät verknüpften Segmentqualifikationen und -disqualifikationen an alle Ziele, die diesen Segmenten zugeordnet sind.

1. **Aktualisierungen der Zielzuordnung**: Wenn eine Zielzuordnung aktualisiert wird, sendet [!UICONTROL IRIS] alle mit einem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind, sobald der Audience Manager das Gerät das nächste Mal sieht.

1. **Gerätediagrammaktualisierungen**: Wenn eine Geräte-ID zum Gerätediagramm hinzugefügt oder aus dem Gerätediagramm entfernt wird, das zum Auswerten eines Segments verwendet wird, sendet [!UICONTROL IRIS] alle mit diesem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind, sobald der Audience Manager das Gerät das nächste Mal sieht.

>[!IMPORTANT]
>
>Wenn Audience Manager keine der oben genannten Aktualisierungen an drei aufeinander folgenden Tagen erkennt, sendet [!UICONTROL IRIS] alle mit einem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind, sobald der Audience Manager das Gerät das nächste Mal sieht.

**Beispieldatendatei**

Das folgende Beispiel enthält Echtzeitsegmentdaten von [!UICONTROL IRIS]. Beachten Sie, dass es sich hierbei nur um Beispieldaten handelt. Jeder Kunde kann unterschiedliche Formatierungsanforderungen haben, sodass der Inhalt variieren kann.

```
{
    "ProcessTime": "Tue Jul 21 19:12:45 UTC 2015",
    "Client_ID": "111111",
    "AAM_Destination_Id": "22222",
    "User_count": "5",
    "Users": [
        {
            "AAM_UUID": "28272096202945091600036434734793744071",
            "DataPartner_UUID": "CAESEFdv5pk-Lurd8vL9Yfb3qFg",
            "Segments": [
                {
                    "Segment_ID": "1200598",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:12 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "35183292386788708387827965829455926157",
            "DataPartner_UUID": "CAESEF_d8blvZjchQ2WTzdB65yk",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:15 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "28012470144260632050402316345856327572",
            "DataPartner_UUID": "CAESEEPfHBiRjhkzvBPXQ-0MFRE|UzCESAAABOnFeHJy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:33 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "18981483751565214534184221210627150539",
            "DataPartner_UUID": "CAK4NDH0ESEE6NBEhoWDkB7s7ZY|VPYFQQAAASXPElL0",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:36 UTC 2015"
                }
            ]
        },
        {
            "AAM_UUID": "04761851136483019318109155624251711702",
            "DataPartner_UUID": "CAESEDkM5aSaKMV8MfaBhgSspmE|VYnTNwAAASzvVhxy",
            "Segments": [
                {
                    "Segment_ID": "1306742",
                    "Status": "1",
                    "DateTime": "Tue Jul 21 19:12:42 UTC 2015"
                }
            ]
        }
    ]
}
```

## Profil-Cache-Server (PCS) {#pcs}

Siehe [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

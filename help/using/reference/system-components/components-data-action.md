---
description: Zu den Datenaktionskomponenten gehören Kundendatenfeeds, Datenkollektionsserver, SFTP/S 3/HTTP-Herausgeber, IRIS und der Profil-Cache-Server.
seo-description: Zu den Datenaktionskomponenten gehören Kundendatenfeeds, Datenkollektionsserver, SFTP/S 3/HTTP-Herausgeber, IRIS und der Profil-Cache-Server.
seo-title: Datenaktionskomponenten
solution: Audience Manager
title: Datenaktionskomponenten
uuid: c 4 c 4 cc 46-8 c 96-4 ef 5-8269-571 cc 5 ac 9276
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Action Components{#data-action-components}

Zu den Datenaktionskomponenten gehören Kundendatenfeeds, Datenkollektionsserver, SFTP/S 3/HTTP-Herausgeber, IRIS und der Profil-Cache-Server.

<!-- 

c_compact.xml

 -->

Action components are systems and processes that let you move data in and out of [!DNL Audience Manager] and (for the lack of a better phrase) do things with it. These [!DNL Audience Manager] components include:

## Customer Data Feeds (CDF) {#cdf}

[!UICONTROL CDF] werden stündlich an Kunden gesendet. Dazu gehören Benutzer-IDs sowie zugehörige Segment-IDs, Eigenschafts-IDs und andere Daten. For more information, see [Customer Data Feed Overview](../../features/cdf-files.md).

## Data Collection Server (DCS) {#dcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

[!UICONTROL SFTP/S3] Die Herausgeber erhalten synchronisierte ID-Daten aus [!UICONTROL Outbound Feed Converter]dem. When these files are ready, the [!UICONTROL SFTP/S3 publishers] send this data to a destination specified by the client. These files contain synchronized ID data with a one-to-many mapping of [!DNL Audience Manager] user IDs (UUID) to:

* Geräte-ID/Datenanbieter-IDs (DPUUID)
* Qualifizierte Segment-IDs
* Eigenschafts-IDs

[!DNL Audience Manager] Kunden haben keinen Zugriff auf Funktionen, die direkt [!UICONTROL SFPT/S3 publishers]steuern. Kunden verwenden diesen Dienst indirekt, wenn sie Daten erstellen und an Ziele senden. The [!UICONTROL SFTP/S3] system is, essentially, an automated job process that runs at scheduled intervals.

## IRIS {#iris}

In Greek mythology, [!UICONTROL Iris] is a figure who travels and delivers messages rapidly. The [!UICONTROL IRIS] system is a namesake that reflects the characteristics of this figure from the ancient world. In modern terms, [!UICONTROL IRIS] is a low-latency, high-frequency cookie synchronization and data transfer service.

[!UICONTROL IRIS] funktioniert mit demselben Datentyp wie das [!UICONTROL SFTP/S3] System. [!UICONTROL IRIS] Es unterscheidet sich jedoch, da es Daten in Echtzeit anstatt in festgelegten Abständen an Ziele sendet. This is a separate system because the [!UICONTROL SFTP/S3] publishers can't send data to an HTTP destination and they're not designed for real-time data transfers.

There are no UI controls that let customers work directly with [!UICONTROL IRIS]. Customers work with [!UICONTROL IRIS] indirectly when they create and send data to destinations, and for other processes that require rapid data transfers.

Examples of [!UICONTROL IRIS] services and features include:

* Schnelle (innerhalb von 30 Sekunden) Synchronisierung von Cookies und Segmenten. It can synchronize the [!DNL Audience Manager] cookie, partner cookies, or both.
* Echtzeit-Datenübertragungen. [!UICONTROL IRIS] ist für den Versand von Echtzeit-Segmentqualifizierungsereignissen an einen Partner oder ein anderes Ziel verantwortlich. This data is JSON-formatted and sent via an HTTP `POST` request.

* Bulk server-to-server data transfers: If you exchange large amounts of data with [!DNL Audience Manager], [!UICONTROL IRIS] is the system that your servers engage with to transfer data.

* Zuverlässige Infrastruktur, die in der Skala funktioniert und Fehlertolerant ist. Systems that power [!UICONTROL IRIS] include Amazon SQS, Amazon EC2, and Cassandra.

**Segmentzuordnungsregeln**

To optimize traffic between [!UICONTROL IRIS] and segment destinations, [!UICONTROL IRIS] sends segments to destinations based on a set of rules.

1. **Neue Segmentqualifizierung**: Wenn ein Gerät sich für ein neues Segment qualifiziert, [!UICONTROL IRIS] sendet es alle mit diesem Gerät verknüpften Segmente an alle diesen Segmenten zugeordneten Ziele.

1. **Neue Segmentabfrage**: Wenn ein Gerät nicht länger für ein Segment qualifiziert ist, [!UICONTROL IRIS] sendet es alle Segmentqualifikationen und die mit diesem Gerät verknüpften Fehlungen an alle diesen Segmenten zugeordneten Ziele.

1. **Aktualisierungsaktualisierungen**: Wenn eine Zielzuordnung aktualisiert wird, [!UICONTROL IRIS] sendet das nächste Mal alle mit einem Gerät verknüpften Segmente an alle diesen Segmenten zugeordneten Ziele, wenn Audience Manager das Gerät das nächste Mal sieht.

1. **Gerätediagramm-Updates**: Wenn eine Geräte-ID hinzugefügt oder aus dem Gerätediagramm entfernt wird, das zur Auswertung eines Segments verwendet wird, [!UICONTROL IRIS] sendet das nächste Mal alle diesem Gerät zugeordneten Segmente an alle Ziele, die diesen Segmenten zugeordnet sind, wenn das nächste Mal Audience Manager das Gerät sieht.

>[!IMPORTANT]
>
>If Audience Manager doesn't detect any of the updates above for 3 consecutive days, [!UICONTROL IRIS] sends all segments associated to a device to all of the destinations mapped to these segments, the next time Audience Manager sees the device.

**Musterdatendatei**

The following example contains real-time segment data from [!UICONTROL IRIS]. Beachten Sie, dass dies nur Musterdaten ist. Jeder Kunde kann unterschiedliche Formatierungsanforderungen haben, damit die Inhalte variieren können.

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

## Profile Cache Server (PCS) {#pcs}

See [Data Collection Components](../../reference/system-components/components-data-collection.md).

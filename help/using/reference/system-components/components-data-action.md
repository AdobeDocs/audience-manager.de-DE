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


# Datenaktionskomponenten{#data-action-components}

Zu den Datenaktionskomponenten gehören Kundendatenfeeds, Datenkollektionsserver, SFTP/S 3/HTTP-Herausgeber, IRIS und der Profil-Cache-Server.

<!-- 

c_compact.xml

 -->

Aktionskomponenten sind Systeme und Prozesse, mit denen Sie Daten in und aus [!DNL Audience Manager] und (für das Fehlen einer besseren Wortgruppe) verschieben können. Zu diesen [!DNL Audience Manager] Komponenten gehören:

## Kundendatenfeeds (CDF) {#cdf}

[!UICONTROL CDF] werden stündlich an Kunden gesendet. Dazu gehören Benutzer-IDs sowie zugehörige Segment-IDs, Eigenschafts-IDs und andere Daten. Weitere Informationen finden Sie unter [Übersicht über die Kundendaten](../../features/cdf-files.md).

## Datenerfassungsserver (DCS) {#dcs}

Siehe [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

## SFTP/S 3 {#sftp-s3}

[!UICONTROL SFTP/S3] Die Herausgeber erhalten synchronisierte ID-Daten aus [!UICONTROL Outbound Feed Converter]dem. Wenn diese Dateien fertig sind, senden Sie [!UICONTROL SFTP/S3 publishers] diese Daten an ein vom Kunden festgelegtes Ziel. Diese Dateien enthalten synchronisierte ID-Daten mit einer Zuordnung von [!DNL Audience Manager] Benutzer-IDs (UUID) zu:

* Geräte-ID/Datenanbieter-IDs (DPUUID)
* Qualifizierte Segment-IDs
* Eigenschafts-IDs

[!DNL Audience Manager] Kunden haben keinen Zugriff auf Funktionen, die direkt [!UICONTROL SFPT/S3 publishers]steuern. Kunden verwenden diesen Dienst indirekt, wenn sie Daten erstellen und an Ziele senden. Das [!UICONTROL SFTP/S3] System ist im Grunde ein automatisierter Auftragsprozess, der in geplanten Intervallen ausgeführt wird.

## IRIS {#iris}

In griechischer mythologie [!UICONTROL Iris] ist eine Abbildung, die Nachrichten schnell verhält und liefert. Das [!UICONTROL IRIS] System ist eine Namesake, die die Merkmale dieser Abbildung aus der alten Welt widerspiegelt. Bei modernen Begriffen [!UICONTROL IRIS] handelt es sich um eine geringe Latenz, eine Hochfrequenz-Cookie-Synchronisierung und einen Datenübertragungsdienst.

[!UICONTROL IRIS] funktioniert mit demselben Datentyp wie das [!UICONTROL SFTP/S3] System. [!UICONTROL IRIS] Es unterscheidet sich jedoch, da es Daten in Echtzeit anstatt in festgelegten Abständen an Ziele sendet. Dies ist ein separates System, da die [!UICONTROL SFTP/S3] Herausgeber keine Daten an ein HTTP-Ziel senden können und diese nicht für Echtzeit-Datenübertragungen entworfen werden.

Es gibt keine Steuerelemente für die Benutzeroberfläche, mit denen Kunden direkt mit ihnen arbeiten [!UICONTROL IRIS]können. Kunden arbeiten [!UICONTROL IRIS] mit indirekten Daten, wenn sie Daten an Ziele senden und an andere Prozesse senden, für die schnelle Datenübertragungen erforderlich sind.

Beispiele für [!UICONTROL IRIS] Dienste und Funktionen:

* Schnelle (innerhalb von 30 Sekunden) Synchronisierung von Cookies und Segmenten. Es kann das [!DNL Audience Manager] Cookie, Partnercookies oder beides synchronisieren.
* Echtzeit-Datenübertragungen. [!UICONTROL IRIS] ist für den Versand von Echtzeit-Segmentqualifizierungsereignissen an einen Partner oder ein anderes Ziel verantwortlich. Diese Daten sind JSON-formatiert und über eine HTTP `POST` -Anforderung gesendet.

* Massenserver-zu-Server-Datenübertragungen: Wenn Sie große Datenmengen austauschen, ist das [!DNL Audience Manager]System, mit [!UICONTROL IRIS] dem die Server interagieren, mit der Übertragung von Daten verbunden.

* Zuverlässige Infrastruktur, die in der Skala funktioniert und Fehlertolerant ist. Systeme, die Amazon [!UICONTROL IRIS] SQS, Amazon EC 2 und Cassandra verwenden.

**Segmentzuordnungsregeln**

Um den Traffic zwischen Zielen [!UICONTROL IRIS] und Segmenten zu optimieren, [!UICONTROL IRIS] sendet es Segmente an Ziele, die auf einer Reihe von Regeln basieren.

1. **Neue Segmentqualifizierung**: Wenn ein Gerät sich für ein neues Segment qualifiziert, [!UICONTROL IRIS] sendet es alle mit diesem Gerät verknüpften Segmente an alle diesen Segmenten zugeordneten Ziele.

1. **Neue Segmentabfrage**: Wenn ein Gerät nicht länger für ein Segment qualifiziert ist, [!UICONTROL IRIS] sendet es alle Segmentqualifikationen und die mit diesem Gerät verknüpften Fehlungen an alle diesen Segmenten zugeordneten Ziele.

1. **Aktualisierungsaktualisierungen**: Wenn eine Zielzuordnung aktualisiert wird, [!UICONTROL IRIS] sendet das nächste Mal alle mit einem Gerät verknüpften Segmente an alle diesen Segmenten zugeordneten Ziele, wenn Audience Manager das Gerät das nächste Mal sieht.

1. **Gerätediagramm-Updates**: Wenn eine Geräte-ID hinzugefügt oder aus dem Gerätediagramm entfernt wird, das zur Auswertung eines Segments verwendet wird, [!UICONTROL IRIS] sendet das nächste Mal alle diesem Gerät zugeordneten Segmente an alle Ziele, die diesen Segmenten zugeordnet sind, wenn das nächste Mal Audience Manager das Gerät sieht.

>[!IMPORTANT]
>
>Wenn Audience Manager keinen der oben aufgeführten Updates für drei aufeinander folgende Tage erkennt und [!UICONTROL IRIS] alle mit einem Gerät verknüpften Segmente an alle diesen Segmenten zugeordneten Ziele sendet, wird das nächste Mal von Audience Manager das Gerät angezeigt.

**Musterdatendatei**

Das folgende Beispiel enthält Echtzeitsegmentdaten aus [!UICONTROL IRIS]. Beachten Sie, dass dies nur Musterdaten ist. Jeder Kunde kann unterschiedliche Formatierungsanforderungen haben, damit die Inhalte variieren können.

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

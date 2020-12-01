---
description: Zu den Datenaktionskomponenten gehören Kundendatenfeeds, der Datenerfassungsserver, SFTP/S3/HTTP-Herausgeber, IRIS und der Profil-Cache-Server.
seo-description: Zu den Datenaktionskomponenten gehören Kundendatenfeeds, der Datenerfassungsserver, SFTP/S3/HTTP-Herausgeber, IRIS und der Profil-Cache-Server.
seo-title: Datenaktionskomponenten
solution: Audience Manager
title: Datenaktionskomponenten
uuid: c4c4cc46-8c96-4ef5-8269-571cc5ac9276
feature: system components
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 3%

---


# Datenaktionskomponenten{#data-action-components}

Zu den Datenaktionskomponenten gehören Kundendatenfeeds, der Datenerfassungsserver, SFTP/S3/HTTP-Herausgeber, IRIS und der Profil-Cache-Server.

<!-- 

c_compact.xml

 -->

Aktionskomponenten sind Systeme und Prozesse, mit denen Sie Daten in und aus [!DNL Audience Manager] verschieben und (wegen des Fehlens einer besseren Wortgruppe) Dinge damit tun können. Zu diesen Komponenten gehören:[!DNL Audience Manager]

## Kundendaten-Feeds (CDF) {#cdf}

[!UICONTROL CDF] sind Dateien, die stündlich an Kunden gesendet werden. Diese enthalten Benutzer-IDs zusammen mit zugehörigen Segment-IDs, Eigenschaften-IDs und anderen Daten. Weitere Informationen finden Sie unter [Übersicht über den Kundendaten-Feed](../../features/cdf-files.md).

## Datenerfassungsserver (DCS) {#dcs}

Siehe [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Die Herausgeber von [!UICONTROL SFTP/S3] erhalten synchronisierte ID-Daten von [!UICONTROL Outbound Feed Converter]. Wenn diese Dateien fertig sind, senden Sie die [!UICONTROL SFTP/S3 publishers]-Daten an ein vom Client angegebenes Ziel. Diese Dateien enthalten synchronisierte ID-Daten mit einer 1-zu-n-Zuordnung von [!DNL Audience Manager] Benutzer-IDs (UUID) zu:

* Geräte-ID/Datenanbieter-IDs (DPUUID)
* Qualifizierte Segment-IDs
* Eigenschaften-IDs

[!DNL Audience Manager] Kunden haben keinen Zugriff auf Funktionen, die die  [!UICONTROL SFPT/S3 publishers]Funktion direkt steuern. Kunden verwenden diesen Dienst indirekt, wenn sie Daten erstellen und an Ziele senden. Das [!UICONTROL SFTP/S3]-System ist im Wesentlichen ein automatisierter Auftragsvorgang, der in eingeplanten Intervallen ausgeführt wird.

## IRIS {#iris}

In der griechischen Mythologie ist [!UICONTROL Iris] eine Figur, die schnell reist und Nachrichten liefert. Das [!UICONTROL IRIS]-System ist ein Namensvetter, der die Eigenschaften dieser Figur aus der alten Welt widerspiegelt. In moderner Form ist [!UICONTROL IRIS] ein Dienst zur Synchronisierung von Cookies mit hoher Frequenz und Datenübertragung mit niedriger Latenz.

[!UICONTROL IRIS] funktioniert mit demselben Datentyp wie das  [!UICONTROL SFTP/S3] System. [!UICONTROL IRIS] ist jedoch anders, da Daten in Echtzeit und nicht in festgelegten Intervallen an Ziele gesendet werden. Dies ist ein separates System, da die Herausgeber von [!UICONTROL SFTP/S3] keine Daten an ein HTTP-Ziel senden können und nicht für Datenübertragungen in Echtzeit konzipiert sind.

Es gibt keine Steuerelemente der Benutzeroberfläche, mit denen Kunden direkt mit [!UICONTROL IRIS] arbeiten können. Kunden arbeiten indirekt mit [!UICONTROL IRIS], wenn sie Daten erstellen und an Ziele senden, und für andere Prozesse, die eine schnelle Datenübertragung erfordern.

Beispiele für Dienste und Funktionen von [!UICONTROL IRIS]:

* Schnelle Synchronisierung (innerhalb von 30 Sekunden) von Cookies und Segmenten. Es kann das [!DNL Audience Manager]-Cookie, Partner-Cookies oder beide synchronisieren.
* Datenübertragung in Echtzeit [!UICONTROL IRIS] ist für den Versand von Segmentqualifizierungs-Ereignissen in Echtzeit an einen Partner oder einen anderen Zielort verantwortlich. Diese Daten sind JSON-formatiert und werden über eine HTTP `POST`-Anforderung gesendet.

* Massenübertragung von Server zu Server: Wenn Sie große Datenmengen mit [!DNL Audience Manager] austauschen, ist [!UICONTROL IRIS] das System, mit dem Ihre Server Daten übertragen.

* Zuverlässige Infrastruktur, die skalierbar funktioniert und fehlertolerant ist. Zu den Systemen mit der Leistung [!UICONTROL IRIS] gehören Amazon SQS, Amazon EC2 und Cassandra.

**Segmentzuordnungsregeln**

Zur Optimierung des Traffics zwischen [!UICONTROL IRIS]- und Segmentzielen sendet [!UICONTROL IRIS] Segmente basierend auf einem Regelsatz an Ziele.

1. **Neue Segmentqualifizierung**: Wenn ein Gerät für ein neues Segment qualifiziert ist,  [!UICONTROL IRIS] sendet es alle mit diesem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind.

1. **Neue Segmentdisqualifikation**: Wenn ein Gerät sich nicht mehr für ein Segment qualifiziert,  [!UICONTROL IRIS] sendet es alle mit diesem Gerät verbundenen Segmentqualifikationen und -disqualifikationen an alle Ziele, die diesen Segmenten zugeordnet sind.

1. **Aktualisierungen** der Zielzuordnung: Wenn eine Zielzuordnung aktualisiert wird, werden alle mit einem Gerät verknüpften Segmente an alle diesen Segmenten zugeordneten Ziele  [!UICONTROL IRIS] gesendet, wenn der Audience Manager das Gerät das nächste Mal sieht.

1. **Aktualisierungen** des Gerätediagramms: Wenn eine Geräte-ID aus dem Gerätediagramm zur Segmentauswertung hinzugefügt oder entfernt wird,  [!UICONTROL IRIS] sendet der Audience Manager alle mit diesem Gerät verknüpften Segmente an alle diesen Segmenten zugeordneten Ziele, sobald das Gerät angezeigt wird.

>[!IMPORTANT]
>
>Wenn Audience Manager an 3 aufeinander folgenden Tagen keine der oben genannten Updates erkennt, sendet [!UICONTROL IRIS] alle mit einem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind, wenn der Audience Manager das Gerät das nächste Mal anzeigt.

**Beispieldatendatei**

Das folgende Beispiel enthält Echtzeitsegmentdaten von [!UICONTROL IRIS]. Beachten Sie, dass dies nur Musterdaten sind. Jeder Kunde kann unterschiedliche Formatierungsanforderungen haben, sodass der Inhalt variieren kann.

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

## Profil Cache Server (PCS) {#pcs}

Siehe [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

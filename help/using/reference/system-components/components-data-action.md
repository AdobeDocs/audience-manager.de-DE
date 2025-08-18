---
description: Zu den Datenaktionskomponenten gehören Kundendaten-Feeds, der Datenerfassungs-Server, SFTP/S3/HTTP-Publisher, IRIS und der Profil-Cache-Server.
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

Zu den Datenaktionskomponenten gehören Kundendaten-Feeds, der Datenerfassungs-Server, SFTP/S3/HTTP-Publisher, IRIS und der Profil-Cache-Server.

<!-- 

c_compact.xml

 -->

Aktionskomponenten sind Systeme und Prozesse, mit denen Sie Daten in und aus [!DNL Audience Manager] verschieben und (mangels einer besseren Phrase) Dinge damit tun können. Zu diesen [!DNL Audience Manager] gehören:

## Kundendaten-Feeds (CDF) {#cdf}

[!UICONTROL CDF] werden die Dateien stündlich an Kunden gesendet. Diese enthalten Benutzer-IDs zusammen mit zugehörigen Segment-IDs, Eigenschafts-IDs und anderen Daten. Weitere Informationen finden Sie unter [Übersicht über Kundendaten-Feeds](../../features/cdf-files.md).

## Datenerfassungs-Server (DCS) {#dcs}

Siehe [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

## SFTP/S3 {#sftp-s3}

Die [!UICONTROL SFTP/S3] Publisher erhalten synchronisierte ID-Daten vom [!UICONTROL Outbound Feed Converter]. Wenn diese Dateien fertig sind, senden die [!UICONTROL SFTP/S3 publishers] diese Daten an ein vom Client angegebenes Ziel. Diese Dateien enthalten synchronisierte ID-Daten mit einer Eins-zu-viele-Zuordnung von [!DNL Audience Manager]-Benutzer-IDs (UUID) zu:

* Geräte-ID/Datenanbieter-IDs (DPUUID)
* Qualifizierte Segment-IDs
* Eigenschaften-IDs

[!DNL Audience Manager] Kunden haben keinen Zugriff auf Funktionen, die die [!UICONTROL SFPT/S3 publishers] direkt steuern. Kundinnen und Kunden verwenden diesen Service indirekt, wenn sie Daten erstellen und an Ziele senden. Das [!UICONTROL SFTP/S3] ist im Wesentlichen ein automatisierter Auftragsprozess, der in terminierten Intervallen ausgeführt wird.

## IRIS {#iris}

In der griechischen Mythologie ist [!UICONTROL Iris] eine Gestalt, die reist und Botschaften schnell verbreitet. Das [!UICONTROL IRIS] ist ein Namensgeber, der die Charakteristika dieser Figur aus der Antike widerspiegelt. In modernen Begriffen ist [!UICONTROL IRIS] ein Service zur Synchronisierung von Cookies mit niedriger Latenz und hoher Häufigkeit sowie zur Datenübertragung.

[!UICONTROL IRIS] funktioniert mit demselben Datentyp wie das [!UICONTROL SFTP/S3]. [!UICONTROL IRIS] unterscheidet sich jedoch, da Daten in Echtzeit und nicht in festgelegten Intervallen an Ziele gesendet werden. Dies ist ein separates System, da die [!UICONTROL SFTP/S3] Publisher keine Daten an ein HTTP-Ziel senden können und nicht für Echtzeit-Datenübertragungen konzipiert sind.

Es gibt keine UI-Steuerelemente, mit denen Kunden direkt mit [!UICONTROL IRIS] arbeiten können. Kundinnen und Kunden arbeiten mit [!UICONTROL IRIS] indirekt zusammen, wenn sie Daten erstellen und an Ziele senden, sowie für andere Prozesse, die schnelle Datenübertragungen erfordern.

Beispiele für [!UICONTROL IRIS]-Services und -Funktionen:

* Schnelle Synchronisierung (innerhalb von 30 Sekunden) für Cookies und Segmente. Es kann das [!DNL Audience Manager]-Cookie, Partner-Cookies oder beides synchronisieren.
* Echtzeit-Datenübertragungen. [!UICONTROL IRIS] ist für das Senden von Echtzeit-Segmentqualifikationsereignissen an einen Partner oder ein anderes Ziel verantwortlich. Diese Daten sind JSON-formatiert und werden über eine HTTP-`POST`-Anfrage gesendet.

* Massen-Server-zu-Server-Datenübertragungen: Wenn Sie große Datenmengen mit [!DNL Audience Manager] austauschen, ist [!UICONTROL IRIS] das System, mit dem Ihre Server Daten übertragen.

* Zuverlässige Infrastruktur, die skaliert und fehlertolerant arbeitet. Zu den Systemen, die [!UICONTROL IRIS] unterstützen, gehören Amazon SQS, Amazon EC2 und Cassandra.

**Regeln für die Segmentzuordnung**

Um den Traffic zwischen [!UICONTROL IRIS]- und Segmentzielen zu optimieren, sendet [!UICONTROL IRIS] basierend auf einem Regelsatz Segmente an Ziele.

1. **Neue Segmentqualifikation**: Wenn sich ein Gerät für ein neues Segment qualifiziert, sendet [!UICONTROL IRIS] alle mit diesem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind.

1. **Neue Segmentdisqualifizierung**: Wenn sich ein Gerät nicht mehr für ein Segment qualifiziert, sendet [!UICONTROL IRIS] alle mit diesem Gerät verknüpften Segmentqualifikationen und Disqualifikationen an alle Ziele, die diesen Segmenten zugeordnet sind.

1. **Aktualisierungen der Zielzuordnung**: Wenn eine Zielzuordnung aktualisiert wird, sendet [!UICONTROL IRIS] alle mit einem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind, wenn Audience Manager das Gerät das nächste Mal sieht.

1. **Aktualisierungen des Gerätediagramms**: Wenn eine Geräte-ID zum Gerätediagramm, das zur Auswertung eines Segments verwendet wird, hinzugefügt oder daraus entfernt wird, sendet [!UICONTROL IRIS] alle mit diesem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind, wenn Audience Manager das Gerät das nächste Mal sieht.

>[!IMPORTANT]
>
>Wenn Audience Manager an drei aufeinander folgenden Tagen keine der oben genannten Aktualisierungen erkennt, sendet [!UICONTROL IRIS] alle mit einem Gerät verknüpften Segmente an alle Ziele, die diesen Segmenten zugeordnet sind, wenn Audience Manager das Gerät das nächste Mal sieht.

**Beispieldatendatei**

Das folgende Beispiel enthält Echtzeit-Segmentdaten aus [!UICONTROL IRIS]. Hierbei handelt es sich ausschließlich um Beispieldaten. Jeder Kunde kann unterschiedliche Formatierungsanforderungen haben, sodass der Inhalt variieren kann.

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

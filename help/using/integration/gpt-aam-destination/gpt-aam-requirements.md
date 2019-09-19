---
description: Sie können qualifizierte Segmente entweder über eine clientseitige oder über eine serverseitige Integration an DFP senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.
seo-description: Sie können qualifizierte Segmente entweder über eine clientseitige oder über eine serverseitige Integration an DFP senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.
seo-title: Anforderungen und Methoden zum Senden von Segmenten an DFP mithilfe von Google Publisher Tags (GPT)
solution: Audience Manager
title: Anforderungen und Methoden zum Senden von Segmenten an DFP mithilfe von Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Anforderungen und Methoden zum Senden von Segmenten an DFP mithilfe von Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Sie können qualifizierte Segmente entweder über eine clientseitige oder [!DNL DFP] über eine serverseitige Integration senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.

## Clientseitige Integration {#client-side-integration}

Für eine clientseitige Integration müssen Sie ein [!DNL GPT] Ziel in Audience Manager einrichten. Berücksichtigen Sie die folgenden Punkte, wenn Sie [!DNL GPT] als Audience Manager-Ziel einrichten möchten:

* **[!UICONTROL DIL]Hinzufügen**: Stellen Sie [!UICONTROL Data Integration Library (DIL)] Code auf allen Seiten bereit, die Sie als Ziel auswählen möchten. [!UICONTROL DIL] schreibt Audience Manager-Segmentdaten und Benutzer-IDs in Cookies, die [!DNL GPT] für das Targeting verwendet werden.

* **[!UICONTROL Cookie Destination]Erstellen eines**: muss in Audience Manager als cookie-basiertes Ziel eingerichtet werden. [!DNL GPT]

* **** Cookie-Überprüfungscode implementieren: Schließen Sie die [!DNL GPT] API-Methode in unseren empfohlenen `.setTargeting`Cookie-Prüfcode[](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) ein. Dieser Code verhindert Fehler, indem vor dem Aufruf der `.setTargeting` Methode nach gültigen AAM-Cookies gesucht wird.

* **`AamGpt`Funktion hinzufügen:** Der `AamGpt` Code erfasst Daten von Audience Manager-Cookies und sendet sie an [!DNL GPT]. Platzieren Sie den [Audience Manager-Code für Google Publisher-Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) oben auf der Seite oder innerhalb des `<head>` Codeblocks.

   >[!NOTE]
   >
   >Die `AamGpt` Funktion ist nicht erforderlich, wenn Sie zum Lesen von Audience Manager-Cookie-Daten Ihren eigenen Code verwenden.

* **** Bereitstellungsprotokolle an Audience Manager senden: Wenn Sie einen Segmentauslieferungsbericht (optional) wünschen, stellen Sie Audience Manager ein tägliches Protokoll zur Verfügung, das Auslieferungsdaten auf Impressionsebene enthält. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager enthalten `UUID`. Audience Manager kann diese abrufen oder empfangen [!DNL FTP].

### Nur qualifizierte Segmente werden an GPT gesendet

Die Datenmenge, an die ein Benutzer weitergeleitet wird, [!DNL GPT] hängt davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Beispiel: Sie richten 100 Audience Manager-Segmente ein. Wenn sich ein Besucher für fünf davon qualifiziert, werden nur diese fünf Segmente an gesendet [!DNL GPT] (nicht alle 100).

>[!NOTE]
>
>Die Anzahl der Schlüsselwerte, die Sie senden können, ist unbegrenzt. Die [!DNL Google] Anforderung [!DNL URL] beschränkt sich jedoch auf die Anzahl der Zeichen, die sie akzeptieren können. Siehe [Festlegen von Targeting und Größen mit GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Serverseitige Integration {#server-side-integration}

Wenden Sie sich an Ihren Audience Manager-Berater oder an den Kundendienst, wenn Sie eine serverseitige Integration mit [!DNL DFP]der [!DNL GPT]Anwendung einrichten möchten. Sie müssen Ihre [!DNL DFP] Konto-Netzwerk-ID und die Zielgruppen-Link-ID angeben.

>[!IMPORTANT]
>
>Wenn auf Ihren Webseiten die Bibliothek [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) ausgeführt wird, müssen Sie die serverseitige Integration mit Audience Manager verwenden. Wenn Sie eine clientseitige Integration verwenden [!DNL AMP] und eine solche verwenden, müssen Sie zur serverseitigen Integration migrieren [!DNL AMP]. Wenden Sie sich an Ihren Audience Manager-Berater oder an den Kundendienst, um über die Migration zu sprechen.

>[!MORE_LIKE_THIS]
>
>* [GPT API-Referenzhandbuch](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)


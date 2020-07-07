---
description: Sie können qualifizierte Segmente entweder über eine clientseitige oder über eine serverseitige Integration an Google Ad Manager senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.
seo-description: Sie können qualifizierte Segmente entweder über eine clientseitige oder über eine serverseitige Integration an Google Ad Manager senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.
seo-title: Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)
solution: Audience Manager
title: Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Sie können qualifizierte Segmente an [!DNL Google Ad Manager] (früher DFP) entweder über eine clientseitige oder über eine serverseitige Integration senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.

## Clientseitige Integration {#client-side-integration}

Für eine clientseitige Integration müssen Sie ein [!DNL GPT] Ziel in Audience Manager einrichten. Berücksichtigen Sie die folgenden Punkte, wenn Sie [!DNL GPT] als Audience Manager-Ziel einrichten möchten:

* **Hinzufügen[!UICONTROL DIL]:** Stellen Sie [!UICONTROL Data Integration Library (DIL)] Code auf allen Seiten bereit, die Sie Zielgruppen durchführen möchten. [!UICONTROL DIL] schreibt Audience Manager-Segmentdaten und Benutzer-IDs in Cookies, die [!DNL GPT] für das Targeting verwendet werden.

* **Erstellen Sie eine[!UICONTROL Cookie Destination]:** [!DNL GPT] muss als cookie-basiertes Ziel in Audience Manager eingerichtet werden.

* **Cookie-Überprüfungscode implementieren:** Schließen Sie die [!DNL GPT] API-Methode in unseren empfohlenen `.setTargeting` Cookie-Prüfcode [](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)ein. Dieser Code hilft, Fehler zu vermeiden, indem nach gültigen AAM-Cookies gesucht wird, bevor die `.setTargeting` Methode aufgerufen wird.

* **Hinzufügen der`AamGpt`Funktion:** Der `AamGpt` Code erfasst Daten von Audience Manager-Cookies und sendet sie an [!DNL GPT]. Platzieren Sie den [Audience Manager-Code für Google Publisher-Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) oben auf der Seite oder innerhalb des `<head>` Codeblocks.

   >[!NOTE]
   >
   >Die `AamGpt` Funktion ist nicht erforderlich, wenn Sie zum Lesen von Audience Manager-Cookie-Daten Ihren eigenen Code verwenden.

* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentbericht (optional) erstellen möchten, stellen Sie dem Audience Manager ein tägliches Protokoll mit Daten zum Versand auf Impressionsebene zur Verfügung. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager enthalten `UUID`. Audience Manager können diese abholen oder empfangen [!DNL FTP].

### Nur qualifizierte Segmente werden an GPT gesendet

Die Datenmenge, an die ein Benutzer weitergeleitet wird, [!DNL GPT] hängt davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Angenommen, Sie richten 100 Audience Manager ein. Wenn ein Site-Besucher für fünf davon qualifiziert ist, werden nur diese fünf Segmente an gesendet [!DNL GPT] (nicht alle 100).

>[!NOTE]
>
>Die Anzahl der Schlüsselwerte, die Sie senden können, ist unbegrenzt. Die [!DNL Google] Anforderung [!DNL URL] beschränkt sich jedoch auf die Anzahl der Zeichen, die sie akzeptieren können. Siehe [Festlegen von Targeting und Größen mit GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Serverseitige Integration {#server-side-integration}

Wenden Sie sich an Ihren Audience Manager-Berater oder an den Kundendienst, wenn Sie eine serverseitige Integration mithilfe von [!DNL Google Ad Manager][!DNL GPT]konfigurieren möchten. Sie müssen Ihre [!DNL Google Ad Manager] Konto-Netzwerk-ID und Audience-Link-ID angeben.

>[!IMPORTANT]
>
>Wenn auf Ihren Webseiten die [Bibliothek &quot;Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP])&quot;ausgeführt wird, müssen Sie die serverseitige Integration mit Audience Manager verwenden. Wenn Sie eine clientseitige Integration verwenden [!DNL AMP] und eine solche verwenden, müssen Sie zur serverseitigen Integration migrieren [!DNL AMP]. Wenden Sie sich an Ihren Audience Manager-Berater oder an die Kundenunterstützung, um die Migration zu besprechen.

>[!MORELIKETHIS]
>
>* [GPT API-Referenzhandbuch](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)


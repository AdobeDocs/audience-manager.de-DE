---
description: Sie können qualifizierte Segmente entweder clientseitig oder über eine serverseitige Integration an DFP senden. Anforderungen und zugehörige Informationen zu beiden Methoden sind nachfolgend aufgeführt.
seo-description: Sie können qualifizierte Segmente entweder clientseitig oder über eine serverseitige Integration an DFP senden. Anforderungen und zugehörige Informationen zu beiden Methoden sind nachfolgend aufgeführt.
seo-title: Anforderungen und Methoden zum Senden von Segmenten an DFP mithilfe von Google Publisher Tags (GPT)
solution: Audience Manager
title: Anforderungen und Methoden zum Senden von Segmenten an DFP mithilfe von Google Publisher Tags (GPT)
uuid: 4 b 2 ea 81 c -29 bb -42 d 3-93 d 3-1 d 8 e 677790 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Anforderungen und Methoden zum Senden von Segmenten an DFP mithilfe von Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Sie können qualifizierte Segmente entweder [!DNL DFP] clientseitig oder über eine serverseitige Integration senden. Anforderungen und zugehörige Informationen zu beiden Methoden sind nachfolgend aufgeführt.

## Clientseitige Integration {#client-side-integration}

Für eine clientseitige Integration müssen Sie in Audience Manager ein [!DNL GPT] Ziel einrichten. Berücksichtigen Sie die folgenden Punkte, wenn Sie [!DNL GPT] als Audience Manager-Ziel einrichten möchten:

* **Hinzufügen[!UICONTROL DIL]:** Stellen Sie [!UICONTROL Data Integration Library (DIL)] den Code auf allen Seiten bereit, die Sie als Ziel auswählen möchten. [!UICONTROL DIL] schreibt Audience Manager-Segmentdaten und Benutzer-IDs in Cookies, die für [!DNL GPT] das Targeting verwendet werden.

* **Erstellen[!UICONTROL Cookie Destination]Sie:**[!DNL GPT] muss als Cookie-basiertes Ziel in Audience Manager eingerichtet werden.

* **Cookie-Prüfcode implementieren:** Schließen Sie die [!DNL GPT]`.setTargeting` API-Methode in unserem empfohlenen [Cookie-Prüfcode ein](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Dieser Code verhindert Fehler, indem Sie nach gültigen AAM-Cookies suchen, bevor die `.setTargeting` Methode aufgerufen wird.

* **`AamGpt`Funktion hinzufügen:** Der `AamGpt` Code erfasst Daten aus Audience Manager-Cookies und sendet sie an [!DNL GPT]. Platzieren Sie den [Audience Manager-Code für Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) oben auf der Seite oder innerhalb des `<head>` Codeblocks.

   >[!NOTE]
   >
   >Die `AamGpt` Funktion ist nicht erforderlich, wenn Sie Ihren eigenen Code zum Lesen von Audience Manager-Cookie-Daten verwenden.

* **Versandprotokolle an Audience Manager senden:** Wenn Sie einen Segmentauslieferungsbericht wünschen (optional), geben Sie Audience Manager ein Tagesprotokoll mit Bereitstellungsdaten auf Impression-Ebene an. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager `UUID`enthalten. Zielgruppen-Manager können diese Daten [!DNL FTP]abrufen oder empfangen.

### Nur qualifizierte Segmente werden an GPT gesendet

Die Menge an übergebenen Daten [!DNL GPT] hängt davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Angenommen, Sie richten 100 Audience Manager-Segmente ein. Wenn sich ein Site-Besucher für fünf davon qualifiziert, werden nur die fünf Segmente an [!DNL GPT] (nicht alle 100) gesendet.

>[!NOTE]
>
>Die Anzahl der wichtigsten Werte, die Sie senden können, ist nicht beschränkt. Die [!DNL Google] Anforderung [!DNL URL] hat jedoch Beschränkungen für die zulässige Anzahl von Zeichen. Siehe [Festlegen von Targeting und Größen mit GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Serverseitige Integration {#server-side-integration}

Wenden Sie sich an Ihren Berater für Audience Manager oder an den Kundendienst, wenn Sie eine serverseitige Integration mit [!DNL DFP]verwenden [!DNL GPT]möchten. Sie müssen Ihre [!DNL DFP] Konto-ID und die Zielgruppen-Link-ID bereitstellen.

>[!IMPORTANT]
>
>Wenn Ihre Webseiten die [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP])-Bibliothek ausführen, müssen Sie die serverseitige Integration mit Audience Manager verwenden. Wenn Sie eine [!DNL AMP] client-seitige Integration verwenden [!DNL AMP], müssen Sie zur serverseitigen Integration migrieren. Wenden Sie sich an Ihren Audience Manager-Berater oder an den Kundendienst, um die Migration zu besprechen.

>[!MORE_ LIKE_ THIS]
>
>* [GPT API-Referenzhandbuch](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)


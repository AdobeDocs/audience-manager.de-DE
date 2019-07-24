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

You can send qualified segments to [!DNL DFP] either through a client-side or through a server-side integration. Anforderungen und zugehörige Informationen zu beiden Methoden sind nachfolgend aufgeführt.

## Client-Side Integration {#client-side-integration}

For a client-side integration, you need to set up a [!DNL GPT] destination in Audience Manager. Consider the following points when you want to set up [!DNL GPT] as an Audience Manager destination:

* **Hinzufügen[!UICONTROL DIL]:** Stellen Sie [!UICONTROL Data Integration Library (DIL)] den Code auf allen Seiten bereit, die Sie als Ziel auswählen möchten. [!UICONTROL DIL] schreibt Audience Manager-Segmentdaten und Benutzer-IDs in Cookies, die für [!DNL GPT] das Targeting verwendet werden.

* **Erstellen[!UICONTROL Cookie Destination]Sie:**[!DNL GPT] muss als Cookie-basiertes Ziel in Audience Manager eingerichtet werden.

* **Cookie-Prüfcode implementieren:** Schließen Sie die [!DNL GPT]`.setTargeting` API-Methode in unserem empfohlenen [Cookie-Prüfcode ein](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). This code helps prevent errors by looking for valid AAM cookies before the `.setTargeting` method gets invoked.

* **`AamGpt`Funktion hinzufügen:** Der `AamGpt` Code erfasst Daten aus Audience Manager-Cookies und sendet sie an [!DNL GPT]. Place the [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) at the top of the page or inside the `<head>` code block.

   >[!NOTE]
   >
   >The `AamGpt` function is not required if you use your own code to read Audience Manager cookie data.

* **Versandprotokolle an Audience Manager senden:** Wenn Sie einen Segmentauslieferungsbericht wünschen (optional), geben Sie Audience Manager ein Tagesprotokoll mit Bereitstellungsdaten auf Impression-Ebene an. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Nur qualifizierte Segmente werden an GPT gesendet

The amount of data passed in to [!DNL GPT] depends on how many segments a particular user qualifies for. Angenommen, Sie richten 100 Audience Manager-Segmente ein. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL GPT] (not all 100).

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. See [Setting targeting and sizes with GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-Side Integration {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL DFP], using [!DNL GPT]. You'll need to provide your [!DNL DFP] account Network ID and Audience Link ID.

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. If you are on [!DNL AMP] and have a client-side integration with [!DNL AMP], you must migrate to the server-side integration. Wenden Sie sich an Ihren Audience Manager-Berater oder an den Kundendienst, um die Migration zu besprechen.

>[!MORE_ LIKE_ THIS]
>
>* [GPT API-Referenzhandbuch](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)


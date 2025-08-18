---
description: Sie können qualifizierte Segmente entweder über eine Client-seitige oder eine Server-seitige Integration an Google Ad Manager senden. Die Anforderungen und die zugehörigen Informationen zu beiden Methoden sind unten aufgeführt.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Anforderungen und Methoden für das Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Anforderungen und Methoden für das Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Sie können qualifizierte Segmente entweder über eine Client-seitige oder eine Server-seitige Integration an [!DNL Google Ad Manager] (ehemals DFP) senden. Die Anforderungen und die zugehörigen Informationen zu beiden Methoden sind unten aufgeführt.

## Client-seitige Integration {#client-side-integration}

Für eine Client-seitige Integration müssen Sie ein [!DNL GPT] Ziel in Audience Manager einrichten. Beachten Sie die folgenden Punkte, wenn Sie [!DNL GPT] als Audience Manager-Ziel einrichten möchten:

* **[!UICONTROL DIL] hinzufügen:** Stellen Sie [!UICONTROL Data Integration Library (DIL)] Code auf allen Seiten bereit, die Sie ansprechen möchten. [!UICONTROL DIL] schreibt Audience Manager-Segmentdaten und Benutzer-IDs in Cookies, die von [!DNL GPT] für das Targeting verwendet werden.

* **Erstellen eines [!UICONTROL Cookie Destination]:** [!DNL GPT] muss in Audience Manager als Cookie-basiertes Ziel eingerichtet sein.

* **Implementierung des Cookie-Prüfcodes:** Schließen Sie die [!DNL GPT] `.setTargeting`-API-Methode in Ihrem empfohlenen [Cookie-Prüfcode](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) ein. Dieser Code verhindert Fehler, indem nach gültigen AAM-Cookies gesucht wird, bevor die `.setTargeting` aufgerufen wird.

* **Funktion `AamGpt` hinzufügen:** Der `AamGpt` erfasst Daten aus Audience Manager-Cookies und sendet sie an [!DNL GPT]. Platzieren Sie den [Audience Manager-Code für Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) oben auf der Seite oder innerhalb des `<head>`.

  >[!NOTE]
  >
  >Die `AamGpt` ist nicht erforderlich, wenn Sie zum Lesen von Audience Manager-Cookie-Daten Ihren eigenen Code verwenden.

* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentversandbericht (optional) wünschen, stellen Sie Audience Manager ein tägliches Protokoll zur Verfügung, das Versanddaten auf Impression-Ebene enthält. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss die Audience Manager-`UUID` enthalten. Audience Manager kann diese per [!DNL FTP] abholen oder empfangen.

### Nur qualifizierte Segmente werden an GPT gesendet

Die Menge der an [!DNL GPT] übergebenen Daten hängt von der Anzahl der Segmente ab, für die sich ein bestimmter Benutzer qualifiziert. Angenommen, Sie richten 100 Audience Manager-Segmente ein. Wenn sich ein Site-Besucher für fünf von ihnen qualifiziert, werden nur diese fünf Segmente an [!DNL GPT] gesendet (nicht alle 100).

>[!NOTE]
>
>Es gibt keine Begrenzung für die Anzahl der Schlüsselwerte, die Sie senden können, aber die [!DNL Google] Anfrage [!DNL URL] verfügt über Beschränkungen für die Anzahl der Zeichen, die sie akzeptieren kann. Siehe [Festlegen von Zielgruppen und Größen mit GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-seitige Integration {#server-side-integration}

Wenden Sie sich an Ihren Audience Manager-Berater oder an die Kundenunterstützung, wenn Sie mithilfe von [!DNL Google Ad Manager] eine Server-seitige Integration mit [!DNL GPT] einrichten möchten. Sie müssen Ihre Netzwerk-ID für das [!DNL Google Ad Manager]-Konto und die Zielgruppen-Link-ID angeben.

>[!IMPORTANT]
>
>Wenn auf Ihren Web-Seiten die Bibliothek [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) ausgeführt wird, müssen Sie die Server-seitige Integration mit Audience Manager verwenden. Wenn Sie [!DNL AMP] sind und eine Client-seitige Integration mit [!DNL AMP] haben, müssen Sie zur Server-seitigen Integration migrieren. Wenden Sie sich an Ihren Audience Manager-Berater oder an die Kundenunterstützung, um die Migration zu besprechen.

>[!MORELIKETHIS]
>
>* [GPT-API-Referenzhandbuch](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

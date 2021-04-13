---
description: Sie können qualifizierte Segmente entweder über eine clientseitige oder über eine serverseitige Integration an Google Ad Manager senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.
seo-description: Sie können qualifizierte Segmente entweder über eine clientseitige oder über eine serverseitige Integration an Google Ad Manager senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.
seo-title: Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)
solution: Audience Manager
title: Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Integration von Drittanbietern
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags ( GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Sie können qualifizierte Segmente entweder über eine clientseitige oder über eine serverseitige Integration an [!DNL Google Ad Manager] (ehemals DFP) senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.

## Clientseitige Integration {#client-side-integration}

Für eine clientseitige Integration müssen Sie in Audience Manager ein [!DNL GPT]-Ziel einrichten. Beachten Sie die folgenden Punkte, wenn Sie [!DNL GPT] als Audience Manager-Ziel einrichten möchten:

* **hinzufügen  [!UICONTROL DIL]:** Stellen Sie  [!UICONTROL Data Integration Library (DIL)] Code auf allen zu Zielgruppe Seiten bereit. [!UICONTROL DIL] schreibt Audience Manager-Segmentdaten und Benutzer-IDs in Cookies, die  [!DNL GPT] für das Targeting verwendet werden.

* **Create a  [!UICONTROL Cookie Destination]:** [!DNL GPT] must be set as a cookie-based destination in Audience Manager.

* **Cookie-Überprüfungscode implementieren:** Schließen Sie die  [!DNL GPT] `.setTargeting` API-Methode in unseren empfohlenen  [Cookie-Überprüfungscode](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) ein. Dieser Code hilft, Fehler zu vermeiden, indem nach gültigen AAM Cookies gesucht wird, bevor die `.setTargeting`-Methode aufgerufen wird.

* **hinzufügen der  `AamGpt` Funktion:** Der  `AamGpt` Code erfasst Daten aus Audience Manager-Cookies und sendet sie an  [!DNL GPT]. Platzieren Sie den [Audience Manager-Code für Google Publisher-Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) oben auf der Seite oder innerhalb des `<head>`-Codeblocks.

   >[!NOTE]
   >
   >Die Funktion `AamGpt` ist nicht erforderlich, wenn Sie zum Lesen von Audience Manager-Cookie-Daten Ihren eigenen Code verwenden.

* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentbericht (optional) erstellen möchten, stellen Sie dem Audience Manager ein tägliches Protokoll zur Verfügung, das Versand-Daten auf Impressionsebene enthält. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager `UUID` enthalten. Audience Manager können diese über [!DNL FTP] abrufen oder empfangen.

### Nur qualifizierte Segmente werden an GPT gesendet

Die Menge der an [!DNL GPT] weitergeleiteten Daten hängt davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Angenommen, Sie richten 100 Audience Manager ein. Wenn ein Site-Besucher für fünf davon qualifiziert ist, werden nur diese fünf Segmente an [!DNL GPT] gesendet (nicht alle 100).

>[!NOTE]
>
>Die Anzahl der Schlüsselwerte, die Sie senden können, ist unbegrenzt. Die [!DNL Google]-Anforderung [!DNL URL] hat jedoch eine Beschränkung der Zeichenanzahl, die sie akzeptieren können. Siehe [Festlegen von Targeting und Größen mit GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Serverseitige Integration {#server-side-integration}

Wenden Sie sich an Ihren Audience Manager- oder Kundendienst, wenn Sie eine serverseitige Integration mit [!DNL Google Ad Manager] mithilfe von [!DNL GPT] einrichten möchten. Sie müssen Ihre [!DNL Google Ad Manager]-Konto-Netzwerk-ID und Audience-Link-ID angeben.

>[!IMPORTANT]
>
>Wenn auf Ihren Webseiten die Bibliothek [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) ausgeführt wird, müssen Sie die serverseitige Integration mit Audience Manager verwenden. Wenn Sie [!DNL AMP] verwenden und eine clientseitige Integration mit [!DNL AMP] haben, müssen Sie zur serverseitigen Integration migrieren. Wenden Sie sich an Ihren Audience Manager-Berater oder an die Kundenunterstützung, um die Migration zu besprechen.

>[!MORELIKETHIS]
>
>* [GPT API-Referenzhandbuch](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)


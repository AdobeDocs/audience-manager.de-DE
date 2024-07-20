---
description: Sie können qualifizierte Segmente entweder über eine Client-seitige Integration oder über eine serverseitige Integration an Google Ad Manager senden. Die Anforderungen und damit zusammenhängenden Informationen zu beiden Methoden sind unten aufgeführt.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Sie können qualifizierte Segmente entweder über eine Client-seitige oder eine Server-seitige Integration an [!DNL Google Ad Manager] (ehemals DFP) senden. Die Anforderungen und damit zusammenhängenden Informationen zu beiden Methoden sind unten aufgeführt.

## Clientseitige Integration {#client-side-integration}

Für eine Client-seitige Integration müssen Sie ein [!DNL GPT] -Ziel in Audience Manager einrichten. Beachten Sie die folgenden Punkte, wenn Sie [!DNL GPT] als Audience Manager-Ziel einrichten möchten:

* **Hinzufügen von [!UICONTROL DIL]:** Stellen Sie den Code [!UICONTROL Data Integration Library (DIL)] auf allen Seiten bereit, die Sie als Ziel auswählen möchten. [!UICONTROL DIL] schreibt Audience Manager-Segmentdaten und Benutzer-IDs in Cookies, die von [!DNL GPT] für das Targeting verwendet werden.

* **Erstellen Sie einen [!UICONTROL Cookie Destination]:** [!DNL GPT] muss in Audience Manager als Cookie-basiertes Ziel eingerichtet werden.

* **Implementieren des Cookie-Überprüfungscodes:** Schließen Sie die API-Methode [!DNL GPT] `.setTargeting` in unseren empfohlenen Code zur Cookie-Überprüfung [ ein. ](../../integration/gpt-aam-destination/gpt-aam-modify-api.md) Dieser Code hilft dabei, Fehler zu vermeiden, indem nach gültigen AAM-Cookies gesucht wird, bevor die `.setTargeting` -Methode aufgerufen wird.

* **Fügen Sie die Funktion `AamGpt` hinzu:** Der Code `AamGpt` erfasst Daten aus Audience Manager-Cookies und sendet sie an [!DNL GPT]. den [Audience Manager-Code für Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) oben auf der Seite oder innerhalb des `<head>` -Codeblocks platzieren.

  >[!NOTE]
  >
  >Die Funktion `AamGpt` ist nicht erforderlich, wenn Sie zum Lesen von Audience Manager-Cookie-Daten Ihren eigenen Code verwenden.

* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentversandbericht (optional) wünschen, stellen Sie dem Audience Manager ein tägliches Protokoll mit Versanddaten auf Impressionsebene zur Verfügung. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager `UUID` enthalten. Audience Manager können diese über [!DNL FTP] abrufen oder empfangen.

### Nur qualifizierte Segmente werden an GPT gesendet

Die an [!DNL GPT] übergebene Datenmenge hängt davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Angenommen, Sie richten 100 Audience Manager-Segmente ein. Wenn ein Site-Besucher für fünf davon qualifiziert ist, werden nur diese fünf Segmente an [!DNL GPT] gesendet (nicht alle 100).

>[!NOTE]
>
>Die Anzahl der Schlüssel-Werte, die Sie senden können, ist unbegrenzt. Die [!DNL Google] Anfrage [!DNL URL] beschränkt jedoch die Anzahl der Zeichen, die sie akzeptieren kann. Siehe [Festlegen von Targeting und Größen mit GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Serverseitige Integration {#server-side-integration}

Wenden Sie sich an Ihren Audience Manager-Berater oder an die Kundenunterstützung, wenn Sie eine serverseitige Integration mit [!DNL Google Ad Manager] mithilfe von [!DNL GPT] einrichten möchten. Sie müssen Ihre [!DNL Google Ad Manager]-Konto-Netzwerk-ID und Zielgruppenverknüpfungskennung angeben.

>[!IMPORTANT]
>
>Wenn auf Ihren Webseiten die Bibliothek [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) ausgeführt wird, müssen Sie die serverseitige Integration mit Audience Manager verwenden. Wenn Sie [!DNL AMP] verwenden und eine clientseitige Integration mit [!DNL AMP] haben, müssen Sie zur serverseitigen Integration migrieren. Wenden Sie sich an Ihren Audience Manager-Berater oder an die Kundenunterstützung, um die Migration zu besprechen.

>[!MORELIKETHIS]
>
>* [GPT API-Referenzhandbuch](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

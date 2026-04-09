---
description: Übersicht über die Integration von Google Ad Manager mit Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Integrieren von Google Ad Manager mithilfe von Google Publisher Tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
TQID: https://experienceleague.adobe.com/29V5C3MbEondd3-qWLBfi3jaGid1I1UM9nYIl9nZWVo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 212
ht-degree: 0%

---

# Integrieren von [!DNL Google Ad Manager] (früher DFP) mithilfe von Google Publisher Tags (GPT)

Die folgenden Artikel bieten einen Überblick über die Integration von [!DNL Google Ad Manager] mit Google Publisher Tags (GPT). Sie können eine Server-seitige Integration verwenden oder GPT als Ziel einrichten, um Audience Manager-Segmentdaten an [!DNL Google Ad Manager] zu senden. Außerdem lernen Sie die erforderlichen Schritte zur Aufnahme [!DNL Google Ad Manager] Protokolldateien für das Reporting in Audience Manager kennen.

* [Anforderungen und Methoden für das Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  Sie können qualifizierte Segmente entweder über eine Client-seitige oder eine Server-seitige Integration an [!DNL Google Ad Manager] senden. Die Anforderungen und die zugehörigen Informationen zu beiden Methoden sind unten aufgeführt.

* [Erstellen eines GPT-Ziels](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  Sie können qualifizierte Segmente über eine Client-seitige (Browser-seitige) Integration oder eine Server-seitige Integration an [!DNL Google Ad Manager] senden. Wenn Sie sich für die Client-seitige Integration entscheiden, müssen Sie ein Cookie-basiertes Ziel für Google Publisher Tags in Audience Manager erstellen.

* [Ändern des GPT-setTargeting-API-Aufrufs](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  Fügen Sie eine if-Anweisung hinzu, um auf Audience Manager-Cookies zu prüfen, bevor Sie die setTargeting-Methode für das Google Publisher-Tag aufrufen.

* [Audience Manager-Code für Google Publisher-Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt ist eine JavaScript-Funktion, die Audience Manager-Cookie-Daten liest und diese Informationen an Google Publisher Tags sendet.

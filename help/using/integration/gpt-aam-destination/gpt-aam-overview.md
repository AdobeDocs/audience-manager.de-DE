---
description: Überblick über die Integration von Google Ad Manager mit Google Publisher Tags (GPT).
seo-description: Überblick über die Integration von Google Ad Manager mit Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrieren von Google Ad Manager mithilfe von Google Publisher Tags (GPT) in Adobe Audience Manager (AAM)
title: 'Integrieren von Google Ad Manager mit Google Publisher Tags (GPT) '
feature: Drittanbieterintegration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 10%

---

# Integrieren von [!DNL Google Ad Manager] (ehemals DFP) mit Google Publisher Tags (GPT)

Die unten aufgeführten Artikel bieten einen Überblick darüber, wie Sie [!DNL Google Ad Manager] mit Google Publisher Tags (GPT) integrieren können. Sie können eine serverseitige Integration verwenden oder GPT als Ziel einrichten, um Audience Manager-Segmentdaten an [!DNL Google Ad Manager] zu senden. Außerdem lernen Sie die erforderlichen Schritte zum Erfassen von Protokolldateien für die Berichterstellung in Audience Manager kennen.[!DNL Google Ad Manager]

* [Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Sie können qualifizierte Segmente entweder über eine Client-seitige Integration oder über eine Server-seitige Integration an [!DNL Google Ad Manager] senden. Die Anforderungen und damit zusammenhängenden Informationen zu beiden Methoden sind unten aufgeführt.

* [Erstellen eines GPT-Ziels](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an [!DNL Google Ad Manager] senden. Wenn Sie die Client-seitige Integration wählen, müssen Sie ein Cookie-basiertes Ziel für Google Publisher Tags in Audience Manager erstellen.

* [Ändern des GPT-API-Aufrufs setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Fügen Sie eine if -Anweisung hinzu, um vor dem Aufruf der Google Publisher Tag .setTargeting -Methode nach Audience Manager-Cookies zu suchen.

* [Audience Manager-Code für Google Publisher Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt ist eine JavaScript-Funktion, die Audience Manager-Cookie-Daten liest und diese Informationen an Google Publisher Tags sendet.

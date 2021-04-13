---
description: Übersicht über die Integration von Google Ad Manager mit Google Publisher Tags (GPT).
seo-description: Übersicht über die Integration von Google Ad Manager mit Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Google Ad Manager mithilfe von Google Publisher Tags (GPT) in Adobe Audience Manager (AAM) integrieren
title: 'Integrieren von Google Ad Manager mit Google Publisher Tags (GPT) '
feature: Integration von Drittanbietern
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 10%

---

# [!DNL Google Ad Manager] (ehemals DFP) mit Google Publisher Tags (GPT) integrieren

Die unten aufgeführten Artikel bieten einen Überblick darüber, wie [!DNL Google Ad Manager] mithilfe von Google Publisher Tags (GPT) integriert werden kann. Sie können eine serverseitige Integration verwenden oder GPT als Ziel einrichten, um Audience Manager-Segmentdaten an [!DNL Google Ad Manager] zu senden. Außerdem erfahren Sie, wie Sie die [!DNL Google Ad Manager] Protokolldateien für den Berichte in Audience Manager erfassen können.

* [Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Sie können qualifizierte Segmente entweder über eine clientseitige oder über eine serverseitige Integration an [!DNL Google Ad Manager] senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.

* [Erstellen eines GPT-Ziels](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an [!DNL Google Ad Manager] senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie in Audience Manager ein cookie-basiertes Ziel für Google Publisher Tags erstellen.

* [Ändern des GPT-API-Aufrufs setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   hinzufügen Sie eine if-Anweisung, um vor dem Aufruf der Google Publisher Tag .setTargeting-Methode nach Audience Manager-Cookies zu suchen.

* [Audience Manager-Code für Google Publisher Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt ist eine JavaScript-Funktion, die Audience Manager-Cookie-Daten liest und diese Informationen an Google Publisher-Tags sendet.

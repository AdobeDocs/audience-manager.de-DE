---
description: Übersicht über die Integration von DFP mit Google Publisher Tags (GPT).
seo-description: Übersicht über die Integration von DFP mit Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: DFP mit Google Publisher Tags (GPT) in Adobe Audience Manager (AAM) integrieren
title: DFP mit Google Publisher Tags (GPT) integrieren
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---


# DFP mit Google Publisher Tags (GPT) integrieren

Die unten aufgeführten Artikel bieten einen Überblick darüber, wie DFP mit Google Publisher Tags (GPT) integriert werden kann. Sie können eine serverseitige Integration verwenden oder GPT als Ziel einrichten, um Audience Manager-Segmentdaten an DFP zu senden. Außerdem erfahren Sie, wie Sie DFP-Protokolldateien für den Berichte in Audience Manager erfassen können.

* [Anforderungen und Methoden zum Senden von Segmenten an DFP mithilfe von Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Sie können qualifizierte Segmente entweder über eine clientseitige oder über eine serverseitige Integration an DFP senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.

* [GPT-Ziel erstellen](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an DFP senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie in Audience Manager ein cookie-basiertes Ziel für Google Publisher Tags erstellen.

* [Ändern des GPT-setTargeting-API-Aufrufs](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Hinzufügen Sie eine if-Anweisung, um vor dem Aufruf der Google Publisher Tag .setTargeting-Methode nach Audience Manager-Cookies zu suchen.

* [Audience Manager-Code für Google Publisher-Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt ist eine JavaScript-Funktion, die Audience Manager-Cookie-Daten liest und diese Informationen an Google Publisher-Tags sendet.

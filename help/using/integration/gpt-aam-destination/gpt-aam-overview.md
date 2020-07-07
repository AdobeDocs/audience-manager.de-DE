---
description: Übersicht über die Integration von Google Ad Manager mit Google Publisher Tags (GPT).
seo-description: Übersicht über die Integration von Google Ad Manager mit Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Google Ad Manager mit Google Publisher Tags (GPT) in Adobe Audience Manager (AAM) integrieren
title: Google Ad Manager mit Google Publisher Tags (GPT) integrieren
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Integrate [!DNL Google Ad Manager] (formerly DFP) using Google Publisher Tags (GPT)

Die unten aufgeführten Artikel bieten einen Überblick über die Integration [!DNL Google Ad Manager] mit Google Publisher Tags (GPT). Sie können eine serverseitige Integration verwenden oder GPT als Ziel einrichten, an das Audience Manager-Segmentdaten gesendet werden [!DNL Google Ad Manager]. Außerdem lernen Sie die erforderlichen Schritte zum Erfassen von [!DNL Google Ad Manager] Protokolldateien für den Berichte in Audience Manager kennen.

* [Anforderungen und Methoden zum Senden von Segmenten an Google Ad Manager mithilfe von Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Sie können qualifizierte Segmente entweder über eine clientseitige oder [!DNL Google Ad Manager] über eine serverseitige Integration senden. Die Anforderungen und damit zusammenhängende Informationen zu beiden Methoden sind unten aufgeführt.

* [Erstellen eines GPT-Ziels](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration [!DNL Google Ad Manager] an diese senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie in Audience Manager ein cookie-basiertes Ziel für Google Publisher Tags erstellen.

* [Ändern des GPT-API-Aufrufs setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Hinzufügen Sie eine if-Anweisung, um vor dem Aufruf der Google Publisher Tag .setTargeting-Methode nach Audience Manager-Cookies zu suchen.

* [Audience Manager-Code für Google Publisher Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt ist eine JavaScript-Funktion, die Audience Manager-Cookie-Daten liest und diese Informationen an Google Publisher-Tags sendet.

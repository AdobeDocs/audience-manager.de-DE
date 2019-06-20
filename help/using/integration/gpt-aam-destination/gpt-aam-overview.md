---
description: Übersicht zur Integration von DFP mit Google Publisher Tags (GPT).
seo-description: Übersicht zur Integration von DFP mit Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrieren von DFP mithilfe von Google Publisher Tags (GPT) in Adobe Audience Manager (AAM)
title: DFP mit Google Publisher Tags (GPT) integrieren
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# DFP mit Google Publisher Tags (GPT) integrieren

Die unten aufgeführten Artikel bieten einen Überblick darüber, wie DFP mithilfe von Google Publisher Tags (GPT) integriert werden kann. Sie können eine serverseitige Integration verwenden oder GPT als Ziel einrichten, um Audience Manager-Segmentdaten an DFP zu senden. Außerdem lernen Sie die erforderlichen Schritte zum Erfassen von DFP-Protokolldateien für die Berichterstellung in Audience Manager kennen.

* [Anforderungen und Methoden zum Senden von Segmenten an DFP mithilfe von Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Sie können qualifizierte Segmente entweder clientseitig oder über eine serverseitige Integration an DFP senden. Anforderungen und zugehörige Informationen zu beiden Methoden sind nachfolgend aufgeführt.

* [Erstellen eines GPT-Ziels](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Sie können qualifizierte Segmente über eine clientseitige (browserseitige) Integration oder eine serverseitige Integration an DFP senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie ein Cookie-basiertes Ziel für Google Publisher Tags in Audience Manager erstellen.

* [Ändern des GPT settargeting-API-Aufrufs](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Fügen Sie eine if-Anweisung hinzu, um vor dem Aufruf der Google Publisher Tag. settargeting-Methode nach Audience Manager-Cookies zu suchen.

* [Audience Manager-Code für Google Publisher Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   Aamgpt ist eine javascript-Funktion, die die Audience Manager-Cookie-Daten liest und diese Informationen an Google Publisher Tags sendet.

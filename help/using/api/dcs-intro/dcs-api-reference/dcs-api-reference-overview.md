---
description: Konzeptinformationen, Beschreibungen und Definitionen für DCS-API-Code, -Methoden und -Prozesse.
seo-description: Konzeptinformationen, Beschreibungen und Definitionen für DCS-API-Code, -Methoden und -Prozesse in Adobe Audience Manager (AAM).
seo-title: Übersicht über die DCS-API-Referenz in Adobe Audience Manager (AAM)
title: DCS-API-Referenz – Überblick
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 14%

---

# DCS-API-Referenz – Überblick

Konzeptbezogene Informationen, Beschreibungen und Definitionen für [!DNL DCS API]-Code, -Methoden und -Prozesse.

* [DCS-API-Methoden](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Senden Sie Daten mithilfe von GET- oder POST-Methoden an [!DNL DCS API].

* [DCS-Fehlercodes, Meldungen und Beispiele](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Von Datenerfassungsservern (Data Collection Servers, DCS) generierte Fehlercodes und Meldungen werden in numerischer Reihenfolge nach Code-ID aufgelistet.

* [ID-Überwachung und Blockierungsauflistung](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   Der DES überwacht die IDs, die er erhält, und fügt die IDs, die in einer ungewöhnlich hohen Senderate über einen kurzen Zeitraum gesendet werden, zu einer Blockierungsliste hinzu.

* [DCS-Regions-IDs, Standorte und Hostnamen](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Der regionale DCS-Server-Hostname ist erforderlich, um Aufrufe an den DES durchzuführen. Der Grund dafür ist, dass der DES Informationen in Rechenzentren speichert, die geografisch nah an den Site-Besuchern liegen. Ihre Abfragen funktionieren, wenn Sie sie an das falsche DCS senden, diese Aufrufe sind jedoch ineffizient und können die Antwort verzögern. Um eine DCS-Anfrage zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Hostnamen zu und formulieren Sie Ihre Abfrage mit dem richtigen Hostnamen.

* [Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Beim Aufrufen akzeptiert der DES Schlüsselwertdaten im standardmäßigen oder serialisierten Format. In diesem Abschnitt finden Sie Informationen zum Formatieren von standardmäßigen und serialisierten Schlüsselwertdaten.

* [Wettlaufsituationen (Race Conditions) und Fehlerbehandlung](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Beschreibt, wie Race-Bedingungen und DCS-Fehlerverarbeitung verhindert werden.

* [Unterstützte Attribute für DCS-API-Aufrufe](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Führt die Syntax und die unterstützten Attribute (oder Schlüssel-Wert-Paare) auf und beschreibt sie, die Sie an die Datenerfassungs-Server (DCS) übergeben können. Mithilfe dieser Informationen können Sie Ihre DCS-Anfragen formatieren und die von diesem System zurückgegebenen Parameter verstehen.

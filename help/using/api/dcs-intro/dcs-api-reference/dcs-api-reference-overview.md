---
description: Konzeptbezogene Informationen, Beschreibungen und Definitionen für DCS-API-Code, -Methoden und -Prozesse.
seo-description: Konzeptbezogene Informationen, Beschreibungen und Definitionen für DCS-API-Code, -Methoden und -Prozesse in Adobe Audience Manager (AAM).
seo-title: Übersicht über die DCS API-Referenz in Adobe Audience Manager (AAM)
title: Übersicht über die DCS API
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 1%

---


# Übersicht über die DCS API

Konzeptbezogene Informationen, Beschreibungen und Definitionen für [!DNL DCS API] Code, Methoden und Prozesse.

* [DCS API-Methoden](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Senden Sie Daten mit den Methoden GET oder POST an die [!DNL DCS API] Kommission.

* [DCS-Fehlercodes, Nachrichten und Beispiele](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Fehlercodes und Meldungen, die von den Datenerfassungsservern (Data Collection Servers, DCS) erzeugt wurden, werden in numerischer Reihenfolge nach Code-ID aufgeführt.

* [ID-Überwachung und -Denylierung](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   Der DCS überwacht die IDs, die er erhält, und fügt die IDs, die über einen kurzen Zeitraum ungewöhnlich hoch gesendet werden, zu einer blockierungsliste hinzu.

* [DCS-Regions-IDs, Speicherorte und Hostnamen](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Der regionale Hostname des DCS-Servers ist erforderlich, um den DCS aufzurufen. Der Grund dafür ist, dass der DCS Informationen in Rechenzentren speichert, die geografisch nahe an Site-Besuchern liegen. Ihre Abfragen funktionieren, wenn Sie sie an das falsche DCS senden, aber diese Aufrufe sind ineffizient und können die Antwort verzögern. Um eine DCS-Anforderung zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Hostnamen zu und erstellen Sie Ihre Abfrage mit dem richtigen Hostnamen.

* [Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Bei einem Aufruf akzeptiert der DCS wichtige Daten im standardmäßigen oder serialisierten Format. Informationen zum Formatieren von Standard- und serialisierten Schlüsselwertdaten finden Sie in diesem Abschnitt.

* [Rassenbedingungen und Fehlerbehandlung](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Beschreibt, wie Racebedingungen und DCS-Fehlerverarbeitung verhindert werden.

* [Unterstützte Attribute für DCS-API-Aufrufe](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Listen und Beschreibungen der Syntax und unterstützten Attribute (oder Schlüssel/Wert-Paare), die Sie an die Datenerfassungsserver (DCS) weitergeben können. Anhand dieser Informationen können Sie Ihre DCS-Anforderungen formatieren und die von diesem System zurückgegebenen Parameter verstehen.

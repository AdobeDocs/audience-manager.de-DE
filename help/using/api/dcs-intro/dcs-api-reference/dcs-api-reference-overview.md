---
description: Grundlegende Informationen, Beschreibungen und Definitionen für den DCS-API-Code, -methoden und -prozesse.
seo-description: Grundlegende Informationen, Beschreibungen und Definitionen für den DCS-API-Code, -methoden und -prozesse in Adobe Audience Manager (AAM).
seo-title: Übersicht über die DCS-API in Adobe Audience Manager (AAM)
title: Übersicht über die DCS-API
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Übersicht über die DCS-API

Grundlegende Informationen, Beschreibungen und Definitionen für den DCS-API-Code, -methoden und -prozesse.

* [DCS-API-Methoden](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Senden Sie Daten mit GET- oder POST-Methoden an die DCS-API.

* [DCS-Fehlercodes, Nachrichten und Beispiele](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Fehlercodes und Meldungen, die von den Datenerfassungsservern (DCS) in numerischer Reihenfolge durch Code-ID generiert wurden.

* [ID-Überwachung und Blacklisting](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-blacklisting.md)

   Das DCS überwacht die empfangenen IDs und die schwarzen Listen, die in einer kurzen Zeitspanne ungewöhnlich hoch gesendet werden.

* [DCS Regions-IDs, Speicherorte und Hostnamen](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Der regionale Hostname des DCS-Servers ist erforderlich, um dem DCS Aufrufe zu tätigen. Dies liegt daran, dass das DCS Informationen in Datenzentren speichert, die geografisch zu den Besuchern der Site nah sind. Ihre Abfragen funktionieren, wenn Sie sie an das falsche DCS senden, diese Aufrufe jedoch ineffizient sind und die Antwort verzögern können. Um eine DCS-Anforderung vorzunehmen, passen Sie die Regions-ID an den entsprechenden regionalen Hostnamen an und bilden Sie Ihre Abfrage mit dem richtigen Hostnamen.

* [Formatieren von Schlüsselwertpaaren in DCS-Aufrufen](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Bei einem Aufruf akzeptiert das DCS wichtige Wertdaten im Standard- oder serialisierten Format. Lesen Sie diesen Abschnitt, um Informationen zur Formatierung von standardmäßigen und serialisierten Schlüsselwertdaten zu erhalten.

* [Race Conditions und Fehlerbearbeitung](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Beschreibt, wie Sie Race-Bedingungen und die Verarbeitung von DCS-Fehlern verhindern.

* [Unterstützte Attribute für DCS-API-Aufrufe](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Listet die Syntax und unterstützte Attribute (oder Schlüssel/Wert-Paare) auf und beschreibt sie, die Sie an die Datenerfassungsserver (DCS) übergeben können. Diese Informationen können Ihnen dabei helfen, Ihre DCS-Anforderungen zu formatieren und die von diesem System zurückgegebenen Parameter zu verstehen.

---
description: Konzeptuelle Informationen, Beschreibungen und Definitionen für DCS-API-Code, Methoden und Prozesse.
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: Übersicht über die DCS-API-Referenz
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
TQID: https://experienceleague.adobe.com/e7W6fcETh4YArPa0k2hn11GMYgFjSU4AxALe92a7DhE
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 0%

---

# Übersicht über die DCS-API-Referenz

Konzeptuelle Informationen, Beschreibungen und Definitionen für [!DNL DCS API] Code, Methoden und Prozesse.

* [DCS-API-Methoden](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

  Senden Sie Daten mithilfe von GET oder POST-Methoden an die [!DNL DCS API].

* [DCS-Fehler-Codes, Meldungen und Beispiele](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

  Fehlercodes und Meldungen, die von den Datenerfassungs-Servern (DCS) generiert werden und in numerischer Reihenfolge nach Code-ID aufgeführt sind.

* [ID-Überwachung und -Blockierungsauflistung](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

  Der DCS überwacht die empfangenen IDs und fügt die IDs, die über einen kurzen Zeitraum mit ungewöhnlich hoher Rate gesendet werden, zu einer Blockierungsliste hinzu.

* [DCS-Regions-IDs, Standorte und Hostnamen](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

  Für Aufrufe an den DCS ist der regionale Hostname des DCS-Servers erforderlich. Dies liegt daran, dass der DCS Informationen in Rechenzentren speichert, die geografisch nah an den Besuchern der Website liegen. Ihre Abfragen funktionieren, wenn Sie sie an die falschen DCS senden, aber diese Aufrufe sind ineffizient und können die Antwort verzögern. Um eine DCS-Anfrage zu stellen, ordnen Sie die Regions-ID dem entsprechenden regionalen Host-Namen zu und erstellen Sie eine Abfrage mit dem richtigen Host-Namen.

* [Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

  Beim Aufruf akzeptiert der DCS Schlüssel-Wert-Daten im Standard- oder serialisierten Format. In diesem Abschnitt finden Sie Informationen zum Formatieren standardmäßiger und serialisierter Schlüssel-Wert-Daten.

* [Wettlaufbedingungen und Fehlerbehandlung](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

  Beschreibt, wie Racebedingungen und DCS-Fehlerbehandlung verhindert werden können.

* [Unterstützte Attribute für DCS-API-Aufrufe](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

  Listet die Syntax und die unterstützten Attribute (oder Schlüssel-Wert-Paare) auf, die Sie an die Datenerfassungs-Server (DCS) übergeben können, und beschreibt sie. Diese Informationen können Ihnen dabei helfen, Ihre DCS-Anfragen zu formatieren und die von diesem System zurückgegebenen Parameter zu verstehen.

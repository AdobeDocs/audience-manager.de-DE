---
description: Beschreibt, wie Race-Bedingungen und DCS-Fehlerverarbeitung verhindert werden.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Wettlaufsituationen (Race Conditions) und Fehlerbehandlung
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---

# Wettlaufsituationen, Ratenbegrenzung und Umgang mit Fehlern {#race-conditions-and-error-handling}

Beschreibt, wie Race-Bedingungen verhindert werden und [!DNL DCS] Fehlerbehandlung.

## Race Conditions verhindern {#prevent-race-conditions}

Eine Wettlaufsituation kann auftreten, wenn Sie mehrere Aufrufe gleichzeitig (oder in schneller Folge) an die [!DNL DCS] bevor sie auf die ersten Abfragen reagiert und Daten in das Cookie des Benutzers schreibt. Eine Race-Bedingung ist nicht wünschenswert, da sie Cookie-Daten beschädigen oder falsch überschreiben kann. Beachten Sie als Best Practice die folgenden Methoden, um dieses Problem zu vermeiden:

* Führen Sie keine gleichzeitigen Aufrufe oder Aufrufe in schneller Folge an die [!DNL DCS] von demselben Benutzer aus.
* Warten Sie, bis jede Antwort zurückgegeben wird, bevor Sie nachfolgende Aufrufe durchführen.

## Begrenzung {#rate-limiting}

Adobe kann eine Ratenbegrenzung einführen, wenn sie übermäßige DCS-API-Aufrufe erkennt, die sich negativ auf die Dienstverfügbarkeit auswirken könnten.

Wenn die Ratenbegrenzung aktiviert ist, erhalten Sie möglicherweise eine `429 Too Many Requests` HTTP-Antwortstatus-Code für Ihre DCS-Aufrufe. Versuchen Sie beim Erhalt dieser HTTP-Antwort die API-Aufrufe zu einem späteren Zeitpunkt erneut.

## Umgang mit Fehlern {#error-handling}

Die Fehlerbehebung ist auf ungültige oder schlecht geformte Abfragen beschränkt. Eine ungültige Anfrage gibt eine `HTTP 200 OK` Antwort und keine Daten. Außerdem wird die [!DNL DCS] stoppt die Verarbeitung einer Anforderung, verwirft Eigenschaftsdaten und gibt eine `HTTP 200 OK` Antwort, wenn ein Benutzer:

* Opt-out vom Tracking auf Audience Manager- oder Partnerebene.
* Sie stammt aus einer ungültigen/nicht ausgewählten geografischen Region.
* Deaktiviert Browser-Cookies (entweder alle oder Drittanbieter).

Siehe auch [DCS-Fehlercodes, Meldungen und Beispiele](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

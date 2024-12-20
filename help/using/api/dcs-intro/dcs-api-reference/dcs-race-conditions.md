---
description: Beschreibt, wie Racebedingungen und DCS-Fehlerbehandlung verhindert werden können.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Wettlaufbedingungen und Fehlerbehandlung
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# Wettlaufbedingungen, Ratenbegrenzung und Fehlerbehandlung {#race-conditions-and-error-handling}

Beschreibt, wie Racebedingungen und [!DNL DCS] Fehlerbehandlung verhindert werden können.

## Verhindern von Wettlaufsbedingungen {#prevent-race-conditions}

Eine Race-Condition kann auftreten, wenn Sie mehrere Aufrufe gleichzeitig (oder in schneller Folge) an die [!DNL DCS] senden, bevor diese die ersten Abfragen beendet und Daten in das Cookie des Benutzers geschrieben hat. Eine Race-Condition ist unerwünscht, da sie Cookie-Daten beschädigen oder unzulässig überschreiben kann. Als Best Practice sollten Sie die folgenden Methoden verwenden, um dieses Problem zu vermeiden:

* Führen Sie keine gleichzeitigen Aufrufe oder Aufrufe in schneller Folge an die [!DNL DCS] von demselben Benutzer aus.
* Warten Sie, bis jede Antwort zurückgegeben wird, bevor Sie nachfolgende Aufrufe ausführen.

## Ratenbegrenzung {#rate-limiting}

Adobe kann eine Ratenbegrenzung einführen, wenn zu viele DCS-API-Aufrufe entdeckt werden, die sich negativ auf die Service-Verfügbarkeit auswirken könnten.

Wenn die Ratenbegrenzung aktiviert ist, erhalten Sie möglicherweise einen `429 Too Many Requests` HTTP-Antwort-Status-Code für Ihre DCS-Aufrufe. Bitte API-Aufrufe zu einem späteren Zeitpunkt wiederholen, wenn Sie diese HTTP-Antwort erhalten.

## Fehlerbehandlung {#error-handling}

Die Fehlerbehandlung ist bei ungültigen oder schlecht geformten Abfragen beschränkt. Eine ungültige Anfrage gibt eine `HTTP 200 OK` Antwort und keine Daten zurück. Außerdem stoppt der [!DNL DCS] die Verarbeitung einer Anfrage, verwirft Eigenschaftsdaten und gibt eine `HTTP 200 OK` Antwort zurück, wenn ein Benutzer:

* Opt-out vom Tracking auf Audience Manager- oder Partnerebene.
* Stammt aus einer ungültigen/nicht ausgewählten geografischen Region.
* Deaktiviert Browser-Cookies (alle oder Drittanbieter).

Siehe auch [DCS-Fehler-Codes, Meldungen und Beispiele](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

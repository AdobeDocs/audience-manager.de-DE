---
description: Beschreibt, wie Race-Bedingungen und DCS-Fehlerverarbeitung verhindert werden.
seo-description: Beschreibt, wie Race-Bedingungen und DCS-Fehlerverarbeitung verhindert werden.
seo-title: Wettlaufsituationen (Race Conditions) und Fehlerbehandlung
solution: Audience Manager
title: Wettlaufsituationen (Race Conditions) und Fehlerbehandlung
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---

# Wettlaufsituationen (Race Conditions) und Fehlerbehandlung {#race-conditions-and-error-handling}

Beschreibt, wie Race-Bedingungen und die Fehlerbehandlung für [!DNL DCS] verhindert werden.

## Race Conditions verhindern {#prevent-race-conditions}

Es kann zu einer Wettlaufsituation kommen, wenn Sie mehrere Aufrufe gleichzeitig (oder in schneller Folge) an [!DNL DCS] senden, bevor diese auf die ersten Abfragen reagiert und Daten in das Cookie des Benutzers schreibt. Eine Race-Bedingung ist nicht wünschenswert, da sie Cookie-Daten beschädigen oder falsch überschreiben kann. Beachten Sie als Best Practice die folgenden Methoden, um dieses Problem zu vermeiden:

* Führen Sie keine gleichzeitigen Aufrufe oder Aufrufe in schneller Folge an [!DNL DCS] vom selben Benutzer durch.
* Warten Sie, bis jede Antwort zurückgegeben wird, bevor Sie nachfolgende Aufrufe durchführen.

## Umgang mit Fehlern {#error-handling}

Die Fehlerbehebung ist auf ungültige oder schlecht geformte Abfragen beschränkt. Eine ungültige Anfrage gibt eine `HTTP 200 OK` -Antwort und keine Daten zurück. Außerdem stoppt [!DNL DCS] die Verarbeitung einer Anforderung, verwirft Eigenschaftsdaten und gibt eine `HTTP 200 OK`-Antwort zurück, wenn ein Benutzer:

* Opt-out vom Tracking auf Audience Manager- oder Partnerebene.
* Sie stammt aus einer ungültigen/nicht ausgewählten geografischen Region.
* Deaktiviert Browser-Cookies (entweder alle oder Drittanbieter).

Siehe auch [DCS-Fehlercodes, Nachrichten und Beispiele](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

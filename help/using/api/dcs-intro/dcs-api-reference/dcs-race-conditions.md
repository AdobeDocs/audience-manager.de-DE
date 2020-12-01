---
description: Beschreibt, wie Racebedingungen und DCS-Fehlerverarbeitung verhindert werden.
seo-description: Beschreibt, wie Racebedingungen und DCS-Fehlerverarbeitung verhindert werden.
seo-title: Wettlaufsituationen (Race Conditions) und Fehlerbehandlung
solution: Audience Manager
title: Wettlaufsituationen (Race Conditions) und Fehlerbehandlung
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---


# Wettlaufsituationen (Race Conditions) und Fehlerbehandlung {#race-conditions-and-error-handling}

Beschreibt, wie Racebedingungen und die Fehlerbearbeitung von [!DNL DCS] verhindert werden.

## Racebedingungen verhindern {#prevent-race-conditions}

Eine Race-Bedingung kann auftreten, wenn Sie mehrere Aufrufe gleichzeitig (oder in schneller Folge) an das [!DNL DCS] senden, bevor diese auf die ersten Abfragen reagieren und Daten in das Cookie des Benutzers schreiben. Eine Racebedingung ist nicht wünschenswert, da sie Cookie-Daten beschädigen oder falsch überschreiben kann. Als Best Practice sollten Sie die folgenden Methoden in Erwägung ziehen, um dieses Problem zu vermeiden:

* Führen Sie keine gleichzeitigen Anrufe oder Aufrufe in rascher Folge vom gleichen Benutzer an das [!DNL DCS] aus.
* Warten Sie, bis jede Antwort zurückgegeben wird, bevor Sie nachfolgende Aufrufe durchführen.

## Fehlerbearbeitung {#error-handling}

Die Fehlerbearbeitung ist bei ungültigen oder schlecht geformten Abfragen eingeschränkt. Eine ungültige Anforderung gibt eine `HTTP 200 OK`-Antwort zurück und keine Daten. Außerdem beendet [!DNL DCS] die Verarbeitung einer Anforderung, verwirft Eigenschaftendaten und gibt eine `HTTP 200 OK`-Antwort zurück, wenn ein Benutzer:

* Schließt die Verfolgung auf Audience Manager- oder Partnerebene ab.
* Es stammt aus einer ungültigen/nicht ausgewählten geografischen Region.
* Deaktiviert Browser-Cookies (entweder alle oder Drittanbieter).

Siehe auch [DCS-Fehlercodes, Nachrichten und Beispiele](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
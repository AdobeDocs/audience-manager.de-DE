---
description: Beschreibt, wie Sie Race-Bedingungen und die Verarbeitung von DCS-Fehlern verhindern.
seo-description: Beschreibt, wie Sie Race-Bedingungen und die Verarbeitung von DCS-Fehlern verhindern.
seo-title: Race Conditions und Fehlerbearbeitung
solution: Audience Manager
title: Race Conditions und Fehlerbearbeitung
uuid: b 0 aac 60-6732-4 e 96-87 a 5-40 ba 2755 e 02 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Race Conditions und Fehlerbearbeitung {#race-conditions-and-error-handling}

Beschreibt, wie Sie Race-Bedingungen und [!UICONTROL DCS] Fehlerbehandlung vermeiden.

## Verhindern von Race Conditions {#prevent-race-conditions}

Eine Race-Bedingung kann auftreten, wenn Sie mehrere Aufrufe gleichzeitig (oder in schnelle Folge) an den [!UICONTROL DCS] vorherigen Abruf senden, bevor sie auf die ersten Abfragen reagieren und Daten in das Cookie des Benutzers schreiben. Eine Race-Bedingung ist nicht wünschenswert, da Cookie-Daten beschädigt oder falsch überschrieben werden können. Es empfiehlt sich, die folgenden Methoden zu beachten, um dieses Problem zu vermeiden:

* Machen Sie dem Benutzer [!UICONTROL DCS] keine gleichzeitigen Aufrufe oder Aufrufe in schnelle Folge.
* Warten Sie, bis jede Antwort zurückgegeben wird, bevor Sie nachfolgende Aufrufe durchführen.

## Fehlerbearbeitung {#error-handling}

Die Fehlerbearbeitung ist bei ungültigen oder schlecht formatierten Abfragen eingeschränkt. Eine ungültige Anforderung gibt eine `HTTP 200 OK` Antwort und keine Daten zurück. Außerdem werden bei der [!UICONTROL DCS] Bearbeitung einer Anforderung die Eigenschaftendaten verworfen und eine `HTTP 200 OK` Antwort zurückgegeben, wenn ein Benutzer:

* Deaktiviert die Verfolgung auf Audience Manager oder Partner-Ebene.
* Stammt aus einer ungültigen/nicht ausgewählten geografischen Region.
* Deaktiviert Browser-Cookies (entweder alle oder Drittanbieter).

Siehe auch [DCS-Fehlercodes, Nachrichten und Beispiele](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
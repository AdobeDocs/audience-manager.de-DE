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


# Race Conditions and Error Handling {#race-conditions-and-error-handling}

Describes how to prevent race conditions and [!UICONTROL DCS] error handling.

## Preventing Race Conditions {#prevent-race-conditions}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!UICONTROL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. Eine Race-Bedingung ist nicht wünschenswert, da Cookie-Daten beschädigt oder falsch überschrieben werden können. Es empfiehlt sich, die folgenden Methoden zu beachten, um dieses Problem zu vermeiden:

* Don't make simultaneous calls, or calls in rapid succession, to the [!UICONTROL DCS] from the same user.
* Warten Sie, bis jede Antwort zurückgegeben wird, bevor Sie nachfolgende Aufrufe durchführen.

## Error Handling {#error-handling}

Die Fehlerbearbeitung ist bei ungültigen oder schlecht formatierten Abfragen eingeschränkt. An invalid request returns an `HTTP 200 OK` response and no data. Also, the [!UICONTROL DCS] stops processing a request, discards trait data, and returns an `HTTP 200 OK` response when a user:

* Deaktiviert die Verfolgung auf Audience Manager oder Partner-Ebene.
* Stammt aus einer ungültigen/nicht ausgewählten geografischen Region.
* Deaktiviert Browser-Cookies (entweder alle oder Drittanbieter).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
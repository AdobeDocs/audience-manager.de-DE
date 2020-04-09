---
description: Wir verwenden keinen Audience Manager, aber es werden Audience Manager-Javascript-Aufrufe im Javascript-Debugger angezeigt - Warum?
seo-description: Wir verwenden nicht, aber wir sehen Audience Manager Javascript-Aufrufe im Javascript-Debugger - Warum?
seo-title: Wir verwenden keinen Audience Manager, aber es werden Audience Manager-Javascript-Aufrufe im Javascript-Debugger angezeigt - Warum?
solution: Audience Manager
title: Wir verwenden keinen Audience Manager, aber es werden Audience Manager-Javascript-Aufrufe im Javascript-Debugger angezeigt - Warum?
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# Wir sind kein Audience Manager-Kunde, aber sehen Sie sich die Audience Manager JavaScript-Aufrufe auf unserer Site an.

## Frage

Adobe Audience Manager wird nicht verwendet, aber im Javascript-Debugger werden JavaScript-Aufrufe von Audience Manager angezeigt.  Warum sollte das passieren?

## Antwort

Es ist wahrscheinlich, dass Sie den Besucher-ID-Dienst für Ihre Eigenschaft ausführen. Wenn Sie dies tun, bezieht sich diese AAM-Referenz nicht unbedingt auf die Eigenschaft, die Audience Manager ausführt, aber es bedeutet, dass Audience Manager diesen Dienst tatsächlich aktiviert.

Beachten Sie, dass der AAM-Aufruf in der Regel zur Synchronisierung von Set-Kunden-IDs erfolgt.

---
description: Wir verwenden Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt. Warum?
seo-description: Wir verwenden Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt. Warum?
seo-title: Wir verwenden Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt. Warum?
solution: Audience Manager
title: Wir verwenden Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt. Warum?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Wir sind kein Audience Manager-Kunde, sehen aber die Javascript-Aufrufe von Audience Manager auf unserer Website.

## Frage

Wir verwenden Adobe Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt.

Warum passiert das?

## Antwort

Wahrscheinlich führen Sie [Experience Cloud Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html) für Ihre Eigenschaft aus. Wenn dies der Fall ist, bezieht sich dieser Verweis auf Audience Manager nicht unbedingt auf die Eigenschaft, für die Audience Manager ausgeführt wird. Stattdessen bedeutet dies, dass Audience Manager diesen Service betreibt.

Der Audience Manager-Server-Aufruf wird normalerweise zur [Synchronisierung von Kunden-IDs](https://docs.adobe.com/content/help/de-DE/id-service/using/id-service-api/methods/setcustomerids.html) durchgeführt.

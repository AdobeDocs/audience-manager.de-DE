---
description: Wir verwenden Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt. Warum?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: Wir verwenden Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt. Warum?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 98%

---

# Wir sind kein Audience Manager-Kunde, sehen aber die Javascript-Aufrufe von Audience Manager auf unserer Website.

## Frage

Wir verwenden Adobe Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt.

Warum passiert das?

## Antwort

Wahrscheinlich führen Sie [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) für Ihre Eigenschaft aus. Wenn dies der Fall ist, bezieht sich dieser Verweis auf Audience Manager nicht unbedingt auf die Eigenschaft, für die Audience Manager ausgeführt wird. Stattdessen bedeutet dies, dass Audience Manager diesen Service betreibt.

Der Audience Manager-Server-Aufruf wird normalerweise zur [Synchronisierung von Kunden-IDs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) durchgeführt.

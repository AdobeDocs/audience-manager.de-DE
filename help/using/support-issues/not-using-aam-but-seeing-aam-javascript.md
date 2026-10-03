---
description: Wir verwenden Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt. Warum?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: Wir verwenden Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt. Warum?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: 'https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 88%
---
# Wir sind kein Audience Manager-Kunde, sehen aber die Javascript-Aufrufe von Audience Manager auf unserer Website.

## Frage

Wir verwenden Adobe Audience Manager nicht, aber im Javascript-Debugger werden Javascript-Aufrufe von Audience Manager angezeigt.

Warum passiert das?

## Antwort

Wahrscheinlich führen Sie [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=de) für Ihre Eigenschaft aus. Wenn dies der Fall ist, bezieht sich dieser Verweis auf Audience Manager nicht unbedingt auf die Eigenschaft, für die Audience Manager ausgeführt wird. Stattdessen bedeutet dies, dass Audience Manager diesen Service betreibt.

Der Audience Manager-Server-Aufruf wird normalerweise zur [Synchronisierung von Kunden-IDs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=de) durchgeführt.

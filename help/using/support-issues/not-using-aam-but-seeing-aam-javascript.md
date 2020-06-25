---
description: Wir verwenden keinen Audience Manager, aber wir sehen Audience Manager Javascript-Aufrufe im Javascript-Debugger - Warum?
seo-description: Wir verwenden nicht, aber wir sehen Audience Manager Javascript-Aufrufe im Javascript-Debugger - Warum?
seo-title: Wir verwenden keinen Audience Manager, aber wir sehen Audience Manager Javascript-Aufrufe im Javascript-Debugger - Warum?
solution: Audience Manager
title: Wir verwenden keinen Audience Manager, aber wir sehen Audience Manager Javascript-Aufrufe im Javascript-Debugger - Warum?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 1%

---


# Wir sind kein Audience Manager-Kunde, aber sehen Sie sich die Audience Manager Javascript-Aufrufe auf unserer Website.

## Frage

Wir verwenden keinen Adobe Audience Manager, aber wir sehen Audience Manager-Javascript-Aufrufe im Javascript-Debugger.

Warum geschieht das?

## Antwort

Es ist wahrscheinlich, dass Sie den [Experience Cloud-Identitätsdienst](https://docs.adobe.com/content/help/en/id-service/using/home.html) für Ihre Eigenschaft ausführen. Ist dies der Fall, bezieht sich der Verweis auf diesen Audience Manager nicht unbedingt auf die Eigenschaft, die Audience Manager ausführt. Stattdessen bedeutet es, dass Audience Manager diesen Dienst antreibt.

Der Audience Manager-Server-Aufruf wird in der Regel zur [Synchronisierung von Kunden-IDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)durchgeführt.

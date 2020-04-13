---
description: Wir verwenden keinen Audience Manager, aber es werden Audience Manager-Javascript-Aufrufe im Javascript-Debugger angezeigt - Warum?
seo-description: Wir verwenden nicht, aber wir sehen Audience Manager Javascript-Aufrufe im Javascript-Debugger - Warum?
seo-title: Wir verwenden keinen Audience Manager, aber es werden Audience Manager-Javascript-Aufrufe im Javascript-Debugger angezeigt - Warum?
solution: Audience Manager
title: Wir verwenden keinen Audience Manager, aber es werden Audience Manager-Javascript-Aufrufe im Javascript-Debugger angezeigt - Warum?
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# Wir sind kein Audience Manager-Kunde, aber sehen Sie sich die Audience Manager JavaScript-Aufrufe auf unserer Site an.

## Frage

Adobe Audience Manager wird nicht verwendet, aber im Javascript-Debugger werden JavaScript-Aufrufe von Audience Manager angezeigt.

Warum geschieht das?

## Antwort

Es ist wahrscheinlich, dass Sie den [Experience Cloud-Identitätsdienst](https://docs.adobe.com/content/help/en/id-service/using/home.html) für Ihre Eigenschaft ausführen. Ist dies der Fall, bezieht sich der Verweis auf Audience Manager nicht unbedingt auf die Eigenschaft, die Audience Manager ausführt. Stattdessen bedeutet dies, dass Audience Manager diesen Dienst aktiviert.

Der Audience Manager-Serveraufruf wird normalerweise zur [Synchronisierung von Kunden-IDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)durchgeführt.

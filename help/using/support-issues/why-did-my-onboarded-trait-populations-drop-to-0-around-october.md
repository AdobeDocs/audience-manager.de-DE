---
description: Um den 14. Oktober 2019 herum bemerkte ich, dass meine integrierten Eigenschaftspopulationen für das Geräte-ID-Diagramm auf 0 gefallen sind, obwohl sie zuvor viel höher waren.
seo-description: Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.
seo-title: Why did my Onboarded trait populations drop to 0 around October 15th?
solution: Audience Manager
title: Warum sind meine integrierten Eigenschaftspopulationen um den 15. Oktober auf 0 zurückgegangen?
feature: Support
exl-id: e93cee15-7d05-4f81-8f14-a3e03f214542
TQID: https://experienceleague.adobe.com/AMglvoNdxz7SDKZN3B52mBnFiJVRQvzsAvykIv2foCo
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 100%

---

# Warum sind meine integrierten Eigenschaftspopulationen um den 15. Oktober auf 0 zurückgegangen? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Frage

Um den 14. Oktober 2019 herum bemerkte ich, dass meine integrierten Eigenschaftspopulationen für das Geräte-ID-Diagramm auf 0 gefallen sind, obwohl sie zuvor viel höher waren. Warum ist das passiert?

![Bild des Abfalls der Geräte-ID](assets/device_id_populationdrop.png)

## Antwort

Am 15. Oktober wurde die Funktionalität der Profilzusammenführungsrichtlinien von Audience Manager durch eine Aktualisierung dahingehend geändert, dass integrierte Daten, die von einer CRM-ID eingegeben wurden, die in eine geräteübergreifende Datenquelle hochgeladen wurde, nicht mehr mit Geräte-IDs realisiert werden.  Bisher wurde Audience Manager sowohl für die geräteübergreifende ID (oder CRM-ID) als auch für das Kopieren dieser Realisierungen in die zugehörigen Audience Manager UUIDs (Geräte-IDs) implementiert.  Die Änderung wurde vorgenommen, um die Art der Eigenschaftsdaten und der realisierten Profile genauer widerzuspiegeln.

Zur Ansicht der Eigenschaftsrealisierungen wählen Sie bitte die Option „Cross-Device ID“ aus der Dropdown-Liste oben rechts in der Ansicht „Trait“ aus.

![Anzeigen von Realisierungen nach geräteübergreifender ID](assets/deviceid-crossdevice.png)

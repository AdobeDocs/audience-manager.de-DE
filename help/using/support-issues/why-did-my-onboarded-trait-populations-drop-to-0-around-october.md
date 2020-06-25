---
description: Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren.
seo-description: Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren.
seo-title: Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken?
solution: Audience Manager
title: Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---


# Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Frage

Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren. Warum ist das passiert?

![Ablegen der Geräte-ID](assets/device_id_populationdrop.png)

## Antwort

Am 15. Oktober wurde eine Aktualisierung der Funktionalität der Profil Merge Rule des Audience Managers dahingehend geändert, dass Onboarded-Daten, die von einer CRM-ID stammen, die auf eine geräteübergreifende Datenquelle hochgeladen wurde, nicht mehr für Geräte-IDs implementiert werden.  Bisher wurde Audience Manager sowohl für die geräteübergreifende ID (oder CRM-ID) als auch für das Kopieren dieser Realisierungen in die zugehörigen Audience Manager-UUIDs (Geräte-IDs) erkannt.  Die Änderung wurde vorgenommen, um die Natur der Eigenschaftsdaten und die Profile, die realisiert werden, genauer widerzuspiegeln.

Zur Ansicht der Eigenschaften wählen Sie bitte die Option &quot;Geräteübergreifende ID&quot;aus der Dropdown-Liste oben rechts in der Ansicht &quot;Eigenschaften&quot;.

![Ansichten anhand der geräteübergreifenden ID](assets/deviceid-crossdevice.png)
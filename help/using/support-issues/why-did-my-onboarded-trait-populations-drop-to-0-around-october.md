---
description: Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren.
seo-description: Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren.
seo-title: Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken?
solution: Audience Manager
title: Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken?
translation-type: tm+mt
source-git-commit: 0487a15c5fcd0e653bedf0e7fd8326f5cc363660

---


# Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Frage

Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren. Warum ist das passiert?

![Ablegen der Geräte-ID](assets/device_id_populationdrop.png)

## Antwort

Am 15. Oktober wurde eine Aktualisierung der Profil Merge Rule-Funktion von Audience Manager dahingehend geändert, dass Onboarded-Daten, die von einer CRM-ID, die auf eine geräteübergreifende Datenquelle hochgeladen wurde, herausgegeben wurden, nicht mehr für Geräte-IDs realisiert werden.  Bisher wurde Audience Manager sowohl für die geräteübergreifende ID (oder CRM-ID) als auch für das Kopieren dieser Realisierungen in die zugehörigen Audience Manager-UUIDs (Geräte-IDs) implementiert.  Die Änderung wurde vorgenommen, um die Natur der Eigenschaftsdaten und die Profile, die realisiert werden, genauer widerzuspiegeln.

Zur Ansicht der Eigenschaften wählen Sie bitte die Option &quot;Geräteübergreifende ID&quot;aus der Dropdown-Liste oben rechts in der Ansicht &quot;Eigenschaften&quot;.

![Ansichten anhand der geräteübergreifenden ID](assets/deviceid-crossdevice.png)
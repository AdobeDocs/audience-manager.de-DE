---
description: Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren.
seo-description: Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren.
seo-title: Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken?
solution: Audience Manager
title: Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken?
translation-type: tm+mt
source-git-commit: eb129bbf642cb666ce3ea05ff606c051e02f4d1e

---


# Warum sind meine Trait-Populationen mit Onboarded um den 15. Oktober auf 0 gesunken? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Etwa am 14. Oktober 2019 bemerkte ich, dass die Populationen für die integrierten Eigenschaften des Geräte-ID-Diagramms auf 0 gesunken sind, wo sie früher viel höher waren.

![Ablegen der Geräte-ID](/help/using/support-issues/assets/device_id_populationdrop.png)

**Antwort**

Am 15. Oktober wurde eine Aktualisierung der Profilzusammenführungsregel-Funktion von Audience Manager dahingehend geändert, dass Onboarded-Daten, die von einer CRM-ID, die auf eine geräteübergreifende Datenquelle hochgeladen wurde, herausgegeben wurden, nicht mehr für Geräte-IDs implementiert werden.  Zuvor wurde Audience Manager sowohl für die geräteübergreifende ID (oder CRM-ID) als auch für das Kopieren dieser Realisierungen in die entsprechenden UUIDs (Geräte-IDs) von Audience Manager erkannt.  Die Änderung wurde vorgenommen, um die Art der Eigenschaftsdaten und die zu realisierenden Profile genauer widerzuspiegeln.

Um die Eigenschaften anzuzeigen, wählen Sie bitte die Option &quot;Geräteübergreifende ID&quot;aus der Dropdown-Liste oben rechts in der Ansicht &quot;Eigenschaften&quot;.

![Realisierungen nach geräteübergreifender ID anzeigen](/help/using/support-issues/assets/deviceid-crossdevice.png)


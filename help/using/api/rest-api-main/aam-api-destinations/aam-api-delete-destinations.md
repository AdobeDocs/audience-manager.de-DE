---
description: DELETE- und POST-Methoden zum Entfernen von Zielen und Segmentzuordnungen.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Löschen von Zielen
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
TQID: https://experienceleague.adobe.com/hONQoLCrSxcMnDY7yPf-RX22Etj3WIykBhKEx1IyRMo
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 104
ht-degree: 0%

---

# Löschen von Zielen {#delete-destinations}

`DELETE` und `POST` Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.

<!-- r_delete_destinations_all.xml -->

## Löschen eines Ziels

Eine `DELETE` Methode, die ein Ziel entfernt.

>[!NOTE]
>
>Sie müssen alle Segmentzuordnungen entfernen, bevor Sie ein Ziel löschen können.

* Anfrage: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Antwort: Gibt bei Erfolg Code `204 No Content` zurück.

## Massenlöschziele

Entfernen Sie mehrere Ziele mit dieser `POST`. Übergeben Sie Ziel-IDs ( `destinationId`) mit einem -Array im Anfragetext.

* Anfrage: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Antwort: Gibt bei Erfolg Code `204 No Content` zurück.

## Löschen von Zielzuordnungen nach Segmentzuordnungs-ID

Eine `POST` Methode, die Zielzuordnungen entsprechend der angegebenen Segment-ID entfernt.

* Anfrage: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Antwort: Gibt bei Erfolg Code `204 No Content` zurück.

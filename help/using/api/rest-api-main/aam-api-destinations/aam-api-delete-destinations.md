---
description: DELETE- und POST-Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Löschen von Zielen
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
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

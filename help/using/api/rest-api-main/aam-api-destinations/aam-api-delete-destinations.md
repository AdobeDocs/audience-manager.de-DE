---
description: DELETE- und POST-Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.
seo-description: DELETE- und POST-Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.
seo-title: Ziele löschen
solution: Audience Manager
title: Ziele löschen
uuid: 38 fb 2228-e 564-49 a 3-9930-3139 f 8799 a 8 f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Delete Destinations {#delete-destinations}

`DELETE` und `POST` Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.

<!-- r_delete_destinations_all.xml -->

## Ein Ziel löschen

`DELETE` Eine Methode, die ein Ziel entfernt.

>[!NOTE]
>
>Sie müssen alle Segmentzuordnungen entfernen, bevor Sie ein Ziel löschen können.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Response: Returns code `204 No Content` if successful.

## Ziele für Massenlöschung

Remove multiple destinations with this `POST` method. Pass in destination IDs ( `destinationId`) with an array in the request body.

* Anfrage: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Response: Returns code `204 No Content` if successful.

## Zielzuordnungen nach Segmentzuordnungs-ID löschen

A `POST` method that removes destination mappings according to the specified segment ID.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Response: Returns code `204 No Content` if successful.
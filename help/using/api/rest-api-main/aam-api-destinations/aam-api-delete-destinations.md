---
description: DELETE- und POST-Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.
seo-description: DELETE- und POST-Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.
seo-title: Ziele löschen
solution: Audience Manager
title: Ziele löschen
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Ziele löschen {#delete-destinations}

`DELETE` und `POST` Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.

<!-- r_delete_destinations_all.xml -->

## Ziel löschen

Eine `DELETE` Methode, die ein Ziel entfernt.

>[!NOTE]
>
>Sie müssen alle Segmentzuordnungen entfernen, bevor Sie ein Ziel löschen können.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Antwort: Gibt Code `204 No Content` bei erfolgreicher Ausführung zurück.

## Massenlöschziele

Entfernen Sie mehrere Ziele mit dieser `POST` Methode. Geben Sie Ziel-IDs ( `destinationId`) mit einem Array im Anforderungstext ein.

* Anfrage: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Antwort: Gibt Code `204 No Content` bei erfolgreicher Ausführung zurück.

## Zielzuordnungen nach Segmentzuordnungs-ID löschen

Eine `POST` Methode, die Zielzuordnungen gemäß der angegebenen Segment-ID entfernt.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Antwort: Gibt Code `204 No Content` bei erfolgreicher Ausführung zurück.
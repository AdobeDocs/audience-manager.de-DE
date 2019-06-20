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


# Ziele löschen {#delete-destinations}

`DELETE` und `POST` Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.

<!-- r_delete_destinations_all.xml -->

## Ein Ziel löschen

`DELETE` Eine Methode, die ein Ziel entfernt.

>[!NOTE]
>
>Sie müssen alle Segmentzuordnungen entfernen, bevor Sie ein Ziel löschen können.

* Anforderung: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Antwort: Gibt Code `204 No Content` zurück, wenn erfolgreich.

## Ziele für Massenlöschung

Entfernen Sie mehrere Ziele mit dieser `POST` Methode. Geben Sie Ziel-IDs ( `destinationId`) mit einem Array im Anforderungstext an.

* Anfrage: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Antwort: Gibt Code `204 No Content` zurück, wenn erfolgreich.

## Zielzuordnungen nach Segmentzuordnungs-ID löschen

Eine `POST` Methode, die Zielzuordnungen entsprechend der angegebenen Segment-ID entfernt.

* Anforderung: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/segments/`*`<mappingId>`*
* Antwort: Gibt Code `204 No Content` zurück, wenn erfolgreich.
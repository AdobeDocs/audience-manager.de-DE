---
description: DELETE- und POST-Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.
seo-description: DELETE- und POST-Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.
seo-title: Löschen von Zielen
solution: Audience Manager
title: Löschen von Zielen
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 7%

---


# Löschen von Zielen {#delete-destinations}

`DELETE` und  `POST` Methoden, mit denen Sie Ziele und Segmentzuordnungen entfernen können.

<!-- r_delete_destinations_all.xml -->

## Ziel löschen

Eine `DELETE`-Methode, die ein Ziel entfernt.

>[!NOTE]
>
>Sie müssen alle Segmentzuordnungen entfernen, bevor Sie ein Ziel löschen können.

* Anfrage: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Antwort: Gibt Code `204 No Content` zurück, falls erfolgreich.

## Massenlöschziele

Entfernen Sie mehrere Ziele mit dieser `POST`-Methode. Geben Sie Ziel-IDs ( `destinationId`) mit einem Array im Anforderungstext ein.

* Anfrage: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Antwort: Gibt Code `204 No Content` zurück, falls erfolgreich.

## Zielzuordnungen nach Segmentzuordnungs-ID löschen

Eine `POST`-Methode, die Zielzuordnungen gemäß der angegebenen Segment-ID entfernt.

* Anfrage: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Antwort: Gibt Code `204 No Content` zurück, falls erfolgreich.
---
description: Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit Segment Builder anhalten oder löschen.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Ausgesetzte und gelöschte Segmente
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Ausgesetzte und gelöschte Segmente {#paused-and-deleted-segments}

Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mithilfe von [!UICONTROL Segment Builder] anhalten oder löschen.

## Zugriff auf die Steuerelemente Pause und Löschen

Bewegen Sie den Mauszeiger über einen Segmentnamen in der Segmentliste, um die **[!UICONTROL pause]**- und **[!UICONTROL delete]** anzuzeigen (in der [!UICONTROL Actions] Spalte). Diese Funktionen wirken sich wie unten beschrieben auf Segmente aus.

## Ausgesetzte Segmentfunktion

Ein pausiertes (deaktiviertes) Segment:

* Beendet die Segmentierung neuer, qualifizierter Benutzer.
* Behält den Segmentierungsstatus/die Mitgliedschaft eines Benutzers bei (entfernt keinen Benutzer aus dem Segment).
* verbleibt in der Segmentliste und kann reaktiviert werden
* Sendet keine Daten an verknüpfte Ziele.
* Gibt Daten aus den verfügbaren Berichten zurück (bis zum Deaktivierungsdatum).

## Gelöschte Segmentfunktionen

Ein gelöschtes Segment:

* Beendet die Segmentierung neuer, qualifizierter Benutzer.
* Entfernt qualifizierte Benutzer aus der Segmentzugehörigkeit.
* wird aus der Segmentliste entfernt.
* Löschen nicht rückgängig gemacht werden.
* Sendet keine Daten an verknüpfte Ziele.
* Gibt keine Daten aus den verfügbaren Berichten zurück.

>[!NOTE]
>
>Sie können Segmente auch mithilfe einer [!DNL API] Methode anhalten und löschen. Weitere Informationen finden Sie unter [REST-APIs](../../api/rest-api-main/rest-api-main.md).

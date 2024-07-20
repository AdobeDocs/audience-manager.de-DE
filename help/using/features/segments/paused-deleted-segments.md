---
description: Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit Segment Builder anhalten oder löschen.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Angehaltene und gelöschte Segmente
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Angehaltene und gelöschte Segmente {#paused-and-deleted-segments}

Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit [!UICONTROL Segment Builder] anhalten oder löschen.

## Zugriff auf die Steuerelemente zum Anhalten und Löschen

Bewegen Sie den Mauszeiger über einen Segmentnamen in der Segmentliste, um die Symbole **[!UICONTROL pause]** und **[!UICONTROL delete]** anzuzeigen (in der Spalte [!UICONTROL Actions] ). Diese Funktionen wirken sich wie unten beschrieben auf Segmente aus.

## Angehaltene Segmentfunktionen

Ein angehaltenes (deaktiviertes) Segment:

* Stoppt die Segmentierung neuer, qualifizierter Benutzer.
* Behält den Segmentierungsstatus eines Benutzers bei (entfernt einen Benutzer nicht aus dem Segment).
* Verbleibt in der Segmentliste und kann reaktiviert werden.
* Sendet keine Daten an verknüpfte Ziele.
* Gibt Daten in den verfügbaren Berichten zurück (bis zum Deaktivierungsdatum).

## Funktion für gelöschte Segmente

Ein gelöschtes Segment:

* Stoppt die Segmentierung neuer, qualifizierter Benutzer.
* Entfernt qualifizierte Benutzer aus der Segmentzugehörigkeit.
* wird aus der Segmentliste entfernt.
* Die Löschung kann nicht rückgängig gemacht werden.
* Sendet keine Daten an verknüpfte Ziele.
* Gibt in den verfügbaren Berichten keine Daten zurück.

>[!NOTE]
>
>Sie können Segmente auch mit der Methode [!DNL API] anhalten und löschen. Weitere Informationen finden Sie unter [REST-APIs](../../api/rest-api-main/rest-api-main.md).

---
description: Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit Segment Builder anhalten oder löschen.
seo-description: Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit Segment Builder anhalten oder löschen.
seo-title: Angehaltene und gelöschte Segmente
solution: Audience Manager
title: Angehaltene und gelöschte Segmente
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: 'Segmente '
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 6%

---

# Angehaltene und gelöschte Segmente {#paused-and-deleted-segments}

Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit [!UICONTROL Segment Builder] anhalten oder löschen.

## Zugriff auf die Steuerelemente zum Anhalten und Löschen

Bewegen Sie den Mauszeiger über einen Segmentnamen in der Segmentliste, um die Symbole **[!UICONTROL pause]** und **[!UICONTROL delete]** anzuzeigen (in der Spalte [!UICONTROL Actions] ). Diese Funktionen wirken sich wie unten beschrieben auf Segmente aus.

## Angehaltene Segmentfunktionen

Ein angehaltenes (deaktiviertes) Segment:

* Stoppt die Segmentierung neuer, qualifizierter Benutzer.
* Behält den Segmentierungsstatus/die Mitgliedschaft eines Benutzers bei (entfernt einen Benutzer nicht aus dem Segment).
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
>Sie können Segmente auch mithilfe einer [!DNL API] -Methode anhalten und löschen. Weitere Informationen finden Sie unter [REST-APIs](../../api/rest-api-main/rest-api-main.md).

---
description: Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit dem Segmentaufbau anhalten oder löschen.
seo-description: Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit dem Segmentaufbau anhalten oder löschen.
seo-title: Angehaltene und gelöschte Segmente
solution: Audience Manager
title: Angehaltene und gelöschte Segmente
uuid: 88 efe 4 af-f 9 a 4-4 bce -920 a -352 bd 4 d 505 dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Angehaltene und gelöschte Segmente {#paused-and-deleted-segments}

Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment anhalten oder löschen [!UICONTROL Segment Builder].

## Zugriff auf die Steuerelemente &quot;Pause&quot; und&quot; Löschen «

Bewegen Sie den Mauszeiger über einen Segmentnamen in der Segmentliste, um die Symbole und **[!UICONTROL pause]****[!UICONTROL delete]** Symbole (in der [!UICONTROL Actions] Spalte) anzuzeigen. Diese Funktionen wirken sich wie unten beschrieben auf Segmente aus.

## Angehaltene Segmentfunktionen

Ein angehaltenes (deaktiviertes) Segment:

* Stoppt die Segmentierung neuer, qualifizierter Benutzer.
* Behält den Segmentierungsstatus/die Mitgliedschaft eines Benutzers bei (wird kein Benutzer aus dem Segment entfernt).
* Verbleibt in der Segmentliste und kann reaktiviert werden.
* Sendet keine Daten an verbundene Ziele.
* Gibt Daten in den verfügbaren Berichten zurück (bis zum Deaktivierungsdatum).

## Gelöschte Segmentfunktionen

Ein gelöschtes Segment:

* Stoppt die Segmentierung neuer, qualifizierter Benutzer.
* Entfernt qualifizierte Benutzer aus der Segmentmitgliedschaft.
* Wird aus der Segmentliste entfernt.
* Kann nicht rückgängig gemacht werden.
* Sendet keine Daten an verbundene Ziele.
* Gibt keine Daten in den verfügbaren Berichten zurück.

>[!NOTE]
>
>Sie können Segmente mit einer [!DNL API] Methode anhalten und löschen. Weitere Informationen finden Sie unter [REST-apis](../../api/rest-api-main/rest-api-main.md).
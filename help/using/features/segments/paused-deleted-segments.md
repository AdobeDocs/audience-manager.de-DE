---
description: Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit dem Segmentaufbau anhalten oder löschen.
seo-description: Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit dem Segmentaufbau anhalten oder löschen.
seo-title: Angehaltene und gelöschte Segmente
solution: Audience Manager
title: Angehaltene und gelöschte Segmente
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 5%

---


# Angehaltene und gelöschte Segmente {#paused-and-deleted-segments}

Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit [!UICONTROL Segment Builder] anhalten oder löschen.

## Zugriff auf die Steuerelemente zum Anhalten und Löschen

Bewegen Sie den Mauszeiger über einen Segmentnamen in der Segmentspalte, um die Symbole **[!UICONTROL pause]** und **[!UICONTROL delete]** anzuzeigen (in der Liste [!UICONTROL Actions]). Diese Funktionen wirken sich wie unten beschrieben auf Segmente aus.

## Angehaltene Segmentfunktionalität

Ein angehaltenes (deaktiviertes) Segment:

* Stoppt die Segmentierung neuer, qualifizierter Benutzer.
* Behält den Segmentierungsstatus/die Mitgliedschaft eines Benutzers bei (entfernt keinen Benutzer aus dem Segment).
* Verbleibt in der Segment-Liste und kann reaktiviert werden.
* Sendet keine Daten an verbundene Ziele.
* Gibt Daten in den verfügbaren Berichten zurück (bis zum Deaktivierungsdatum).

## Funktion gelöschter Segmente

Ein gelöschtes Segment:

* Stoppt die Segmentierung neuer, qualifizierter Benutzer.
* Entfernt qualifizierte Benutzer aus der Segmentmitgliedschaft.
* Wird aus der Liste entfernt.
* Die Markierung kann nicht aufgehoben werden.
* Sendet keine Daten an verbundene Ziele.
* Gibt keine Daten in den verfügbaren Berichten zurück.

>[!NOTE]
>
>Sie können Segmente auch mit einer [!DNL API]-Methode anhalten und löschen. Weitere Informationen finden Sie unter [REST-APIs](../../api/rest-api-main/rest-api-main.md).
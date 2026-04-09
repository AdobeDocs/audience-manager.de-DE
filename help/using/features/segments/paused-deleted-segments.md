---
description: Beschreibt die Auswirkungen auf segmentierte Benutzer, Daten und Ziele, wenn Sie ein aktives Segment mit Segment Builder anhalten oder löschen.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Ausgesetzte und gelöschte Segmente
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
TQID: https://experienceleague.adobe.com/aLnmaOxB3fkGdwq4XjKz8SFKizwHI7Ll5rBUb-o34BM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 187
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

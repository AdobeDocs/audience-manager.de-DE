---
description: Auf der Seite Segmentzusammenfassung werden Details wie Name, Eigenschaften im Segment, Regeln, Leistungsdaten und Informationen zur Zielzuordnung angezeigt.
seo-description: Auf der Seite Segmentzusammenfassung werden Details wie Name, Eigenschaften im Segment, Regeln, Leistungsdaten und Informationen zur Zielzuordnung angezeigt.
seo-title: Seite "Segmentdetails"
solution: Audience Manager
title: Seite "Segmentdetails"
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: Aufschlüsselung nach Identitätstyp, Identitätsaufschlüsselung, Berichte zur Zielgruppenidentität, geräteübergreifend, geräteübergreifende ID, Geräte-ID
feature: 'Segmente '
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Seite &quot;Segmentdetails&quot; {#segment-summary-view}

Die Detailseite für ein einzelnes Segment bietet einen Überblick über die Segmentdetails, wie Segmentname, ID, Leistungsmetriken, Regeln, die das Segment definieren, und Zielzuordnungen. Um diese Details anzuzeigen, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** und klicken Sie auf den Namen des Segments, mit dem Sie arbeiten möchten.

## Segmentverwaltungswerkzeuge {#segment-management-tools}

Am oberen Rand der Segmentdetailseite befinden sich die Tools, die Sie zur Verwaltung Ihrer Segmente verwenden können:

1. **[!UICONTROL Add New]**: Verwenden Sie diese Option, um die zu aktivieren  [!UICONTROL Segment Builder] und neue Segmente zu erstellen.
2. **[!UICONTROL Edit]**: Verwenden Sie diese Option, um die Konfiguration des aktuellen Segments zu ändern.
3. **[!UICONTROL Duplicate]**: Verwenden Sie diese Option, um eine Kopie des aktuellen Segments zu erstellen.
4. **[!UICONTROL Delete]**: Verwenden Sie diese Option, um das aktuelle Segment aus Ihrem Audience Manager-Konto zu entfernen.
5. **[!UICONTROL Marketplace Recommendations]**: Verwenden Sie diese Option, um ähnliche Segmente wie die angezeigten aus  [!UICONTROL Audience Marketplace] Daten-Feeds zu finden, die Sie nicht abonniert haben. Unter [Audience Marketplace für Datenkäufer](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) erfahren Sie, wie Sie auf dem Marketplace navigieren und ähnliche Segmente finden.

![basic-segment-information](assets/basic-segment-information.png)

## Segmentinformationen {#basics}

Unter den Segmentverwaltungswerkzeugen finden Sie die folgenden Segmentinformationen:

1. **[!UICONTROL Basic Information]:** Zeigt erforderliche und optionale Details an, die beim Erstellen des Segments angegeben wurden. Eine ausführliche Übersicht über die Bedeutung dieser Felder finden Sie unter [Segment Builder](segment-builder.md) .
2. **[!UICONTROL Segment Graph]:** Zeigt Leistungsdaten grafisch und für feste Zeiträume von 1, 7, 14, 30, 60 und 90 Tagen an. Wir erklären die Segmentpopulationszahlen in einem [separaten Artikel](../../features/segments/segment-builder-data.md).

   ![segments-graph](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** Der Bericht zeigt die Anzahl der Personen oder Haushalte an, die sich für ein Segment qualifizieren, indem er die Anzahl der geräteübergreifenden IDs und/oder externen Gerätediagramm-IDs zählt, die mit den Geräten verknüpft sind, die sich für das Segment qualifiziert haben (siehe  [!UICONTROL Total Segment Population]). Die in diesem Bericht angezeigten geräteübergreifenden IDs und externen Gerätediagramm-IDs werden verwendet, um Profile mit der Profilzusammenführungsregel zusammenzuführen, die das Segment verwendet. Dieser Bericht wird nur angezeigt, wenn Sie in der vom Segment verwendeten Profilzusammenführungsregel eine geräteübergreifende Datenquelle oder ein externes Gerätediagramm ausgewählt haben.

   ![segments-graph](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager zeigt nur den Bericht [!UICONTROL Identity Type Breakdown] an, wenn Sie geräteübergreifende IDs für das Segment qualifiziert haben.

   Sehen Sie sich das folgende Video an, um einen Überblick über [!UICONTROL Identity Type Breakdown] zu erhalten.
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:** Listet Eigenschaften im Segment zusammen mit Qualifizierungsregeln auf.
5. **[!UICONTROL Destination Mappings]:** Listet Zielzuordnungen für das Segment auf.
6. **[!UICONTROL Management Tools]:** Steuerelemente zum Erstellen, Bearbeiten, Klonen und Löschen von Segmenten.

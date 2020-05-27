---
description: Auf der Seite "Segmentzusammenfassung"werden Details wie Name, Eigenschaften im Segment, Regeln, Leistungsdaten und Zielzuordnungsinformationen angezeigt.
seo-description: Auf der Seite "Segmentzusammenfassung"werden Details wie Name, Eigenschaften im Segment, Regeln, Leistungsdaten und Zielzuordnungsinformationen angezeigt.
seo-title: Segmentdetailseite
solution: Audience Manager
title: Segmentdetailseite
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
translation-type: tm+mt
source-git-commit: 3b56d7ecdef4375bf3b007fa9b325618c701c174
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---


# Segmentdetailseite {#segment-summary-view}

Die Detailseite für ein einzelnes Segment bietet einen Überblick über die Segmentdetails, wie Segmentname, ID, Leistungsmetriken, Regeln, die das Segment definieren, und die Zielzuordnungen. Um diese Details Ansicht, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** und klicken Sie auf den Segmentnamen, mit dem Sie arbeiten möchten.

## Segmentverwaltungswerkzeuge {#segment-management-tools}

Auf der oberen Seite der Segmentdetailseite finden Sie die Tools, mit denen Sie Ihre Segmente verwalten können:

1. **[!UICONTROL Add New]**: Verwenden Sie diese Option, um das Segment zu aktivieren [!UICONTROL Segment Builder] und neue Segmente zu erstellen.
2. **[!UICONTROL Edit]**: Verwenden Sie diese Option, um die Konfiguration des aktuellen Segments zu ändern.
3. **[!UICONTROL Duplicate]**: Verwenden Sie diese Option, um eine Kopie des aktuellen Segments zu erstellen.
4. **[!UICONTROL Delete]**: Verwenden Sie diese Option, um das aktuelle Segment aus Ihrem Audience Manager-Konto zu entfernen.
5. **[!UICONTROL Marketplace Recommendations]**: Verwenden Sie diese Option, um ähnliche Segmente wie die, die Sie anzeigen, aus [!UICONTROL Audience Marketplace] Datenfeeds zu finden, die Sie nicht abonniert haben. Unter [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) erfahren Sie, wie Sie im Marketplace navigieren und ähnliche Segmente finden.

![basic-segment-information](assets/basic-segment-information.png)

## Segmentinformationen {#basics}

Unter den Segmentverwaltungstools finden Sie die folgenden Segmentinformationen:

1. **[!UICONTROL Basic Information]:**Zeigt erforderliche und optionale Details an, die beim Erstellen des Segments angegeben wurden. Eine detaillierte Übersicht darüber, was diese Felder bedeuten, finden Sie unter[Segmentaufbau](segment-builder.md).
2. **[!UICONTROL Segment Graph]:**Zeigt Leistungsdaten grafisch und für feste Zeiträume von 1, 7, 14, 30, 60 und 90 Tagen an. Wir erklären die Segmentpopulationszahlen in einem[separaten Artikel](../../features/segments/segment-builder-data.md).

   ![segmentdiagramm](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:**Der Bericht zeigt die Anzahl der Personen oder Haushalte an, die sich für ein Segment qualifizieren, indem die Anzahl der geräteübergreifenden IDs und/oder externen Gerätediagramm-IDs gezählt wird, die mit den Geräten verknüpft sind, die für das Segment qualifiziert sind (siehe[!UICONTROL Total Segment Population]). Die in diesem Bericht angezeigten geräteübergreifenden IDs und externen Gerätediagramme-IDs werden verwendet, um Profil mit der Segmentzusammenführungsregel zusammenzuführen, die das Profil verwendet. Dieser Bericht wird nur angezeigt, wenn Sie in der Segmentzusammenführungsregel eine geräteübergreifende Datenquelle oder ein Diagramm für ein externes Profil ausgewählt haben.

   ![segmentdiagramm](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager zeigt den [!UICONTROL Identity Type Breakdown] Bericht nur dann an, wenn Sie geräteübergreifende IDs für das Segment qualifiziert haben.

   Sehen Sie sich das unten stehende Video an, um eine Übersicht zu [!UICONTROL Identity Type Breakdown]erhalten.
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:**Segmenteigenschaften und Qualifikationsregeln werden in Listen angezeigt.
5. **[!UICONTROL Destination Mappings]:**Segmentzielzuordnungen für Listen.
6. **[!UICONTROL Management Tools]:**Steuerelemente, mit denen Sie Segmente erstellen, bearbeiten, klonen und löschen können.
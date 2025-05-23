---
description: Die Seite „Segmentzusammenfassung“ zeigt Details wie Namen, Eigenschaften im Segment, Regeln, Leistungsdaten und Informationen zur Zielzuordnung an.
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: Seite mit Segmentdetails
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: Aufschlüsselung des Identitätstyps, Identitätsaufschlüsselung, Berichte zur Zielgruppen-Identität, geräteübergreifend, geräteübergreifende ID, Geräte-ID
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Seite mit Segmentdetails {#segment-summary-view}

Die Detailseite für ein einzelnes Segment bietet einen Überblick über die Segmentdetails, wie den Segmentnamen, die ID, Leistungsmetriken, Regeln, die das Segment definieren, und die Zielzuordnungen. Um diese Details anzuzeigen, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** und klicken Sie auf den Namen des Segments, mit dem Sie arbeiten möchten.

## Tools zur Segmentverwaltung {#segment-management-tools}

Oben auf der Seite mit den Segmentdetails befinden sich die Tools, mit denen Sie Ihre Segmente verwalten können:

1. **[!UICONTROL Add New]**: Verwenden Sie diese Option, um die [!UICONTROL Segment Builder] zu aktivieren und neue Segmente zu erstellen.
2. **[!UICONTROL Edit]**: Verwenden Sie diese Option, um die Konfiguration des aktuellen Segments zu ändern.
3. **[!UICONTROL Duplicate]**: Verwenden Sie diese Option, um eine Kopie des aktuellen Segments zu erstellen.
4. **[!UICONTROL Delete]**: Verwenden Sie diese Option, um das aktuelle Segment aus Ihrem Audience Manager-Konto zu entfernen.
5. **[!UICONTROL Marketplace Recommendations]**: Verwenden Sie diese Option, um ähnliche Segmente wie das angezeigte zu finden, und zwar aus [!UICONTROL Audience Marketplace] Daten-Feeds, die Sie nicht abonniert haben. Unter [Audience Marketplace für Datenkäufer erfahren ](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md), wie Sie auf dem Marketplace navigieren und ähnliche Segmente finden können.

![basic-segment-information](assets/basic-segment-information.png)

## Segmentinformationen {#basics}

Unter den Tools für die Segmentverwaltung finden Sie die folgenden Segmentinformationen:

1. **[!UICONTROL Basic Information]:** Zeigt die erforderlichen und optionalen Details an, die beim Erstellen des Segments angegeben wurden. Unter [Segment Builder](segment-builder.md) finden Sie einen detaillierten Überblick darüber, was diese Felder bedeuten.
2. **[!UICONTROL Segment Graph]:** Zeigt Leistungsdaten grafisch und für feste Intervalle von 1, 7, 14, 30, 60 und 90 Tagen an. Die Zahlen der Segmentpopulation werden in einem [ Artikel ](../../features/segments/segment-builder-data.md).

   ![segments-graph](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown]:** Der Bericht zeigt die Anzahl der Personen oder Haushalte an, die für ein Segment qualifiziert sind, indem die Anzahl der geräteübergreifenden und/oder externen Gerätediagramm-IDs gezählt wird, die mit den Geräten verknüpft sind, die für das Segment qualifiziert sind (angezeigt durch die [!UICONTROL Total Segment Population]). Die in diesem Bericht angezeigten geräteübergreifenden IDs und externen Gerätediagramm-IDs werden verwendet, um Profile mit der Profilzusammenführungsregel zusammenzuführen, die das Segment verwendet. Dieser Bericht wird nur angezeigt, wenn Sie in der vom Segment verwendeten Profilzusammenführungsregel eine geräteübergreifende Datenquelle oder ein externes Gerätediagramm ausgewählt haben.

   ![segments-graph](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager zeigt den [!UICONTROL Identity Type Breakdown] nur an, wenn geräteübergreifende IDs für das Segment qualifiziert sind.

   Sehen Sie sich das folgende Video an, um einen Überblick über [!UICONTROL Identity Type Breakdown] zu erhalten.
   >[!VIDEO](https://video.tv.adobe.com/v/32712?captions=ger)

4. **[!UICONTROL Segment Rules]:** Listet Merkmale im Segment zusammen mit Qualifizierungsregeln auf.
5. **[!UICONTROL Destination Mappings]:** Listet Zielzuordnungen für das Segment auf.
6. **[!UICONTROL Management Tools]:** Steuerelemente zum Erstellen, Bearbeiten, Klonen und Löschen von Segmenten.

---
description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie für eine Datenquelle festlegen. Datenexportbeschriftungen verhindern, dass Sie einem Segment eingeschränkte Eigenschaften hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportkennzeichnungen für ein neues oder vorhandenes Cookie- oder URL-Ziel festlegen.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: Hinzufügen oder Bearbeiten von Segmenten für Server-zu-Server-Ziele
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# Hinzufügen oder Bearbeiten von Segmenten für Server-zu-Server-Ziele {#add-edit-segments}

Sie können nur Segmente für ein Server-zu-Server-Ziel ([!DNL S2S]) hinzufügen oder bearbeiten. Sie können keine [!DNL S2S] Ziele mit [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md) erstellen. Wenden Sie sich an Ihren Berater, um [!DNL S2S] Ziele einzurichten. Befolgen Sie diese Anweisungen, um Segmente für ein [!DNL S2S]-Ziel hinzuzufügen oder zu bearbeiten.

<!-- destination-s2s-edit.xml -->

So fügen Sie Segmentzuordnungen für ein [!DNL S2S] hinzu oder bearbeiten diese:

1. Gehe zu **[!UICONTROL Audience Data > Destinations]**. Wählen Sie **Integrierte Plattformen > Gerätebasiert** und suchen Sie das [!DNL S2S] Ziel, mit dem Sie arbeiten möchten.
2. Klicken Sie in der Spalte [!UICONTROL Action] auf das Stiftsymbol, um das Ziel zu bearbeiten.
   * Beginnen Sie im **[!UICONTROL Search and Add Segments]**, den Namen eines Segments einzugeben, oder klicken Sie **[!UICONTROL Browse All Segments]** eine Liste der verfügbaren Segmente zu durchsuchen.
   * Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das Segment finden, das Sie verwenden möchten. Durch Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] geöffnet.
   * In [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Legen Sie einen Wert für das [Schlüssel-Wert-Paar](../../features/destinations/key-value-pairs.md) fest, das von diesem Ziel verwendet wird.
      * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für das Ziel aus. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
3. Klicken Sie auf **[!UICONTROL Save]** und dann auf **[!UICONTROL Done]**.

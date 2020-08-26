---
description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festlegen. Datenexportbeschriftungen verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbeschriftungen für ein neues oder vorhandenes Cookie- oder URL-Ziel festlegen.
seo-description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festlegen. Datenexport-Bezeichnungen verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbeschriftungen für ein neues oder vorhandenes Cookie- oder URL-Ziel festlegen.
seo-title: Hinzufügen oder Bearbeiten von Segmenten für Server-zu-Server-Ziele
solution: Audience Manager
title: Hinzufügen oder Bearbeiten von Segmenten für Server-zu-Server-Ziele
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 55925e803e16580e0d9357d973405cf39370a8fd
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 8%

---


# Hinzufügen oder Bearbeiten von Segmenten für Server-zu-Server-Ziele {#add-edit-segments}

Sie können nur Segmente für ein Server-zu-Server-([!DNL S2S]) Ziel hinzufügen oder bearbeiten. Sie können keine [!DNL S2S] Ziele mit erstellen [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Wenden Sie sich an Ihren Berater, um [!DNL S2S] Ziele einzurichten. Befolgen Sie diese Anweisungen, um Segmente für ein [!DNL S2S] Ziel hinzuzufügen oder zu bearbeiten.

<!-- destination-s2s-edit.xml -->

So fügen Sie Segmentzuordnungen für ein [!DNL S2S] Ziel hinzu oder bearbeiten sie:

1. Geh zu **[!UICONTROL Audience Data > Destinations]**. Wählen Sie &quot; **Integrierte Plattformen&quot;> &quot;Gerätebasiert** &quot;und suchen Sie das gewünschte [!DNL S2S] Ziel.
2. Klicken Sie in der [!UICONTROL Action] Spalte auf das Stiftsymbol, um das Ziel zu bearbeiten.
   * Geben Sie im **[!UICONTROL Search and Add Segments]** Feld einen Segmentnamen ein oder klicken Sie auf eine Liste der verfügbaren Segmente **[!UICONTROL Browse All Segments]** .
   * Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das gewünschte Segment finden. Durch Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
   * Mit [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Legen Sie einen Wert für das [Schlüssel-Wert-Paar](../../features/destinations/key-value-pairs.md) fest, das von diesem Ziel verwendet wird.
      * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie einen Beginn und ein Enddatum für das Ziel aus. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
3. Klicken Sie auf **[!UICONTROL Save]** und dann auf **[!UICONTROL Done]**.

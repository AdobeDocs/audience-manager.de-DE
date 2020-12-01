---
description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festlegen. Datenexportbeschriftungen verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbeschriftungen für ein neues oder vorhandenes Cookie- oder URL-Ziel festlegen.
seo-description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festlegen. Datenexportbeschriftungen verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbeschriftungen für ein neues oder vorhandenes Cookie- oder URL-Ziel festlegen.
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

Sie können nur Segmente für ein Server-zu-Server-Ziel ([!DNL S2S]) hinzufügen oder bearbeiten. Sie können [!DNL S2S]-Ziele nicht mit [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md) erstellen. Wenden Sie sich an Ihren Berater, um [!DNL S2S]-Ziele einzurichten. Befolgen Sie diese Anweisungen, um Segmente für ein [!DNL S2S]-Ziel hinzuzufügen oder zu bearbeiten.

<!-- destination-s2s-edit.xml -->

So fügen Sie Segmentzuordnungen für ein [!DNL S2S]-Ziel hinzu oder bearbeiten sie:

1. Gehen Sie zu **[!UICONTROL Audience Data > Destinations]**. Wählen Sie **Integrierte Plattformen > Device-Based** und suchen Sie das [!DNL S2S]-Ziel, mit dem Sie arbeiten möchten.
2. Klicken Sie in der Spalte [!UICONTROL Action] auf das Stiftsymbol, um das Ziel zu bearbeiten.
   * Geben Sie im Feld **[!UICONTROL Search and Add Segments]** den Segmentnamen ein oder klicken Sie auf **[!UICONTROL Browse All Segments]**, um eine Liste der verfügbaren Segmente zu durchsuchen.
   * Klicken Sie auf **[!UICONTROL Add Selected Segments]**, wenn Sie das gewünschte Segment finden. Durch Hinzufügen eines Segments wird das Fenster [!UICONTROL Edit Mapping] geöffnet.
   * Mit [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Legen Sie einen Wert für die  [Schlüssel-Wert-](../../features/destinations/key-value-pairs.md) Paarung dieses Ziels fest.
      * **[!UICONTROL Start Date]** und  **[!UICONTROL End Date]**: Wählen Sie einen Beginn und ein Enddatum für das Ziel aus. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
3. Klicken Sie auf **[!UICONTROL Save]** und dann auf **[!UICONTROL Done]**.

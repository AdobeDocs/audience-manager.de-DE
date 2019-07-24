---
description: Sie können qualifizierte Segmente über eine clientseitige (browserseitige) Integration oder eine serverseitige Integration an DFP senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie ein Cookie-basiertes Ziel für Google Publisher Tags in Audience Manager erstellen.
seo-description: Sie können qualifizierte Segmente über eine clientseitige (browserseitige) Integration oder eine serverseitige Integration an DFP senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie ein Cookie-basiertes Ziel für Google Publisher Tags in Audience Manager erstellen.
seo-title: Erstellen eines GPT-Ziels
solution: Audience Manager
title: Erstellen eines GPT-Ziels
uuid: e 3 bbf 327-a 7 e 0-48 da-bc 84-8 f 531 b 7 f 6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Create a GPT Destination {#create-a-gpt-destination}

You can send qualified segments to [!DNL DFP] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for [!DNL Google Publisher Tags] in Audience Manager.

## Ziele

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] bietet die Tools, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Audience Manager destination features are located in *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## Basisinformationen

To complete the [!UICONTROL Basic Information] section:

1. Geben Sie dem Ziel einen Namen.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## Cookie-Konfiguration

Provide the following to complete the [!UICONTROL Configuration] section (other fields are optional):

1. **Cookie-Name:** Geben Sie einen kurzen, beschreibenden Namen für Ihr Cookie an.
1. **Datenformat:** Wählen Sie die **[!UICONTROL "Single Key"]** Option aus.
1. **Schlüssel:** Geben Sie einen Schlüsselnamen an.
1. **Serialisieren:** Aktivieren **[!UICONTROL Enable]** Sie das Kontrollkästchen.
1. **Serientrennzeichen:** Verwenden Sie nur Kommas.

## Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. Find segments: The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. So suchen Sie ein Segment:

   * Option 1: Geben Sie einen Segmentnamen in das Suchfeld ein. Das Feld wird automatisch basierend auf eingegebenen Text aktualisiert. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **Zuordnungen hinzufügen:** Geben Sie in das Feld Zuordnungen die Segment-ID im Feld Zuordnungen ein und klicken **[!UICONTROL Save]** Sie auf.

1. Klicken Sie auf **[!UICONTROL Done]**.
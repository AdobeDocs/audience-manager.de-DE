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


# Erstellen eines GPT-Ziels {#create-a-gpt-destination}

Sie können qualifizierte Segmente [!DNL DFP] über eine clientseitige (browserseitige) Integration oder eine serverseitige Integration senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie ein Cookie-basiertes Ziel für [!DNL Google Publisher Tags] Audience Manager erstellen.

## Ziele

In Audience Manager ist ein *`destination`* beliebiges anderes System (Werbeserver, [!DNL DSP]Werbenetzwerk usw.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] bietet die Tools, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Zielfunktionen von Audience Manager befinden sich in *[!UICONTROL Audience Data] &gt; [!UICONTROL Destinations]*. Um zu beginnen, klicken Sie **[!UICONTROL Add New Destination]** auf und gehen Sie wie folgt vor.

## Basisinformationen

So füllen Sie den [!UICONTROL Basic Information] Abschnitt aus:

1. Geben Sie dem Ziel einen Namen.
1. Wählen **[!UICONTROL "Cookie"]** Sie aus der [!UICONTROL Type] Dropdownliste aus.
1. Klicken **[!UICONTROL Next]** Sie auf und wechseln Sie zu [!UICONTROL Configuration] den [!UICONTROL Segment Mappings] Abschnitten.

## Cookie-Konfiguration

Geben Sie Folgendes an, um den [!UICONTROL Configuration] Abschnitt abzuschließen (andere Felder sind optional):

1. **Cookie-Name:** Geben Sie einen kurzen, beschreibenden Namen für Ihr Cookie an.
1. **Datenformat:** Wählen Sie die **[!UICONTROL "Single Key"]** Option aus.
1. **Schlüssel:** Geben Sie einen Schlüsselnamen an.
1. **Serialisieren:** Aktivieren **[!UICONTROL Enable]** Sie das Kontrollkästchen.
1. **Serientrennzeichen:** Verwenden Sie nur Kommas.

## Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. Segmente suchen: Der [!UICONTROL Segment Mappings] Abschnitt enthält zwei Tools zur Suche nach Segmenten. So suchen Sie ein Segment:

   * Option 1: Geben Sie einen Segmentnamen in das Suchfeld ein. Das Feld wird automatisch basierend auf eingegebenen Text aktualisiert. Klicken **[!UICONTROL Add]** Sie auf, sobald Sie das gewünschte Segment gefunden haben.
   * Option 2: Klicken **[!UICONTROL Browse All Segments]** Sie, um ein Fenster zu öffnen, mit dem Sie nach Segmenten nach Namen oder Speicherort suchen können. Klicken Sie auf, **[!UICONTROL Add Selected Segments]** wenn Sie fertig sind.

1. **Zuordnungen hinzufügen:** Geben Sie in das Feld Zuordnungen die Segment-ID im Feld Zuordnungen ein und klicken **[!UICONTROL Save]** Sie auf.

1. Klicken Sie auf **[!UICONTROL Done]**.
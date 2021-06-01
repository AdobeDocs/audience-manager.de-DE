---
description: Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an Google Ad Manager senden. Wenn Sie die Client-seitige Integration wählen, müssen Sie ein Cookie-basiertes Ziel für Google Publisher Tags in Audience Manager erstellen.
seo-description: Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an Google Ad Manager senden. Wenn Sie die Client-seitige Integration wählen, müssen Sie ein Cookie-basiertes Ziel für Google Publisher Tags in Audience Manager erstellen.
seo-title: Erstellen eines GPT-Ziels
solution: Audience Manager
title: Erstellen eines GPT-Ziels
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Drittanbieterintegration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 7%

---

# Erstellen eines GPT-Ziels {#create-a-gpt-destination}

Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an [!DNL Google Ad Manager] senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie ein Cookie-basiertes Ziel für [!DNL Google Publisher Tags] in Audience Manager erstellen.

## Ziele 

Im Audience Manager ist ein *`destination`* ein anderes System (Anzeigenserver, [!DNL DSP], Werbenetzwerk usw.), für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Die Zielfunktionen für Audience Manager befinden sich unter *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]** und führen Sie die folgenden Schritte aus.

## Basisinformationen

So schließen Sie den Abschnitt [!UICONTROL Basic Information] ab:

1. Benennen Sie das Ziel.
1. Wählen Sie **[!UICONTROL "Cookie"]** aus der Dropdownliste [!UICONTROL Type] aus.
1. Klicken Sie auf **[!UICONTROL Next]** und fahren Sie mit den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] fort.

## Cookie-Konfiguration

Geben Sie Folgendes an, um den Abschnitt [!UICONTROL Configuration] auszufüllen (andere Felder sind optional):

1. **Cookie-Name:**  Geben Sie einen kurzen, beschreibenden Namen für Ihr Cookie ein.
1. **Datenformat:** Wählen Sie die  **[!UICONTROL "Single Key"]** Option aus.
1. **Schlüssel:** Geben Sie einen Schlüsselnamen an.
1. **Serialisieren:** Aktivieren Sie das  **[!UICONTROL Enable]** Kontrollkästchen.
1. **Serielle Trennzeichen:** Verwenden Sie nur ein Komma.

## Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. Segmente suchen: Der Abschnitt [!UICONTROL Segment Mappings] enthält zwei Suchwerkzeuge, mit denen Sie Segmente finden können. So suchen Sie ein Segment:

   * Option 1: Beginnen Sie mit der Eingabe eines Segmentnamens in das Suchfeld. Das Feld wird automatisch auf der Basis des eingegebenen Texts aktualisiert. Klicken Sie auf **[!UICONTROL Add]** , sobald Sie das Segment gefunden haben, das Sie verwenden möchten.
   * Option 2: Klicken Sie auf **[!UICONTROL Browse All Segments]** , um ein Fenster zu öffnen, in dem Sie nach Namen oder Speicherort nach Segmenten suchen können. Klicken Sie abschließend auf **[!UICONTROL Add Selected Segments]** .

1. **Zuordnungen hinzufügen:** Geben Sie im Popup-Zuordnungen die Segment-ID in das Feld Zuordnungen ein und klicken Sie auf  **[!UICONTROL Save]**.

1. Klicken **[!UICONTROL Done]**.

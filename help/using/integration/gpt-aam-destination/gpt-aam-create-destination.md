---
description: Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an DFP senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie in Audience Manager ein cookie-basiertes Ziel für Google Publisher Tags erstellen.
seo-description: Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an DFP senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie in Audience Manager ein cookie-basiertes Ziel für Google Publisher Tags erstellen.
seo-title: GPT-Ziel erstellen
solution: Audience Manager
title: GPT-Ziel erstellen
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# GPT-Ziel erstellen {#create-a-gpt-destination}

Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration [!DNL DFP] an diese senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie ein cookie-basiertes Ziel für [!DNL Google Publisher Tags] in Audience Manager erstellen.

## Ziele

In Audience Manager *`destination`* ist ein beliebiges anderes System (Anzeigenserver, [!DNL DSP]Werbenetzwerk usw.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Die Zielfunktionen von Audience Manager finden Sie unter *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]** und befolgen Sie die folgenden Schritte.

## Basisinformationen

So füllen Sie den [!UICONTROL Basic Information] Abschnitt aus:

1. Benennen Sie das Ziel.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Klicken Sie auf **[!UICONTROL Next]** und gehen Sie zu den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] .

## Cookie-Konfiguration

Geben Sie Folgendes an, um den [!UICONTROL Configuration] Abschnitt auszufüllen (andere Felder sind optional):

1. **** Cookie-Name: Geben Sie einen kurzen beschreibenden Namen für Ihr Cookie ein.
1. **** Datenformat: Wählen Sie die **[!UICONTROL "Single Key"]** Option aus.
1. **** Schlüssel: Geben Sie einen Schlüsselnamen ein.
1. **** Serialisieren: Aktivieren Sie das **[!UICONTROL Enable]** Kontrollkästchen.
1. **** Serieller Trennzeichen: Verwenden Sie nur ein Komma.

##  Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. Segmente suchen: Der [!UICONTROL Segment Mappings] Abschnitt enthält zwei Suchwerkzeuge, die Ihnen bei der Suche nach Segmenten helfen. So suchen Sie ein Segment:

   * Option 1: Geben Sie einen Segmentnamen in das Suchfeld ein. Das Feld wird automatisch anhand des eingegebenen Texts aktualisiert. Klicken Sie auf **[!UICONTROL Add]** , sobald Sie das gewünschte Segment gefunden haben.
   * Option 2: Klicken Sie auf **[!UICONTROL Browse All Segments]** , um ein Fenster zu öffnen, in dem Sie nach Namen oder Speicherort nach Segmenten suchen können. Click **[!UICONTROL Add Selected Segments]** when done.

1. **** Zuordnungen hinzufügen: Geben Sie im Popup für Zuordnungen die Segment-ID in das Zuordnungsfeld ein und klicken Sie auf **[!UICONTROL Save]**.

1. Klicken Sie auf **[!UICONTROL Done]**.
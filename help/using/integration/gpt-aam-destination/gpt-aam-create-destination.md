---
description: Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an Google Ad Manager senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie in Audience Manager ein cookie-basiertes Ziel für Google Publisher Tags erstellen.
seo-description: Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration an Google Ad Manager senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie in Audience Manager ein cookie-basiertes Ziel für Google Publisher Tags erstellen.
seo-title: Erstellen eines GPT-Ziels
solution: Audience Manager
title: Erstellen eines GPT-Ziels
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---


# Erstellen eines GPT-Ziels {#create-a-gpt-destination}

Sie können qualifizierte Segmente über eine clientseitige (Browser-seitige) Integration oder eine serverseitige Integration [!DNL Google Ad Manager] an diese senden. Wenn Sie die clientseitige Integration auswählen, müssen Sie ein cookie-basiertes Ziel für [!DNL Google Publisher Tags] den Audience Manager erstellen.

## Ziele 

Im Audience Manager *`destination`* ist ein anderes System (Anzeigen-Server, [!DNL DSP]Anzeigen-Netzwerk usw.) für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Data Versand-Prozesse erstellen und verwalten können. Die Audience Manager-Zielfunktionen finden Sie unter *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]**und befolgen Sie die folgenden Schritte.

## Basisinformationen

So füllen Sie den [!UICONTROL Basic Information] Abschnitt aus:

1. Benennen Sie das Ziel.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Klicken Sie auf **[!UICONTROL Next]** und gehen Sie zu den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] .

## Cookie-Konfiguration

Geben Sie Folgendes an, um den [!UICONTROL Configuration] Abschnitt auszufüllen (andere Felder sind optional):

1. **Cookie-Name:** Geben Sie einen kurzen beschreibenden Namen für Ihr Cookie ein.
1. **Datenformat:** Wählen Sie die **[!UICONTROL "Single Key"]** Option aus.
1. **Schlüssel:** Geben Sie einen Schlüsselnamen ein.
1. **Serialisieren:** Aktivieren Sie das **[!UICONTROL Enable]** Kontrollkästchen.
1. **Serieller Trennzeichen:** Verwenden Sie nur ein Komma.

## Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. Segmente suchen: Der [!UICONTROL Segment Mappings] Abschnitt enthält zwei Suchwerkzeuge, die Ihnen bei der Suche nach Segmenten helfen. So suchen Sie ein Segment:

   * Option 1: Beginn, der einen Segmentnamen in das Suchfeld eingibt. Das Feld wird automatisch anhand des eingegebenen Texts aktualisiert. Klicken Sie auf **[!UICONTROL Add]** , sobald Sie das gewünschte Segment gefunden haben.
   * Option 2: Klicken Sie auf **[!UICONTROL Browse All Segments]** , um ein Fenster zu öffnen, in dem Sie nach Datenspeicherung oder Namen suchen können. Klicken Sie **[!UICONTROL Add Selected Segments]** nach Abschluss des Vorgangs auf .

1. **Hinzufügen Zuordnungen:** Geben Sie im Popup für Zuordnungen die Segment-ID in das Zuordnungsfeld ein und klicken Sie auf **[!UICONTROL Save]**.

1. Klicken **[!UICONTROL Done]**.
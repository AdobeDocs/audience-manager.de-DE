---
description: Sie können qualifizierte Segmente über eine Client-seitige (Browser-seitige) Integration oder eine Server-seitige Integration an Google Ad Manager senden. Wenn Sie sich für die Client-seitige Integration entscheiden, müssen Sie ein Cookie-basiertes Ziel für Google Publisher Tags in Audience Manager erstellen.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Erstellen eines GPT-Ziels
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
TQID: https://experienceleague.adobe.com/v24OVLvNGPvqASZ4CPh2xbBgVcXZNCitCBM76nUXRsE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: e7029888-c8b0-46a7-849a-cf132a1559bf
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 1%

---

# Erstellen eines GPT-Ziels {#create-a-gpt-destination}

Sie können qualifizierte Segmente über eine Client-seitige (Browser-seitige) Integration oder eine Server-seitige Integration an [!DNL Google Ad Manager] senden. Wenn Sie sich für die Client-seitige Integration entscheiden, müssen Sie ein Cookie-basiertes Ziel für [!DNL Google Publisher Tags] in Audience Manager erstellen.

## Ziele

In Audience Manager ist ein *`destination`* jedes andere System (Werbeserver, [!DNL DSP], Werbenetzwerk usw.), für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Audience Manager-Zielfunktionen befinden sich unter *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]** und führen Sie die folgenden Schritte aus.

## Basisinformationen

So schließen Sie den Abschnitt [!UICONTROL Basic Information] ab:

1. Benennen Sie das Ziel.
1. Wählen Sie **[!UICONTROL "Cookie"]** aus der Dropdown-Liste [!UICONTROL Type] aus.
1. Klicken Sie auf **[!UICONTROL Next]** und fahren Sie mit den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] fort.

## Cookie-Konfiguration

Geben Sie Folgendes an, um den Abschnitt [!UICONTROL Configuration] auszufüllen (andere Felder sind optional):

1. **Cookie-Name:** Geben Sie einen kurzen, beschreibenden Namen für Ihr Cookie an.
1. **Datenformat:** Sie die Option **[!UICONTROL "Single Key"]** aus.
1. **Key:** Geben Sie einen Schlüsselnamen an.
1. **Serialisieren** Aktivieren Sie das Kontrollkästchen **[!UICONTROL Enable]** .
1. **Serielles Trennzeichen:** Verwenden Sie nur ein Komma.

## Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. Segmente suchen: Der Abschnitt [!UICONTROL Segment Mappings] bietet zwei Suchwerkzeuge, mit denen Sie Segmente finden können. So suchen Sie ein Segment:

   * Option 1: Beginnen Sie, einen Segmentnamen in das Suchfeld einzugeben. Das Feld wird automatisch auf der Grundlage des eingegebenen Texts aktualisiert. Wenn Sie das Segment gefunden haben, das Sie verwenden möchten, klicken Sie auf **[!UICONTROL Add]** .
   * Option 2: Klicken Sie auf **[!UICONTROL Browse All Segments]** , um ein Fenster zu öffnen, in dem Sie nach Segmenten anhand des Namens oder des Speicherorts suchen können. Klicken Sie abschließend auf **[!UICONTROL Add Selected Segments]** .

1. **Zuordnungen hinzufügen:** Geben Sie im Pop-up „Zuordnungen“ die Segment-ID in das Feld Zuordnungen ein und klicken Sie auf **[!UICONTROL Save]**.

1. Klicken Sie auf **[!UICONTROL Done]**.

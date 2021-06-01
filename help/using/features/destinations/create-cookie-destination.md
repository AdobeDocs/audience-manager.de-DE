---
description: Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [!UICONTROL Destination Builder] zu erstellen.
seo-description: Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [!UICONTROL Destination Builder] zu erstellen.
seo-title: Konfigurieren eines Cookie-Ziels
solution: Audience Manager
title: Konfigurieren eines Cookie-Ziels
feature: Zielgrundlagen
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 3%

---

# Konfigurieren eines Cookie-Ziels {#create-cookie-destination}

Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [!UICONTROL Destination Builder] zu erstellen.

<!-- create-cookie-destination.xml -->

Um ein neues Cookie-Ziel zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Destinations > Create New Destination]** und füllen Sie die Abschnitte wie unten beschrieben aus.

## Basisinformationen {#basic-information}

Dieser Abschnitt enthält Felder und Optionen, die die Erstellung des Cookie-Ziels starten. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Basic Information]** , um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine kurze Beschreibung ist eine effektive Möglichkeit, um weitere Informationen über ein Ziel zu definieren oder bereitzustellen.
4. Wählen Sie in der Liste **[!UICONTROL Category]** **[!UICONTROL Custom]** aus.
5. Wählen Sie in der Liste **[!UICONTROL Environment]** **[!UICONTROL Browser]** aus. Sie können keine Cookie-Ziele für native mobile Umgebungen wie Android- oder iOS-Apps konfigurieren.
6. Klicken Sie in der Liste **[!UICONTROL Type]** auf **[!UICONTROL Cookie]**.
7. *(Optional)* Wählen Sie eine  **[!UICONTROL Auto-fill Destination Mapping]** aus. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt die Segment-ID automatisch hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist eine eindeutige Kennung, die vom Kunden erstellt und verwendet wird. Er ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie auf **[!UICONTROL Next]** , um zu den Einstellungen [!UICONTROL Configuration] zu wechseln, oder klicken Sie auf **[!UICONTROL Data Export Labels]** , um Exportkontrollen auf das Ziel anzuwenden.

## Datenexportbeschriftungen {#data-export-labels-cookies}

Dieser Abschnitt enthält Optionen, die [Datenexport-Steuerelemente](../../features/data-export-controls.md) auf ein Cookie-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexport-Steuerelemente verwenden. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung aus, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (weitere Informationen finden Sie unter [Hinzufügen von Exportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) ).
3. Klicken **[!UICONTROL Save]**.

## Konfiguration {#configuration}

Dieser Abschnitt enthält Felder und Optionen, mit denen Sie das Cookie für Ihr Ziel einrichten können.

>[!NOTE]
>
>[!DNL Audience Manager] kodiert Daten, die in das Ziel-Cookie geschrieben wurden. Beispielsweise werden Leerzeichen als `%20` und Semikolons als `%3B` kodiert.

So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Configuration]** , um die Steuerelemente anzuzeigen.
1. Nennen Sie das Cookie. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. Wählen Sie eine Datenformatoption. Mit diesen Optionen können Sie die Trennzeichen und Trennzeichen für die Schlüssel-Wert-Paare auswählen, die Segmentdaten an ein Ziel senden. Zu den Formatoptionen gehören:
   * **Einzelschlüssel:** Ermöglicht das Festlegen des Schlüssels in einem Schlüssel-Wert-Paar. Sie legen den Wert fest, nachdem Sie ein Segment im Abschnitt [!UICONTROL Segment Mappings] unten ausgewählt haben.
   * **Schlüssel mit mehreren Schlüsseln:** Ermöglicht das Festlegen von Schlüssel und Wert für ein Schlüssel-Wert-Paar. Sie erstellen das Schlüssel-Wert-Paar, nachdem Sie im Abschnitt Segmentzuordnungen unten ein Segment ausgewählt haben.
Weitere Informationen zu diesen Datenelementen finden Sie unter [Standardwerte und Serielle Schlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md) .
1. Klicken **[!UICONTROL Save]**.

Alle anderen Einstellungen sind optional. Weitere Informationen zu den Einstellungen **[!UICONTROL Cookie Domain]** und **[!UICONTROL Publish data to]** finden Sie unter [Optionale Einstellungen für Cookie-Ziele](/help/using/features/destinations/cookie-destination-options.md).

## Segmentzuordnungen {#segments-mapping}

In diesem Abschnitt können Sie nach Segmenten suchen und diese zu Ihrem Ziel hinzufügen. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]** , um die Steuerelemente anzuzeigen.
1. Geben Sie im Feld **[!UICONTROL Search and Add Segments]** den Namen eines Segments ein oder klicken Sie auf **[!UICONTROL Browse All Segments]** , um eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das Segment finden, das Sie verwenden möchten. Durch Hinzufügen eines Segments wird das Fenster [!UICONTROL Edit Mapping] geöffnet.
1. Im Dialogfeld [!UICONTROL Edit Mapping] :
   * **[!UICONTROL Mapping]** können Sie einen Wert für den Schlüssel festlegen, der oben im Abschnitt Konfiguration angegeben ist.
   * **[!UICONTROL Publish from]** ermöglicht die Festlegung des Start- und Enddatums für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken **[!UICONTROL Save]**.
1. Klicken **[!UICONTROL Done]**.

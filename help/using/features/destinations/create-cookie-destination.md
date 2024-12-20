---
description: Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [!UICONTROL Destination Builder] zu erstellen.
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Konfigurieren eines Cookie-Ziels
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# Konfigurieren eines Cookie-Ziels {#create-cookie-destination}

Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [!UICONTROL Destination Builder] zu erstellen.

<!-- create-cookie-destination.xml -->

Um ein neues Cookie-Ziel zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Destinations > Create New Destination]** und füllen Sie die Abschnitte wie unten beschrieben aus.

## Basisinformationen {#basic-information}

Dieser Abschnitt enthält Felder und Optionen, mit denen der Erstellungsprozess des Cookie-Ziels gestartet wird. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Basic Information]** , um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine knappe Beschreibung ist eine effektive Möglichkeit, um mehr Informationen über ein Ziel zu definieren oder bereitzustellen.
4. Wählen Sie in der Liste **[!UICONTROL Category]** die Option **[!UICONTROL Custom]** aus.
5. Wählen Sie in der Liste **[!UICONTROL Environment]** die Option **[!UICONTROL Browser]** aus. Sie können keine Cookie-Ziele für native mobile Umgebungen wie Android oder iOS Apps konfigurieren.
6. Klicken Sie in der **[!UICONTROL Type]** auf **[!UICONTROL Cookie]**.
7. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]** aus. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt automatisch die Segment-ID hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrations-Code hinzu und sendet ihn an die Zielzuordnung. Der Integrations-Code ist eine eindeutige Kennung, die vom Kunden erstellt und verwendet wird. Es ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie auf **[!UICONTROL Next]** , um zu den [!UICONTROL Configuration] zu wechseln, oder klicken Sie auf **[!UICONTROL Data Export Labels]** , um Exportsteuerungen auf das Ziel anzuwenden.

## Beschriftungen für Datenexporte {#data-export-labels-cookies}

Dieser Abschnitt enthält Optionen, die [Datenexportsteuerelemente) auf ](../../features/data-export-controls.md) Cookie-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Kennzeichnung aus, die der auf das Ziel angewendeten Datenexportsteuerung entspricht (weitere Informationen finden Sie [Hinzufügen von Exportkennzeichnungen ](/help/using/features/destinations/add-data-export-labels.md) Ziel).
3. Klicken Sie auf **[!UICONTROL Save]**.

## Konfiguration {#configuration}

Dieser Abschnitt enthält Felder und Optionen, mit denen Sie das -Cookie für Ihr Ziel einrichten können.

>[!NOTE]
>
>[!DNL Audience Manager] kodiert Daten, die in das Ziel-Cookie geschrieben werden. Leerzeichen werden beispielsweise als `%20` und Semikolons als `%3B` codiert.

So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Configuration]** , um die Steuerelemente anzuzeigen
1. Benennen Sie das Cookie. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. Wählen Sie eine Option für das Datenformat aus. Mit diesen Optionen können Sie die Trennzeichen und Trennzeichen für die Schlüssel-Wert-Paare auswählen, die Segmentdaten an ein Ziel senden. Zu den Formatoptionen gehören:
   * **Einzelschlüssel** Ermöglicht das Festlegen des Schlüssels in einem Schlüssel-Wert-Paar. Nachdem Sie im Abschnitt [!UICONTROL Segment Mappings] ein Segment ausgewählt haben, legen Sie den Wert fest.
   * **Mehrere Schlüssel:** Ermöglicht das Festlegen von Schlüssel und Wert für ein Schlüssel-Wert-Paar. Sie erstellen das Schlüssel-Wert-Paar, nachdem Sie im Abschnitt Segmentzuordnungen unten ein Segment ausgewählt haben.
Weitere [ zu diesen Datenelementen finden Sie unter ](../../features/destinations/key-value-pairs.md) und Serielle Schlüssel-Wert-Paare .
1. Klicken Sie auf **[!UICONTROL Save]**.

Alle anderen Einstellungen sind optional. Weitere Informationen zu den **[!UICONTROL Cookie Domain]**- und **[!UICONTROL Publish data to]** finden Sie unter [Optionale Einstellungen für Cookie-Ziele](/help/using/features/destinations/cookie-destination-options.md).

## Segmentzuordnungen {#segments-mapping}

In diesem Abschnitt können Sie nach Segmenten suchen und diese zu Ihrem Ziel hinzufügen. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]** , um die Steuerelemente anzuzeigen.
1. Beginnen Sie im **[!UICONTROL Search and Add Segments]**, den Namen eines Segments einzugeben, oder klicken Sie auf **[!UICONTROL Browse All Segments]** , um eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das Segment finden, das Sie verwenden möchten. Durch Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] geöffnet.
1. Im Dialogfeld [!UICONTROL Edit Mapping] :
   * **[!UICONTROL Mapping]** können Sie einen Wert für den Schlüssel festlegen, der im obigen Abschnitt Konfiguration angegeben ist.
   * **[!UICONTROL Publish from]** können Sie das Start- und Enddatum für das Ziel festlegen. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie auf **[!UICONTROL Done]**.

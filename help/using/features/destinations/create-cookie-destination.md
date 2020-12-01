---
description: Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [!UICONTROL Destination Builder] zu erstellen.
seo-description: Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [!UICONTROL Destination Builder] zu erstellen.
seo-title: Konfigurieren eines Cookie-Ziels
solution: Audience Manager
title: Konfigurieren eines Cookie-Ziels
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 3%

---


# Konfigurieren eines Cookie-Ziels {#create-cookie-destination}

Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [!UICONTROL Destination Builder] zu erstellen.

<!-- create-cookie-destination.xml -->

Um ein neues Cookie-Ziel zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Destinations > Create New Destination]** und füllen Sie die Abschnitte wie unten beschrieben aus.

## Basisinformationen {#basic-information}

Dieser Abschnitt enthält Felder und Optionen, die den Erstellungsvorgang für das Cookie-Ziel Beginn haben. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Basic Information]**, um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine knappe Beschreibung ist eine effektive Methode, um mehr Informationen über ein Ziel zu definieren oder bereitzustellen.
4. Wählen Sie in der Liste **[!UICONTROL Category]** **[!UICONTROL Custom]**.
5. Wählen Sie in der Liste **[!UICONTROL Environment]** **[!UICONTROL Browser]**. Sie können keine Cookie-Ziele für native mobile Umgebung wie Android- oder iOS-Apps konfigurieren.
6. Klicken Sie in der Liste **[!UICONTROL Type]** auf **[!UICONTROL Cookie]**.
7. *(Optional)* Wählen Sie eine  **[!UICONTROL Auto-fill Destination Mapping]** aus. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt die Segment-ID automatisch hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Er ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie auf **[!UICONTROL Next]**, um die [!UICONTROL Configuration]-Einstellungen aufzurufen, oder klicken Sie auf **[!UICONTROL Data Export Labels]**, um Exportsteuerelemente auf das Ziel anzuwenden.

## Datenexportbeschriftungen {#data-export-labels-cookies}

Dieser Abschnitt enthält Optionen, die [Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein Cookie-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Steuerelemente für den Datenexport verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]**, um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung aus, die der Datenexportkontrolle entspricht, die auf das Ziel angewendet wurde (weitere Informationen finden Sie unter [Hinzufügen &quot;Beschriftungen in ein Ziel exportieren](/help/using/features/destinations/add-data-export-labels.md)&quot;).
3. Klicken **[!UICONTROL Save]**.

## Konfiguration {#configuration}

Dieser Abschnitt enthält Felder und Optionen, mit denen Sie das Cookie für Ihr Ziel einrichten können.

>[!NOTE]
>
>[!DNL Audience Manager] kodiert Daten, die in das Ziel-Cookie geschrieben wurden. Leerzeichen werden beispielsweise als `%20` und Semikolons als `%3B` kodiert.

So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Configuration]**, um die Steuerelemente anzuzeigen.
1. Benennen Sie das Cookie. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. Wählen Sie eine Datenformatoption. Mit diesen Optionen können Sie die Trennzeichen und Trennzeichen für die Schlüssel-Wert-Paare auswählen, die Segmentdaten an ein Ziel senden. Zu den Formatoptionen gehören:
   * **Einzelschlüssel:** Hiermit können Sie den Schlüssel in einem Schlüssel-Wert-Paar festlegen. Sie legen den Wert fest, nachdem Sie im Abschnitt [!UICONTROL Segment Mappings] ein Segment ausgewählt haben.
   * **Multi-Key:** Hiermit können Sie Schlüssel und Wert für ein Schlüssel-Wert-Paar festlegen. Sie erstellen das Schlüssel-Wert-Paar, nachdem Sie im Abschnitt &quot;Segmentzuordnungen&quot;ein Segment ausgewählt haben.
Weitere Informationen zu diesen Datenelementen finden Sie unter [Standard- und Serial-Key-Value-Paare](../../features/destinations/key-value-pairs.md).
1. Klicken **[!UICONTROL Save]**.

Alle anderen Einstellungen sind optional. Weitere Informationen zu den Einstellungen **[!UICONTROL Cookie Domain]** und **[!UICONTROL Publish data to]** finden Sie unter [Optionale Einstellungen für Cookie-Ziele](/help/using/features/destinations/cookie-destination-options.md).

## Segmentzuordnungen {#segments-mapping}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]**, um die Steuerelemente anzuzeigen.
1. Geben Sie im Feld **[!UICONTROL Search and Add Segments]** den Segmentnamen ein oder klicken Sie auf **[!UICONTROL Browse All Segments]**, um eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]**, wenn Sie das gewünschte Segment finden. Durch Hinzufügen eines Segments wird das Fenster [!UICONTROL Edit Mapping] geöffnet.
1. Im Dialogfeld [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mapping]** können Sie einen Wert für den Schlüssel festlegen, der oben im Abschnitt Konfiguration angegeben ist.
   * **[!UICONTROL Publish from]** können Sie das Beginns- und Enddatum für das Ziel festlegen. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken **[!UICONTROL Save]**.
1. Klicken **[!UICONTROL Done]**.
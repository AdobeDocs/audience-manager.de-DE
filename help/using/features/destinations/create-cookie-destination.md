---
description: Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit dem [!UICONTROL-Zielaufbau] zu erstellen.
seo-description: Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit dem [!UICONTROL-Zielaufbau] zu erstellen.
seo-title: Cookie-Ziel konfigurieren
solution: Audience Manager
title: Cookie-Ziel konfigurieren
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 1%

---


# Cookie-Ziel konfigurieren {#create-cookie-destination}

Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [!UICONTROL Destination Builder]zu erstellen.

<!-- create-cookie-destination.xml -->

Um ein neues Cookie-Ziel zu erstellen, gehen Sie zu den Abschnitten **[!UICONTROL Audience Data > Destinations > Create New Destination]** und füllen Sie sie wie unten beschrieben aus.

## Basisinformationen {#basic-information}

Dieser Abschnitt enthält Felder und Optionen, die den Erstellungsvorgang für das Cookie-Ziel Beginn haben. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Basic Information]** , um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine knappe Beschreibung ist eine effektive Methode, um mehr Informationen über ein Ziel zu definieren oder bereitzustellen.
4. Wählen Sie in der **[!UICONTROL Category]** Liste **[!UICONTROL Custom]**.
5. Wählen Sie in der **[!UICONTROL Environment]** Liste **[!UICONTROL Browser]**. Sie können keine Cookie-Ziele für native mobile Umgebung wie Android- oder iOS-Apps konfigurieren.
6. Klicken Sie in der **[!UICONTROL Type]** Liste auf **[!UICONTROL Cookie]**.
7. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]**. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt die Segment-ID automatisch hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Er ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie **[!UICONTROL Next]** auf , um zu den [!UICONTROL Configuration] Einstellungen zu wechseln, oder klicken Sie auf , **[!UICONTROL Data Export Labels]** um Exportsteuerelemente auf das Ziel anzuwenden.

## Datenexportbeschriftungen {#data-export-labels-cookies}

Dieser Abschnitt enthält Optionen, die [Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein Cookie-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Steuerelemente für den Datenexport verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung aus, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (weitere Informationen finden Sie unter [Hinzufügen Exportieren von Beschriftungen in ein Ziel](/help/using/features/destinations/add-data-export-labels.md) ).
3. Klicken **[!UICONTROL Save]**.

## Konfiguration {#configuration}

Dieser Abschnitt enthält Felder und Optionen, mit denen Sie das Cookie für Ihr Ziel einrichten können.

>[!NOTE]
>
>[!DNL Audience Manager] kodiert Daten, die in das Ziel-Cookie geschrieben wurden. Leerzeichen werden beispielsweise als kodiert `%20` und Semikolons als `%3B`kodiert.

So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Configuration]** , um die Steuerelemente anzuzeigen
1. Benennen Sie das Cookie. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. Wählen Sie eine Datenformatoption. Mit diesen Optionen können Sie die Trennzeichen und Trennzeichen für die Schlüssel-Wert-Paare auswählen, die Segmentdaten an ein Ziel senden. Zu den Formatoptionen gehören:
   * **Einzelschlüssel:** Ermöglicht das Festlegen des Schlüssels in einem Schlüssel-Wert-Paar. Sie legen den Wert fest, nachdem Sie ein Segment im [!UICONTROL Segment Mappings] Abschnitt unten ausgewählt haben.
   * **Mehrere Schlüssel:** Hiermit können Sie Schlüssel und Wert für ein Schlüssel-Wert-Paar festlegen. Sie erstellen das Schlüssel-Wert-Paar, nachdem Sie im Abschnitt &quot;Segmentzuordnungen&quot;ein Segment ausgewählt haben.
Weitere Informationen zu diesen Datenelementen finden Sie unter [Standard- und Serial-Key-Value-Paare](../../features/destinations/key-value-pairs.md) .
1. Klicken **[!UICONTROL Save]**.

Alle anderen Einstellungen sind optional. Weitere Informationen zu den Einstellungen **[!UICONTROL Cookie Domain]** und **[!UICONTROL Publish data to]** Einstellungen finden Sie unter [Optionale Einstellungen für Cookie-Ziele](/help/using/features/destinations/cookie-destination-options.md).

## Segmentzuordnungen {#segments-mapping}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]** , um die Steuerelemente anzuzeigen.
1. Geben Sie im **[!UICONTROL Search and Add Segments]** **[!UICONTROL Browse All Segments]** Feld Beginn den Segmentnamen ein oder klicken Sie auf , um eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das gewünschte Segment finden. Durch Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
1. Im [!UICONTROL Edit Mapping] Dialog:
   * **[!UICONTROL Mapping]** können Sie einen Wert für den Schlüssel festlegen, der oben im Abschnitt Konfiguration angegeben ist.
   * **[!UICONTROL Publish from]** können Sie das Beginns- und Enddatum für das Ziel festlegen. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken **[!UICONTROL Save]**.
1. Klicken **[!UICONTROL Done]**.
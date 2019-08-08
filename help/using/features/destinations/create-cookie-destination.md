---
description: Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [! UICONTROL Destination Builder].
seo-description: Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel mit [! UICONTROL Destination Builder].
seo-title: Konfigurieren eines Cookie-Ziels
solution: Audience Manager
title: Konfigurieren eines Cookie-Ziels
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Konfigurieren eines Cookie-Ziels {#create-cookie-destination}

Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel zu [!UICONTROL Destination Builder]erstellen.

<!-- create-cookie-destination.xml -->

Um ein neues Cookie-Ziel zu erstellen, gehen **[!UICONTROL Audience Data > Destinations > Create New Destination]** Sie zu den Abschnitten, wie unten beschrieben.

## Basisinformationen {#basic-information}

Dieser Abschnitt enthält Felder und Optionen, die den Cookie-Zielerstellungsprozess starten. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Basic Information]** Sie auf, um die Steuerelemente anzuzeigen.
2. Geben Sie dem Ziel einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine genaue Beschreibung ist eine effektive Möglichkeit, weitere Informationen zu einem Ziel zu definieren oder bereitzustellen.
4. Wählen Sie in der **[!UICONTROL Category]** Liste **[!UICONTROL Custom]** den Eintrag.
5. Wählen Sie in der **[!UICONTROL Environment]** Liste **[!UICONTROL Browser]** den Eintrag. Cookie-Ziele für native mobile Umgebungen wie Android- oder ios-Apps können nicht konfiguriert werden.
6. Klicken Sie in der **[!UICONTROL Type]** Liste **[!UICONTROL Cookie]** auf.
7. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]**. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt automatisch die Segment-ID hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Sie ist auf maximal 255 Zeichen begrenzt.
8. Klicken **[!UICONTROL Next]** Sie auf, um die [!UICONTROL Configuration] Einstellungen aufzurufen, oder klicken **[!UICONTROL Data Export Labels]** Sie auf, um die Exportsteuerelemente auf das Ziel anzuwenden.

## Datenexportbeschriftungen {#data-export-labels-cookies}

Dieser Abschnitt enthält Optionen, die [die Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein Cookie-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Data Export Labels]** Sie auf, um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (siehe [Hinzufügen von Exportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) für weitere Details).
3. Klicken Sie auf **[!UICONTROL Save]**.

## Konfiguration {#configuration}

Dieser Abschnitt enthält Felder und Optionen, mit denen Sie das Cookie für Ihr Ziel einrichten können.

>[!NOTE]
>
>[!DNL Audience Manager] kodiert Daten, die in das Zielcookie geschrieben wurden. Beispielsweise sind Leerzeichen kodiert `%20` und Semikolons werden kodiert `%3B`.

So füllen Sie diesen Abschnitt aus:

1. Klicken Sie, **[!UICONTROL Configuration]** um die Steuerelemente verfügbar zu machen.
1. Geben Sie dem Cookie einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. Wählen Sie eine Datenformat-Option. Mit diesen Optionen können Sie die Trennzeichen und Trennzeichen für Schlüssel/Wert-Paare auswählen, die Segmentdaten an ein Ziel senden. Zu den Formatierungsoptionen gehören:
   * **Einzelner Schlüssel:** Hiermit können Sie den Schlüssel in einem Schlüssel-Wert-Paar festlegen. Sie legen den Wert fest, nachdem Sie ein Segment im folgenden [!UICONTROL Segment Mappings] Abschnitt ausgewählt haben.
   * **Mehrere Schlüssel:** Hiermit können Sie den Schlüssel und den Wert für ein Schlüssel-Wert-Paar festlegen. Sie erstellen das Schlüssel-Wert-Paar, nachdem Sie im Abschnitt "Segmentzuordnungen" ein Segment ausgewählt haben.
Weitere Informationen zu diesen Datenelementen finden Sie unter [Standard- und Serialschlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md) .
1. Klicken Sie auf **[!UICONTROL Save]**.

Alle anderen Einstellungen sind optional. Weitere Informationen zu **[!UICONTROL Cookie Domain]** den und **[!UICONTROL Publish data to]** den Einstellungen finden Sie unter [Optionale Einstellungen für Cookie-Ziele](/help/using/features/destinations/cookie-destination-options.md).

## Segmentzuordnungen {#segments-mapping}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Segment Mappings]** Sie auf, um die Steuerelemente anzuzeigen.
1. Geben Sie in das **[!UICONTROL Search and Add Segments]** Feld den Namen eines Segments ein oder klicken Sie auf, **[!UICONTROL Browse All Segments]** um eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken **[!UICONTROL Add Selected Segments]** Sie auf, wenn Sie das gewünschte Segment suchen. Durch das Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
1. Im [!UICONTROL Edit Mapping] Dialogfeld:
   * **[!UICONTROL Mapping]** Hier können Sie einen Wert für den Schlüssel festlegen, der im Abschnitt "Konfiguration" angegeben ist.
   * **[!UICONTROL Publish from]** ermöglicht das Festlegen des Start- und Enddatums für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie auf **[!UICONTROL Done]**.
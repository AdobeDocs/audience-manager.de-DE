---
description: Ein URL-Ziel führt Pixelaufrufe von einer Seite zum Ziel durch. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit dem Destination Builder zu erstellen.
seo-description: Ein URL-Ziel führt Pixelaufrufe von einer Seite zum Ziel durch. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit dem Destination Builder zu erstellen.
seo-title: URL-Ziel konfigurieren
solution: Audience Manager
title: URL-Ziel konfigurieren
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# URL-Ziel konfigurieren {#configure-url-destination}

Ein [!DNL URL] Ziel führt Pixelaufrufe von einer Seite zum Ziel durch. Befolgen Sie diese Anweisungen, um ein [!DNL URL] Ziel zu erstellen mit [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Um ein neues [!DNL URL] **[!UICONTROL Audience Data > Destinations > Create New Destination]** Ziel zu erstellen, gehen Sie zu den Abschnitten und füllen Sie sie wie unten beschrieben aus.

## Basisinformationen {#basic-info}

Dieser Abschnitt enthält Felder und Optionen, mit denen der URL-Zielerstellungsprozess gestartet wird. Um diesen Abschnitt abzuschließen:

1. Klicken Sie auf **[!UICONTROL Basic Information]** , um die Steuerelemente anzuzeigen.
2. Benennen Sie das Ziel. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine knappe Beschreibung ist eine effektive Methode, um mehr Informationen über ein Ziel zu definieren oder bereitzustellen.
4. Wählen Sie in der **[!UICONTROL Category]** Liste **[!UICONTROL Custom]**.
5. Wählen Sie in der **[!UICONTROL Environment]** Liste die Umgebung aus, in der das URL-Ziel ausgelöst werden soll.
6. Klicken Sie in der **[!UICONTROL Type]** Liste auf **[!UICONTROL URL]**.
7. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]**. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt die Segment-ID automatisch hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist eine eindeutige Kennung, die vom Kunden erstellt und verwendet wird. Er ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie **[!UICONTROL Next]** auf , um zu den [!UICONTROL Configuration] Einstellungen zu wechseln, oder klicken Sie auf , **[!UICONTROL Data Export Labels]** um Exportsteuerelemente auf das Ziel anzuwenden.

## Datenexportbeschriftungen {#data-export-labels-dest}

Dieser Abschnitt enthält Optionen, die [Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein [!DNL URL] Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Steuerelemente für den Datenexport verwenden. Um diesen Abschnitt abzuschließen:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung aus, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (weitere Informationen finden Sie unter Exportbezeichnungen zu einem Ziel [hinzufügen](/help/using/features/destinations/add-data-export-labels.md) ).
3. Klicken Sie auf **[!UICONTROL Save]**.

## Konfiguration {#configure-base-data}

Dieser Abschnitt enthält Optionen, mit denen Sie Basis- [!DNL URL] und Datentrennzeichen festlegen können, die von der [!DNL URL] Zeichenfolge übergeben werden. Dieser Abschnitt ist optional. Um diesen Abschnitt abzuschließen:

1. Klicken Sie auf **[!UICONTROL Configuration]** , um die Steuerelemente anzuzeigen.
1. *(Optional)* Aktivieren Sie das **[!UICONTROL Serialize]** Kontrollkästchen.
Auf diese Weise können Sie Segmente sequenziell an ein Ziel senden, anstatt separate Aufrufe für jedes Segment durchzuführen. Durch die Serialisierung wird die Datenübertragung effizienter. Wenn Sie dieses Kontrollkästchen aktivieren, werden die Felder "URL"und "Trennzeichen"angezeigt. Weitere Informationen finden Sie unter [Standard- und Serial-Key-Wert-Paare](../../features/destinations/key-value-pairs.md).
1. Wenn Sie diese Option auswählen, müssen Sie auch die unten beschriebenen Felder für URL und Trennzeichen konfigurieren. **[!UICONTROL Serialize]**

| Feld | Beschreibung |
|--- |--- |
| Basis-URL | Der Basisteil eines Standards, `HTTP` der sich nicht ändert. [!DNL URL] Außerdem müssen Sie das `%ALIAS%` Platzhaltermakro[ ](../../features/destinations/destination-macros.md#destination-macros-defined)in der Basis-URL platzieren. Beispiel: `https://www.myCompany.com/%alias%...` |
| Sichere URL | Der Basisteil eines sicheren `HTTPS`[!DNL URL] Systems, der sich nicht ändert. Außerdem müssen Sie das `%ALIAS%` Platzhaltermakro[ ](../../features/destinations/destination-macros.md#destination-macros-defined)in der Basis-URL platzieren. Beispiel: `https://www.myCompany.com/%alias%...` |
| Trennzeichen | Das Symbol, das die Segmentvariablen in der [!DNL URL] Zeichenfolge voneinander trennt. Dies ist normalerweise ein Komma oder Semikolon. Rufen Sie diese Informationen von Ihrem Partner ab. |

## Segmentzuordnungen {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. Um diesen Abschnitt abzuschließen:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]** , um die Steuerelemente anzuzeigen.
1. Geben Sie im **[!UICONTROL Search and Add Segments]** Feld den Namen eines Segments ein oder klicken Sie auf eine Liste der verfügbaren Segmente **[!UICONTROL Browse All Segments]** .
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das gewünschte Segment finden. Durch Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
1. Mit [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geben Sie die Schlüssel-Wert-Paare an, die vom Segment verwendet werden.
   * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken Sie auf **[!UICONTROL Done]**.
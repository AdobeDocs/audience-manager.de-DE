---
description: Ein URL-Ziel führt Pixelaufrufe von einer Seite zum Ziel durch. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit dem Destination Builder zu erstellen.
seo-description: Ein URL-Ziel führt Pixelaufrufe von einer Seite zum Ziel durch. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit dem Destination Builder zu erstellen.
seo-title: URL-Ziel konfigurieren
solution: Audience Manager
title: URL-Ziel konfigurieren
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 2%

---



# Konfigurieren Sie eine [!DNL URL Destination] {#configure-url-destination}

Ein [!DNL URL destination] führt Pixelaufrufe von einer Seite zu Ihrer [!DNL destination]. Befolgen Sie diese Anweisungen, um eine [!DNL URL] mit zu erstellen [!DNL destination] [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Um eine neue zu erstellen, [!DNL URL] gehen Sie zu den Abschnitten [!DNL destination]**[!UICONTROL Audience Data > Destinations > Create New Destination]** und füllen Sie sie wie unten beschrieben aus.

## Basisinformationen {#basic-info}

Dieser Abschnitt enthält die Felder und Optionen, die den [!DNL URL destination] Erstellungsprozess Beginn haben. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Basic Information]** , um die Steuerelemente anzuzeigen.
2. Benennen Sie die [!DNL destination]. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie die [!DNL destination]. Eine knappe Beschreibung ist eine effektive Möglichkeit, weitere Informationen zu einer [!DNL destination]Beschreibung zu definieren oder bereitzustellen.
4. Wählen Sie in der **[!UICONTROL Category]** Liste **[!UICONTROL Custom]**.
5. Wählen Sie in der **[!UICONTROL Environment]** Liste die Umgebung aus, in der der Auslöser [!DNL URL destination]angezeigt werden soll.
6. Klicken Sie in der **[!UICONTROL Type]** Liste auf **[!UICONTROL URL]**.
7. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]**. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt die Segment-ID automatisch hinzu und sendet sie an die [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Er ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie auf **[!UICONTROL Next]** , um zu den [!UICONTROL Configuration] Einstellungen zu wechseln, oder klicken Sie auf **[!UICONTROL Data Export Labels]** , um Exportsteuerelemente auf die [!DNL destination]Anwendung anzuwenden.

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Dieser Abschnitt enthält Optionen, die [Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein [!DNL URL] Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Steuerelemente für den Datenexport verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung aus, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (weitere Informationen finden Sie unter [Hinzufügen Exportieren von Beschriftungen in ein Ziel](/help/using/features/destinations/add-data-export-labels.md) ).
3. Klicken **[!UICONTROL Save]**.

## Konfiguration {#configure-base-data}

Dieser Abschnitt enthält Optionen, mit denen Sie Basis- [!DNL URL] und Datentrennzeichen festlegen können, die von der [!DNL URL] Zeichenfolge übergeben werden. Dieser Abschnitt ist optional. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Configuration]** , um die Steuerelemente anzuzeigen.
1. *(Optional)* Aktivieren Sie das **[!UICONTROL Serialize]** Kontrollkästchen.
Auf diese Weise können Sie Segmente an eine [!DNL destination] Sequenz senden, anstatt für jedes Segment separate Aufrufe durchzuführen. Durch die Serialisierung wird die Datenübertragung effizienter. Wenn Sie dieses Kontrollkästchen aktivieren, werden die Felder &quot;URL&quot;und &quot;Trennzeichen&quot;angezeigt. Weitere Informationen finden Sie unter [Standard- und Serial-Key-Wert-Paare](../../features/destinations/key-value-pairs.md).
1. Wenn Sie diese Option auswählen, müssen Sie auch die unten beschriebenen Felder für URL und Trennzeichen konfigurieren. **[!UICONTROL Serialize]**

| Feld | Beschreibung |
|--- |--- |
| [!UICONTROL Base URL] | Der Basisteil eines Standards, `HTTP` der sich nicht ändert. [!DNL URL] Außerdem müssen Sie das `%ALIAS%` Platzhaltermakro [](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL platzieren. Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Der Basisteil eines sicheren `HTTPS`[!DNL URL] Systems, der sich nicht ändert. Außerdem müssen Sie das `%ALIAS%` Platzhaltermakro [](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL platzieren. Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Das Symbol, das die Segmentvariablen in der [!DNL URL] Zeichenfolge voneinander trennt. Dies ist normalerweise ein Komma oder Semikolon. Rufen Sie diese Informationen von Ihrem Partner ab. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und sie zu Ihrem [!UICONTROL destination]Projekt hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]** , um die Steuerelemente anzuzeigen.
1. Geben Sie im **[!UICONTROL Search and Add Segments]** Feld einen Segmentnamen ein oder klicken Sie auf eine Liste der verfügbaren Segmente **[!UICONTROL Browse All Segments]** .
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das gewünschte Segment finden. Durch Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
1. Mit [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geben Sie die Schlüssel-Wert-Paare an, die vom Segment verwendet werden.
   * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie einen Beginn und ein Enddatum für den [!DNL destination]. Wenn das Enddatum leer ist, läuft das [!DNL destination] nie ab.
1. Klicken **[!UICONTROL Done]**.
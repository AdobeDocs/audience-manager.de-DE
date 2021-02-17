---
description: Ein URL-Ziel führt Pixelaufrufe von einer Seite zum Ziel durch. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit dem Destination Builder zu erstellen.
seo-description: Ein URL-Ziel führt Pixelaufrufe von einer Seite zum Ziel durch. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit dem Destination Builder zu erstellen.
seo-title: Konfigurieren eines URL-Ziels
solution: Audience Manager
title: Konfigurieren eines URL-Ziels
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 3%

---



# [!DNL URL Destination] {#configure-url-destination} konfigurieren

Ein [!DNL URL destination] führt Pixelaufrufe von einer Seite zu Ihrem [!DNL destination] durch. Befolgen Sie diese Anweisungen, um ein [!DNL URL] [!DNL destination] mit [!UICONTROL Destination Builder] zu erstellen.

<!-- create-url-destination.xml -->

Um ein neues [!DNL URL] [!DNL destination] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Destinations > Create New Destination]** und füllen Sie die Abschnitte wie unten beschrieben aus.

## Basisinformationen {#basic-info}

Dieser Abschnitt enthält Felder und Optionen, mit denen der Erstellungsprozess von [!DNL URL destination] Beginn wird. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Basic Information]**, um die Steuerelemente anzuzeigen.
2. Benennen Sie [!DNL destination]. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie die  [!DNL destination]. Eine knappe Beschreibung ist eine effektive Methode, um mehr Informationen über ein [!DNL destination] zu definieren oder bereitzustellen.
4. Wählen Sie in der Liste **[!UICONTROL Category]** **[!UICONTROL Custom]**.
5. Wählen Sie in der Liste **[!UICONTROL Environment]** die Umgebung aus, in der das [!DNL URL destination]-Zeichen Trigger werden soll.
6. Klicken Sie in der Liste **[!UICONTROL Type]** auf **[!UICONTROL URL]**.
7. *(Optional)* Wählen Sie eine  **[!UICONTROL Auto-fill Destination Mapping]** aus. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt die Segment-ID automatisch hinzu und sendet sie an die  [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Er ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie auf **[!UICONTROL Next]**, um die [!UICONTROL Configuration]-Einstellungen aufzurufen, oder klicken Sie auf **[!UICONTROL Data Export Labels]**, um die Exportsteuerelemente auf das [!DNL destination] anzuwenden.

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Dieser Abschnitt enthält Optionen, die [Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein [!DNL URL]-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Steuerelemente für den Datenexport verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]**, um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung aus, die der Datenexportkontrolle entspricht, die auf das Ziel angewendet wurde (weitere Informationen finden Sie unter [Hinzufügen &quot;Beschriftungen in ein Ziel exportieren](/help/using/features/destinations/add-data-export-labels.md)&quot;).
3. Klicken **[!UICONTROL Save]**.

## Konfiguration {#configure-base-data}

Dieser Abschnitt enthält Optionen, mit denen Sie eine Basis-[!DNL URL]- und durch die [!DNL URL]-Zeichenfolge übergebene Datentrennzeichen festlegen können. Dieser Abschnitt ist optional. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Configuration]**, um die Steuerelemente anzuzeigen.
1. *(Optional)* Aktivieren Sie das  **[!UICONTROL Serialize]** Kontrollkästchen.
Auf diese Weise können Sie Segmente sequenziell an ein [!DNL destination] senden, anstatt für jedes Segment separate Aufrufe durchzuführen. Durch die Serialisierung wird die Datenübertragung effizienter. Wenn Sie dieses Kontrollkästchen aktivieren, werden die Felder &quot;URL&quot;und &quot;Trennzeichen&quot;angezeigt. Weitere Informationen finden Sie unter [Standardwerte und Serielle Schlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md).
1. Wenn Sie **[!UICONTROL Serialize]** auswählen, müssen Sie auch die unten beschriebenen Felder für URL und Trennzeichen konfigurieren.

| Feld | Beschreibung |
|--- |--- |
| [!UICONTROL Base URL] | Der Basisteil eines Standards `HTTP` [!DNL URL], der sich nicht ändert. Außerdem müssen Sie das `%ALIAS%` [Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in die Basis-URL setzen. Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Der Basisteil eines sicheren `HTTPS` [!DNL URL], der sich nicht ändert. Außerdem müssen Sie `%ALIAS%`   [Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL. Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Das Symbol, das die Segmentvariablen im String [!DNL URL] trennt. Dies ist normalerweise ein Komma oder Semikolon. Rufen Sie diese Informationen von Ihrem Partner ab. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und diese zu Ihrem [!UICONTROL destination] hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]**, um die Steuerelemente anzuzeigen.
1. Geben Sie im Feld **[!UICONTROL Search and Add Segments]** den Segmentnamen ein oder klicken Sie auf **[!UICONTROL Browse All Segments]**, um eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]**, wenn Sie das gewünschte Segment finden. Durch Hinzufügen eines Segments wird das Fenster [!UICONTROL Edit Mapping] geöffnet.
1. Mit [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geben Sie die Schlüssel-Wert-Paare an, die vom Segment verwendet werden.
   * **[!UICONTROL Start Date]** und  **[!UICONTROL End Date]**: Wählen Sie einen Beginn und ein Enddatum für den  [!DNL destination]. Wenn das Enddatum leer ist, läuft [!DNL destination] nie ab.
1. Klicken **[!UICONTROL Done]**.
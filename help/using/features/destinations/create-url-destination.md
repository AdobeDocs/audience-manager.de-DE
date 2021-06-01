---
description: Ein URL-Ziel führt Pixelaufrufe von einer Seite an Ihr Ziel durch. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit Destination Builder zu erstellen.
seo-description: Ein URL-Ziel führt Pixelaufrufe von einer Seite an Ihr Ziel durch. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit Destination Builder zu erstellen.
seo-title: Konfigurieren eines URL-Ziels
solution: Audience Manager
title: Konfigurieren eines URL-Ziels
feature: Zielgrundlagen
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 3%

---

# Konfigurieren eines [!DNL URL Destination] {#configure-url-destination}

Ein [!DNL URL destination] führt Pixelaufrufe von einer Seite zu Ihrem [!DNL destination] durch. Befolgen Sie diese Anweisungen, um ein [!DNL URL] [!DNL destination] mit [!UICONTROL Destination Builder] zu erstellen.

<!-- create-url-destination.xml -->

Um ein neues [!DNL URL] [!DNL destination] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Destinations > Create New Destination]** und füllen Sie die Abschnitte wie unten beschrieben aus.

## Basisinformationen {#basic-info}

Dieser Abschnitt enthält Felder und Optionen, die den Erstellungsprozess [!DNL URL destination] starten. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Basic Information]** , um die Steuerelemente anzuzeigen.
2. Benennen Sie [!DNL destination]. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie die  [!DNL destination]. Eine kurze Beschreibung ist eine effektive Möglichkeit, um mehr Informationen über ein [!DNL destination] zu definieren oder bereitzustellen.
4. Wählen Sie in der Liste **[!UICONTROL Category]** **[!UICONTROL Custom]** aus.
5. Wählen Sie in der Liste **[!UICONTROL Environment]** die Umgebung aus, in der die [!DNL URL destination]-URL Trigger werden soll.
6. Klicken Sie in der Liste **[!UICONTROL Type]** auf **[!UICONTROL URL]**.
7. *(Optional)* Wählen Sie eine  **[!UICONTROL Auto-fill Destination Mapping]** aus. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt die Segment-ID automatisch hinzu und sendet sie an die  [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist eine eindeutige Kennung, die vom Kunden erstellt und verwendet wird. Er ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie auf **[!UICONTROL Next]** , um zu den Einstellungen [!UICONTROL Configuration] zu wechseln, oder klicken Sie auf **[!UICONTROL Data Export Labels]** , um die Exportkontrollen auf [!DNL destination] anzuwenden.

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Dieser Abschnitt enthält Optionen, die [Datenexportkontrollen](../../features/data-export-controls.md) auf ein [!DNL URL]-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexport-Steuerelemente verwenden. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung aus, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (weitere Informationen finden Sie unter [Hinzufügen von Exportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) ).
3. Klicken **[!UICONTROL Save]**.

## Konfiguration {#configure-base-data}

Dieser Abschnitt enthält Optionen, mit denen Sie eine Basis-[!DNL URL] und durch die [!DNL URL]-Zeichenfolge übergebene Datentrennzeichen festlegen können. Dieser Abschnitt ist optional. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Configuration]** , um die Steuerelemente anzuzeigen.
1. *(Optional)* Aktivieren Sie das  **[!UICONTROL Serialize]** Kontrollkästchen.
Auf diese Weise können Sie Segmente sequenziell an [!DNL destination] senden, anstatt für jedes Segment separate Aufrufe durchzuführen. Die Serialisierung trägt dazu bei, Datenübertragungen effizienter zu gestalten. Wenn Sie dieses Kontrollkästchen aktivieren, werden die Felder URL und Trennzeichen angezeigt. Weitere Informationen finden Sie unter [Standardmäßige und serielle Schlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md).
1. Wenn Sie **[!UICONTROL Serialize]** auswählen, müssen Sie auch die unten beschriebenen Felder URL und Trennzeichen konfigurieren.

| Feld | Beschreibung |
|--- |--- |
| [!UICONTROL Base URL] | Der Basisteil eines Standards `HTTP` [!DNL URL] , der sich nicht ändert. Außerdem müssen Sie das `%ALIAS%` [Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in die Basis-URL einfügen. Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Der Basisteil eines sicheren `HTTPS` [!DNL URL] , der sich nicht ändert. Außerdem müssen Sie `%ALIAS%` platzieren   [Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL. Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Das Symbol, das die Segmentvariablen in der Zeichenfolge [!DNL URL] trennt. Dies ist normalerweise ein Komma oder ein Semikolon. Rufen Sie diese Informationen von Ihrem Zielpartner ab. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und diese Ihrem [!UICONTROL destination] hinzufügen. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]** , um die Steuerelemente anzuzeigen.
1. Geben Sie im Feld **[!UICONTROL Search and Add Segments]** den Namen eines Segments ein oder klicken Sie auf **[!UICONTROL Browse All Segments]**, um eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das Segment finden, das Sie verwenden möchten. Durch Hinzufügen eines Segments wird das Fenster [!UICONTROL Edit Mapping] geöffnet.
1. Mit [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geben Sie die Schlüssel-Wert-Paare an, die vom Segment verwendet werden.
   * **[!UICONTROL Start Date]** und  **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für die  [!DNL destination]aus. Wenn das Enddatum leer ist, läuft [!DNL destination] nie ab.
1. Klicken **[!UICONTROL Done]**.

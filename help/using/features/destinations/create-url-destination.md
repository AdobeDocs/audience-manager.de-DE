---
description: Ein URL-Ziel führt Pixelaufrufe von einer Seite an Ihr Ziel durch. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit Destination Builder zu erstellen.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Konfigurieren eines URL-Ziels
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 1%

---

# Konfigurieren eines [!DNL URL Destination] {#configure-url-destination}

Ein [!DNL URL destination] führt Pixelaufrufe von einer Seite zu Ihrem [!DNL destination] durch. Befolgen Sie diese Anweisungen, um eine [!DNL URL] [!DNL destination] mit [!UICONTROL Destination Builder] zu erstellen.

<!-- create-url-destination.xml -->

Um eine neue [!DNL URL] [!DNL destination] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Destinations > Create New Destination]** und füllen Sie die Abschnitte wie unten beschrieben aus.

## Basisinformationen {#basic-info}

Dieser Abschnitt enthält Felder und Optionen, die den Erstellungsprozess für [!DNL URL destination] starten. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Basic Information]** , um die Steuerelemente anzuzeigen.
2. Nennen Sie die &quot;[!DNL destination]&quot;. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie die [!DNL destination]. Eine kurze Beschreibung ist eine effektive Möglichkeit, um mehr Informationen über ein [!DNL destination] zu definieren oder bereitzustellen.
4. Wählen Sie in der Liste **[!UICONTROL Category]** die Option **[!UICONTROL Custom]**.
5. Wählen Sie in der Liste &quot;**[!UICONTROL Environment]**&quot;die Umgebung aus, in der der Trigger &quot;[!DNL URL destination]&quot;erfolgen soll.
6. Klicken Sie in der Liste **[!UICONTROL Type]** auf **[!UICONTROL URL]**.
7. *(Optional)* Wählen Sie einen **[!UICONTROL Auto-fill Destination Mapping]** aus. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt die Segment-ID automatisch hinzu und sendet sie an die [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist eine eindeutige Kennung, die vom Kunden erstellt und verwendet wird. Er ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie auf **[!UICONTROL Next]** , um zu den Einstellungen [!UICONTROL Configuration] zu wechseln, oder klicken Sie auf **[!UICONTROL Data Export Labels]** , um Exportkontrollen auf die [!DNL destination] anzuwenden.

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Dieser Abschnitt enthält Optionen, die [Datenexport-Steuerelemente](../../features/data-export-controls.md) auf ein [!DNL URL] -Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexport-Steuerelemente verwenden. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung aus, die der auf das Ziel angewendeten Datenexport-Kontrolle entspricht (weitere Informationen finden Sie unter [Hinzufügen von Exportbeschriftungen zu einem Ziel ](/help/using/features/destinations/add-data-export-labels.md) ).
3. Klicken Sie auf **[!UICONTROL Save]**.

## Konfiguration {#configure-base-data}

Dieser Abschnitt enthält Optionen zum Festlegen von Basis-Trennzeichen [!DNL URL] und von der [!DNL URL] -Zeichenfolge übergebenen Datentrennzeichen. Dieser Abschnitt ist optional. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Configuration]** , um die Steuerelemente anzuzeigen.
1. *(Optional)* Aktivieren Sie das Kontrollkästchen **[!UICONTROL Serialize]**.
Auf diese Weise können Sie Segmente sequenziell an [!DNL destination] senden, anstatt für jedes Segment separate Aufrufe durchzuführen. Die Serialisierung trägt dazu bei, Datenübertragungen effizienter zu gestalten. Wenn Sie dieses Kontrollkästchen aktivieren, werden die Felder URL und Trennzeichen angezeigt. Weitere Informationen finden Sie unter [Standardwerte und Serielle Schlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md).
1. Wenn Sie &quot;**[!UICONTROL Serialize]**&quot;auswählen, müssen Sie auch die unten beschriebenen Felder URL und Trennzeichen konfigurieren.

| Feld | Beschreibung |
|--- |--- |
| [!UICONTROL Base URL] | Der Basisteil eines standardmäßigen `HTTP` [!DNL URL], der sich nicht ändert. Außerdem müssen Sie das Platzhaltermakro `%ALIAS%` [2} in die Basis-URL einfügen. ](../../features/destinations/destination-macros.md#destination-macros-defined) Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Der Basisteil eines sicheren `HTTPS` [!DNL URL] , der sich nicht ändert. Außerdem müssen Sie die `%ALIAS%` platzieren   [Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL. Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Das Symbol, das die Segmentvariablen in der Zeichenfolge [!DNL URL] trennt. Dies ist normalerweise ein Komma oder ein Semikolon. Rufen Sie diese Informationen von Ihrem Zielpartner ab. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und diese Ihrem [!UICONTROL destination] hinzufügen. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]** , um die Steuerelemente anzuzeigen.
1. Geben Sie im Feld **[!UICONTROL Search and Add Segments]** den Namen eines Segments ein oder klicken Sie auf **[!UICONTROL Browse All Segments]**, um eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das Segment finden, das Sie verwenden möchten. Durch Hinzufügen eines Segments wird das Fenster [!UICONTROL Edit Mapping] geöffnet.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geben Sie die Schlüssel-Wert-Paare an, die vom Segment verwendet werden.
   * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für die [!DNL destination] aus. Wenn das Enddatum leer ist, läuft der [!DNL destination] nie ab.
1. Klicken Sie auf **[!UICONTROL Done]**.

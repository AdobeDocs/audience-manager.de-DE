---
description: Ein URL-Ziel führt Pixel-Aufrufe von einer Seite zu Ihrem Ziel durch. Befolgen Sie diese Anweisungen, um mit Destination Builder ein URL-Ziel zu erstellen.
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

Ein [!DNL URL destination] führt Pixel-Aufrufe von einer Seite zu Ihrer [!DNL destination] durch. Befolgen Sie diese Anweisungen, um eine [!DNL URL] [!DNL destination] mit [!UICONTROL Destination Builder] zu erstellen.

<!-- create-url-destination.xml -->

Um ein neues [!DNL URL]-[!DNL destination] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Destinations > Create New Destination]** und füllen Sie die Abschnitte wie unten beschrieben aus.

## Basisinformationen {#basic-info}

Dieser Abschnitt enthält Felder und Optionen, mit denen der [!DNL URL destination] gestartet wird. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Basic Information]** , um die Steuerelemente anzuzeigen.
2. Benennen Sie die [!DNL destination]. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie die [!DNL destination]. Eine knappe Beschreibung ist eine effektive Möglichkeit, um mehr Informationen über eine [!DNL destination] zu definieren oder bereitzustellen.
4. Wählen Sie in der Liste **[!UICONTROL Category]** die Option **[!UICONTROL Custom]** aus.
5. Wählen Sie in der **[!UICONTROL Environment]** die Umgebung aus, in der die [!DNL URL destination] Trigger werden sollen.
6. Klicken Sie in der **[!UICONTROL Type]** auf **[!UICONTROL URL]**.
7. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]** aus. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: fügt die Segment-ID automatisch hinzu und sendet sie an die [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrations-Code hinzu und sendet ihn an die Zielzuordnung. Der Integrations-Code ist eine eindeutige Kennung, die vom Kunden erstellt und verwendet wird. Es ist auf maximal 255 Zeichen begrenzt.
8. Klicken Sie auf **[!UICONTROL Next]** , um zu den [!UICONTROL Configuration] zu wechseln, oder klicken Sie auf **[!UICONTROL Data Export Labels]** , um Exportsteuerelemente auf die [!DNL destination] anzuwenden.

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Dieser Abschnitt enthält Optionen, die [Datenexportsteuerelemente) &#x200B;](../../features/data-export-controls.md) ein [!DNL URL] Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Data Export Labels]** , um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung aus, die dem auf das Ziel angewendeten Datenexportsteuerelement entspricht (weitere Informationen finden Sie unter [Hinzufügen von &#x200B;](/help/using/features/destinations/add-data-export-labels.md) zu einem Ziel).
3. Klicken Sie auf **[!UICONTROL Save]**.

## Konfiguration {#configure-base-data}

Dieser Abschnitt enthält Optionen, mit denen Sie eine [!DNL URL] festlegen und Datentrennzeichen festlegen können, die von der [!DNL URL] übergeben werden. Dieser Abschnitt ist optional. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Configuration]** , um die Steuerelemente anzuzeigen.
1. *(Optional)* Aktivieren Sie das Kontrollkästchen **[!UICONTROL Serialize]** .
Auf diese Weise können Sie Segmente sequenziell an einen [!DNL destination] senden, anstatt für jedes Segment separate Aufrufe durchzuführen. Die Serialisierung hilft, Datenübertragungen effizient zu gestalten. Wenn Sie dieses Kontrollkästchen aktivieren, werden die URL- und Trennzeichenfelder angezeigt. Weitere Informationen finden Sie unter [Standardmäßige und serielle Schlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md).
1. Wenn Sie **[!UICONTROL Serialize]** auswählen, müssen Sie auch die unten beschriebenen URL- und Trennzeichenfelder konfigurieren.

| Feld | Beschreibung |
|--- |--- |
| [!UICONTROL Base URL] | Der Basisteil eines `HTTP` [!DNL URL], der sich nicht ändert. Außerdem müssen Sie das `%ALIAS%`Platzhaltermakro[&#x200B; in &#x200B;](../../features/destinations/destination-macros.md#destination-macros-defined) Basis-URL einfügen. Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Der Basisteil eines sicheren `HTTPS` [!DNL URL], der sich nicht ändert. Außerdem müssen Sie die `%ALIAS%` platzieren   [Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL Beispiel: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Das Symbol, das die Segmentvariablen in der [!DNL URL] trennt. Dies ist normalerweise ein Komma oder Semikolon. Rufen Sie diese Informationen von Ihrem Zielpartner ab. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und diese zu Ihrem [!UICONTROL destination] hinzufügen. So schließen Sie diesen Abschnitt ab:

1. Klicken Sie auf **[!UICONTROL Segment Mappings]** , um die Steuerelemente anzuzeigen.
1. Beginnen Sie im **[!UICONTROL Search and Add Segments]**, den Namen eines Segments einzugeben, oder klicken Sie **[!UICONTROL Browse All Segments]** eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken Sie auf **[!UICONTROL Add Selected Segments]** , wenn Sie das Segment finden, das Sie verwenden möchten. Durch Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] geöffnet.
1. In [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Angabe der vom Segment verwendeten Schlüssel-Wert-Paare.
   * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für die [!DNL destination] aus. Wenn das Enddatum leer ist, läuft die [!DNL destination] nie ab.
1. Klicken Sie auf **[!UICONTROL Done]**.

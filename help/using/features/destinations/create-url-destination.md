---
description: Ein URL-Ziel führt Pixelaufrufe von einer Seite zu Ihrem Ziel aus. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit Zielaufbau zu erstellen.
seo-description: Ein URL-Ziel führt Pixelaufrufe von einer Seite zu Ihrem Ziel aus. Befolgen Sie diese Anweisungen, um ein URL-Ziel mit Zielaufbau zu erstellen.
seo-title: URL-Ziel konfigurieren
solution: Audience Manager
title: URL-Ziel konfigurieren
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---



# URL-Ziel konfigurieren {#configure-url-destination}

Ein [!DNL URL] Ziel führt Pixelaufrufe von einer Seite zu Ihrem Ziel aus. Befolgen Sie diese Anweisungen, um ein [!DNL URL] Ziel zu [!UICONTROL Destination Builder]erstellen.

<!-- create-url-destination.xml -->

Um ein neues [!DNL URL] Ziel zu erstellen, gehen **[!UICONTROL Audience Data > Destinations > Create New Destination]** Sie zu den Abschnitten, wie unten beschrieben.

## Basisinformationen {#basic-info}

Dieser Abschnitt enthält Felder und Optionen, die den URL-Zielerstellungsprozess starten. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Basic Information]** Sie auf, um die Steuerelemente anzuzeigen.
2. Geben Sie dem Ziel einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine genaue Beschreibung ist eine effektive Möglichkeit, weitere Informationen zu einem Ziel zu definieren oder bereitzustellen.
4. Wählen Sie in der **[!UICONTROL Category]** Liste **[!UICONTROL Custom]** den Eintrag.
5. Wählen Sie in der **[!UICONTROL Environment]** Liste die Umgebung aus, in der das URL-Ziel ausgelöst werden soll.
6. Klicken Sie in der **[!UICONTROL Type]** Liste **[!UICONTROL URL]** auf.
7. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]**. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt automatisch die Segment-ID hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Sie ist auf maximal 255 Zeichen begrenzt.
8. Klicken **[!UICONTROL Next]** Sie auf, um die [!UICONTROL Configuration] Einstellungen aufzurufen, oder klicken **[!UICONTROL Data Export Labels]** Sie auf, um die Exportsteuerelemente auf das Ziel anzuwenden.

## Datenexportbeschriftungen {#data-export-labels-dest}

Dieser Abschnitt enthält Optionen, die [die Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein [!DNL URL] Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Data Export Labels]** Sie auf, um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung, die dem auf das Ziel angewendeten Datenexportsteuerelement entspricht (siehe [Hinzufügen von Exportbeschriftungen zu einem Ziel](/help/using/features/destinations/add-data-export-labels.md) für weitere Details).
3. Klicken Sie auf **[!UICONTROL Save]**.

## Konfiguration {#configure-base-data}

Dieser Abschnitt enthält Optionen, mit denen Sie eine Basis [!DNL URL] - und Datentrennzeichen festlegen können, die durch die [!DNL URL] Zeichenfolge weitergegeben werden. Dieser Abschnitt ist optional. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Configuration]** Sie auf, um die Steuerelemente anzuzeigen.
1. *(Optional)* Aktivieren Sie das **[!UICONTROL Serialize]** Kontrollkästchen.
Dadurch können Sie Segmente an ein Ziel senden, anstatt jedem Segment separate Aufrufe zu tätigen. Die Serialisierung erleichtert die effiziente Datenübertragung. Wenn Sie dieses Kontrollkästchen aktivieren, werden die Felder "URL" und" Trennzeichen" angezeigt. Weitere Informationen finden Sie unter [Standard- und Serialschlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md).
1. Wenn Sie auswählen **[!UICONTROL Serialize]**, müssen Sie auch die unten beschriebenen URL- und Trennzeichen konfigurieren.

| Feld | Beschreibung |
|--- |--- |
| Basis-URL | Der Basisteil eines Standards, `HTTP`[!DNL URL] der sich nicht ändert. Außerdem müssen Sie das `%ALIAS%`[Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL platzieren. Beispiel: `https://www.myCompany.com/%alias%...` |
| Sichere URL | Der Basisteil eines sicheren Schutzes, `HTTPS`[!DNL URL] der sich nicht ändert. Außerdem müssen Sie das `%ALIAS%`[Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL platzieren. Beispiel: `https://www.myCompany.com/%alias%...` |
| Trennzeichen | Das Symbol, das die Segmentvariablen in der [!DNL URL] Zeichenfolge trennt. Dies ist normalerweise ein Komma oder ein Semikolon. Erhalten Sie diese Informationen von Ihrem Zielpartner. |

## Segmentzuordnungen {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Segment Mappings]** Sie auf, um die Steuerelemente anzuzeigen.
1. Geben Sie in das **[!UICONTROL Search and Add Segments]** Feld den Namen eines Segments ein oder klicken **[!UICONTROL Browse All Segments]** Sie auf eine Liste der verfügbaren Segmente.
1. Klicken **[!UICONTROL Add Selected Segments]** Sie auf, wenn Sie das gewünschte Segment suchen. Durch das Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
1. Mit [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geben Sie die Schlüssel/Wert-Paare ein, die vom Segment verwendet werden.
   * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken Sie auf **[!UICONTROL Done]**.
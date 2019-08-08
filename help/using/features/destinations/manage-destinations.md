---
description: Auf der Ziellandingpage werden alle URL-, Cookie- und Server-to-Server-Ziele aufgelistet. Es bietet Funktionen, mit denen Sie Ziele erstellen, bearbeiten, suchen und Berichte erstellen können. Die Einstiegsseite befindet sich unter Zielgruppendaten > Ziele.
seo-description: Auf der Ziellandingpage werden alle URL-, Cookie- und Server-to-Server-Ziele aufgelistet. Es bietet Funktionen, mit denen Sie Ziele erstellen, bearbeiten, suchen und Berichte erstellen können. Die Einstiegsseite befindet sich unter Zielgruppendaten > Ziele.
seo-title: Ziele verwalten
solution: Audience Manager
title: Ziele verwalten
uuid: 6 b 66 ff 42-0075-49 a 7-a 58 f -7 f 8 ea 2295 fdc
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Ziele verwalten {#manage-destinations}

Auf der [!UICONTROL Destination] Einstiegsseite werden alle Ziele, [!DNL URL]Cookies und Server-to-Server-Ziele aufgelistet. Es bietet Funktionen, mit denen Sie Ziele erstellen, bearbeiten, suchen und Berichte erstellen können. Die Einstiegsseite **[!UICONTROL Audience Data > Destinations]** befindet sich in.

## Standard-Landingpage {#default-landing-page}

<!-- destinations-home.xml -->

Auf der Standardmäßigen Landingpage werden Ihre Ziele basierend auf dem Typ aufgelistet. Sie können die Ziele mithilfe der vier verfügbaren Registerkarten filtern:

* **Alle**: zeigt alle Arten von Zielen an.
* **Adobe Experience Cloud**: zeigt Ziele an, die Daten an andere Adobe Experience Cloud-Lösungen senden. Derzeit wird nur Adobe Analytics unterstützt. See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **Integrierte Plattformen**: zeigt benutzerbasierte und gerätebasierte Ziele an (auch als Server-zu-Server-Ziele bezeichnet). Beachten Sie, dass benutzerbasierte Ziele derzeit nur für ausgewählte Kunden verfügbar sind.
* **Benutzerspezifisch**: zeigt Cookie- und URL-Ziele an.


![](assets/destinations-landing.png)

## Addressable Audiences-Einstiegsseite {#audiences-landing-page}

Um Zielgruppendaten und Übereinstimmungsraten für Ihr Server-to-Server-Ziel anzuzeigen, wählen **[!UICONTROL Integrated Platforms > Device-Based]** Sie die Option.

Weitere Informationen zu den angezeigten Informationen finden Sie unter [Addressable Audiences Interface](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## URL-Ziel konfigurieren {#configure-url-destination}

Ein [!DNL URL] Ziel führt Pixelaufrufe von einer Seite zu Ihrem Ziel aus. Befolgen Sie diese Anweisungen, um ein [!DNL URL] Ziel zu [!UICONTROL Destination Builder]erstellen.

<!-- create-url-destination.xml -->

Um ein neues [!DNL URL] Ziel zu erstellen, gehen **[!UICONTROL Audience Data > Destinations > Create New Destination]** Sie zu den Abschnitten, wie unten beschrieben.

### Basisinformationen {#basic-info}

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

### Datenexportbeschriftungen {#data-export-labels-dest}

Dieser Abschnitt enthält Optionen, die [die Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein [!DNL URL] Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Data Export Labels]** Sie auf, um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung, die dem auf das Ziel angewendeten Datenexportsteuerelement entspricht (siehe [Hinzufügen von Exportbeschriftungen zu einem Ziel](../../features/destinations/manage-destinations.md#add-data-export-labels) für weitere Details).
3. Klicken Sie auf **[!UICONTROL Save]**.

### Konfiguration {#configure-base-data}

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

### Segmentzuordnungen {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Segment Mappings]** Sie auf, um die Steuerelemente anzuzeigen.
1. Geben Sie in das **[!UICONTROL Search and Add Segments]** Feld den Namen eines Segments ein oder klicken **[!UICONTROL Browse All Segments]** Sie auf eine Liste der verfügbaren Segmente.
1. Klicken **[!UICONTROL Add Selected Segments]** Sie auf, wenn Sie das gewünschte Segment suchen. Durch das Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
1. Mit [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geben Sie die Schlüssel/Wert-Paare ein, die vom Segment verwendet werden.
   * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken Sie auf **[!UICONTROL Done]**.

## Segmente für Server-zu-Server-Ziele hinzufügen oder bearbeiten {#add-edit-segments}

Sie können nur Segmente für ein Server-to-Server ([!DNL S2S])-Ziel hinzufügen oder bearbeiten. Ziele können nicht erstellt [!DNL S2S][!UICONTROL Destination Builder]werden. Wenden Sie sich an Ihren Berater, um [!DNL S2S] Ziele einzurichten. Befolgen Sie diese Anweisungen, um Segmente für ein [!DNL S2S] Ziel hinzuzufügen oder zu bearbeiten.

<!-- destination-s2s-edit.xml -->

So fügen Sie Segmentzuordnungen für ein [!DNL S2S] Ziel hinzu oder bearbeiten es:

1. Gehe **[!UICONTROL Audience Data > Destinations]** zu. Wählen **Sie Integrierte Plattformen &gt; Gerätebasiert** und suchen Sie das [!DNL S2S] Ziel, mit dem Sie arbeiten möchten.
2. Klicken Sie in der [!UICONTROL Action] Spalte auf das Stiftsymbol, um das Ziel zu bearbeiten.
   * Geben Sie in das **[!UICONTROL Search and Add Segments]** Feld den Namen eines Segments ein oder klicken **[!UICONTROL Browse All Segments]** Sie auf eine Liste der verfügbaren Segmente.
   * Klicken **[!UICONTROL Add Selected Segments]** Sie auf, wenn Sie das gewünschte Segment suchen. Durch das Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
   * Mit [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Legen Sie einen Wert für das [Schlüssel-Wert-Paar](../../features/destinations/key-value-pairs.md) fest, das von diesem Ziel verwendet wird.
      * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
3. Klicken **[!UICONTROL Save]****[!UICONTROL Done]** Sie auf und dann auf.

## Datenexport-Beschriftungen zu einem Ziel hinzufügen {#add-data-export-labels}

[!DNL Data Export Labels] mit den [!DNL Export Controls] in einer Datenquelle festgelegten Arbeiten. [!DNL Data Export Labels] verhindern, dass Sie einem Segment eingeschränkte Eigenschaften hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Beschriftungen auf ein neues oder ein vorhandenes [!DNL cookie] oder [!DNL URL] ein Ziel festlegen.

>[!NOTE]
>
>Um eine Exportbeschriftung hinzuzufügen, benötigen Sie Administratorrechte *oder* ausreichende Rechte, um ein Ziel zu erstellen oder zu bearbeiten.

<!-- t_export_labels.xml -->

So fügen Sie einem Ziel eine Exportbeschriftung hinzu:

1. Klicken Sie auf **[!UICONTROL Audience Data]**:
   * Für neue Ziele: Klicken **[!UICONTROL Create New Destination]** Sie auf. Füllen Sie den [!UICONTROL Basic Information] Abschnitt aus, bevor Sie eine Datenexportbeschriftung auswählen. Weitere Informationen finden Sie unter [Erstellen eines Cookie-Ziels](../../features/destinations/manage-destinations.md#create-cookie-destination) oder [Erstellen eines URL-Ziels](../../features/destinations/manage-destinations.md#configure-url-destination) .
   * Für vorhandene Ziele: Verwenden Sie das [!DNL Search] Kästchen, um Ihr Ziel zu finden, oder klicken Sie auf den Zielnamen, um ihn zu öffnen.
1. Wählen Sie eine [!DNL Data Export Label]. Lassen Sie die Kontrollkästchen leer, wenn Sie keine Exportbeschränkungen festlegen möchten. Zu den Exportbeschriftungen zählen die folgenden Optionen:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Exporteinschränkungen funktionieren nur, wenn Sie ein [passendes Exportsteuerelement](../../features/data-export-controls.md) für eine Datenquelle festlegen.
1. Klicken Sie auf **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Datenquelle erstellen](../../features/manage-datasources.md#create-data-source)


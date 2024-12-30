---
description: Richten Sie Open Ad Server als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS als Audience Manager-Ziel
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 0%

---

# OAS als Audience Manager-Ziel {#oas-as-an-audience-manager-destination}

Richten Sie [!DNL Open Ad Server] als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.

## OAS-Zielanforderungen {#oas-requirements}

Standards für die Code-Platzierung, unterstützte Schlüsselwertformate, Berichte und den Typ der an [!DNL OAS] gesendeten Segmentdaten.

<!-- aam-oas-requirements.xml -->

Dieser Zieltyp erfordert Folgendes:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] Code sollte im Inventar bereitgestellt werden. [!UICONTROL DIL] ist es nicht mehr erforderlich, speziellen Code für die Datenerfassung, -integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben.
* **`get_aamCookie`:**, der die Benutzer-ID des Audience Managers und Cookie-Daten erfasst. Platzieren Sie [diesen Code](../../features/destinations/get-aam-cookie-code.md) oben auf der Seite oder im `<head>` Codeblock.
* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentversandbericht erstellen möchten (optional), stellen Sie dem Audience Manager ein tägliches Protokoll zur Verfügung, das Versanddaten auf Impression-Ebene enthält. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss die [!UICONTROL UUID] Audience Manager enthalten. Audience Manager können diese per [!DNL FTP] abholen oder empfangen.

### Cookie-Format und Schlüssel-Wert-Daten

Audience Manager können Segmentdaten wie folgt an ein Browser-Cookie senden:

* Einzelschlüssel (`x=1&x=2`);
* Mehrere Schlüssel (`x=1&x=2&y=3&y=4`);
* Serialisierte Werte (`x=1,2,3`);
* Ein Standardwerttrennzeichen, das zum Trennen einzelner Schlüssel-Wert-Paare verwendet wird.

### Nur qualifizierte Segmente werden an OAS gesendet

Wie viele Daten an [!DNL OAS] übergeben werden, hängt davon ab, für wie viele Segmente sich ein bestimmter Benutzer qualifiziert. Angenommen, Sie richten 100 Audience Manager-Segmente ein. Wenn sich ein Site-Besucher für fünf von ihnen qualifiziert, werden nur diese fünf Segmente an OAS gesendet (nicht alle 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-Code](../../features/destinations/get-aam-cookie-code.md)
>* [Schlüssel-Wert-Paare – Erklärung](../../reference/key-value-pairs-explained.md)

## Erstellen eines OAS-Ziels {#oas-dest-setup}

Erstellen Sie ein Cookie-basiertes Ziel für [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

Im Audience Manager ist *Ziel* jedes andere System (Werbeserver, [!DNL DSP], Werbenetzwerk usw.), für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Audience Manager-Zielfunktionen befinden sich unter *Zielgruppendaten > Ziele*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]** und führen Sie die folgenden Schritte aus.

### Schritt 1: Grundlegende Informationen

So schließen Sie den Abschnitt [!UICONTROL Basic Information] ab:

1. Benennen Sie das Ziel.
1. Wählen Sie **[!UICONTROL "Cookie"]** aus der Dropdown-Liste [!UICONTROL Type] aus.
1. Klicken Sie auf **[!UICONTROL Save]** und fahren Sie mit den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] fort.

### Schritt 2: Konfigurationsinformationen

So schließen Sie den Abschnitt [!UICONTROL Configuration] ab:

1. **Cookie-Name:** Geben Sie einen kurzen, beschreibenden Namen für Ihr Cookie an.
1. **Cookie-Domain** Lassen Sie dieses Feld leer, um ein Cookie in der Domain der aktuellen Seite des Benutzers zu setzen. Wenn Sie eine Domain angeben möchten, setzen Sie `.mydomain.com` einen Punkt vor den Namen.
1. Wählen Sie eine Schlüsseloption im Abschnitt [!UICONTROL Data Format] aus.
1. Wenn Ihre Schlüssel Daten mit serialisierten Werten verwenden, wählen Sie das **[!UICONTROL Serialize]** aus und geben Sie das serielle Trennzeichen (das Zeichen, das die serialisierten Werte trennt) an.
1. Klicken Sie auf **[!UICONTROL Save]** und erweitern Sie den Abschnitt [!UICONTROL Segment Mappings] .

### Schritt 3: Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. **Segmente suchen:** Der Abschnitt [!UICONTROL Segment Mappings] bietet zwei Suchwerkzeuge, mit denen Sie Segmente finden können. So suchen Sie ein Segment:
   * Option 1: Beginnen Sie, einen Segmentnamen in das Suchfeld einzugeben. Das Feld wird automatisch auf der Grundlage des Texts aktualisiert. Wenn Sie das Segment gefunden haben, das Sie verwenden möchten, klicken Sie auf **[!UICONTROL Add]** .
   * Option 2: Klicken Sie auf **[!UICONTROL Browse All Segments]** , um ein Fenster zu öffnen, in dem Sie nach Segmenten anhand des Namens oder des Speicherorts suchen können. Klicken Sie abschließend auf **[!UICONTROL Add Selected Segments]** .
1. **Zuordnungen hinzufügen:** Geben Sie im Pop-up „Zuordnungen“ die Segment-ID in das Feld Zuordnungen ein und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie auf **[!UICONTROL Done]**.

## OAS-Setup {#oas-code-setup}

Ändern Sie [!DNL OAS] Einstellungen, um mit Audience Manager-Segmentdaten zu arbeiten.

<!-- aam-oas-code.xml -->

Einrichten von [!DNL OAS]

* Installieren Sie [!UICONTROL DIL] Code auf Ihrer Site.
* Erstellen Sie OAS als Cookie-Ziel in Audience Manager.
* Platzieren Sie die `get_aamCookie` Funktion am Anfang der Seite, idealerweise im `<head>` Codeblock. Der `get_aamCookie`-Code ist verfügbar [hier](../../features/destinations/get-aam-cookie-code.md).
* Ändern Sie Ihr Anzeigen-Tag, um die Funktion `get_aamCookie` aufzurufen, und geben Sie den Cookie-Namen an, den Sie beim Einrichten des [!DNL OAS]-Ziels angegeben haben. Wenn Sie beispielsweise den Cookie-`test_cookie` benannt haben, sollte das Anzeigen-Tag `get_aamCookie` aufrufen und auf den Cookie-Namen verweisen.
* Ihr Anzeigen-Tag könnte dem folgenden Beispiel ähneln.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

Denken Sie daran, die Variable `u=` einzuschließen. Sie enthält die tatsächliche eindeutige Benutzer-ID ([!UICONTROL UUID]), die während eines Anzeigenaufrufs übergeben wurde.

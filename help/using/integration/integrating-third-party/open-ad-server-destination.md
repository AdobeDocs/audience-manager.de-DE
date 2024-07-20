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
ht-degree: 2%

---

# OAS als Audience Manager-Ziel {#oas-as-an-audience-manager-destination}

Richten Sie [!DNL Open Ad Server] als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.

## Anforderungen an das OAS-Ziel {#oas-requirements}

Standards für die Codeplatzierung, unterstützte Schlüsselwertformate, Berichte und den Typ der an [!DNL OAS] gesendeten Segmentdaten.

<!-- aam-oas-requirements.xml -->

Dieser Zieltyp erfordert Folgendes:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] -Code sollte auf Ihrem Bestand bereitgestellt werden. Mit [!UICONTROL DIL] können Sie vermeiden, dass Sie speziellen Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten schreiben müssen.
* **`get_aamCookie`Funktion:** Code, der die Audience Manager-Benutzer-ID und Cookie-Daten erfasst. Setzen Sie [diesen Code](../../features/destinations/get-aam-cookie-code.md) oben auf der Seite oder innerhalb des `<head>` -Codeblocks.
* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentversandbericht (optional) wünschen, stellen Sie dem Audience Manager ein tägliches Protokoll mit Versanddaten auf Impressionsebene zur Verfügung. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager [!UICONTROL UUID] enthalten. Audience Manager können diese über [!DNL FTP] abrufen oder empfangen.

### Cookie-Format und Schlüssel-Wert-Daten

Audience Manager können Segmentdaten wie folgt an ein Browser-Cookie senden:

* Einzelschlüssel (`x=1&x=2`);
* Mehrere Schlüssel (`x=1&x=2&y=3&y=4`);
* Serialisierte Werte (`x=1,2,3`);
* Ein Standardwerttrennzeichen, das zum Trennen einzelner Schlüssel-Wert-Paare verwendet wird.

### Nur qualifizierte Segmente werden an OAS gesendet

Die an [!DNL OAS] übergebenen Summendaten hängen von der Anzahl der Segmente ab, für die sich ein bestimmter Benutzer qualifiziert. Angenommen, Sie richten 100 Audience Manager-Segmente ein. Wenn ein Site-Besucher für fünf davon qualifiziert ist, werden nur diese fünf Segmente an OAS gesendet (nicht alle 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-Code](../../features/destinations/get-aam-cookie-code.md)
>* [Schlüssel-Wert-Paare – Erklärung](../../reference/key-value-pairs-explained.md)

## Erstellen eines OAS-Ziels {#oas-dest-setup}

Erstellen Sie ein Cookie-basiertes Ziel für [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

Im Audience Manager ist ein *Ziel* ein anderes System (Anzeigenserver, [!DNL DSP], Anzeigennetzwerk usw.) für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] bietet die Tools, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Die Audience Manager-Zielfunktionen befinden sich unter *Zielgruppendaten > Ziele*. Klicken Sie zunächst auf **[!UICONTROL Add New Destination]** und führen Sie die folgenden Schritte aus.

### Schritt 1: Grundlegende Informationen

So schließen Sie den Abschnitt [!UICONTROL Basic Information] ab:

1. Benennen Sie das Ziel.
1. Wählen Sie **[!UICONTROL "Cookie"]** aus der Dropdownliste [!UICONTROL Type] aus.
1. Klicken Sie auf **[!UICONTROL Save]** und fahren Sie mit den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] fort.

### Schritt 2: Konfigurationsinformationen

So schließen Sie den Abschnitt [!UICONTROL Configuration] ab:

1. **Cookie-Name:** Geben Sie einen kurzen, beschreibenden Namen für Ihr Cookie ein.
1. **Cookie-Domäne:** Lassen Sie das Feld leer, um ein Cookie in der Domäne der aktuellen Seite des Benutzers festzulegen. Wenn Sie eine Domäne angeben möchten, setzen Sie dem Namen den Punkt &quot;`.mydomain.com`&quot;voran.
1. Wählen Sie eine Schlüsseloption im Abschnitt [!UICONTROL Data Format] aus.
1. Wenn Ihre Schlüssel Daten mit serialisierten Werten verwenden, wählen Sie das Steuerelement **[!UICONTROL Serialize]** aus und geben Sie das serielle Trennzeichen (das Zeichen, das die serialisierten Werte trennt) an.
1. Klicken Sie auf &quot;**[!UICONTROL Save]**&quot;und erweitern Sie den Abschnitt &quot;[!UICONTROL Segment Mappings]&quot;.

### Schritt 3: Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. **Segmente suchen:** Der Abschnitt [!UICONTROL Segment Mappings] enthält zwei Suchwerkzeuge, mit denen Segmente gefunden werden können. So suchen Sie ein Segment:
   * Option 1: Beginnen Sie mit der Eingabe eines Segmentnamens in das Suchfeld. Das Feld wird automatisch auf der Basis des Textes aktualisiert. Klicken Sie auf **[!UICONTROL Add]** , sobald Sie das Segment gefunden haben, das Sie verwenden möchten.
   * Option 2: Klicken Sie auf **[!UICONTROL Browse All Segments]** , um ein Fenster zu öffnen, in dem Sie nach Namen oder Speicherort nach Segmenten suchen können. Klicken Sie abschließend auf **[!UICONTROL Add Selected Segments]** .
1. **Zuordnungen hinzufügen:** Geben Sie im Popup-Fenster &quot;Zuordnungen&quot;die Segment-ID in das Feld &quot;Zuordnungen&quot;ein und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie auf **[!UICONTROL Done]**.

## OAS-Einrichtung {#oas-code-setup}

Ändern Sie die [!DNL OAS] -Einstellungen, um mit den Segmentdaten des Audience Managers zu arbeiten.

<!-- aam-oas-code.xml -->

Einrichten von [!DNL OAS]

* Installieren Sie den Code [!UICONTROL DIL] auf Ihrer Site.
* Erstellen Sie OAS als Cookie-Ziel in Audience Manager.
* Platzieren Sie die Funktion `get_aamCookie` oben auf der Seite, idealerweise innerhalb des Codeblocks `<head>` . Der Code `get_aamCookie` ist [hier](../../features/destinations/get-aam-cookie-code.md) verfügbar.
* Ändern Sie Ihr Anzeigen-Tag, um die Funktion `get_aamCookie` aufzurufen, und fügen Sie den Cookie-Namen ein, den Sie beim Einrichten des [!DNL OAS] -Ziels angegeben haben. Wenn Sie beispielsweise das Cookie `test_cookie` nennen, sollte das Anzeigen-Tag `get_aamCookie` aufrufen und auf den Cookie-Namen verweisen.
* Ihr Anzeigen-Tag könnte dem unten stehenden Beispiel ähneln.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

Denken Sie daran, die Variable &quot;`u=`&quot;einzuschließen. Sie enthält die tatsächliche eindeutige Benutzer-ID ([!UICONTROL UUID]), die während eines Anzeigenaufrufs übergeben wird.

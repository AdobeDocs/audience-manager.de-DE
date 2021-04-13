---
description: Richten Sie Open Ad Server als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.
seo-description: Richten Sie Open Ad Server als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.
seo-title: OAS als Audience Manager-Ziel
solution: Audience Manager
title: OAS als Audience Manager-Ziel
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Integration von Drittanbietern
exl-id: cf919c27-691f-424b-be83-040f03e34455
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 4%

---

# OAS als Audience Manager-Ziel {#oas-as-an-audience-manager-destination}

Richten Sie [!DNL Open Ad Server] als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.

## OAS-Zielanforderungen {#oas-requirements}

Standards für die Codeplatzierung, unterstützte Schlüsselwertformate, Berichte und den Typ der an [!DNL OAS] gesendeten Segmentdaten.

<!-- aam-oas-requirements.xml -->

Dieser Zieltyp erfordert Folgendes:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] Code sollte in Ihrem Bestand bereitgestellt werden. [!UICONTROL DIL] hilft, die Notwendigkeit zu vermeiden, speziellen Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben.
* **`get_aamCookie`Funktion:** Code, der die Audience Manager-Benutzer-ID und Cookie-Daten erfasst. Platzieren Sie [diesen Code](../../features/destinations/get-aam-cookie-code.md) oben auf der Seite oder innerhalb des `<head>`-Codeblocks.
* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentbericht (optional) erstellen möchten, stellen Sie dem Audience Manager ein tägliches Protokoll zur Verfügung, das Versand-Daten auf Impressionsebene enthält. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager [!UICONTROL UUID] enthalten. Audience Manager können diese über [!DNL FTP] abrufen oder empfangen.

### Cookie-Format und Schlüsselwertdaten

Audience Manager können Segmentdaten wie folgt an ein Browser-Cookie senden:

* Einzelschlüssel (`x=1&x=2`);
* Mehrere Schlüssel (`x=1&x=2&y=3&y=4`);
* Serialisierte Werte (`x=1,2,3`);
* Ein Trennzeichen für Standardwerte, das zum Trennen einzelner Schlüssel/Wert-Paare verwendet wird.

### Nur qualifizierte Segmente werden an OAS gesendet

Die an [!DNL OAS] weitergeleiteten Daten hängen davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Angenommen, Sie richten 100 Audience Manager ein. Wenn ein Site-Besucher für fünf davon qualifiziert ist, werden nur diese fünf Segmente an OAS gesendet (nicht alle 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-Code](../../features/destinations/get-aam-cookie-code.md)
>* [Schlüssel-Wert-Paare – Erklärung](../../reference/key-value-pairs-explained.md)


## Erstellen eines OAS-Ziels {#oas-dest-setup}

Erstellen Sie ein cookie-basiertes Ziel für [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Managern ist ein *Ziel* ein anderes System (Anzeigenserver, [!DNL DSP], Anzeigennetzwerk usw.) für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Data Versand-Prozesse erstellen und verwalten können. Die Zielfunktionen des Audience Managers befinden sich unter *Audience Data > Destinations*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]** und befolgen Sie die folgenden Schritte.

### Schritt 1: Basisinformationen

So füllen Sie den Abschnitt [!UICONTROL Basic Information] aus:

1. Benennen Sie das Ziel.
1. Wählen Sie **[!UICONTROL "Cookie"]** aus der Dropdown-Liste [!UICONTROL Type].
1. Klicken Sie auf **[!UICONTROL Save]** und gehen Sie zu den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings].

### Schritt 2: Konfigurationsinformationen

So füllen Sie den Abschnitt [!UICONTROL Configuration] aus:

1. **Cookie-Name:** Geben Sie einen kurzen beschreibenden Namen für Ihr Cookie ein.
1. **Cookie-Domäne:** Lassen Sie das Feld leer, um ein Cookie in der Domäne der aktuellen Seite des Benutzers festzulegen. Wenn Sie eine Domäne angeben möchten, setzen Sie dem Namen einen Punkt wie den folgenden vorangestellten (`.mydomain.com`).
1. Wählen Sie eine Schlüsseloption im Abschnitt [!UICONTROL Data Format].
1. Wenn Ihre Schlüssel Daten mit serialisierten Werten verwenden, wählen Sie das **[!UICONTROL Serialize]**-Steuerelement und geben Sie das serielle Trennzeichen (das Zeichen, das die serialisierten Werte trennt) an.
1. Klicken Sie auf **[!UICONTROL Save]** und erweitern Sie den Abschnitt [!UICONTROL Segment Mappings].

### Schritt 3: Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. **Segmente suchen:** Der  [!UICONTROL Segment Mappings] Abschnitt enthält zwei Suchwerkzeuge, die Ihnen bei der Suche nach Segmenten helfen. So suchen Sie ein Segment:
   * Option 1: Beginn, der einen Segmentnamen in das Suchfeld eingibt. Das Feld wird automatisch anhand des Textes aktualisiert. Klicken Sie auf **[!UICONTROL Add]**, sobald Sie das gewünschte Segment gefunden haben.
   * Option 2: Klicken Sie auf **[!UICONTROL Browse All Segments]**, um ein Fenster zu öffnen, in dem Sie nach Datenspeicherung oder Namen suchen können. Klicken Sie abschließend auf **[!UICONTROL Add Selected Segments]**.
1. **hinzufügen Zuordnungen: Geben Sie** im Popupfenster &quot;Zuordnungen&quot;die Segment-ID in das Zuordnungsfeld ein und klicken Sie auf  **[!UICONTROL Save]**.
1. Klicken **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Ändern Sie die [!DNL OAS]-Einstellungen, um mit Segmentdaten des Audience Managers zu arbeiten.

<!-- aam-oas-code.xml -->

So richten Sie [!DNL OAS] ein

* [!UICONTROL DIL]-Code auf Ihrer Site installieren.
* Erstellen Sie OAS als Cookie-Ziel in Audience Manager.
* Platzieren Sie die Funktion `get_aamCookie` oben auf der Seite, idealerweise innerhalb des Codeblocks `<head>`. Der `get_aamCookie`-Code ist [hier](../../features/destinations/get-aam-cookie-code.md) verfügbar.
* Ändern Sie Ihr Anzeigentag, um die Funktion `get_aamCookie` aufzurufen, und fügen Sie den Cookie-Namen ein, den Sie beim Einrichten des [!DNL OAS]-Ziels angegeben haben. Wenn Sie beispielsweise das Cookie `test_cookie` benannt haben, sollte das Anzeigen-Tag `get_aamCookie` aufrufen und auf den Cookie-Namen verweisen.
* Ihr Anzeigentag könnte dem Beispiel unten ähnlich aussehen.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Denken Sie daran, die Variable `u=` einzuschließen. Es enthält die tatsächliche eindeutige Benutzer-ID ([!UICONTROL UUID]), die während eines Anzeigenaufrufs weitergegeben wird.

---
description: Richten Sie Open Ad Server als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.
seo-description: Richten Sie Open Ad Server als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.
seo-title: OAS als Zielgruppen-Manager-Ziel
solution: Audience Manager
title: OAS als Zielgruppen-Manager-Ziel
uuid: 5891 a 063-5 a 4 b -4 ea 7-865 f-b 24 e 17 ca 735 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OAS als Zielgruppen-Manager-Ziel {#oas-as-an-audience-manager-destination}

Richten Sie [!DNL Open Ad Server] ein Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.

## OAS-Zielanforderungen {#oas-requirements}

Standards für Codeplatzierung, unterstützte Schlüsselwertformate, Berichte und den Typ der gesendeten Segmentdaten [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Für diesen Zieltyp ist Folgendes erforderlich:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] muss für den Bestand bereitgestellt werden. [!UICONTROL DIL] verhindert, dass der spezielle Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und die Wiederherstellung von Seitendaten nicht geschrieben werden müssen.
* **`get_aamCookie`Funktion:** Code, der die Benutzer-ID und die Cookie-Daten des Audience Manager erfasst. Fügen [Sie diesen Code](../../features/destinations/get-aam-cookie-code.md) oben auf der Seite oder innerhalb des `<head>` Codeblock ein.
* **Versandprotokolle an Audience Manager senden:** Wenn Sie einen Segmentauslieferungsbericht wünschen (optional), geben Sie Audience Manager ein Tagesprotokoll mit Bereitstellungsdaten auf Impression-Ebene an. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager [!UICONTROL UUID]enthalten. Zielgruppen-Manager können diese Daten [!DNL FTP]abrufen oder empfangen.

### Cookie-Format und Schlüssel-Wert-Daten

Audience Manager kann Segmentdaten wie folgt an ein Browser-Cookie senden:

* Einzelne Schlüssel (`x=1&x=2`);
* Mehrere Schlüssel (`x=1&x=2&y=3&y=4`);
* Serialisierte Werte (`x=1,2,3`);
* Ein Trennzeichen mit Standardwerten, mit dem einzelne Schlüssel-Wert-Paare getrennt werden.

### Nur qualifizierte Segmente werden an OAS gesendet

Die an die Menge übergebenen Daten [!DNL OAS] hängen davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Angenommen, Sie richten 100 Zielgruppen-Management-Segmente ein. Wenn sich ein Site-Besucher für fünf davon qualifiziert, werden nur die fünf Segmente an OAS gesendet (nicht alle 100).

>[!MORE_ LIKE_ THIS]
>
>* [get_ aamcookie-Code](../../features/destinations/get-aam-cookie-code.md)
>* [Wichtige Wertpaare](../../reference/key-value-pairs-explained.md)


## OAS-Ziel erstellen {#oas-dest-setup}

Erstellen Sie ein Cookie-basiertes Ziel für [!DNL OAS] Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager ist ein *Ziel* ein anderes System (Anzeigen-Server, [!DNL DSP]Werbenetzwerk usw.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] bietet die Tools, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Zielfunktionen von Audience Manager finden Sie unter *Zielgruppendaten &gt; Ziele*. Um zu beginnen, klicken Sie **[!UICONTROL Add New Destination]** auf und gehen Sie wie folgt vor.

### Schritt 1: Grundlegende Informationen

So füllen Sie den [!UICONTROL Basic Information] Abschnitt aus:

1. Geben Sie dem Ziel einen Namen.
1. Wählen **[!UICONTROL "Cookie"]** Sie aus der [!UICONTROL Type] Dropdownliste aus.
1. Klicken **[!UICONTROL Save]** Sie auf und wechseln Sie zu [!UICONTROL Configuration] den [!UICONTROL Segment Mappings] Abschnitten.

### Schritt 2: Konfigurationsinformationen

So füllen Sie den [!UICONTROL Configuration] Abschnitt aus:

1. **Cookie-Name:** Geben Sie einen kurzen, beschreibenden Namen für Ihr Cookie an.
1. **Cookie-Domäne:** Lassen Sie leer, um ein Cookie in der Domäne der aktuellen Seite des Benutzers festzulegen. Wenn Sie eine Domäne angeben `.mydomain.com`möchten, präfix Sie den Namen mit einem Punkt wie dieser.
1. Wählen Sie im [!UICONTROL Data Format] Abschnitt eine Schlüsseloption aus.
1. Wenn Ihre Schlüssel Daten mit serialisierten Werten verwenden, wählen Sie das **[!UICONTROL Serialize]** Steuerelement aus und geben Sie das Serientrennzeichen an (das Zeichen, das die serialisierten Werte trennt).
1. Klicken **[!UICONTROL Save]** Sie auf den [!UICONTROL Segment Mappings] Abschnitt und erweitern Sie ihn.

### Schritt 3: Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. **Segmente suchen:** Der [!UICONTROL Segment Mappings] Abschnitt enthält zwei Tools zur Suche nach Segmenten. So suchen Sie ein Segment:
   * Option 1: Geben Sie einen Segmentnamen in das Suchfeld ein. Das Feld wird automatisch basierend auf dem Text aktualisiert. Klicken **[!UICONTROL Add]** Sie auf, sobald Sie das gewünschte Segment gefunden haben.
   * Option 2: Klicken **[!UICONTROL Browse All Segments]** Sie, um ein Fenster zu öffnen, mit dem Sie nach Segmenten nach Namen oder Speicherort suchen können. Klicken Sie auf, **[!UICONTROL Add Selected Segments]** wenn Sie fertig sind.
1. **Zuordnungen hinzufügen:** Geben Sie in das Feld Zuordnungen die Segment-ID im Feld Zuordnungen ein und klicken **[!UICONTROL Save]** Sie auf.
1. Klicken Sie auf **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Ändern [!DNL OAS] Sie die Einstellungen für die Verwendung mit Audience Manager-Segmentdaten.

<!-- aam-oas-code.xml -->

So richten Sie [!DNL OAS]

* Installieren [!UICONTROL DIL] Sie Code auf Ihrer gesamten Site.
* Erstellen Sie OAS als Cookie-Ziel in Audience Manager.
* Platzieren Sie die `get_aamCookie` Funktion am Anfang der Seite idealerweise im `<head>` Codeblock. Der `get_aamCookie` Code ist [hier verfügbar](../../features/destinations/get-aam-cookie-code.md).
* Ändern Sie Ihr Anzeigentag, um die `get_aamCookie` Funktion aufzurufen, und schließen Sie den Cookie-Namen ein, den Sie beim Einrichten des [!DNL OAS] Ziels angegeben haben. Wenn Sie beispielsweise das Cookie `test_cookie`benannt haben, sollte das Anzeigen-Tag aufgerufen `get_aamCookie` und auf den Cookie-Namen verweisen.
* Ihr Anzeigentag könnte dem unten stehenden Beispiel ähnlich aussehen.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Denken Sie daran, die `u=` Variable einzuschließen. Es enthält die tatsächliche eindeutige Benutzer-ID ([!UICONTROL UUID]), die während eines Anzeigenaufrufs weitergegeben wird.

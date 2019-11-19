---
description: Richten Sie Open Ad Server als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.
seo-description: Richten Sie Open Ad Server als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.
seo-title: OAS als Audience Manager-Ziel
solution: Audience Manager
title: OAS als Audience Manager-Ziel
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# OAS als Audience Manager-Ziel {#oas-as-an-audience-manager-destination}

Richten Sie [!DNL Open Ad Server] als Ziel ein und senden Sie Audience Manager-Daten an diese Plattform.

## Anforderungen an das OAS-Ziel {#oas-requirements}

Standards für die Codeplatzierung, unterstützte Schlüsselwertformate, Berichte und den Typ der an [!DNL OAS]gesendeten Segmentdaten.

<!-- aam-oas-requirements.xml -->

Dieser Zieltyp erfordert Folgendes:

* **[!UICONTROL DIL]** : Der [!UICONTROL Data Integration Library] Code sollte in Ihrem Bestand bereitgestellt werden. [!UICONTROL DIL] hilft, die Notwendigkeit zu vermeiden, speziellen Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben.
* **`get_aamCookie`** Funktion: Code, der die Benutzer-ID und Cookie-Daten von Audience Manager erfasst. Platzieren Sie [diesen Code](../../features/destinations/get-aam-cookie-code.md) oben auf der Seite oder innerhalb des `<head>` Codeblocks.
* **** Bereitstellungsprotokolle an Audience Manager senden: Wenn Sie einen Segmentauslieferungsbericht (optional) wünschen, stellen Sie Audience Manager ein tägliches Protokoll zur Verfügung, das Auslieferungsdaten auf Impressionsebene enthält. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager enthalten [!UICONTROL UUID]. Audience Manager kann diese abrufen oder empfangen [!DNL FTP].

### Cookie-Format und Schlüsselwertdaten

Audience Manager kann Segmentdaten wie folgt an ein Browser-Cookie senden:

* Einzelschlüssel (`x=1&x=2`);
* Mehrere Schlüssel (`x=1&x=2&y=3&y=4`);
* Serialisierte Werte (`x=1,2,3`);
* Ein Trennzeichen für Standardwerte, das zum Trennen einzelner Schlüssel/Wert-Paare verwendet wird.

### Nur qualifizierte Segmente werden an OAS gesendet

Die Menge an Daten, an die ein Benutzer weitergeleitet wird, [!DNL OAS] hängt davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Beispiel: Sie richten 100 Audience Manager-Segmente ein. Wenn sich ein Besucher für fünf davon qualifiziert, werden nur diese fünf Segmente an OAS gesendet (nicht alle 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-Code](../../features/destinations/get-aam-cookie-code.md)
>* [Erläuterung von wichtigen Seiten](../../reference/key-value-pairs-explained.md)


## OAS-Ziel erstellen {#oas-dest-setup}

Erstellen Sie ein cookie-basiertes Ziel für [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager ist ein *Ziel* ein beliebiges anderes System (Anzeigen-Server, [!DNL DSP]Werbenetzwerk usw.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Die Zielfunktionen von Audience Manager finden Sie unter *Zielgruppendaten &gt; Ziele*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]** und befolgen Sie die folgenden Schritte.

### Schritt 1: Basisinformationen

So füllen Sie den [!UICONTROL Basic Information] Abschnitt aus:

1. Benennen Sie das Ziel.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Klicken Sie auf **[!UICONTROL Save]** und gehen Sie zu den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] .

### Schritt 2: Konfigurationsinformationen

So füllen Sie den [!UICONTROL Configuration] Abschnitt aus:

1. **** Cookie-Name: Geben Sie einen kurzen beschreibenden Namen für Ihr Cookie ein.
1. **** Cookie-Domäne: Lassen Sie das Feld leer, um ein Cookie in der Domäne der aktuellen Seite des Benutzers festzulegen. Wenn Sie eine Domäne angeben möchten, setzen Sie dem Namen einen Punkt wie den folgenden voran `.mydomain.com`.
1. Wählen Sie eine Schlüsseloption im [!UICONTROL Data Format] Abschnitt aus.
1. Wenn Ihre Schlüssel Daten mit serialisierten Werten verwenden, wählen Sie das **[!UICONTROL Serialize]** Steuerelement aus und geben Sie das serielle Trennzeichen (das Zeichen, das die serialisierten Werte trennt) an.
1. Klicken Sie auf **[!UICONTROL Save]** und erweitern Sie den [!UICONTROL Segment Mappings] Abschnitt.

### Schritt 3: Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. **** Segmente suchen: Der [!UICONTROL Segment Mappings] Abschnitt enthält zwei Suchwerkzeuge, die Ihnen bei der Suche nach Segmenten helfen. So suchen Sie ein Segment:
    * Option 1: Geben Sie einen Segmentnamen in das Suchfeld ein. Das Feld wird automatisch anhand des Textes aktualisiert. Klicken Sie auf **[!UICONTROL Add]** , sobald Sie das gewünschte Segment gefunden haben.
    * Option 2: Klicken Sie auf **[!UICONTROL Browse All Segments]** , um ein Fenster zu öffnen, in dem Sie nach Namen oder Speicherort nach Segmenten suchen können. Click **[!UICONTROL Add Selected Segments]** when done.
1. **** Zuordnungen hinzufügen: Geben Sie im Popup für Zuordnungen die Segment-ID in das Zuordnungsfeld ein und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie auf **[!UICONTROL Done]**.

## OAS-Einrichtung {#oas-code-setup}

Ändern Sie die [!DNL OAS] Einstellungen, um mit den Segmentdaten von Audience Manager zu arbeiten.

<!-- aam-oas-code.xml -->

So richten Sie [!DNL OAS]

* Installieren Sie [!UICONTROL DIL] Code auf Ihrer Website.
* Erstellen Sie OAS als Cookie-Ziel in Audience Manager.
* Platzieren Sie die `get_aamCookie` Funktion am Anfang der Seite, idealerweise innerhalb des `<head>` Codeblocks. Der `get_aamCookie` Code ist [hier](../../features/destinations/get-aam-cookie-code.md)verfügbar.
* Ändern Sie Ihren Anzeigentag, um die `get_aamCookie` Funktion aufzurufen, und fügen Sie den Cookie-Namen ein, den Sie beim Einrichten des [!DNL OAS] Ziels angegeben haben. Wenn Sie beispielsweise den Namen des Cookies angeben `test_cookie`, sollte das Anzeigen-Tag den Cookie-Namen aufrufen `get_aamCookie` und referenzieren.
* Ihr Anzeigentag könnte dem Beispiel unten ähnlich aussehen.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Denken Sie daran, die `u=` Variable einzubeziehen. Es enthält die tatsächliche eindeutige Benutzer-ID ([!UICONTROL UUID]), die während eines Anzeigenaufrufs weitergegeben wird.

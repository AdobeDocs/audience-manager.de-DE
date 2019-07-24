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


# OAS as an Audience Manager Destination {#oas-as-an-audience-manager-destination}

Set up [!DNL Open Ad Server] as a destination and send Audience Manager data to that platform.

## OAS Destination Requirements {#oas-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Für diesen Zieltyp ist Folgendes erforderlich:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] muss für den Bestand bereitgestellt werden. [!UICONTROL DIL] verhindert, dass der spezielle Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und die Wiederherstellung von Seitendaten nicht geschrieben werden müssen.
* **`get_aamCookie`Funktion:** Code, der die Benutzer-ID und die Cookie-Daten des Audience Manager erfasst. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Versandprotokolle an Audience Manager senden:** Wenn Sie einen Segmentauslieferungsbericht wünschen (optional), geben Sie Audience Manager ein Tagesprotokoll mit Bereitstellungsdaten auf Impression-Ebene an. The data can be in a raw format, but each record must contain the Audience Manager [!UICONTROL UUID]. Audience Manager can pick up or receive these via [!DNL FTP].

### Cookie-Format und Schlüssel-Wert-Daten

Audience Manager kann Segmentdaten wie folgt an ein Browser-Cookie senden:

* Single keys (`x=1&x=2`);
* Multiple keys (`x=1&x=2&y=3&y=4`);
* Serialized values (`x=1,2,3`);
* Ein Trennzeichen mit Standardwerten, mit dem einzelne Schlüssel-Wert-Paare getrennt werden.

### Nur qualifizierte Segmente werden an OAS gesendet

The amount data passed in to [!DNL OAS] depends on how many segments a particular user qualifies for. Angenommen, Sie richten 100 Zielgruppen-Management-Segmente ein. Wenn sich ein Site-Besucher für fünf davon qualifiziert, werden nur die fünf Segmente an OAS gesendet (nicht alle 100).

>[!MORE_ LIKE_ THIS]
>
>* [get_ aamcookie-Code](../../features/destinations/get-aam-cookie-code.md)
>* [Wichtige Wertpaare](../../reference/key-value-pairs-explained.md)


## Create an OAS Destination {#oas-dest-setup}

Create a cookie-based destination for [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] bietet die Tools, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Schritt 1: Grundlegende Informationen

To complete the [!UICONTROL Basic Information] section:

1. Geben Sie dem Ziel einen Namen.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Save]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### Schritt 2: Konfigurationsinformationen

To complete the [!UICONTROL Configuration] section:

1. **Cookie-Name:** Geben Sie einen kurzen, beschreibenden Namen für Ihr Cookie an.
1. **Cookie-Domäne:** Lassen Sie leer, um ein Cookie in der Domäne der aktuellen Seite des Benutzers festzulegen. If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`.
1. Choose a key option in the [!UICONTROL Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### Schritt 3: Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. **Segmente suchen:** Der [!UICONTROL Segment Mappings] Abschnitt enthält zwei Tools zur Suche nach Segmenten. So suchen Sie ein Segment:
   * Option 1: Geben Sie einen Segmentnamen in das Suchfeld ein. Das Feld wird automatisch basierend auf dem Text aktualisiert. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.
1. **Zuordnungen hinzufügen:** Geben Sie in das Feld Zuordnungen die Segment-ID im Feld Zuordnungen ein und klicken **[!UICONTROL Save]** Sie auf.
1. Klicken Sie auf **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Modify [!DNL OAS] settings to work with Audience Manager segment data.

<!-- aam-oas-code.xml -->

To set up [!DNL OAS]

* Install [!UICONTROL DIL] code across your site.
* Erstellen Sie OAS als Cookie-Ziel in Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. The `get_aamCookie` code is available [here](../../features/destinations/get-aam-cookie-code.md).
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OAS] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* Ihr Anzeigentag könnte dem unten stehenden Beispiel ähnlich aussehen.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Remember to include the `u=` variable. It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.

---
description: Richten Sie openx als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.
seo-description: Richten Sie openx als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.
seo-title: Openx als Zielgruppen-Manager-Ziel
solution: Audience Manager
title: Openx als Zielgruppen-Manager-Ziel
uuid: 5 e 86 ba 73-281 c -403 b-af 06-64 a 1 d 427526 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OpenX as an Audience Manager Destination{#openx-as-an-audience-manager-destination}

Set up [!DNL OpenX] as a destination and send Audience Manager segment data to that platform.

>[!NOTE]
>
>Nur für das Targeting von Onsite-Werbeservern.

## OpenX Destination Requirements {#openx-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Review the following before setting up [!DNL OpenX] as an Audience Manager destination:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] muss auf Ihrer Site bereitgestellt werden. [!UICONTROL DIL] verhindert, dass der spezielle Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und die Wiederherstellung von Seitendaten nicht geschrieben werden müssen.
* **`get_aamCookie`Funktion:** Code, der die Benutzer-ID und die Cookie-Daten des Audience Manager erfasst. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Versandprotokolle an Audience Manager senden:** Wenn Sie einen Segmentauslieferungsbericht wünschen (optional), geben Sie Audience Manager ein Tagesprotokoll mit Bereitstellungsdaten auf Impression-Ebene an. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Schlüssel-Wert-Daten: Formatierungsanforderungen

Audience Manager sendet Daten in Form von Schlüssel/Wert-Paaren. Erstellen Sie Schlüssel-Wert-Paare gemäß den folgenden Spezifikationen:

* Preface keys with `c.` (e.g., `c.color` or `c.price`).
* Separate serialized values attached to a single key with a comma (e.g., `c.color = red, green, blue`).
* Separate multiple key-value pairs with an ampersand (e.g., `c.color=red & c.price = 100 & c.condition = new`).
* Schlüsselnamen dürfen keine Sonderzeichen wie Akzentzeichen und Satzzeichen oder andere Symbole enthalten.

### Nur qualifizierte Segmente werden an openx gesendet

The amount data passed in to [!DNL OpenX] depends on how many segments a particular user qualifies for. Angenommen, Sie richten 100 Zielgruppen-Management-Segmente ein. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL OpenX] (not all 100).

## Create an OpenX Destination {#openx-destination}

Create a cookie destination for [!DNL OpenX] in Audience Management.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] bietet die Tools, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Schritt 1: Grundlegende Informationen

To complete the [!UICONTROL Basic Information] section:

1. Geben Sie dem Ziel einen Namen.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

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

## OpenX Setup {#openx-code-setup}

Modify [!DNL OpenX] settings to work with Audience Manager segment data.

<!-- aam-openx-code.xml -->

[!DNL OpenX]So richten Sie Folgendes ein:

* Install [!UICONTROL DIL] code across your site.
* Create [!DNL OpenX] as a cookie destination in Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. The `get_aamCookie` code is available [here](../../features/destinations/get-aam-cookie-code.md).
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OpenX] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* Ihr Anzeigentag könnte dem unten stehenden Beispiel ähnlich aussehen.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Remember to include `xid=` . It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.

Der vollständig formatierte Anzeigenaufruf könnte wie folgt aussehen:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```

---
description: Richten Sie OpenX als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.
seo-description: Richten Sie OpenX als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.
seo-title: OpenX als Audience Manager-Ziel
solution: Audience Manager
title: OpenX als Audience Manager-Ziel
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%

---


# OpenX als Audience Manager-Ziel{#openx-as-an-audience-manager-destination}

Richten Sie [!DNL OpenX] als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.

>[!NOTE]
>
>Nur für Onsite-Anzeigenserver-Targeting.

## OpenX-Zielanforderungen {#openx-requirements}

Standards für die Codeplatzierung, unterstützte Schlüsselwertformate, Berichte und den Typ der an [!DNL OpenX] gesendeten Segmentdaten.

<!-- aam-openx-requirements.xml -->

Überprüfen Sie Folgendes, bevor Sie [!DNL OpenX] als Audience Manager-Ziel einrichten:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code sollte auf Ihrer Site bereitgestellt werden. [!UICONTROL DIL] hilft, die Notwendigkeit zu vermeiden, speziellen Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben.
* **`get_aamCookie`Funktion:** Code, der die Audience Manager-Benutzer-ID und Cookie-Daten erfasst. Platzieren Sie [diesen Code](../../features/destinations/get-aam-cookie-code.md) oben auf der Seite oder innerhalb des `<head>`-Codeblocks.
* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentbericht (optional) erstellen möchten, stellen Sie dem Audience Manager ein tägliches Protokoll zur Verfügung, das Versand-Daten auf Impressionsebene enthält. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager `UUID` enthalten. Audience Manager können diese über [!DNL FTP] abrufen oder empfangen.

### Schlüsselwertdaten: Formatanforderungen

Audience Manager sendet Daten in Form von Schlüssel-Wert-Paaren. Erstellen Sie Schlüssel-Wert-Paare gemäß den folgenden Spezifikationen:

* Vorgabetasten mit `c.` (z. B. `c.color` oder `c.price`).
* Trennen Sie serialisierte Werte, die mit einem Komma (z. B. `c.color = red, green, blue`) an einen einzelnen Schlüssel angehängt werden.
* Trennen Sie mehrere Schlüssel/Wert-Paare durch ein kaufmännisches Und (z. B. `c.color=red & c.price = 100 & c.condition = new`).
* Schlüsselnamen dürfen keine Sonderzeichen wie Akzent- und Interpunktionszeichen oder andere Symbole enthalten.

### Nur qualifizierte Segmente werden an OpenX gesendet

Die an [!DNL OpenX] weitergeleiteten Daten hängen davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Angenommen, Sie richten 100 Audience Manager ein. Wenn ein Site-Besucher für fünf davon qualifiziert ist, werden nur diese fünf Segmente an [!DNL OpenX] gesendet (nicht alle 100).

## Erstellen eines OpenX-Ziels {#openx-destination}

Erstellen Sie ein Cookie-Ziel für [!DNL OpenX] in Audience Manager.

<!-- aam-openx-destination.xml -->

In Audience Managern ist ein *Ziel* ein anderes System (Anzeigenserver, [!DNL DSP], Anzeigennetzwerk usw.) für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Data Versand-Prozesse erstellen und verwalten können. Die Zielfunktionen des Audience Managers befinden sich unter *Audience Data > Destinations*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]** und befolgen Sie die folgenden Schritte.

### Schritt 1: Basisinformationen

So füllen Sie den Abschnitt [!UICONTROL Basic Information] aus:

1. Benennen Sie das Ziel.
1. Wählen Sie **[!UICONTROL "Cookie"]** aus der Dropdown-Liste [!UICONTROL Type].
1. Klicken Sie auf **[!UICONTROL Next]** und gehen Sie zu den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings].

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

## OpenX Setup {#openx-code-setup}

Ändern Sie die [!DNL OpenX]-Einstellungen, um mit Segmentdaten des Audience Managers zu arbeiten.

<!-- aam-openx-code.xml -->

So richten Sie [!DNL OpenX] ein:

* [!UICONTROL DIL]-Code auf Ihrer Site installieren.
* Erstellen Sie [!DNL OpenX] als Cookie-Ziel in Audience Manager.
* Platzieren Sie die Funktion `get_aamCookie` oben auf der Seite, idealerweise innerhalb des Codeblocks `<head>`. Der `get_aamCookie`-Code ist [hier](../../features/destinations/get-aam-cookie-code.md) verfügbar.
* Ändern Sie Ihr Anzeigentag, um die Funktion `get_aamCookie` aufzurufen, und fügen Sie den Cookie-Namen ein, den Sie beim Einrichten des [!DNL OpenX]-Ziels angegeben haben. Wenn Sie beispielsweise das Cookie `test_cookie` benannt haben, sollte das Anzeigen-Tag `get_aamCookie` aufrufen und auf den Cookie-Namen verweisen.
* Ihr Anzeigentag könnte dem Beispiel unten ähnlich aussehen.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Denken Sie daran, `xid=` einzuschließen. Es enthält die tatsächliche eindeutige Benutzer-ID ([!UICONTROL UUID]), die während eines Anzeigenaufrufs weitergegeben wird.

Der vollständig formatierte Anzeigenaufruf könnte wie folgt aussehen:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```

---
description: Richten Sie OpenX als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX als Audience Manager-Ziel
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 1%

---

# OpenX als Audience Manager-Ziel{#openx-as-an-audience-manager-destination}

Richten Sie [!DNL OpenX] als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.

>[!NOTE]
>
>Nur für Onsite-Adserver-Targeting.

## Anforderungen an OpenX-Ziele {#openx-requirements}

Standards für die Codeplatzierung, unterstützte Schlüsselwertformate, Berichte und den Typ der an [!DNL OpenX] gesendeten Segmentdaten.

<!-- aam-openx-requirements.xml -->

Überprüfen Sie Folgendes, bevor Sie [!DNL OpenX] als Audience Manager-Ziel einrichten:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] -Code sollte auf Ihrer Site bereitgestellt werden. Mit [!UICONTROL DIL] können Sie vermeiden, dass Sie speziellen Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten schreiben müssen.
* **`get_aamCookie`Funktion:** Code, der die Audience Manager-Benutzer-ID und Cookie-Daten erfasst. Setzen Sie [diesen Code](../../features/destinations/get-aam-cookie-code.md) oben auf der Seite oder innerhalb des `<head>` -Codeblocks.
* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentversandbericht (optional) wünschen, stellen Sie dem Audience Manager ein tägliches Protokoll mit Versanddaten auf Impressionsebene zur Verfügung. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager `UUID` enthalten. Audience Manager können diese über [!DNL FTP] abrufen oder empfangen.

### Schlüsselwertdaten: Formatanforderungen

Audience Manager sendet Daten in Form von Schlüssel-Wert-Paaren. Erstellen Sie Schlüssel-Wert-Paare gemäß den folgenden Spezifikationen:

* Vorsichtsschlüssel mit `c.` (z. B. `c.color` oder `c.price`).
* Trennen Sie die serialisierten Werte, die an einen einzelnen Schlüssel mit einem Komma angehängt sind (z. B. `c.color = red, green, blue`).
* Trennen Sie mehrere Schlüssel-Wert-Paare durch ein kaufmännisches Und-Zeichen (z. B. `c.color=red & c.price = 100 & c.condition = new`).
* Schlüsselnamen dürfen keine Sonderzeichen wie Akzent- und Satzzeichen oder andere Symbole enthalten.

### Nur qualifizierte Segmente werden an OpenX gesendet

Die an [!DNL OpenX] übergebenen Summendaten hängen von der Anzahl der Segmente ab, für die sich ein bestimmter Benutzer qualifiziert. Angenommen, Sie richten 100 Audience Manager-Segmente ein. Wenn ein Site-Besucher für fünf davon qualifiziert ist, werden nur diese fünf Segmente an [!DNL OpenX] gesendet (nicht alle 100).

## Erstellen eines OpenX-Ziels {#openx-destination}

Erstellen Sie ein Cookie-Ziel für [!DNL OpenX] in Audience Manager.

<!-- aam-openx-destination.xml -->

Im Audience Manager ist ein *Ziel* ein anderes System (Anzeigenserver, [!DNL DSP], Anzeigennetzwerk usw.) für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] bietet die Tools, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Die Audience Manager-Zielfunktionen befinden sich unter *Zielgruppendaten > Ziele*. Klicken Sie zunächst auf **[!UICONTROL Add New Destination]** und führen Sie die folgenden Schritte aus.

### Schritt 1: Grundlegende Informationen

So schließen Sie den Abschnitt [!UICONTROL Basic Information] ab:

1. Benennen Sie das Ziel.
1. Wählen Sie **[!UICONTROL "Cookie"]** aus der Dropdownliste [!UICONTROL Type] aus.
1. Klicken Sie auf **[!UICONTROL Next]** und fahren Sie mit den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] fort.

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

## OpenX-Einrichtung {#openx-code-setup}

Ändern Sie die [!DNL OpenX] -Einstellungen, um mit den Segmentdaten des Audience Managers zu arbeiten.

<!-- aam-openx-code.xml -->

So richten Sie [!DNL OpenX] ein:

* Installieren Sie den Code [!UICONTROL DIL] auf Ihrer Site.
* Erstellen Sie [!DNL OpenX] als Cookie-Ziel in Audience Manager.
* Platzieren Sie die Funktion `get_aamCookie` oben auf der Seite, idealerweise innerhalb des Codeblocks `<head>` . Der Code `get_aamCookie` ist [hier](../../features/destinations/get-aam-cookie-code.md) verfügbar.
* Ändern Sie Ihr Anzeigen-Tag, um die Funktion `get_aamCookie` aufzurufen, und fügen Sie den Cookie-Namen ein, den Sie beim Einrichten des [!DNL OpenX] -Ziels angegeben haben. Wenn Sie beispielsweise das Cookie `test_cookie` nennen, sollte das Anzeigen-Tag `get_aamCookie` aufrufen und auf den Cookie-Namen verweisen.
* Ihr Anzeigen-Tag könnte dem unten stehenden Beispiel ähneln.

  ```
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

Denken Sie daran, `xid=` einzubeziehen. Sie enthält die tatsächliche eindeutige Benutzer-ID ([!UICONTROL UUID]), die während eines Anzeigenaufrufs übergeben wird.

Der vollständig formulierte Anzeigenaufruf könnte in etwa wie folgt aussehen:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```

---
description: Richten Sie OpenX als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX als Audience Manager-Ziel
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
TQID: https://experienceleague.adobe.com/67hm8M7jiloQBgDcJG3fRPZueDPrJPDhfPI69z-ZOZg
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: e7029888-c8b0-46a7-849a-cf132a1559bf
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 681
ht-degree: 0%

---

# OpenX als Audience Manager-Ziel{#openx-as-an-audience-manager-destination}

Richten Sie [!DNL OpenX] als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.

>[!NOTE]
>
>Nur für Onsite-Targeting von Anzeigen-Servern.

## OpenX-Zielanforderungen {#openx-requirements}

Standards für die Code-Platzierung, unterstützte Schlüsselwertformate, Berichte und den Typ der an [!DNL OpenX] gesendeten Segmentdaten.

<!-- aam-openx-requirements.xml -->

Überprüfen Sie Folgendes, bevor Sie [!DNL OpenX] als Audience Manager-Ziel einrichten:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] Code sollte auf Ihrer Site bereitgestellt werden. [!UICONTROL DIL] ist es nicht mehr erforderlich, speziellen Code für die Datenerfassung, -integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben.
* **`get_aamCookie`:**, der die Audience Manager-Benutzer-ID und Cookie-Daten erfasst. Platzieren Sie [diesen Code](../../features/destinations/get-aam-cookie-code.md) oben auf der Seite oder im `<head>` Codeblock.
* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentversandbericht (optional) wünschen, stellen Sie Audience Manager ein tägliches Protokoll zur Verfügung, das Versanddaten auf Impression-Ebene enthält. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss die Audience Manager-`UUID` enthalten. Audience Manager kann diese per [!DNL FTP] abholen oder empfangen.

### Schlüssel-Wert-Daten: Formatanforderungen

Audience Manager sendet Daten in Form von Schlüssel-Wert-Paaren. Erstellen Sie Schlüssel-Wert-Paare gemäß den folgenden Spezifikationen:

* Stellen Sie Schlüssel mit `c.` voran (z. B. `c.color` oder `c.price`).
* Trennen Sie serialisierte Werte, die an einen einzelnen Schlüssel mit einem Komma angehängt sind (z. B. `c.color = red, green, blue`).
* Trennen Sie mehrere Schlüssel-Wert-Paare durch ein kaufmännisches Und-Zeichen (z. B. `c.color=red & c.price = 100 & c.condition = new`).
* Schlüsselnamen sollten keine Sonderzeichen wie Akzent- und Satzzeichen oder andere Symbole enthalten.

### Nur qualifizierte Segmente werden an OpenX gesendet

Wie viele Daten an [!DNL OpenX] übergeben werden, hängt davon ab, für wie viele Segmente sich ein bestimmter Benutzer qualifiziert. Angenommen, Sie richten 100 Audience Manager-Segmente ein. Wenn sich ein Site-Besucher für fünf von ihnen qualifiziert, werden nur diese fünf Segmente an [!DNL OpenX] gesendet (nicht alle 100).

## Erstellen eines OpenX-Ziels {#openx-destination}

Erstellen Sie ein Cookie-Ziel für [!DNL OpenX] in Audience Manager.

<!-- aam-openx-destination.xml -->

In Audience Manager ist *Ziel* jedes andere System (Werbeserver, [!DNL DSP], Werbenetzwerk usw.), für das Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Datenbereitstellungsprozesse erstellen und verwalten können. Audience Manager-Zielfunktionen befinden sich unter *Zielgruppendaten > Ziele*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]** und führen Sie die folgenden Schritte aus.

### Schritt 1: Grundlegende Informationen

So schließen Sie den Abschnitt [!UICONTROL Basic Information] ab:

1. Benennen Sie das Ziel.
1. Wählen Sie **[!UICONTROL "Cookie"]** aus der Dropdown-Liste [!UICONTROL Type] aus.
1. Klicken Sie auf **[!UICONTROL Next]** und fahren Sie mit den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] fort.

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

## OpenX-Setup {#openx-code-setup}

Ändern Sie [!DNL OpenX] Einstellungen, um mit Audience Manager-Segmentdaten zu arbeiten.

<!-- aam-openx-code.xml -->

Einrichten von [!DNL OpenX]:

* Installieren Sie [!UICONTROL DIL] Code auf Ihrer Site.
* Erstellen Sie [!DNL OpenX] als Cookie-Ziel in Audience Manager.
* Platzieren Sie die `get_aamCookie` Funktion am Anfang der Seite, idealerweise im `<head>` Codeblock. Der `get_aamCookie`-Code ist verfügbar [hier](../../features/destinations/get-aam-cookie-code.md).
* Ändern Sie Ihr Anzeigen-Tag, um die Funktion `get_aamCookie` aufzurufen, und geben Sie den Cookie-Namen an, den Sie beim Einrichten des [!DNL OpenX]-Ziels angegeben haben. Wenn Sie beispielsweise den Cookie-`test_cookie` benannt haben, sollte das Anzeigen-Tag `get_aamCookie` aufrufen und auf den Cookie-Namen verweisen.
* Ihr Anzeigen-Tag könnte dem folgenden Beispiel ähneln.

  ```
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

Denken Sie daran, `xid=` einzuschließen. Sie enthält die tatsächliche eindeutige Benutzer-ID ([!UICONTROL UUID]), die während eines Anzeigenaufrufs übergeben wurde.

Der vollständig geformte Anzeigenaufruf könnte in etwa wie folgt aussehen:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```

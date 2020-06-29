---
description: Richten Sie OpenX als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.
seo-description: Richten Sie OpenX als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.
seo-title: OpenX als Audience Manager-Ziel
solution: Audience Manager
title: OpenX als Audience Manager-Ziel
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 0%

---


# OpenX als Audience Manager-Ziel{#openx-as-an-audience-manager-destination}

Richten Sie [!DNL OpenX] als Ziel ein und senden Sie Audience Manager-Segmentdaten an diese Plattform.

>[!NOTE]
>
>Nur für Onsite-Anzeigenserver-Targeting.

## Anforderungen an OpenX-Ziele {#openx-requirements}

Standards für die Codeplatzierung, unterstützte Schlüsselwertformate, Berichte und die Art der an [!DNL OpenX]gesendeten Segmentdaten.

<!-- aam-openx-requirements.xml -->

Überprüfen Sie Folgendes, bevor Sie sich [!DNL OpenX] als Audience Manager-Ziel einrichten:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library]Code sollte auf Ihrer Site bereitgestellt werden.[!UICONTROL DIL]hilft, die Notwendigkeit zu vermeiden, speziellen Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben.
* **`get_aamCookie`Funktion:**Code, der die Audience Manager-Benutzer-ID und Cookie-Daten erfasst. Platzieren Sie[diesen Code](../../features/destinations/get-aam-cookie-code.md)oben auf der Seite oder innerhalb des`<head>`Codeblocks.
* **Versandlogs an Audience Manager senden:** Wenn Sie einen Segmentbericht (optional) erstellen möchten, stellen Sie dem Audience Manager ein tägliches Protokoll mit Daten zum Versand auf Impressionsebene zur Verfügung. Die Daten können im Rohformat vorliegen, aber jeder Datensatz muss den Audience Manager enthalten `UUID`. Audience Manager können diese abholen oder empfangen [!DNL FTP].

### Schlüsselwertdaten: Formatanforderungen

Audience Manager sendet Daten in Form von Schlüssel-Wert-Paaren. Erstellen Sie Schlüssel-Wert-Paare gemäß den folgenden Spezifikationen:

* Vorgabetasten mit `c.` (z. B. `c.color` oder `c.price`).
* Trennen Sie die serialisierten Werte, die mit einem Komma (z. B. `c.color = red, green, blue`) an einen einzelnen Schlüssel angehängt werden.
* Trennen Sie mehrere Schlüssel/Wert-Paare durch ein kaufmännisches Und (z. B. `c.color=red & c.price = 100 & c.condition = new`).
* Schlüsselnamen dürfen keine Sonderzeichen wie Akzent- und Interpunktionszeichen oder andere Symbole enthalten.

### Nur qualifizierte Segmente werden an OpenX gesendet

Die Menge an Daten, an die ein Benutzer weitergeleitet wird, [!DNL OpenX] hängt davon ab, für wie viele Segmente ein bestimmter Benutzer qualifiziert ist. Angenommen, Sie richten 100 Audience Manager ein. Wenn ein Site-Besucher für fünf davon qualifiziert ist, werden nur diese fünf Segmente an gesendet [!DNL OpenX] (nicht alle 100).

## Erstellen eines OpenX-Ziels {#openx-destination}

Erstellen Sie ein Cookie-Ziel für [!DNL OpenX] den Audience Manager.

<!-- aam-openx-destination.xml -->

Im Audience Manager ist ein *Ziel* ein anderes System (Anzeigen-Server, [!DNL DSP]Werbungsnetzwerk usw.) , für die Sie Daten freigeben möchten. [!UICONTROL Destination Builder] stellt die Tools bereit, mit denen Sie diese Data Versand-Prozesse erstellen und verwalten können. Die Audience Manager-Zielfunktionen finden Sie unter *Audience Data > Ziele*. Um zu beginnen, klicken Sie auf **[!UICONTROL Add New Destination]** und befolgen Sie die folgenden Schritte.

### Schritt 1: Basisinformationen

So füllen Sie den [!UICONTROL Basic Information] Abschnitt aus:

1. Benennen Sie das Ziel.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Klicken Sie auf **[!UICONTROL Next]** und gehen Sie zu den Abschnitten [!UICONTROL Configuration] und [!UICONTROL Segment Mappings] .

### Schritt 2: Konfigurationsinformationen

So füllen Sie den [!UICONTROL Configuration] Abschnitt aus:

1. **Cookie-Name:** Geben Sie einen kurzen beschreibenden Namen für Ihr Cookie ein.
1. **Cookie-Domäne:** Lassen Sie das Feld leer, um ein Cookie in der Domäne der aktuellen Seite des Benutzers festzulegen. Wenn Sie eine Domäne angeben möchten, setzen Sie dem Namen einen Punkt wie den folgenden voran `.mydomain.com`.
1. Wählen Sie eine Schlüsseloption im [!UICONTROL Data Format] Abschnitt aus.
1. Wenn Ihre Schlüssel Daten mit serialisierten Werten verwenden, wählen Sie das **[!UICONTROL Serialize]** Steuerelement aus und geben Sie das serielle Trennzeichen (das Zeichen, das die serialisierten Werte trennt) an.
1. Klicken Sie auf **[!UICONTROL Save]** und erweitern Sie den [!UICONTROL Segment Mappings] Abschnitt.

### Schritt 3: Segmentzuordnungen

So fügen Sie einem Cookie-Ziel ein Segment hinzu:

1. **Segmente suchen:** Der [!UICONTROL Segment Mappings] Abschnitt enthält zwei Suchwerkzeuge, die Ihnen bei der Suche nach Segmenten helfen. So suchen Sie ein Segment:
   * Option 1: Beginn, der einen Segmentnamen in das Suchfeld eingibt. Das Feld wird automatisch anhand des Textes aktualisiert. Klicken Sie auf **[!UICONTROL Add]** , sobald Sie das gewünschte Segment gefunden haben.
   * Option 2: Klicken Sie auf **[!UICONTROL Browse All Segments]** , um ein Fenster zu öffnen, in dem Sie nach Datenspeicherung oder Namen suchen können. Klicken Sie **[!UICONTROL Add Selected Segments]** nach Abschluss des Vorgangs auf .
1. **Hinzufügen Zuordnungen:** Geben Sie im Popup für Zuordnungen die Segment-ID in das Zuordnungsfeld ein und klicken Sie auf **[!UICONTROL Save]**.
1. Klicken **[!UICONTROL Done]**.

## OpenX-Einrichtung {#openx-code-setup}

Ändern Sie die [!DNL OpenX] Einstellungen, um mit den Segmentdaten des Audience Managers zu arbeiten.

<!-- aam-openx-code.xml -->

So richten Sie [!DNL OpenX]Folgendes ein:

* Installieren Sie [!UICONTROL DIL] Code auf Ihrer Website.
* Erstellen Sie [!DNL OpenX] als Cookie-Ziel in Audience Manager.
* Platzieren Sie die `get_aamCookie` Funktion am Anfang der Seite, idealerweise innerhalb des `<head>` Codeblocks. Der `get_aamCookie` Code ist [hier](../../features/destinations/get-aam-cookie-code.md)verfügbar.
* Ändern Sie Ihren Anzeigentag, um die `get_aamCookie` Funktion aufzurufen, und fügen Sie den Cookie-Namen ein, den Sie beim Einrichten des [!DNL OpenX] Ziels angegeben haben. Wenn Sie beispielsweise den Namen des Cookies angeben `test_cookie`, sollte das Anzeigen-Tag den Cookie-Namen aufrufen `get_aamCookie` und referenzieren.
* Ihr Anzeigentag könnte dem Beispiel unten ähnlich aussehen.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Denken Sie daran, `xid=` . Es enthält die tatsächliche eindeutige Benutzer-ID ([!UICONTROL UUID]), die während eines Anzeigenaufrufs weitergegeben wird.

Der vollständig formatierte Anzeigenaufruf könnte wie folgt aussehen:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```

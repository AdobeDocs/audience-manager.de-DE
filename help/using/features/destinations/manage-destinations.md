---
description: Auf der Ziellandingpage werden alle URL-, Cookie- und Server-to-Server-Ziele aufgelistet. Es bietet Funktionen, mit denen Sie Ziele erstellen, bearbeiten, suchen und Berichte erstellen können. Die Einstiegsseite befindet sich unter Zielgruppendaten > Ziele.
seo-description: Auf der Ziellandingpage werden alle URL-, Cookie- und Server-to-Server-Ziele aufgelistet. Es bietet Funktionen, mit denen Sie Ziele erstellen, bearbeiten, suchen und Berichte erstellen können. Die Einstiegsseite befindet sich unter Zielgruppendaten > Ziele.
seo-title: Ziele verwalten
solution: Audience Manager
title: Ziele verwalten
uuid: 6 b 66 ff 42-0075-49 a 7-a 58 f -7 f 8 ea 2295 fdc
translation-type: tm+mt
source-git-commit: 1d516c49a16c38adcc22827dc254da1ebada0734

---


# Ziele verwalten {#manage-destinations}

Auf der [!UICONTROL Destination] Einstiegsseite werden alle Ziele, [!DNL URL]Cookies und Server-to-Server-Ziele aufgelistet. Es bietet Funktionen, mit denen Sie Ziele erstellen, bearbeiten, suchen und Berichte erstellen können. Die Einstiegsseite **[!UICONTROL Audience Data > Destinations]** befindet sich in.

## Standard-Landingpage {#default-landing-page}

<!-- destinations-home.xml -->

Auf der Standardmäßigen Landingpage werden Ihre Ziele basierend auf dem Typ aufgelistet. Sie können die Ziele mithilfe der vier verfügbaren Registerkarten filtern:

* **Alle**: zeigt alle Arten von Zielen an.
* **Adobe Experience Cloud**: zeigt Ziele an, die Daten an andere Adobe Experience Cloud-Lösungen senden. Derzeit wird nur Adobe Analytics unterstützt. Siehe [Konfigurieren eines Analytics-Ziels](/help/using/features/destinations/create-analytics-destination.md).
* **Integrierte Plattformen**: zeigt benutzerbasierte und gerätebasierte Ziele an (auch als Server-zu-Server-Ziele bezeichnet). Beachten Sie, dass benutzerbasierte Ziele derzeit nur für ausgewählte Kunden verfügbar sind.
* **Benutzerspezifisch**: zeigt Cookie- und URL-Ziele an.


![](assets/destinations-landing.png)

## Addressable Audiences-Einstiegsseite {#audiences-landing-page}

Um Zielgruppendaten und Übereinstimmungsraten für Ihr Server-to-Server-Ziel anzuzeigen, wählen **[!UICONTROL Integrated Platforms > Device-Based]** Sie die Option.

Weitere Informationen zu den angezeigten Informationen finden Sie unter [Addressable Audiences Interface](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Zielaufbau {#destination-builder}

[!UICONTROL Destination Builder] ermöglicht es Ihnen, Cookie-basierte oder [!DNL URL] Ziele zu erstellen. Server-to-Server ([!DNL S2S])-Ziele können nicht erstellt werden, [!UICONTROL Destination Builder]Sie können jedoch ihre Segmentzuordnungen verwalten. Wenden Sie sich an Ihren Berater, um ein [!DNL S2S] Ziel einzurichten. [!UICONTROL Destination Builder] befindet **[!UICONTROL Audience Data > Destinations]**.

### Ziel-Builder-Einstellungen {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] besteht aus den folgenden Abschnitten und Einstellungen:

| [!UICONTROL Destination Builder] Abschnitt | Zielsetzung |
|--- |--- |
| Basisinformationen | Dient zum Benennen des Ziels, der Beschreibung und des Zieltyps ([!DNL URL] oder [!DNL cookie]) sowie der Plattform (alle [!DNL Android], Browser oder [!DNL iOS]). |
| Konfiguration | Enthält Steuerelemente für: <br/><ul><li>Übergabe von Schlüsselwertdaten an [!DNL URL] Ziele. Sie können Daten als einzelne oder serialisierte Schlüssel-Wert-Paare senden. Weitere Informationen finden Sie unter [Zielserialisierung](../../features/destinations/key-value-pairs.md#destination-serialized) sowie [Standard- und Serienschlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md). </li><li>Elemente eines Cookie-Ziels wie Cookie-Name, Domäne, Größe, Ablaufintervall, Datenformat usw.</li></ul> |
| Segmentzuordnungen | Sie können die: <br/><ul><li>Suchen, Hinzufügen und Verwalten von Segmenten, die mit allen Zieltypen verknüpft sind. </li><li>Legen Sie die Bereitstellungsprioritäten für einzelne Segmente fest (nur [!DNL cookie]für -basierte Segmente).</li></ul> |

### Datenbereitstellungsmethoden {#data-delivery-methods}

Senden Sie Informationen an ein Ziel, indem Sie sie über eine [!DNL URL] Zeichenfolge übermitteln, in einen Browser [!DNL cookie]schreiben oder über Offline-Server-zu-Server-Datenübertragungen.

* [!DNL URL] und cookie-basierte Ziele werden synchron übertragen, da ein Benutzer Aktionen auf einer Seite durchführt.
* Die Server-zu-Server-Datenübertragung ist asynchron und kann lange auftreten, nachdem ein Benutzer die Seite verlassen hat. Der Auslieferungstyp, den Sie auswählen, hängt von Ihren geschäftlichen Anforderungen ab und davon, wie ein bestimmter Datenpartner Daten empfangen möchte oder kann.

Weitere [Informationen finden Sie unter Auswählen eines Zieltyps](../../features/destinations/destinations.md) .

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen eines Cookie-Ziels](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [URL-Ziel erstellen](../../features/destinations/manage-destinations.md#configure-url-destination)


## Konfigurieren eines Cookie-Ziels {#create-cookie-destination}

Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Befolgen Sie diese Anweisungen, um ein Cookie-Ziel zu [!UICONTROL Destination Builder]erstellen.

<!-- create-cookie-destination.xml -->

Um ein neues Cookie-Ziel zu erstellen, gehen **[!UICONTROL Audience Data > Destinations > Create New Destination]** Sie zu den Abschnitten, wie unten beschrieben.

### Basisinformationen {#basic-information}

Dieser Abschnitt enthält Felder und Optionen, die den Cookie-Zielerstellungsprozess starten. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Basic Information]** Sie auf, um die Steuerelemente anzuzeigen.
2. Geben Sie dem Ziel einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine genaue Beschreibung ist eine effektive Möglichkeit, weitere Informationen zu einem Ziel zu definieren oder bereitzustellen.
4. Wählen Sie in der **[!UICONTROL Category]** Liste **[!UICONTROL Custom]** den Eintrag.
5. Wählen Sie in der **[!UICONTROL Environment]** Liste **[!UICONTROL Browser]** den Eintrag. Cookie-Ziele für native mobile Umgebungen wie Android- oder ios-Apps können nicht konfiguriert werden.
6. Klicken Sie in der **[!UICONTROL Type]** Liste **[!UICONTROL Cookie]** auf.
7. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]**. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt automatisch die Segment-ID hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Sie ist auf maximal 255 Zeichen begrenzt.
8. Klicken **[!UICONTROL Next]** Sie auf, um die [!UICONTROL Configuration] Einstellungen aufzurufen, oder klicken **[!UICONTROL Data Export Labels]** Sie auf, um die Exportsteuerelemente auf das Ziel anzuwenden.

### Datenexportbeschriftungen {#data-export-labels-cookies}

Dieser Abschnitt enthält Optionen, die [die Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein Cookie-Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Data Export Labels]** Sie auf, um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung, die der auf das Ziel angewendeten Datenexportkontrolle entspricht (siehe [Hinzufügen von Exportbeschriftungen zu einem Ziel](../../features/destinations/manage-destinations.md#add-data-export-labels) für weitere Details).
3. Klicken Sie auf **[!UICONTROL Save]**.

### Konfiguration {#configuration}

Dieser Abschnitt enthält Felder und Optionen, mit denen Sie das Cookie für Ihr Ziel einrichten können.

>[!NOTE]
>
>[!DNL Audience Manager] kodiert Daten, die in das Zielcookie geschrieben wurden. Beispielsweise sind Leerzeichen kodiert `%20` und Semikolons werden kodiert `%3B`.

So füllen Sie diesen Abschnitt aus:

1. Klicken Sie, **[!UICONTROL Configuration]** um die Steuerelemente verfügbar zu machen.
1. Geben Sie dem Cookie einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. Wählen Sie eine Datenformat-Option. Mit diesen Optionen können Sie die Trennzeichen und Trennzeichen für Schlüssel/Wert-Paare auswählen, die Segmentdaten an ein Ziel senden. Zu den Formatierungsoptionen gehören:
   * **Einzelner Schlüssel:** Hiermit können Sie den Schlüssel in einem Schlüssel-Wert-Paar festlegen. Sie legen den Wert fest, nachdem Sie ein Segment im folgenden [!UICONTROL Segment Mappings] Abschnitt ausgewählt haben.
   * **Mehrere Schlüssel:** Hiermit können Sie den Schlüssel und den Wert für ein Schlüssel-Wert-Paar festlegen. Sie erstellen das Schlüssel-Wert-Paar, nachdem Sie im Abschnitt &quot;Segmentzuordnungen&quot; ein Segment ausgewählt haben.
Weitere Informationen zu diesen Datenelementen finden Sie unter [Standard- und Serialschlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md) .
1. Klicken Sie auf **[!UICONTROL Save]**.

Alle anderen Einstellungen sind optional. Weitere Informationen zu **[!UICONTROL Cookie Domain]** den und **[!UICONTROL Publish data to]** den Einstellungen finden Sie unter [Optionale Einstellungen für Cookie-Ziele](../../features/destinations/manage-destinations.md#optional-settings-cookies).

### Segmentzuordnungen {#segments-mapping}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Segment Mappings]** Sie auf, um die Steuerelemente anzuzeigen.
1. Geben Sie in das **[!UICONTROL Search and Add Segments]** Feld den Namen eines Segments ein oder klicken Sie auf, **[!UICONTROL Browse All Segments]** um eine Liste der verfügbaren Segmente zu durchsuchen.
1. Klicken **[!UICONTROL Add Selected Segments]** Sie auf, wenn Sie das gewünschte Segment suchen. Durch das Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
1. Im [!UICONTROL Edit Mapping] Dialogfeld:
   * **[!UICONTROL Mapping]** Hier können Sie einen Wert für den Schlüssel festlegen, der im Abschnitt &quot;Konfiguration&quot; angegeben ist.
   * **[!UICONTROL Publish from]** ermöglicht das Festlegen des Start- und Enddatums für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie auf **[!UICONTROL Done]**.

## URL-Ziel konfigurieren {#configure-url-destination}

Ein [!DNL URL] Ziel führt Pixelaufrufe von einer Seite zu Ihrem Ziel aus. Befolgen Sie diese Anweisungen, um ein [!DNL URL] Ziel zu [!UICONTROL Destination Builder]erstellen.

<!-- create-url-destination.xml -->

Um ein neues [!DNL URL] Ziel zu erstellen, gehen **[!UICONTROL Audience Data > Destinations > Create New Destination]** Sie zu den Abschnitten, wie unten beschrieben.

### Basisinformationen {#basic-info}

Dieser Abschnitt enthält Felder und Optionen, die den URL-Zielerstellungsprozess starten. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Basic Information]** Sie auf, um die Steuerelemente anzuzeigen.
1. Geben Sie dem Ziel einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. *(Optional)* Beschreiben Sie das Ziel. Eine genaue Beschreibung ist eine effektive Möglichkeit, weitere Informationen zu einem Ziel zu definieren oder bereitzustellen.
1. Wählen Sie in der **[!UICONTROL Category]** Liste **[!UICONTROL Custom]** den Eintrag.
1. Wählen Sie in der **[!UICONTROL Environment]** Liste die Umgebung aus, in der das URL-Ziel ausgelöst werden soll.
1. Klicken Sie in der **[!UICONTROL Type]** Liste **[!UICONTROL URL]** auf.
1. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]**. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt automatisch die Segment-ID hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Sie ist auf maximal 255 Zeichen begrenzt.
1. Klicken **[!UICONTROL Next]** Sie auf, um die [!UICONTROL Configuration] Einstellungen aufzurufen, oder klicken **[!UICONTROL Data Export Labels]** Sie auf, um die Exportsteuerelemente auf das Ziel anzuwenden.

### Datenexportbeschriftungen {#data-export-labels-dest}

Dieser Abschnitt enthält Optionen, die [die Datenexportsteuerelemente](../../features/data-export-controls.md) auf ein [!DNL URL] Ziel anwenden. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Data Export Labels]** Sie auf, um die Steuerelemente anzuzeigen.
2. Wählen Sie eine Beschriftung, die dem auf das Ziel angewendeten Datenexportsteuerelement entspricht (siehe [Hinzufügen von Exportbeschriftungen zu einem Ziel](../../features/destinations/manage-destinations.md#add-data-export-labels) für weitere Details).
3. Klicken Sie auf **[!UICONTROL Save]**.

### Konfiguration {#configure-base-data}

Dieser Abschnitt enthält Optionen, mit denen Sie eine Basis [!DNL URL] - und Datentrennzeichen festlegen können, die durch die [!DNL URL] Zeichenfolge weitergegeben werden. Dieser Abschnitt ist optional. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Configuration]** Sie auf, um die Steuerelemente anzuzeigen.
1. *(Optional)* Aktivieren Sie das **[!UICONTROL Serialize]** Kontrollkästchen.
Dadurch können Sie Segmente an ein Ziel senden, anstatt jedem Segment separate Aufrufe zu tätigen. Die Serialisierung erleichtert die effiziente Datenübertragung. Wenn Sie dieses Kontrollkästchen aktivieren, werden die Felder &quot;URL&quot; und&quot; Trennzeichen&quot; angezeigt. Weitere Informationen finden Sie unter [Standard- und Serialschlüssel-Wert-Paare](../../features/destinations/key-value-pairs.md).
1. Wenn Sie auswählen **[!UICONTROL Serialize]**, müssen Sie auch die unten beschriebenen URL- und Trennzeichen konfigurieren.

| Feld | Beschreibung |
|--- |--- |
| Basis-URL | Der Basisteil eines Standards, `HTTP`[!DNL URL] der sich nicht ändert. Außerdem müssen Sie das `%ALIAS%`[Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL platzieren. Beispiel: `https://www.myCompany.com/%alias%...` |
| Sichere URL | Der Basisteil eines sicheren Schutzes, `HTTPS`[!DNL URL] der sich nicht ändert. Außerdem müssen Sie das `%ALIAS%`[Platzhaltermakro](../../features/destinations/destination-macros.md#destination-macros-defined) in der Basis-URL platzieren. Beispiel: `https://www.myCompany.com/%alias%...` |
| Trennzeichen | Das Symbol, das die Segmentvariablen in der [!DNL URL] Zeichenfolge trennt. Dies ist normalerweise ein Komma oder ein Semikolon. Erhalten Sie diese Informationen von Ihrem Zielpartner. |

### Segmentzuordnungen {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Klicken **[!UICONTROL Segment Mappings]** Sie auf, um die Steuerelemente anzuzeigen.
1. Geben Sie in das **[!UICONTROL Search and Add Segments]** Feld den Namen eines Segments ein oder klicken **[!UICONTROL Browse All Segments]** Sie auf eine Liste der verfügbaren Segmente.
1. Klicken **[!UICONTROL Add Selected Segments]** Sie auf, wenn Sie das gewünschte Segment suchen. Durch das Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
1. Mit [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geben Sie die Schlüssel/Wert-Paare ein, die vom Segment verwendet werden.
   * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken Sie auf **[!UICONTROL Done]**.

### Optionale Einstellungen für Cookie-Ziele {#optional-settings-cookies}

In [!UICONTROL Destination Builder]enthält die [!UICONTROL Configuration section] Felder [!UICONTROL Cookie Domain] und [!UICONTROL Publish Data To] Felder. Mit diesen Regeln können Sie Regeln erstellen, um zu bestimmen, ob ein Ziel ein Cookie setzt oder ein Cookie zurückgibt. [!UICONTROL Cookie Domain] und unabhängig voneinander [!UICONTROL Publish Data To] arbeiten und optional sind. Sie können ein Cookie-Ziel erstellen, ohne diese zu verwenden.

## Cookie-Domäne: Syntax und Beispiele {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cookie-Domäne </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Syntax</b> </p> </td> 
   <td colname="col2"> <p>Das Feld <span class="wintitle"> "Cookie-Domäne</span> " akzeptiert eine einfache Textzeichenfolge, mit der Sie Cookies in einer angegebenen Domäne oder in allen Domänen festlegen können. Wenn Sie diese Funktion verwenden: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Legen Sie für jedes Cookie-Ziel nur eine Domäne fest. Geben Sie nicht mehrere Domänen in das Feld <span class="wintitle"> "Cookie-Domäne</span> " ein. Erstellen Sie stattdessen ein anderes <span class="wintitle"> Ziel</span> . </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Verwenden Sie keine Platzhalterzeichen. </li> 
     </ul> </p> <p> Lassen Sie das <span class="wintitle"> Feld Cookie-Domäne</span> leer, um ein Cookie auf allen Domänen festzulegen. Dies ist die Standardeinstellung. </p> <p>So legen Sie Cookies in einer bestimmten Domäne und unter-Domänen fest: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Geben Sie den Namen der Domäne in das Feld <span class="wintitle"> "Cookie-Domäne</span> " ein. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Starten Sie den Domänennamen mit einem Zeitraum. Zum Beispiel <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">Das <code> https://www</code> ist nicht erforderlich. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Beispiel</b> </p> </td> 
   <td colname="col2"> <p>Angenommen wir haben eine fiktive Site namens "sports. com" . Sports.com hat Domänen für Golf, Baseball und Football. Um ein Cookie in allen Sportdomänen festzulegen, geben Sie Folgendes in das <span class="wintitle"> Feld Cookie-Domäne</span> ein: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Dadurch wird <span class="keyword"> Audience Manager</span> angewiesen, in jeder Domäne, die das Muster <code><i>some.</i></code>sports. com enthält, ein Cookie festzulegen. Ein komplexerer Satz Beispiele finden Sie unten. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiele für komplexe Cookie-Domänen

Diese Beispiele zeigen Ihnen, ob [!DNL Audience Manager] Sie ein Cookie festlegen, das auf der Konfiguration der [!UICONTROL Cookie Domain] Option basiert.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Website </th> 
   <th colname="col2" class="entry">Cookie-Domäne: .sports.com <p>Cookie-Satz </p> </th> 
   <th colname="col3" class="entry">Cookie-Domäne: .golf.sports.com <p>Cookie-Satz </p> </th> 
   <th colname="col4" class="entry">Cookie-Domäne: Leer <p>Cookie-Satz </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nein </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Ja </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nein </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> Nein </td> 
   <td colname="col3"> Nein </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
 </tbody> 
</table>

## Daten veröffentlichen auf {#publish-data-to}

Die [!UICONTROL Publish Data To] Einstellungen geben ein Cookie zurück, wenn die Domäne die von Ihnen ausgewählten Kriterien erfüllt. Zu den Optionen zählen:

* **[!UICONTROL All of our domains]**: (Standard) Gibt eine [!DNL cookie] für jede Domäne zurück.
* **[!UICONTROL Only the selected domains]**: Gibt ein Cookie nur für die in der Domänenliste ausgewählten Domänen zurück.
* **[!UICONTROL All of our domains except the selected domains]**: Verhindert, dass ausgewählte Domänen a [!DNL cookie]empfangen. Alle anderen Domänen können a [!DNL cookie]empfangen.

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen eines Cookie-Ziels](../../features/destinations/manage-destinations.md#create-cookie-destination)


## Segmente für Server-zu-Server-Ziele hinzufügen oder bearbeiten {#add-edit-segments}

Sie können nur Segmente für ein Server-to-Server ([!DNL S2S])-Ziel hinzufügen oder bearbeiten. Ziele können nicht erstellt [!DNL S2S][!UICONTROL Destination Builder]werden. Wenden Sie sich an Ihren Berater, um [!DNL S2S] Ziele einzurichten. Befolgen Sie diese Anweisungen, um Segmente für ein [!DNL S2S] Ziel hinzuzufügen oder zu bearbeiten.

<!-- destination-s2s-edit.xml -->

So fügen Sie Segmentzuordnungen für ein [!DNL S2S] Ziel hinzu oder bearbeiten es:

1. Gehe **[!UICONTROL Audience Data > Destinations]** zu. Wählen **Sie Integrierte Plattformen &gt; Gerätebasiert** und suchen Sie das [!DNL S2S] Ziel, mit dem Sie arbeiten möchten.
1. Klicken Sie in der [!UICONTROL Action] Spalte auf das Stiftsymbol, um das Ziel zu bearbeiten.
   * Geben Sie in das **[!UICONTROL Search and Add Segments]** Feld den Namen eines Segments ein oder klicken **[!UICONTROL Browse All Segments]** Sie auf eine Liste der verfügbaren Segmente.
   * Klicken **[!UICONTROL Add Selected Segments]** Sie auf, wenn Sie das gewünschte Segment suchen. Durch das Hinzufügen eines Segments wird das [!UICONTROL Edit Mapping] Fenster geöffnet.
   * Mit [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Legen Sie einen Wert für das [Schlüssel-Wert-Paar](../../features/destinations/key-value-pairs.md) fest, das von diesem Ziel verwendet wird.
      * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken **[!UICONTROL Save]****[!UICONTROL Done]** Sie auf und dann auf.

## Datenexport-Beschriftungen zu einem Ziel hinzufügen {#add-data-export-labels}

[!DNL Data Export Labels] mit den [!DNL Export Controls] in einer Datenquelle festgelegten Arbeiten. [!DNL Data Export Labels] verhindern, dass Sie einem Segment eingeschränkte Eigenschaften hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Beschriftungen auf ein neues oder ein vorhandenes [!DNL cookie] oder [!DNL URL] ein Ziel festlegen.

>[!NOTE]
>
>Um eine Exportbeschriftung hinzuzufügen, benötigen Sie Administratorrechte *oder* ausreichende Rechte, um ein Ziel zu erstellen oder zu bearbeiten.

<!-- t_export_labels.xml -->

So fügen Sie einem Ziel eine Exportbeschriftung hinzu:

1. Klicken Sie auf **[!UICONTROL Audience Data]**:
   * Für neue Ziele: Klicken **[!UICONTROL Create New Destination]** Sie auf. Füllen Sie den [!UICONTROL Basic Information] Abschnitt aus, bevor Sie eine Datenexportbeschriftung auswählen. Weitere Informationen finden Sie unter [Erstellen eines Cookie-Ziels](../../features/destinations/manage-destinations.md#create-cookie-destination) oder [Erstellen eines URL-Ziels](../../features/destinations/manage-destinations.md#configure-url-destination) .
   * Für vorhandene Ziele: Verwenden Sie das [!DNL Search] Kästchen, um Ihr Ziel zu finden, oder klicken Sie auf den Zielnamen, um ihn zu öffnen.
1. Wählen Sie eine [!DNL Data Export Label]. Lassen Sie die Kontrollkästchen leer, wenn Sie keine Exportbeschränkungen festlegen möchten. Zu den Exportbeschriftungen zählen die folgenden Optionen:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Exporteinschränkungen funktionieren nur, wenn Sie ein [passendes Exportsteuerelement](../../features/data-export-controls.md) für eine Datenquelle festlegen.
1. Klicken Sie auf **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Datenquelle erstellen](../../features/manage-datasources.md#create-data-source)


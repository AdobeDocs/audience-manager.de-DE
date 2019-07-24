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


# Manage Destinations {#manage-destinations}

The [!UICONTROL Destination] landing page lists all of your [!DNL URL], cookie, and server-to-server destinations. Es bietet Funktionen, mit denen Sie Ziele erstellen, bearbeiten, suchen und Berichte erstellen können. The landing page is located in **[!UICONTROL Audience Data > Destinations]**.

## Default Landing Page {#default-landing-page}

<!-- destinations-home.xml -->

Auf der Standardmäßigen Landingpage werden Ihre Ziele basierend auf dem Typ aufgelistet. Sie können die Ziele mithilfe der vier verfügbaren Registerkarten filtern:

* **Alle**: zeigt alle Arten von Zielen an.
* **Adobe Experience Cloud**: zeigt Ziele an, die Daten an andere Adobe Experience Cloud-Lösungen senden. Derzeit wird nur Adobe Analytics unterstützt. See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **Integrierte Plattformen**: zeigt benutzerbasierte und gerätebasierte Ziele an (auch als Server-zu-Server-Ziele bezeichnet). Beachten Sie, dass benutzerbasierte Ziele derzeit nur für ausgewählte Kunden verfügbar sind.
* **Benutzerspezifisch**: zeigt Cookie- und URL-Ziele an.


![](assets/destinations-landing.png)

## Addressable Audiences Landing Page {#audiences-landing-page}

To see audience data and match rates for your server-to-server destination, select **[!UICONTROL Integrated Platforms > Device-Based]**.

For more information about the displayed information, see [Addressable Audiences Interface](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] ermöglicht es Ihnen, Cookie-basierte oder [!DNL URL] Ziele zu erstellen. You cannot create server-to-server ([!DNL S2S]) destinations with [!UICONTROL Destination Builder], but you can manage their segment mappings. Contact your consultant to set up a [!DNL S2S] destination. [!UICONTROL Destination Builder] befindet **[!UICONTROL Audience Data > Destinations]**.

### Destination Builder Settings {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] besteht aus den folgenden Abschnitten und Einstellungen:

| [!UICONTROL Destination Builder] Abschnitt | Zielsetzung |
|--- |--- |
| Basisinformationen | Used to name the destination, describe it, and select destination type ([!DNL URL] or [!DNL cookie]), and platform (all, [!DNL Android], browser, or [!DNL iOS]). |
| Konfiguration | Includes controls for: <br/><ul><li>Passing in key-value data to [!DNL URL] destinations. Sie können Daten als einzelne oder serialisierte Schlüssel-Wert-Paare senden. For details see, [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized) and [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md). </li><li>Elemente eines Cookie-Ziels wie Cookie-Name, Domäne, Größe, Ablaufintervall, Datenformat usw.</li></ul> |
| Segmentzuordnungen | Sie können die: <br/><ul><li>Suchen, Hinzufügen und Verwalten von Segmenten, die mit allen Zieltypen verknüpft sind. </li><li>Set delivery priorities on individual segments (for [!DNL cookie]-based segments only).</li></ul> |

### Data Delivery Methods {#data-delivery-methods}

Send information to a destination by passing it in through a [!DNL URL] string, by writing to a browser [!DNL cookie], or through offline server-to-server data transfers.

* [!DNL URL] und cookie-basierte Ziele werden synchron übertragen, da ein Benutzer Aktionen auf einer Seite durchführt.
* Die Server-zu-Server-Datenübertragung ist asynchron und kann lange auftreten, nachdem ein Benutzer die Seite verlassen hat. Der Auslieferungstyp, den Sie auswählen, hängt von Ihren geschäftlichen Anforderungen ab und davon, wie ein bestimmter Datenpartner Daten empfangen möchte oder kann.

See [How to Choose a Destination Type](../../features/destinations/destinations.md) for more information.

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen eines Cookie-Ziels](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [URL-Ziel erstellen](../../features/destinations/manage-destinations.md#configure-url-destination)


## Configure a Cookie Destination {#create-cookie-destination}

Ein Cookie-Ziel gibt Daten zurück und schreibt sie in ein Cookie im Browser des Benutzers. Das Cookie enthält Daten, die von anderen Plattformen gelesen werden können, die Zugriff auf die Seite haben. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

To create a new cookie destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### Basisinformationen {#basic-information}

Dieser Abschnitt enthält Felder und Optionen, die den Cookie-Zielerstellungsprozess starten. So füllen Sie diesen Abschnitt aus:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
2. Geben Sie dem Ziel einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
3. *(Optional)* Beschreiben Sie das Ziel. Eine genaue Beschreibung ist eine effektive Möglichkeit, weitere Informationen zu einem Ziel zu definieren oder bereitzustellen.
4. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
5. In the **[!UICONTROL Environment]** list, select **[!UICONTROL Browser]**. Cookie-Ziele für native mobile Umgebungen wie Android- oder ios-Apps können nicht konfiguriert werden.
6. In the **[!UICONTROL Type]** list, click **[!UICONTROL Cookie]**.
7. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]**. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt automatisch die Segment-ID hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Sie ist auf maximal 255 Zeichen begrenzt.
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-cookies}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a cookie destination. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So füllen Sie diesen Abschnitt aus:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Klicken Sie auf **[!UICONTROL Save]**.

### Konfiguration {#configuration}

Dieser Abschnitt enthält Felder und Optionen, mit denen Sie das Cookie für Ihr Ziel einrichten können.

>[!NOTE]
>
>[!DNL Audience Manager] kodiert Daten, die in das Zielcookie geschrieben wurden. For example, spaces are encoded as `%20` and semicolons are encoded as `%3B`.

So füllen Sie diesen Abschnitt aus:

1. Click **[!UICONTROL Configuration]** to expose the controls
1. Geben Sie dem Cookie einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. Wählen Sie eine Datenformat-Option. Mit diesen Optionen können Sie die Trennzeichen und Trennzeichen für Schlüssel/Wert-Paare auswählen, die Segmentdaten an ein Ziel senden. Zu den Formatierungsoptionen gehören:
   * **Einzelner Schlüssel:** Hiermit können Sie den Schlüssel in einem Schlüssel-Wert-Paar festlegen. You'll set the value after you select a segment in the [!UICONTROL Segment Mappings] section below.
   * **Mehrere Schlüssel:** Hiermit können Sie den Schlüssel und den Wert für ein Schlüssel-Wert-Paar festlegen. Sie erstellen das Schlüssel-Wert-Paar, nachdem Sie im Abschnitt "Segmentzuordnungen" ein Segment ausgewählt haben.
See [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md) for more information about these data elements.
1. Klicken Sie auf **[!UICONTROL Save]**.

Alle anderen Einstellungen sind optional. For more information about the **[!UICONTROL Cookie Domain]** and **[!UICONTROL Publish data to]** settings, see [Optional Settings for Cookie Destinations](../../features/destinations/manage-destinations.md#optional-settings-cookies).

### Segment Mappings {#segments-mapping}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** to browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. In the [!UICONTROL Edit Mapping] dialog:
   * **[!UICONTROL Mapping]** Hier können Sie einen Wert für den Schlüssel festlegen, der im Abschnitt "Konfiguration" angegeben ist.
   * **[!UICONTROL Publish from]** ermöglicht das Festlegen des Start- und Enddatums für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken Sie auf **[!UICONTROL Save]**.
1. Klicken Sie auf **[!UICONTROL Done]**.

## Configure a URL Destination {#configure-url-destination}

A [!DNL URL] destination makes pixel calls from a page to your destination. Follow these instructions to create a [!DNL URL] destination with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

To create a new [!DNL URL] destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### Basisinformationen {#basic-info}

Dieser Abschnitt enthält Felder und Optionen, die den URL-Zielerstellungsprozess starten. So füllen Sie diesen Abschnitt aus:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
1. Geben Sie dem Ziel einen Namen. Vermeiden Sie Abkürzungen und Sonderzeichen.
1. *(Optional)* Beschreiben Sie das Ziel. Eine genaue Beschreibung ist eine effektive Möglichkeit, weitere Informationen zu einem Ziel zu definieren oder bereitzustellen.
1. In the **[!UICONTROL Category]** list, choose **[!UICONTROL Custom]**.
1. In the **[!UICONTROL Environment]** list, select the environment in which to trigger the URL destination.
1. In the **[!UICONTROL Type]** list, click **[!UICONTROL URL]**.
1. *(Optional)* Wählen Sie eine **[!UICONTROL Auto-fill Destination Mapping]**. Zu den Optionen zählen:
   * **[!UICONTROL Segment ID]**: Fügt automatisch die Segment-ID hinzu und sendet sie an das Ziel.
   * **[!UICONTROL Integration Code Value]**: Fügt automatisch den Segmentintegrationscode hinzu und sendet ihn an die Zielzuordnung. Der Integrationscode ist ein eindeutiger Bezeichner, der vom Kunden erstellt und verwendet wird. Sie ist auf maximal 255 Zeichen begrenzt.
1. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-dest}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a [!DNL URL] destination. Überspringen Sie diesen Schritt, wenn Sie keine Datenexportsteuerelemente verwenden. So füllen Sie diesen Abschnitt aus:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. Klicken Sie auf **[!UICONTROL Save]**.

### Konfiguration {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. Dieser Abschnitt ist optional. So füllen Sie diesen Abschnitt aus:

1. Click **[!UICONTROL Configuration]** to expose the controls.
1. *(Optional)* Aktivieren Sie das **[!UICONTROL Serialize]** Kontrollkästchen.
Dadurch können Sie Segmente an ein Ziel senden, anstatt jedem Segment separate Aufrufe zu tätigen. Die Serialisierung erleichtert die effiziente Datenübertragung. Wenn Sie dieses Kontrollkästchen aktivieren, werden die Felder "URL" und" Trennzeichen" angezeigt. For more information, see [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md).
1. If you select **[!UICONTROL Serialize]**, then you must also configure the URL and delimiter fields described below.

| Feld | Beschreibung |
|--- |--- |
| Basis-URL | The base part of a standard `HTTP` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`  [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Beispiel: `https://www.myCompany.com/%alias%...` |
| Sichere URL | The base part of a secure `HTTPS` [!DNL URL] that does not change. Also, you need to place the `%ALIAS%`   [placeholder macro](../../features/destinations/destination-macros.md#destination-macros-defined) in the base URL. Beispiel: `https://www.myCompany.com/%alias%...` |
| Trennzeichen | The symbol that separates the segment variables in the [!DNL URL] string. Dies ist normalerweise ein Komma oder ein Semikolon. Erhalten Sie diese Informationen von Ihrem Zielpartner. |

### Segment Mappings {#segment-mappings}

In diesem Abschnitt können Sie nach Segmenten suchen und sie Ihrem Ziel hinzufügen. So füllen Sie diesen Abschnitt aus:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. Mit [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Geben Sie die Schlüssel/Wert-Paare ein, die vom Segment verwendet werden.
   * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Klicken Sie auf **[!UICONTROL Done]**.

### Optional Settings for Cookie Destinations {#optional-settings-cookies}

In [!UICONTROL Destination Builder], the [!UICONTROL Configuration section] contains the [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] fields. Mit diesen Regeln können Sie Regeln erstellen, um zu bestimmen, ob ein Ziel ein Cookie setzt oder ein Cookie zurückgibt. [!UICONTROL Cookie Domain] und unabhängig voneinander [!UICONTROL Publish Data To] arbeiten und optional sind. Sie können ein Cookie-Ziel erstellen, ohne diese zu verwenden.

## Cookie Domain: Syntax and Examples {#cookie-domain-syntax}

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
   <td colname="col2"> <p>The <span class="wintitle"> Cookie Domain</span> field accepts a simple text string that lets you set cookies on a specified domain or all domains. Wenn Sie diese Funktion verwenden: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Legen Sie für jedes Cookie-Ziel nur eine Domäne fest. Do not type multiple domains in the <span class="wintitle"> Cookie Domain</span> field. Create another <span class="wintitle"> Destination</span> instead. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Verwenden Sie keine Platzhalterzeichen. </li> 
     </ul> </p> <p> Leave the <span class="wintitle"> Cookie Domain</span> field blank to set a cookie on all domains. Dies ist die Standardeinstellung. </p> <p>So legen Sie Cookies in einer bestimmten Domäne und unter-Domänen fest: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Type the name of the domain in the <span class="wintitle"> Cookie Domain</span> field. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Starten Sie den Domänennamen mit einem Zeitraum. For example, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Beispiel</b> </p> </td> 
   <td colname="col2"> <p>Angenommen wir haben eine fiktive Site namens "sports. com" . Sports.com hat Domänen für Golf, Baseball und Football. To set a cookie in all the sports domains, you would type that in the <span class="wintitle"> Cookie Domain</span> box as shown below: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>This tells <span class="keyword"> Audience Manager</span> to set a cookie in any domain that contains the pattern <code><i>something</i></code>.sports.com. Ein komplexerer Satz Beispiele finden Sie unten. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiele für komplexe Cookie-Domänen

These examples show you if [!DNL Audience Manager] will set a cookie based on how the [!UICONTROL Cookie Domain] option is configured.

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

## Publish Data To {#publish-data-to}

The [!UICONTROL Publish Data To] settings return a cookie if the domain meets the criteria set by the options you select. Zu den Optionen zählen:

* **[!UICONTROL All of our domains]**: (Standard) Gibt eine [!DNL cookie] für jede Domäne zurück.
* **[!UICONTROL Only the selected domains]**: Gibt ein Cookie nur für die in der Domänenliste ausgewählten Domänen zurück.
* **[!UICONTROL All of our domains except the selected domains]**: Verhindert, dass ausgewählte Domänen a [!DNL cookie]empfangen. All other domains can receive a [!DNL cookie].

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen eines Cookie-Ziels](../../features/destinations/manage-destinations.md#create-cookie-destination)


## Add or Edit Segments for Server-to-Server Destinations {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. You cannot create [!DNL S2S] destinations with [!UICONTROL Destination Builder]. Contact your consultant to set up [!DNL S2S] destinations. Follow these instructions to add or edit segments for an [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

To add or edit segment mappings for an [!DNL S2S] destination:

1. Go to **[!UICONTROL Audience Data > Destinations]**. Select **Integrated Platforms &gt; Device-Based** and find the [!DNL S2S] destination you want to work with.
1. In the [!UICONTROL Action] column, click the pencil icon to edit the destination.
   * In the **[!UICONTROL Search and Add Segments]** box, start typing the name of a segment or click **[!UICONTROL Browse All Segments]** browse a list of available segments.
   * Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
   * Mit [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Legen Sie einen Wert für das [Schlüssel-Wert-Paar](../../features/destinations/key-value-pairs.md) fest, das von diesem Ziel verwendet wird.
      * **[!UICONTROL Start Date]** und **[!UICONTROL End Date]**: Wählen Sie ein Start- und Enddatum für das Ziel. Wenn das Enddatum leer ist, läuft das Ziel nie ab.
1. Click **[!UICONTROL Save]** and then click **[!UICONTROL Done]**.

## Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] mit den [!DNL Export Controls] in einer Datenquelle festgelegten Arbeiten. [!DNL Data Export Labels] verhindern, dass Sie einem Segment eingeschränkte Eigenschaften hinzufügen und Segmentdaten an ein Ziel senden. You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>To add an export label, you need administrator permissions *or* sufficient privileges to create or edit a destination.

<!-- t_export_labels.xml -->

So fügen Sie einem Ziel eine Exportbeschriftung hinzu:

1. Klicken Sie auf **[!UICONTROL Audience Data]**:
   * For new destinations: Click **[!UICONTROL Create New Destination]**. Complete the [!UICONTROL Basic Information] section before you select a data export label. See [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination) or [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination) for information.
   * For existing destinations: Use the [!DNL Search] box to find your destination or scroll through the list and click on the destination name to open it.
1. Wählen Sie eine [!DNL Data Export Label]. Lassen Sie die Kontrollkästchen leer, wenn Sie keine Exportbeschränkungen festlegen möchten. Zu den Exportbeschriftungen zählen die folgenden Optionen:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Export restrictions will not work unless you set a [matching export control](../../features/data-export-controls.md) on a data source.
1. Klicken Sie auf **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Datenquelle erstellen](../../features/manage-datasources.md#create-data-source)


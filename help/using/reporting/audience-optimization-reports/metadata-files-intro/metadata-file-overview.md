---
description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zur Zielgruppenoptimierung zeigen in den verschiedenen Berichtoptionsmenüs lesbare Namen an.
seo-description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zur Zielgruppenoptimierung zeigen in den verschiedenen Berichtoptionsmenüs lesbare Namen an.
seo-title: Übersicht und Zuordnungen für Metadatendateien
solution: Audience Manager
title: Übersicht und Zuordnungen für Metadatendateien
uuid: 70 df 7 f 11-69 c 5-4873-a 69 d -8 f 93 f 9837
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overview and Mappings for Metadata Files{#overview-and-mappings-for-metadata-files}

Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zur Zielgruppenoptimierung zeigen in den verschiedenen Berichtoptionsmenüs lesbare Namen an.

## Überblick {#overview}

Eine Überprüfung der Metadaten und deren Verwendung. Eine Metadatendatei muss von einer Datendatei begleitet werden. Der Inhalt der Metadatendatei stimmt mit Datendateiinformationen zu verwandten, menschen lesbaren Beschriftungen in den Berichtmenüs überein. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Metadatendateien enthalten Daten zu anderen Daten

Eine Metadatendatei enthält Informationen zu anderen Datentypen. To help you understand how this works, let’s review how [!DNL Audience Manager] receives data.

[!DNL Audience Manager] Empfängt während eines Impressions- oder Klickereignisses Daten in einer URL-Zeichenfolge, die als *Ereignisaufruf bezeichnet* wird.

Der Ereignisaufruf gliedert Informationen in Gruppen definierter Schlüssel-Wert-Paare. Die Werte in einem Schlüssel-Wert-Paar enthalten numerische Daten. Die Metadatendatei enthält Namen und andere lesbare Informationen, die der ID in jedem Schlüssel-Wert-Paar entsprechen.

### Metadaten-Link-IDs zu lesbaren Namen

Die Metadatendatei ist erforderlich, um eine numerische ID mit einem lesbaren Namen zu verknüpfen. As an example, say an event call contains a creative ID in a key-value pair like this: `d_creative:1234`. Ohne Metadatendatei würde dieses kreative Element in einem Optionsmenü als 1234 angezeigt.

Eine ordnungsgemäß formatierte Metadatendatei kann dieses kreative Element jedoch mit einem echten Namen wie "Advertiser Creative A" verknüpfen. Dies ist ein Name, den Sie in einem Bericht lesen und erkennen können.

### Wann benötigen Sie eine Metadatendatei?

First, a metadata file, and all of the parameters listed below, are required in an event call when you want to use the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Second, you need a metadata file if you’re sending your own data to [!DNL Audience Manager] or if you want to see data in the reports from other providers we’re not integrated with. For example, [!DNL Audience Manager] has an integration with Google’s [Double-click Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM). Because of this relationship, [!DNL Audience Manager] can associate IDs with names and descriptions used by the report options. Ohne Integration können wir trotzdem Daten erfassen, aber die Berichtsoptionen zeigen numerische IDs anstelle von beschreibendem Namen an.

![](assets/metadata_menu.png)

## File Mappings {#file-mappings}

The following table lists the key-value pairs that hold data used by the [!UICONTROL Audience Optimization] reports. Wenn Sie eine Metadatendatei verwenden müssen, enthält sie lesbare Informationen, die den Werten in diesen Schlüssel/Wert-Paaren entsprechen. Die Werte für diese Schlüssel akzeptieren nur Ganzzahlen (Datentyp INT). Note, *italics* indicates a variable placeholder. Andere Elemente sind Konstanten oder Schlüssel und ändern sich nicht.

>[!IMPORTANT]
>
>If you're using the [!UICONTROL Audience Optimization] reports, *all* of these values are required in the event call.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Berichtsoption </th> 
   <th colname="col2" class="entry"> Metadaten-Schlüssel-Wert-Paare </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertiser </p> </td> 
   <td colname="col2"> <p> <code>d_ adsrc = <i>Datenquellen-ID oder Integrationscode</i></code> </p> <p>Dies ist die Datenquellen-ID oder der Integrationscode des Werbenden, die beim Erstellen einer Datenquelle bereitgestellt werden. See <a href="../../../features/manage-datasources.md#create-data-source"> Create a Data Source</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geschäftseinheit (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_ bu = <i>Geschäftsentitäts-ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kampagne </p> </td> 
   <td colname="col2"> <p> <code>d_ campaign = <i>Kampagnen-ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kreativ </p> </td> 
   <td colname="col2"> <p> <code>d_ creative = <i>creative id</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange- </p> </td> 
   <td colname="col2"> <p>Akzeptiert zwei verschiedene Schlüssel/Wert-Paare: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_ exchange = <i>ID für den Austausch, der die Anzeige diente</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_ site = <i>ID für die Site, auf der eine Anzeige bereitgestellt wird</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Einfügereihenfolge (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_ io = <i>Einfügereibestellungs-ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plattform </p> </td> 
   <td colname="col2"> <p> <code>d_ src = <i>Datenquellen-ID</i></code> </p> <p>This is the <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> ID for the platform providing metadata information (e.g., DFA, Atlas, GBM, MediaMath, etc.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taktik </p> </td> 
   <td colname="col2"> <p> <code>d_ tactic = <i>taktic id</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertikal </p> </td> 
   <td colname="col2"> <p> <code>d_ vert = <i>vertikale ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## How Event Call IDs Shape File Names, Contents, and Delivery Paths {#how-ids-shape-file-names}

Die von diesen Schlüsselwertpaaren weitergeleiteten IDs helfen dabei, den Metadatendateinamen und dessen Inhalt zu erstellen. Die folgenden Abschnitte und Abbildungen zeigen, wie dies funktioniert. Diese Beispiele erstellen eine Datei, die den Namen eines kreativen Elements in einer Kampagne enthält, aber andere Kombinationen sind möglich.

### Ereignisaufruf

In this example we'll create a metadata file that brings creative names in to an [!UICONTROL Audience Optimization] report. Hierfür müssen wir kreative, Kampagnen- und Datenquellen-IDs aus einem Ereignisaufruf extrahieren.

![](assets/metadata_file_event.png)

### Dateiname

Der Dateiname basiert auf den Kreativen, Kampagnen- und Datenquellen-IDs. Vergleichen Sie in diesem Fall die Unterschiede zwischen den Schlüsselwertdaten in einem Ereignisaufruf und deren Verwendung in einem Dateinamen.

In einem Dateinamen:

* The data source key changes to `dpid` from `d_src`.

* Die kreativen und Kampagnen-IDs stellen eine Kategorie statt einer tatsächlichen Kennung dar.

![](assets/metadata_file_name.png)

See [Naming Conventions for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Dateiinhalt

In diesem Beispiel spiegelt der Dateiinhalt die in dem Ereignisaufruf weitergeleiteten kreativen und Kampagnen-IDs wider. Das neue Element hier ist ein lesbarer Name. Once processed, the name in this file will appear as an option in the Creative menu of an [!UICONTROL Audience Optimization] report.

![](assets/metadata_file_contents.png)

See [Content Format for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Dateiauslieferung

After you name and add data to a file, you send it to an Amazon S3 storage directory provided by [!DNL Audience Manager]. See [Delivery Methods for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md) and [Status Updates for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md).

>[!MORE_ LIKE_ THIS]
>
>* [Datendateien für Zielgruppenoptimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Erfassen von Kampagnenklickdaten über Pixelaufrufe](../../../integration/media-data-integration/click-data-pixels.md)
>* [Erfassen von Kampagnenimpressionsdaten über Pixelabrufe](../../../integration/media-data-integration/impression-data-pixels.md)


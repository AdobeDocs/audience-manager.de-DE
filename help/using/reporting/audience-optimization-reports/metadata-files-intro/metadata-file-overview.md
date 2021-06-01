---
description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte der Audience Optimization zeigen lesbare Namen in den verschiedenen Menüs der Berichtsoptionen an.
seo-description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte der Audience Optimization zeigen lesbare Namen in den verschiedenen Menüs der Berichtsoptionen an.
seo-title: Überblick und Zuordnungen für Metadatendateien
solution: Audience Manager
title: Überblick und Zuordnungen für Metadatendateien
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
feature: Protokolldateien
exl-id: 8c59ab80-f04a-42df-891e-a187ecd0219f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 4%

---

# Überblick und Zuordnungen für Metadatendateien{#overview-and-mappings-for-metadata-files}

Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte der Audience Optimization zeigen lesbare Namen in den verschiedenen Menüs der Berichtsoptionen an.

## Überblick {#overview}

Eine Übersicht über Metadaten und deren Verwendung. Eine Metadatendatei muss von einer Datendatei begleitet sein. Der Inhalt der Metadatendatei stimmt mit den Datendateiinformationen mit den zugehörigen, für Menschen lesbaren Bezeichnungen in den Berichtmenüs überein. Weitere Informationen finden Sie unter [Datendateien für Audience Optimization-Berichte und ausführbare Protokolldateien](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Metadatendateien enthalten Daten zu anderen Daten

Eine Metadatendatei enthält Informationen zu anderen Datentypen. Um Ihnen dabei zu helfen, zu verstehen, wie dies funktioniert, sollten wir überprüfen, wie [!DNL Audience Manager] Daten erhält.

Während eines Impression- oder Klickereignisses empfängt [!DNL Audience Manager] Daten in einer URL-Zeichenfolge, die als *Ereignisaufruf* bezeichnet wird.

Der Ereignisaufruf organisiert Informationen in Sets definierter Schlüssel-Wert-Paare. Die Werte in einem Schlüssel-Wert-Paar enthalten numerische Daten. Die Metadatendatei enthält Namen und andere lesbare Informationen, die der ID in jedem Schlüssel-Wert-Paar entsprechen.

### Metadaten-Links-IDs zu lesbaren Namen

Die Metadatendatei ist erforderlich, um eine numerische ID mit einem lesbaren Namen zu verknüpfen. Beispiel: Ein Ereignisaufruf enthält eine kreative ID in einem Schlüssel-Wert-Paar wie diesem: `d_creative:1234`. Ohne Metadatendatei würde dieses Kreativelement in einem Optionsmenü als 1234 angezeigt werden.

Eine ordnungsgemäß formatierte Metadatendatei kann dieses Kreativelement jedoch an einen echten Namen wie &quot;Advertiser Creative A&quot;binden, einen Namen, den Sie in einem Bericht lesen und erkennen können.

### Wann benötigen Sie eine Metadatendatei?

Zunächst sind eine Metadatendatei und alle unten aufgeführten Parameter in einem Ereignisaufruf erforderlich, wenn Sie die [Audience Optimization-Berichte](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) verwenden möchten.

Außerdem benötigen Sie eine Metadatendatei, wenn Sie Ihre eigenen Daten an [!DNL Audience Manager] senden oder wenn Sie Daten aus den Berichten anderer Anbieter sehen möchten, mit denen wir nicht integriert sind. Beispielsweise verfügt [!DNL Audience Manager] über eine Integration mit dem Google [Doppelklicken Sie auf Kampagnen-Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM). Aufgrund dieser Beziehung kann [!DNL Audience Manager] IDs mit Namen und Beschreibungen verknüpfen, die von den Berichtsoptionen verwendet werden. Ohne eine Integration können wir weiterhin Daten erfassen, aber die Berichtsoptionen zeigen numerische IDs anstelle eines beschreibenden Namens an.

![Metadaten-Menübild](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_menu.png)

## Dateizuordnungen {#file-mappings}

In der folgenden Tabelle sind die Schlüssel-Wert-Paare aufgeführt, die Daten enthalten, die von den [!UICONTROL Audience Optimization] -Berichten verwendet werden. Wenn Sie eine Metadatendatei verwenden müssen, enthält sie für Menschen lesbare Informationen, die den Werten in diesen Schlüssel/Wert-Paaren entsprechen. Die Werte für diese Schlüssel akzeptieren nur Ganzzahlen (Datentyp INT). Hinweis: *kursiv* gibt einen Variablenplatzhalter an. Andere Elemente sind Konstanten oder Schlüssel und ändern sich nicht.

>[!IMPORTANT]
>
>Wenn Sie die [!UICONTROL Audience Optimization] -Berichte verwenden, sind *alle* dieser Werte im Ereignisaufruf erforderlich.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Berichtsoption </th> 
   <th colname="col2" class="entry"> Schlüssel-Wert-Paare für Metadaten </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertiser </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Dies ist die Datenquellen-ID oder der Integrationscode des Advertisers, der beim Erstellen einer Datenquelle bereitgestellt wird. Siehe <a href="../../../features/manage-datasources.md#create-data-source"> Erstellen einer Datenquelle</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geschäftseinheit (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_bu = <i>business unit ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kampagne </p> </td> 
   <td colname="col2"> <p> <code>d_campaign = <i>campaign ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kreativ </p> </td> 
   <td colname="col2"> <p> <code>d_creative = <i>creative ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange- </p> </td> 
   <td colname="col2"> <p>Akzeptiert zwei verschiedene Schlüssel-Wert-Paare: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion Order (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plattform </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Dies ist die <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings">-Datenquelle</a>-ID für die Plattform, die Metadateninformationen bereitstellt (z. B. DFA, Atlas, GBM, MediaMath usw.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taktisch </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertikal </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Wie Ereignisaufruf-IDs Dateinamen, Inhalt und Bereitstellungspfade formen {#how-ids-shape-file-names}

Die von diesen Schlüssel-Wert-Paaren übergebenen IDs helfen beim Erstellen des Metadatendateinamens und des zugehörigen Inhalts. Die folgenden Abschnitte und Abbildungen zeigen, wie dies funktioniert. Mit diesen Beispielen wird eine Datei erstellt, die den Namen eines kreativen Elements in einer Kampagne enthält. Es sind jedoch auch andere Kombinationen möglich.

### Ereignisaufruf

In diesem Beispiel erstellen wir eine Metadatendatei, die kreative Namen in einen [!UICONTROL Audience Optimization] -Bericht einbringt. Dazu müssen wir kreative, kampagnen- und Datenquellen-IDs aus einem Ereignisaufruf extrahieren.

![Ereignisaufrufbild](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_event.png)

### Dateiname

Der Dateiname basiert auf den IDs für Kreativelemente, Kampagnen und Datenquelle. Vergleichen Sie in diesem Fall die Unterschiede zwischen den Schlüssel-Wert-Daten in einem Ereignisaufruf und der Verwendung in einem Dateinamen.

In einem Dateinamen:

* Der Datenquellenschlüssel ändert sich von `d_src` in `dpid`.

* Die Kreativ- und Kampagnen-IDs stellen eher eine Kategorie als eine tatsächliche Kennung dar.

![Wie wird ein Dateiname erstellt?](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_name.png)

Siehe [Benennungskonventionen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Dateiinhalt

In diesem Beispiel spiegeln die Dateiinhalte die Kreativ- und Kampagnen-IDs wider, die beim Ereignisaufruf übergeben werden. Das neue Element hier ist ein lesbarer Name. Nach der Verarbeitung erscheint der Name in dieser Datei als Option im Menü Kreativ eines Berichts [!UICONTROL Audience Optimization] .

![Inhalt einer Metadatendatei](/help/using/reporting/audience-optimization-reports/metadata-files-intro/assets/metadata_file_contents.png)

Siehe [Inhaltsformat für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Dateibereitstellung

Nachdem Sie Daten benannt und zu einer Datei hinzugefügt haben, senden Sie sie an einen Amazon S3-Speicherordner, der von [!DNL Audience Manager] bereitgestellt wird. Siehe [Bereitstellungsmethoden für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORELIKETHIS]
>
>* [Datendateien für Audience Optimization-Berichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
* [Erfassen von Kampagnenklickdaten über Pixelaufrufe](../../../integration/media-data-integration/click-data-pixels.md)
* [Erfassen von Kampagnenimpressionsdaten über Pixelaufrufe](../../../integration/media-data-integration/impression-data-pixels.md)


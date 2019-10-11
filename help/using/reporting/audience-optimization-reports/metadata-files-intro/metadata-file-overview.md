---
description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zur Zielgruppenoptimierung zeigen lesbare Namen in den verschiedenen Berichtoptionen an.
seo-description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zur Zielgruppenoptimierung zeigen lesbare Namen in den verschiedenen Berichtoptionen an.
seo-title: Übersicht und Zuordnungen für Metadatendateien
solution: Audience Manager
title: Übersicht und Zuordnungen für Metadatendateien
uuid: 70df7f11-69c5-4873-a69d-8f93f94e9837
translation-type: tm+mt
source-git-commit: 1ff46970470eae4bc30760468013d994c976e549

---


# Übersicht und Zuordnungen für Metadatendateien{#overview-and-mappings-for-metadata-files}

Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zur Zielgruppenoptimierung zeigen lesbare Namen in den verschiedenen Berichtoptionen an.

## Überblick {#overview}

Eine Übersicht über Metadaten und deren Verwendung. Eine Metadatendatei muss von einer Datendatei begleitet sein. Der Inhalt der Metadatendatei stimmt mit den Datendateiinformationen mit den entsprechenden, für Menschen lesbaren Beschriftungen in den Berichtmenüs überein. Weitere Informationen finden Sie unter [Datendateien für Zielgruppenoptimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Metadatendateien enthalten Daten zu anderen Daten

Eine Metadatendatei enthält Informationen zu anderen Datentypen. Damit Sie besser verstehen können, wie das funktioniert, sollten Sie überprüfen, wie Daten [!DNL Audience Manager] empfangen werden.

Während eines Impressions- oder Klickereignisses werden Daten in einer URL-Zeichenfolge empfangen, die als [!DNL Audience Manager]Ereignisaufruf ** bezeichnet wird.

Der Ereignisaufruf organisiert Informationen in Gruppen definierter Schlüssel/Wert-Paare. Die Werte in einem Schlüssel-Wert-Paar enthalten numerische Daten. Die Metadatendatei enthält Namen und andere lesbare Informationen, die der ID in jedem Schlüssel-Wert-Paar entsprechen.

### Metadaten-Links-IDs zu lesbaren Namen

Die Metadatendatei muss eine numerische ID mit einem lesbaren Namen verknüpfen. Beispiel: Ein Ereignisaufruf enthält eine kreative ID in einem Schlüsselwertpaar wie diesem: `d_creative:1234`. Ohne Metadatendatei würde dieses Kreativelement in einem Optionsmenü als 1234 angezeigt.

Eine ordnungsgemäß formatierte Metadatendatei kann dieses kreative Element jedoch mit einem echten Namen wie "Werbetreibende Kreative A"verbinden, einem Namen, den Sie in einem Bericht lesen und erkennen können.

### Wann benötigen Sie eine Metadatendatei

Zunächst sind eine Metadatendatei und alle unten aufgeführten Parameter für einen Ereignisaufruf erforderlich, wenn Sie die [Zielgruppenoptimierungsberichte](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)verwenden möchten.

Zweitens benötigen Sie eine Metadatendatei, wenn Sie Ihre eigenen Daten an [!DNL Audience Manager] oder wenn Sie Daten aus den Berichten anderer Anbieter sehen möchten, mit denen wir nicht integriert sind. Beispielsweise [!DNL Audience Manager] ist Google mit dem [DCM (Double-Click Campaign Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) ) integriert. Aufgrund dieser Beziehung [!DNL Audience Manager] können IDs mit Namen und Beschreibungen verknüpft werden, die von den Berichtsoptionen verwendet werden. Ohne Integration können wir weiterhin Daten erfassen, aber die Berichtsoptionen zeigen numerische IDs anstelle eines beschreibenden Namens an.

![](assets/metadata_menu.png)

## Dateizuordnungen {#file-mappings}

In der folgenden Tabelle sind die Schlüssel-Wert-Paare aufgeführt, die die von den [!UICONTROL Audience Optimization] Berichten verwendeten Daten enthalten. Wenn Sie eine Metadatendatei verwenden müssen, enthält sie für Menschen lesbare Informationen, die den Werten in diesen Schlüssel/Wert-Paaren entsprechen. Die Werte für diese Schlüssel akzeptieren nur Ganzzahlen (Datentyp INT). Note, *italics* indicates a variable placeholder. Andere Elemente sind Konstanten oder Schlüssel und bleiben unverändert.

>[!IMPORTANT]
>
>Wenn Sie die [!UICONTROL Audience Optimization] Berichte verwenden, sind im Ereignisaufruf *alle* Werte erforderlich.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Berichtsoption </th> 
   <th colname="col2" class="entry"> Metadaten-Schlüsselwertpaare </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertiser </p> </td> 
   <td colname="col2"> <p> <code>d_adsrc = <i>data source ID or integration code</i></code> </p> <p>Dies ist die Datenquelle-ID oder der Integrationscode des Advertisers, die bzw. der beim Erstellen einer Datenquelle bereitgestellt wird. Siehe <a href="../../../features/manage-datasources.md#create-data-source"> Datenquelle</a>erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Business Unit (BU) </p> </td> 
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
   <td colname="col2"> <p>Akzeptiert zwei verschiedene Schlüssel/Wert-Paare: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_exchange = <i>ID for the exchange that served the ad</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_site = <i>ID for the site an ad served on</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Einfügereihenfolge (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_io = <i>insertion order ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plattform </p> </td> 
   <td colname="col2"> <p> <code>d_src = <i>data source ID</i></code> </p> <p>Dies ist die <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Datenquellen</a> -ID für die Plattform, die Metadateninformationen bereitstellt (z. B. DFA, Atlas, GBM, MediaMath usw.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taktik </p> </td> 
   <td colname="col2"> <p> <code>d_tactic = <i>tactic ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertikal </p> </td> 
   <td colname="col2"> <p> <code>d_vert = <i>vertical ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## So werden die Formdateinamen, -inhalte und Bereitstellungspfade für Ereignisaufruf-IDs festgelegt {#how-ids-shape-file-names}

Die von diesen Schlüssel-Wert-Paaren weitergeleiteten IDs helfen beim Erstellen des Metadaten-Dateinamens und seines Inhalts. Die folgenden Abschnitte und Abbildungen zeigen, wie dies funktioniert. Diese Beispiele erstellen eine Datei, die den Namen eines kreativen Elements in einer Kampagne enthält. Es sind jedoch auch andere Kombinationen möglich.

### Ereignisaufruf

In diesem Beispiel erstellen wir eine Metadatendatei, die kreative Namen in einen [!UICONTROL Audience Optimization] Bericht einfügt. Dazu müssen wir kreative IDs, Kampagnen- und Datenquellen-IDs aus einem Ereignisaufruf extrahieren.

![](assets/metadata_file_event.png)

### Dateiname

Der Dateiname basiert auf den kreativen IDs, Kampagnen und Datenquellen-IDs. Vergleichen Sie in diesem Fall die Unterschiede zwischen den Schlüsselwertdaten in einem Ereignisaufruf und der Verwendung in einem Dateinamen.

In einem Dateinamen:

* Der Datenquellenschlüssel ändert sich in `dpid` von `d_src`.

* Die Kreativ- und Kampagnen-IDs stellen eher eine Kategorie als eine tatsächliche ID dar.

![](assets/metadata_file_name.png)

Siehe [Benennungskonventionen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Dateiinhalt

In diesem Beispiel spiegeln die Dateiinhalte die Kreativ- und Kampagnen-IDs wider, die beim Ereignisaufruf weitergegeben werden. Das neue Element hier ist ein lesbarer Name. Nach der Verarbeitung wird der Name in dieser Datei als Option im Menü "Kreativ"eines [!UICONTROL Audience Optimization] Berichts angezeigt.

![](assets/metadata_file_contents.png)

Siehe [Inhaltsformat für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Dateibereitstellung

Nachdem Sie einer Datei einen Namen gegeben und Daten hinzugefügt haben, senden Sie diese an einen Amazon S3-Speicherordner, der von [!DNL Audience Manager]bereitgestellt wird. Siehe [Bereitstellungsmethoden für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md).

>[!MORE_LIKE_THIS]
>
>* [Datendateien für Zielgruppenoptimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Erfassen von Kampagnen-Klickdaten über Pixelaufrufe](../../../integration/media-data-integration/click-data-pixels.md)
>* [Erfassen von Kampagnenimpressionsdaten über Pixelabrufe](../../../integration/media-data-integration/impression-data-pixels.md)

